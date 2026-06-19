# Especificação Textual dos Casos de Uso – SATA

## UC04 – Gerenciar Relatórios

### Identificação

**Código:** UC04  
**Nome:** Gerenciar Relatórios

### Objetivo

Permitir que o Líder de SOC / Gerente de Segurança visualize e exporte relatórios com métricas operacionais do sistema.

### Atores

- Líder de SOC / Gerente de Segurança

### Pré-condições

- O usuário deve estar autenticado no sistema.
- O sistema deve possuir dados processados suficientes para geração de relatórios.

### Fluxo Principal

1. O gerente acessa o módulo de relatórios.
2. O sistema apresenta os indicadores disponíveis.
3. O gerente visualiza métricas operacionais em tela.
4. O gerente pode selecionar um período ou filtro específico.
5. O sistema atualiza os dados apresentados.
6. O gerente pode solicitar a exportação dos relatórios.
7. O sistema gera o arquivo no formato solicitado.

### Dados Apresentados

- Quantidade total de alertas processados
- Quantidade de verdadeiros positivos
- Quantidade de falsos positivos
- Volume de alertas por severidade
- Tempo médio de resposta
- Quantidade de correções realizadas pelos analistas

### Fluxos Alternativos

#### FA01 – Relatório sem dados suficientes

1. O gerente seleciona um intervalo sem registros.
2. O sistema informa que não existem dados para o período selecionado.

#### FA02 – Exportação solicitada

1. O gerente escolhe exportar o relatório.
2. O sistema gera o arquivo.
3. O download é disponibilizado ao usuário.

### Pós-condições

- O relatório foi visualizado e/ou exportado.
- Os dados permanecem disponíveis para consulta posterior.

### Requisitos Relacionados

- RF009
- RF010
