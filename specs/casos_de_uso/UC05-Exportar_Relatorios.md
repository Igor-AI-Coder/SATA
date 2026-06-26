# UC05 – Exportar Relatórios

## Identificação
- **Código:** UC05
- **Nome:** Exportar Relatórios

## Objetivo
Converter os dados gerenciais e estatísticos exibidos em tela na plataforma em arquivos físicos portáteis e padronizados para consumo externo.

## Atores
- Líder de SOC / Gerente de Segurança

## Pré-condições
- Este caso de uso deve ser obrigatoriamente disparado como uma extensão decorrente da navegação do UC04 – Visualizar Relatórios.

## Fluxo Principal
1. O caso de uso inicia-se imediatamente quando o usuário aciona a opção de exportação dentro do módulo de relatórios (UC04).
2. O sistema exibe uma caixa de diálogo solicitando a escolha do formato físico desejado.
3. O gestor seleciona o formato de extração aplicável (PDF para relatórios executivos ou CSV para dados tabulares brutos).
4. O sistema processa as informações atualmente filtradas em tela e gera o arquivo físico binário correspondente.
5. O sistema disponibiliza o download direto do documento compilado através do navegador do usuário.

## Parâmetros do Arquivo
- Formato do documento de saída (.pdf / .csv)
- Conjunto de dados filtrado (Data de início, fim e escopo de métricas do UC04)
- Layout padrão corporativo (para PDFs)

## Fluxos Alternativos

### FA01 – Falha na compilação dos dados
1. Durante o processamento do arquivo físico (passo 4), o sistema detecta estouro de memória ou falha de escrita no servidor de arquivos devido à volumetria massiva.
2. O sistema cancela a operação de download.
3. Uma mensagem de erro informando "Falha ao gerar o arquivo para download. Tente restringir o período selecionado" é exibida ao gestor.

## Pós-condições
- O arquivo contendo as métricas de segurança é disponibilizado com sucesso na máquina local do usuário, mantendo a integridade dos dados originais.