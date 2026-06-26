# UC02 – Manter Alertas

## Identificação
- **Código:** UC02
- **Nome:** Manter Alertas

## Objetivo
Permitir que o Analista de SOC atue diretamente sobre os alertas já processados, confirmando, corrigindo ou descartando as classificações sugeridas pela Inteligência Artificial.

## Atores
- Analista de SOC

## Pré-condições
- O usuário deve estar autenticado no sistema com perfil operacional de SOC.
- O alerta alvo deve ter concluído com sucesso o ciclo de processamento automático (UC01) e estar disponível na fila de triagem.

## Fluxo Principal
1. O analista de SOC acessa a listagem de alertas pendentes de triagem.
2. O sistema exibe os alertas filtrados por ordem de criticidade.
3. O analista seleciona um alerta específico da fila.
4. O sistema apresenta em tela o resumo executivo, o log detalhado e a classificação sugerida pela IA.
5. O analista analisa as informações, concorda com o parecer automatizado e clica em validar.
6. O sistema atualiza o status operacional do alerta para "Validado".
7. O sistema invoca internamente o UC08 – Registrar Histórico (<<include>>) para gravar a auditoria da ação do usuário.

## Dados da Ação
- Identificador único do alerta (ID)
- Status de destino (Validado, Descartado, Corrigido)
- Classificação final adotada
- Identificação do Analista de SOC (User ID)
- Justificativa textual (obrigatória para alterações)
- Marcação temporal (Timestamp)

## Fluxos Alternativos

### FA01 – Descartar Alerta
1. No passo 5 do fluxo principal, o analista constata que o alerta se trata de uma atividade legítima ou irrelevante e opta por descartá-lo.
2. O analista clica na opção de descarte.
3. O sistema atualiza o status do alerta para "Descartado" e o remove da fila principal de triagem.
4. O sistema invoca internamente o UC08 – Registrar Histórico para registrar a remoção.

### FA02 – Corrigir Classificação
1. No passo 5 do fluxo principal, o analista discorda da classificação sugerida pela IA (ex: IA sugeriu Suspeito, mas trata-se de um Verdadeiro Positivo claro).
2. O analista seleciona a classificação manual correta.
3. O sistema solicita obrigatoriamente uma justificativa técnica para a divergência.
4. O analista insere o texto justificando a mudança e confirma.
5. O sistema salva a nova classificação, atualiza o status para "Corrigido" e aciona o UC08 – Registrar Histórico.

## Pós-condições
- O alerta é retirado da fila ativa de triagem técnica.
- O status definitivo da ameaça é consolidado no banco de dados.
- O log de auditoria correspondente é gerado de forma imutável.

## Requisitos Relacionados
- RF006, RF007