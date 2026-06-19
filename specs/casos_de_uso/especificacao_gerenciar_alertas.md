# Especificação Textual dos Casos de Uso – SATA

## UC02 – Gerenciar Alertas

### Identificação

**Código:** UC02  
**Nome:** Gerenciar Alertas

### Objetivo

Permitir que o Analista de SOC visualize os alertas processados e tome a decisão final sobre cada evento.

### Atores

- Analista de SOC

### Pré-condições

- O alerta deve ter sido processado pelo caso de uso UC01.
- O alerta deve estar disponível na fila de alertas processados.
- O analista deve estar autenticado no sistema.

### Fluxo Principal

1. O analista acessa a lista de alertas processados.
2. O sistema exibe o resumo da análise, a classificação preliminar e os dados do alerta.
3. O analista avalia as informações apresentadas.
4. O analista decide como tratar o alerta.
5. O sistema atualiza o status do alerta de acordo com a decisão tomada.
6. O alerta permanece registrado no histórico para futuras consultas.

### Fluxos Alternativos

#### FA01 – Validar alerta

1. O analista concorda com a análise realizada pela IA.
2. O sistema registra a validação.
3. O alerta é marcado como validado.

#### FA02 – Descartar alerta

1. O analista identifica que o alerta não representa risco relevante.
2. O analista descarta o alerta.
3. O sistema registra o descarte.
4. O alerta é marcado como descartado.

#### FA03 – Corrigir classificação

1. O analista identifica que a classificação sugerida está incorreta.
2. O analista informa a classificação correta.
3. O analista pode incluir uma justificativa.
4. O sistema registra a correção e atualiza o alerta.

### Pós-condições

- O alerta possui uma decisão humana registrada.
- A situação do alerta foi atualizada no sistema.
- A ação do analista foi registrada para consulta posterior.

### Requisitos Relacionados

- RF006
- RF007
