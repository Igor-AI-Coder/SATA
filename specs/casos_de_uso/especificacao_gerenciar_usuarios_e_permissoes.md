# Especificação Textual dos Casos de Uso – SATA

## UC06 – Gerenciar Usuários e Permissões

### Identificação

**Código:** UC06  
**Nome:** Gerenciar Usuários e Permissões

### Objetivo

Permitir ao Administrador do Sistema cadastrar usuários, alterar permissões, desativar acessos e definir perfis operacionais.

### Atores

- Administrador do Sistema

### Pré-condições

- O usuário deve estar autenticado com perfil de administrador.
- O módulo de gerenciamento de usuários deve estar disponível.

### Fluxo Principal

1. O administrador acessa o módulo de usuários.
2. O sistema exibe a lista de usuários cadastrados.
3. O administrador escolhe criar, editar ou desativar um usuário.
4. O sistema solicita os dados necessários.
5. O administrador informa nome, e-mail, perfil e permissões.
6. O sistema valida as informações.
7. O administrador confirma a operação.
8. O sistema salva as alterações.

### Dados do Usuário

- Nome completo
- E-mail corporativo
- Perfil de acesso
- Status do usuário
- Permissões associadas

### Perfis Disponíveis

- Analista de SOC
- Líder de SOC / Gerente de Segurança
- Administrador do Sistema

### Fluxos Alternativos

#### FA01 – Usuário já existente

1. O administrador tenta cadastrar um e-mail já utilizado.
2. O sistema informa que o usuário já existe.
3. O cadastro não é concluído.

#### FA02 – Permissão inválida

1. O administrador atribui uma permissão não permitida para o perfil.
2. O sistema rejeita a alteração.
3. A configuração não é salva.

### Pós-condições

- Os usuários e permissões ficam atualizados no sistema.
- O acesso às funcionalidades passa a seguir os perfis definidos.

### Requisitos Relacionados

- RF011
