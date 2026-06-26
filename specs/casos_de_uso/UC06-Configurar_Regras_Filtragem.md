# UC06 – Configurar Regras de Filtragem

## Identificação
- **Código:** UC06
- **Nome:** Configurar Regras de Filtragem

## Objetivo
Permitir ao Administrador do Sistema definir regras para filtrar, descartar ou direcionar alertas antes do processamento pela IA.

## Atores
- Administrador do Sistema

## Pré-condições
- O usuário deve estar autenticado com perfil de administrador.
- O sistema deve permitir acesso ao módulo de regras.

## Fluxo Principal
1. O administrador acessa o módulo de regras de filtragem.
2. O sistema exibe as regras já cadastradas.
3. O administrador escolhe criar, editar ou remover uma regra.
4. O sistema solicita os dados da regra.
5. O administrador informa os critérios desejados.
6. O sistema valida as informações preenchidas.
7. O administrador confirma o salvamento.
8. O sistema armazena a nova configuração.

## Dados da Regra
- Nome da regra
- Descrição
- Severidade mínima ou máxima
- Origem do alerta
- Categoria do evento
- Padrão conhecido
- Status ativo/inativo

## Fluxos Alternativos

### FA01 – Regra inválida
1. O administrador informa critérios inconsistentes.
2. O sistema exibe mensagem de erro.
3. A regra não é salva.

## Pós-condições
- As regras de filtragem ficam atualizadas.
- Os novos critérios passam a ser considerados no processamento dos alertas.

## Requisitos Relacionados
- RF002