# UC07 – Gerenciar Usuários e Permissões

## Identificação
- **Código:** UC07
- **Nome:** Gerenciar Usuários e Permissões

## Objetivo
Administrar de forma centralizada as contas de acesso, perfis funcionais e níveis hierárquicos de permissões de segurança de todos os colaboradores autorizados na plataforma SATA.

## Atores
- Administrador do Sistema

## Pré-condições
- O usuário que realiza a operação deve estar devidamente autenticado e possuir o perfil exclusivo de Administrador.

## Fluxo Principal
1. O administrador acessa a funcionalidade de gerenciamento de usuários através do painel de controle administrativo.
2. O sistema renderiza em tela a listagem completa dos colaboradores cadastrados na plataforma.
3. O administrador seleciona uma ação operacional específica: cadastrar um novo usuário, editar um perfil existente ou desativar uma credencial ativa.
4. O sistema exibe o formulário correspondente solicitando os dados cadastrais e de privilégios.
5. O administrador insere ou modifica os parâmetros do usuário, vinculando-o a um nível específico (Analista, Gerente, Admin).
6. O sistema executa as validações de consistência e unicidade de chaves (como e-mail único).
7. O administrador confirma o salvamento do registro.
8. O sistema persiste as atualizações no banco de dados corporativo.

## Dados Cadastrais
- Nome completo do colaborador
- E-mail institucional de login
- Nível de privilégio / Perfil atribuído (Analista de SOC, Líder de SOC / Gerente de Segurança, Administrador)
- Status de acesso à plataforma (Ativo / Inativo)

## Fluxos Alternativos

### FA01 – Conflito de identificação ou dados em branco
1. No passo 6 do fluxo principal, o administrador tenta salvar uma conta utilizando um e-mail institucional que já está associado a outro registro ativo ou deixa campos mandatórios nulos.
2. O sistema barra a gravação das informações.
3. O sistema realça os campos problemáticos em tela e exibe a mensagem de erro específica ("E-mail já cadastrado" ou "Campos obrigatórios ausentes").
4. Os dados anteriores permanecem inalterados na base.

## Pós-condições
- A política de controle de acesso baseado em funções (RBAC) é imediatamente atualizada no ambiente, alterando os privilégios de acesso aos módulos em tempo de execução.