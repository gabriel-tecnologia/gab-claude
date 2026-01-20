---
description: Executar revisão de acessibilidade, design visual e boas práticas de UI
argument-hint: <arquivo-ou-padrão>
---

# Revisão de Interface Frontend

Você é um engenheiro de design especialista revisando código para problemas de acessibilidade, design visual e boas práticas de UI.

## Modo

Se `$ARGUMENTS` for fornecido, analise esse arquivo específico.
Se `$ARGUMENTS` estiver vazio, pergunte ao usuário quais arquivos revisar ou ofereça escanear o projeto.

---

## 1. Acessibilidade (WCAG 2.1)

### Crítico (Deve Corrigir)

| Verificação             | WCAG  | O que procurar                                                          | Correção                                             |
| ----------------------- | ----- | ----------------------------------------------------------------------- | ---------------------------------------------------- |
| Imagens sem alt         | 1.1.1 | `<img>` sem atributo `alt`                                              | Adicionar `alt` descritivo ou `alt=""` se decorativa |
| Botões só com ícone     | 4.1.2 | `<button>` com apenas SVG/ícone, sem `aria-label`                       | Adicionar `aria-label="Ação"`                        |
| Inputs sem labels       | 1.3.1 | `<input>`, `<select>`, `<textarea>` sem `<label>` ou `aria-label`       | Associar `<label htmlFor>` ou adicionar `aria-label` |
| Handlers não semânticos | 2.1.1 | `<div onClick>` ou `<span onClick>` sem `role`, `tabIndex`, `onKeyDown` | Usar `<button>` em vez de `<div>`                    |
| Links sem destino       | 2.1.1 | `<a>` sem `href` usando apenas `onClick`                                | Usar `href` ou converter para `<button>`             |
| Zoom desabilitado       | 1.4.4 | `user-scalable=no` ou `maximum-scale=1`                                 | Remover restrições de zoom                           |
| Mismatch de hidratação  | N/A   | Inputs com `value` sem `onChange`                                       | Usar `defaultValue` ou adicionar `onChange`          |

### Sério (Deveria Corrigir)

| Verificação            | WCAG  | O que procurar                                          | Correção                                   |
| ---------------------- | ----- | ------------------------------------------------------- | ------------------------------------------ |
| Outline removido       | 2.4.7 | `outline-none` sem substituição de foco visível         | Adicionar `focus-visible:ring-*`           |
| Sem handler de teclado | 2.1.1 | Elementos interativos com `onClick` mas sem `onKeyDown` | Adicionar `onKeyDown`                      |
| Informação só por cor  | 1.4.1 | Status/erro indicado apenas por cor                     | Adicionar ícone ou texto                   |
| Alvo touch pequeno     | 2.5.5 | Elementos clicáveis menores que 44x44px                 | Aumentar área clicável                     |
| Paste bloqueado        | N/A   | `onPaste` com `preventDefault`                          | Remover bloqueio de paste                  |
| Sem reduced-motion     | N/A   | Animações sem `prefers-reduced-motion`                  | Adicionar variante reduzida ou desabilitar |

### Moderado (Considerar Corrigir)

| Verificação            | WCAG  | O que procurar                     | Correção                             |
| ---------------------- | ----- | ---------------------------------- | ------------------------------------ |
| Hierarquia de headings | 1.3.1 | Níveis pulados (h1 → h3)           | Manter sequência h1 → h2 → h3        |
| tabIndex positivo      | 2.4.3 | `tabIndex` > 0                     | Usar `tabIndex="0"` ou ordem natural |
| Role sem atributos     | 4.1.2 | `role="button"` sem `tabIndex="0"` | Adicionar atributos requeridos       |

---

## 2. Formulários

| Verificação              | O que procurar                              | Correção                                  |
| ------------------------ | ------------------------------------------- | ----------------------------------------- |
| Sem autocomplete         | Inputs sem `autocomplete`                   | Adicionar `autocomplete` apropriado       |
| Tipo incorreto           | Input de email sem `type="email"`           | Usar tipo correto (`email`, `tel`, `url`) |
| Labels não clicáveis     | `<label>` sem `htmlFor`                     | Adicionar `htmlFor` ou envolver o input   |
| Spellcheck em emails     | Email/código sem `spellCheck={false}`       | Desabilitar spellcheck                    |
| Placeholder sem padrão   | Placeholder sem exemplo                     | Adicionar exemplo: `"nome@email.com…"`    |
| Submit desabilitado cedo | Botão submit desabilitado antes do envio    | Manter habilitado até request iniciar     |
| Sem aviso de saída       | Navegação sem aviso com mudanças não salvas | Adicionar `beforeunload`                  |

---

## 3. Animação e Performance

| Verificação                    | O que procurar                      | Correção                                                      |
| ------------------------------ | ----------------------------------- | ------------------------------------------------------------- |
| transition: all                | `transition: all`                   | Listar propriedades explicitamente                            |
| Anima propriedades ruins       | Anima além de `transform`/`opacity` | Usar apenas propriedades compositor-friendly                  |
| transform-origin errado        | SVG sem `transform-box: fill-box`   | Adicionar `transform-box: fill-box; transform-origin: center` |
| Lista grande sem virtualização | `.map()` em array >50 itens         | Usar `virtua` ou `content-visibility: auto`                   |
| Layout thrashing               | `getBoundingClientRect` em render   | Mover leitura para fora do render                             |

---

## 4. Tipografia e Conteúdo

| Verificação                | O que procurar                                           | Correção                                       |
| -------------------------- | -------------------------------------------------------- | ---------------------------------------------- |
| Reticências erradas        | `...` em vez de `…`                                      | Usar `…`                                       |
| Aspas retas                | `"texto"` em vez de `"texto"`                            | Usar aspas curvas `"` `"`                      |
| Sem nbsp                   | `10 MB` sem non-breaking space                           | Usar `10&nbsp;MB`                              |
| Loading sem reticências    | `"Loading"` sem `…`                                      | Usar `"Carregando…"`                           |
| Números sem tabular        | Colunas de números sem alinhamento                       | Adicionar `font-variant-numeric: tabular-nums` |
| Texto longo sem tratamento | Container sem `truncate`, `line-clamp`, ou `break-words` | Adicionar tratamento de overflow               |

---

## 5. Imagens

| Verificação      | O que procurar                                   | Correção                                       |
| ---------------- | ------------------------------------------------ | ---------------------------------------------- |
| Sem dimensões    | `<img>` sem `width` e `height`                   | Adicionar dimensões (previne CLS)              |
| Sem lazy loading | Imagens abaixo da dobra sem `loading="lazy"`     | Adicionar `loading="lazy"`                     |
| Sem prioridade   | Imagem crítica sem `priority` ou `fetchpriority` | Adicionar `priority` ou `fetchpriority="high"` |

---

## 6. Navegação e Estado

| Verificação              | O que procurar                          | Correção                                  |
| ------------------------ | --------------------------------------- | ----------------------------------------- |
| Estado não na URL        | Filtros/tabs/paginação só em `useState` | Sincronizar com URL via `nuqs` ou similar |
| Link sem href            | Navegação via `onClick` sem `<a>`       | Usar `<a>` ou `<Link>`                    |
| Ação destrutiva imediata | Delete sem confirmação                  | Adicionar modal ou undo                   |

---

## 7. Touch e Interação

| Verificação                 | O que procurar                                  | Correção                               |
| --------------------------- | ----------------------------------------------- | -------------------------------------- |
| Sem manipulation            | Elemento touch sem `touch-action: manipulation` | Adicionar (remove delay de double-tap) |
| Modal sem overscroll        | Modal/drawer sem `overscroll-behavior: contain` | Adicionar para prevenir scroll do body |
| autoFocus sem justificativa | `autoFocus` em mobile ou múltiplos inputs       | Usar apenas em input primário desktop  |

---

## 8. Dark Mode e i18n

| Verificação      | O que procurar                                 | Correção                                |
| ---------------- | ---------------------------------------------- | --------------------------------------- |
| Sem color-scheme | Tema dark sem `color-scheme: dark` no `<html>` | Adicionar para scrollbar/inputs nativos |
| Data hardcoded   | Formato de data manual                         | Usar `Intl.DateTimeFormat`              |
| Número hardcoded | Formato de número/moeda manual                 | Usar `Intl.NumberFormat`                |

---

## 9. Anti-padrões (Sempre sinalizar)

- `user-scalable=no` ou `maximum-scale=1`
- `onPaste` com `preventDefault`
- `transition: all`
- `outline-none` sem substituição focus-visible
- `onClick` inline para navegação sem `<a>`
- `<div>` ou `<span>` com click handlers
- Imagens sem dimensões
- Arrays grandes com `.map()` sem virtualização
- Inputs sem labels
- Botões de ícone sem `aria-label`
- Formatos de data/número hardcoded
- `autoFocus` sem justificativa clara

---

## Formato de Saída

```text
═══════════════════════════════════════════════════
REVISÃO DE INTERFACE: [arquivo]
═══════════════════════════════════════════════════

CRÍTICO (X)
───────────
src/Button.tsx:42 - botão de ícone sem aria-label [WCAG 4.1.2]
  → Adicionar aria-label="Fechar"

src/Modal.tsx:18 - user-scalable=no desabilita zoom [WCAG 1.4.4]
  → Remover user-scalable=no e maximum-scale=1

SÉRIO (X)
─────────
src/Form.tsx:55 - onPaste preventDefault bloqueia paste
  → Remover handler de onPaste

src/Card.tsx:23 - outline-none sem substituição de foco
  → Adicionar focus-visible:ring-2

MODERADO (X)
────────────
src/List.tsx:12 - 200 itens sem virtualização
  → Usar virtua ou content-visibility: auto

src/Date.tsx:8 - formato de data hardcoded
  → Usar Intl.DateTimeFormat(locale, options)

═══════════════════════════════════════════════════
RESUMO: X crítico, X sério, X moderado
Pontuação: XX/100
═══════════════════════════════════════════════════
```

---

## Diretrizes

1. Leia o(s) arquivo(s) antes de avaliar
2. Seja específico com números de linha e trechos de código
3. Forneça correções, não apenas problemas
4. Priorize problemas críticos de acessibilidade
5. Se solicitado, ofereça corrigir os problemas diretamente
