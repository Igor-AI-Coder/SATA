# Especificação Textual dos Casos de Uso – SATA

## UC01 – Processar Alertas

### Identificação

**Código:** UC01  
**Nome:** Processar Alertas

### Objetivo

Permitir que o sistema receba alertas de segurança, aplique regras de filtragem, envie os dados para análise por IA e produza uma classificação preliminar com resumo do evento.

### Atores

- SIEM
- LLM Externa

### Pré-condições

- A integração com o SIEM deve estar configurada.
- As regras de filtragem devem estar cadastradas no sistema.
- O serviço de IA externa deve estar disponível para uso.
- O sistema deve estar operando normalmente.

### Fluxo Principal

1. O SIEM gera um alerta de segurança com informações do evento.
2. O SIEM envia o alerta ao SATA.
3. O sistema recebe e valida os dados do alerta.
4. O sistema verifica se o alerta atende às regras de filtragem configuradas.
5. Caso o alerta seja elegível para análise, o sistema envia os dados do evento para a LLM externa.
6. A LLM externa analisa os logs recebidos e identifica padrões relevantes.
7. A LLM retorna uma resposta com a interpretação do alerta e a classificação preliminar sugerida.
8. O SATA processa a resposta recebida.
9. O sistema gera um resumo da análise com as informações mais relevantes do evento.
10. O alerta processado fica disponível para a etapa de avaliação humana.

### Fluxos Alternativos

#### FA01 – Alerta bloqueado por regra de filtragem

1. O sistema recebe o alerta do SIEM.
2. O sistema identifica que o alerta se enquadra em uma regra de exceção ou descarte.
3. O alerta não é enviado para a LLM.
4. O evento é registrado para auditoria.
5. O alerta é encerrado sem seguir para análise.

#### FA02 – Falha na comunicação com a LLM

1. O sistema tenta enviar o alerta para a LLM externa.
2. A LLM não responde ou retorna erro.
3. O sistema registra a falha.
4. O alerta fica pendente para nova tentativa ou tratamento posterior.

#### FA03 – Alerta com dados incompletos

1. O sistema recebe um alerta com campos obrigatórios ausentes.
2. O sistema rejeita o processamento.
3. O evento é registrado em log para auditoria.

### Pós-condições

- O alerta foi processado ou rejeitado.
- A análise preliminar ou o motivo da rejeição foi registrado.
- O alerta permanece disponível para consulta, quando aplicável.

### Requisitos Relacionados

- RF001
- RF002
- RF003
- RF004
- RF005
