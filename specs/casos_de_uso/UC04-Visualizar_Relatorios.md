# UC04 – Visualizar Relatórios

## Identificação
- **Código:** UC04
- **Nome:** Visualizar Relatórios

## Objetivo
Apresentar de forma visual e consolidada os indicadores-chave de desempenho (KPIs) operacionais do SOC, como volumetria de incidentes, taxas de acerto da IA e tempo médio de atendimento (MTTR).

## Atores
- Líder de SOC / Gerente de Segurança

## Pré-condições
- O usuário deve estar autenticado com um perfil que possua permissões gerenciais ou de liderança.

## Fluxo Principal
1. O gestor acessa o módulo de métricas, relatórios e dashboards operacionais.
2. O sistema consulta a base histórica de alertas, consolida as estatísticas volumétricas e calcula os tempos de resposta.
3. O sistema constrói dinamicamente painéis analíticos e gráficos interativos na tela.
4. O gestor interage com os gráficos, isolando períodos temporais e analisando a performance operacional da equipe e da IA.

## Indicadores Consolidados
- Volume total de alertas capturados pelo SIEM
- Tempo Médio de Resposta / Triagem (MTTR)
- Taxa de assertividade das sugestões geradas pela LLM
- Distribuição de severidade dos incidentes validados

## Pontos de Extensão

### UC05 – Exportar Relatórios
- **Condição de Extensão:** No passo 4 do fluxo principal, caso o gestor necessite extrair os dados analíticos estruturados para uma auditoria ou apresentação externa, ele pode acionar o comando de download em tela, disparando o UC05 – Exportar Relatórios (<<extend>>).

## Pós-condições
- O dashboard gerencial exibe dados atualizados e precisos baseados nas transações consolidadas do banco de dados.