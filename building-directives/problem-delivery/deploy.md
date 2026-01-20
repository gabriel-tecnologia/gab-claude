# Deploy

Processo de deploy e ambientes.

**Responsável**: Pleno+

---

## Ambientes

| Ambiente       | Propósito          | Quem acessa   |
| -------------- | ------------------ | ------------- |
| **Local**      | Desenvolvimento    | Devs          |
| **Dev**        | Testes integrados  | Devs          |
| **Staging**    | Validação pré-prod | Devs, QA, PMs |
| **Production** | Usuários reais     | Todos         |

---

## Fluxo de Deploy

```
Local → Dev → Staging → Production
  ↓       ↓       ↓          ↓
 push   merge   merge     release
  to    to dev  to main    tag
branch
```

### Triggers

| Ambiente   | Trigger                    | Automático? |
| ---------- | -------------------------- | ----------- |
| Dev        | Push para branch `develop` | Sim         |
| Staging    | Merge para `main`          | Sim         |
| Production | Tag de release             | Manual      |

---

## Deploy para Produção

### Checklist Pré-Deploy

- [ ] Staging testado e aprovado por QA/PM
- [ ] Nenhum bug crítico aberto
- [ ] Feature flags configuradas
- [ ] Rollback plan definido
- [ ] Comunicação no Slack (#deploys)

### Processo

1. **Criar release tag**

   ```bash
   git tag -a v1.2.3 -m "Release v1.2.3"
   git push origin v1.2.3
   ```

2. **Monitorar deploy**
   - Acompanhar CI/CD no GitHub Actions
   - Verificar métricas no DataDog

3. **Validação pós-deploy**
   - Smoke tests
   - Verificar logs de erro
   - Monitorar métricas por 15 min

4. **Comunicar**
   - Postar no #deploys que foi finalizado
   - Atualizar changelog (se aplicável)

---

## Versionamento

### Semantic Versioning

```
MAJOR.MINOR.PATCH

v1.2.3
│ │ └── Patch: bugfixes, sem breaking changes
│ └──── Minor: features novas, backward compatible
└────── Major: breaking changes
```

### Quando Incrementar

| Mudança         | Versão                |
| --------------- | --------------------- |
| Fix de bug      | Patch (1.2.3 → 1.2.4) |
| Nova feature    | Minor (1.2.3 → 1.3.0) |
| Breaking change | Major (1.2.3 → 2.0.0) |

---

## Rollback

### Quando fazer Rollback

- Erros críticos em produção
- Degradação significativa de performance
- Bug que afeta muitos usuários

### Como fazer Rollback

1. **Decisão**
   - Senior Eng decide
   - Comunicar imediatamente no Slack

2. **Executar**

   ```bash
   # Opção 1: Deploy da versão anterior
   git checkout v1.2.2
   # Trigger deploy

   # Opção 2: Revert do commit
   git revert <commit-hash>
   git push
   ```

3. **Pós-rollback**
   - Comunicar no #incidents
   - Abrir postmortem se necessário
   - Investigar root cause

---

## Feature Flags

### Quando Usar

- Features grandes que levam múltiplos PRs
- Experimentos A/B
- Rollout gradual
- Kill switch para features arriscadas

### Convenção de Nomes

```
FF_<TRIBE>_<FEATURE>_<TIPO>

Exemplos:
FF_BORDA_NOVO_SENSOR_ENABLED
FF_PLATAFORMA_NOVA_API_ROLLOUT_PERCENT
```

### Ciclo de Vida

```
Criada → Em teste → Rollout gradual → 100% → Remover flag
```

**Importante**: Remover flags após rollout completo (max 30 dias)

---

## Troubleshooting

### Deploy falhou

1. Verificar logs do CI/CD
2. Identificar stage que falhou
3. Se teste: verificar qual teste quebrou
4. Se deploy: verificar logs do ambiente

### Produção com problemas pós-deploy

1. Verificar métricas no DataDog
2. Verificar logs de erro
3. Se crítico: rollback imediato
4. Se não crítico: hotfix ou esperar próximo deploy
