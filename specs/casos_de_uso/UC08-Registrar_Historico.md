# UC08 – Registrar Histórico

## Identificação
- **Código:** UC08
- **Nome:** Registrar Histórico

## Objetivo
Módulo interno automatizado com responsabilidade exclusiva de gravar de forma imutável, cronológica e segura as trilhas de auditoria das ações operacionais sensíveis executadas no SATA.

## Atores
- Sistema SATA

## Pré-condições
- Este caso de uso não possui execução manual diretamente pela interface do usuário. Ele deve ser obrigatoriamente invocado internamente por outras rotinas por meio de um relacionamento de inclusão (`<<include>>`), como no UC02.

## Fluxo Principal
1. O caso de uso inicia-se automaticamente quando acionado de forma síncrona por uma rotina de negócio do sistema (ex: validação, correção ou descarte de um alerta no UC02).
2. O sistema SATA intercepta e recebe a carga de dados contendo os metadados técnicos e operacionais completos da transação realizada.
3. O sistema valida a integridade do payload técnico recebido.
4. O sistema realiza a persistência física dos dados em tabelas de auditoria imutáveis com política estrita de somente gravação (append-only).

## Metadados do Registro
- Identificador numérico do alerta afetado (ID)
- Identificador exclusivo do usuário responsável pela ação (User ID)
- Carimbo de data e hora de alta precisão (Timestamp do sistema)
- Detalhes exatos da decisão de negócio tomada (Status alterado)
- Justificativa técnica inserida pelo operador humano

## Pós-condições
- Uma entrada permanente e auditável é registrada de maneira íntegra na base de dados de auditoria, garantindo o princípio do não-retrocesso e conformidade regulatória de segurança.