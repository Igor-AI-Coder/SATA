# Especificação Textual dos Casos de Uso – SATA

## UC03 – Consultar Histórico

### Identificação

**Código:** UC03  
**Nome:** Consultar Histórico

### Objetivo

Permitir a busca e visualização dos alertas processados, decisões tomadas e informações relacionadas à auditoria e rastreabilidade.

### Atores

- Analista de SOC
- Líder de SOC / Gerente de Segurança
- Administrador do Sistema

### Pré-condições

- O usuário deve estar autenticado no sistema.
- Deve haver registros armazenados no histórico.

### Fluxo Principal

1. O usuário acessa a área de histórico.
2. O sistema apresenta os filtros disponíveis.
3. O usuário informa os critérios de busca desejados.
4. O sistema executa a pesquisa.
5. O sistema exibe os registros encontrados.
6. O usuário pode abrir um registro específico para ver os detalhes completos.

### Filtros Disponíveis

- Data
- Horário
- Usuário responsável
- Severidade
- Origem do alerta
- Classificação sugerida
- Decisão humana
- Status final do alerta

### Fluxos Alternativos

#### FA01 – Nenhum registro encontrado

1. O usuário informa critérios de busca.
2. O sistema não encontra registros compatíveis.
3. O sistema exibe mensagem informando que não há resultados para os filtros aplicados.

### Pós-condições

- Os registros encontrados foram exibidos ou a ausência de resultados foi informada.

### Requisitos Relacionados

- RF008
