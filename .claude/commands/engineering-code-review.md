# Code Review

Revisão abrangente de segurança e qualidade de mudanças não commitadas:

1. Obter arquivos alterados: git diff --name-only HEAD

2. Para cada arquivo alterado, verificar:

**Problemas de Segurança (CRÍTICO):**

- Credenciais hardcoded, API keys, tokens
- Vulnerabilidades de SQL injection
- Vulnerabilidades de XSS
- Validação de input ausente
- Dependências inseguras
- Riscos de path traversal

**Qualidade de Código (ALTO):**

- Funções > 50 linhas
- Arquivos > 800 linhas
- Profundidade de aninhamento > 4 níveis
- Tratamento de erro ausente
- Statements console.log
- Comentários TODO/FIXME
- JSDoc ausente para APIs públicas

**Melhores Práticas (MÉDIO):**

- Padrões de mutação (usar imutável em vez disso)
- Uso de emojis em código/comentários
- Testes ausentes para código novo
- Problemas de acessibilidade (a11y)

3. Gerar relatório com:
   - Severidade: CRÍTICO, ALTO, MÉDIO, BAIXO
   - Localização do arquivo e números de linha
   - Descrição do problema
   - Correção sugerida

4. Bloquear commit se problemas CRÍTICOS ou ALTOS forem encontrados

Nunca aprove código com vulnerabilidades de segurança!
