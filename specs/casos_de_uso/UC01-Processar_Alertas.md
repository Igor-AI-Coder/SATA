# UC01 – Processar Alertas

## Identificação
- **Código:** UC01
- **Nome:** Processar Alertas

## Objetivo
Centralizar o fluxo automático de recebimento, validação, filtragem, análise via IA, classificação, geração de resumo e notificação dos alertas de segurança.

## Atores
- SIEM
- Serviço de IA (LLM Externa)
- Slack / Teams

## Pré-condições
- Integração com o SIEM devidamente configurada e operacional.
- Regras de filtragem ativas no sistema.
- Conexão e autenticação com a API da LLM estabelecidas.

## Fluxo Principal
1. O SIEM identifica um evento de segurança e envia o alerta correspondente ao SATA.
2. O sistema valida a estrutura dos dados recebidos e verifica as regras de filtragem configuradas.
3. Sendo aprovado na etapa de filtragem, o SATA empacota e envia os logs brutos para o Serviço de IA (LLM Externa).
4. A LLM analisa os logs, identifica padrões de ameaça relevantes e retorna uma classificação sugerida.
5. O sistema consolida o retorno da IA e gera um resumo automático contendo os pontos críticos e a justificativa técnica.
6. O sistema prepara a carga útil da notificação e a envia diretamente para os canais de comunicação integrados (Slack/Teams).

## Dados do Processamento
- Payload do evento enviado pelo SIEM (IP de origem, IP de destino, timestamp, tipo de evento, logs correlacionados)
- Status da validação estrutural
- Resposta analítica da LLM
- Classificação sugerida (Verdadeiro Positivo, Falso Positivo ou Suspeito)
- Resumo executivo do incidente
- Metadados de envio da notificação

## Fluxos Alternativos

### FA01 – Falha de comunicação ou Dados Inválidos
1. O sistema falha em estabelecer conexão com as APIs externas ou identifica a ausência de parâmetros obrigatórios no payload.
2. O evento é rejeitado pelo sistema.
3. O SATA registra a falha detalhada no log interno para fins de auditoria e monitoramento.
4. O fluxo é encerrado.

### FA02 – Alerta barrado na filtragem
1. No passo 2 do fluxo principal, o alerta atende a critérios específicos de uma regra de descarte ativa (ex: ruído conhecido ou falso positivo pré-mapeado).
2. O fluxo automático de análise é interrompido.
3. O alerta é arquivado diretamente no banco de dados com a marcação de descartado por regra, sem acionar o consumo da LLM.
4. O fluxo é encerrado.

## Pós-condições
- O alerta válido é processado, enriquecido com inteligência artificial e disponibilizado para triagem.
- Os canais operacionais do SOC recebem as notificações em tempo real.
- Falhas e descartes são devidamente persistidos para fins de conformidade.

## Requisitos Relacionados
- RF001, RF002, RF003, RF004, RF005