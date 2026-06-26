# UC03 – Consultar Histórico

## Identificação
- **Código:** UC03
- **Nome:** Consultar Histórico

## Objetivo
Permitir a busca estruturada, filtragem e visualização detalhada de todas as ações operacionais e decisões tomadas pela equipe sobre os alertas de segurança da plataforma.

## Atores
- Analista de SOC
- Líder de SOC / Gerente de Segurança
- Administrador

## Pré-condições
- O usuário deve estar autenticado em uma sessão válida do sistema.

## Fluxo Principal
1. O usuário acessa a funcionalidade de consulta ao histórico de auditoria.
2. O sistema exibe a interface de busca contendo os parâmetros de filtragem disponíveis.
3. O usuário define as restrições desejadas preenchendo os critérios de busca.
4. O usuário aciona a execução da consulta.
5. O sistema realiza a busca na base de auditoria imutável aplicando os filtros fornecidos.
6. O sistema retorna e lista em tela os registros localizados em ordem cronológica reversa.
7. O usuário seleciona um registro para visualizar os metadados completos e justificativas salvas.

## Dados de Filtro
- Intervalo de datas (Data Inicial / Data Final)
- Identificador do usuário executor (Analista / Admin)
- Nível de severidade do alerta original
- Classificação aplicada na triagem (Verdadeiro Positivo, Falso Positivo, Suspeito, Descartado)
- ID específico do alerta

## Fluxos Alternativos

### FA01 – Nenhum registro localizado
1. No passo 5 do fluxo principal, o sistema executa a consulta e constata que nenhum registro atende à combinação de filtros informada pelo usuário.
2. O sistema renderiza uma mensagem na interface informando: "Nenhum registro encontrado para os filtros aplicados."
3. O quadro de listagem permanece limpo, permitindo que o usuário redefina os parâmetros.

## Pós-condições
- Os dados detalhados de auditoria são expostos de forma legível e estruturada na interface para avaliação e conformidade.