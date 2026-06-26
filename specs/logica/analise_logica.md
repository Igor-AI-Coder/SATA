```mermaid
classDiagram
    %% Enumerações para padronizar os domínios
    class PerfilAcesso {
        <<enumeration>>
        ANALISTA
        GERENTE
        ADMIN
    }

    class StatusAlerta {
        <<enumeration>>
        PENDENTE
        VALIDADO
        DESCARTADO
        CORRIGIDO
    }

    class ClassificacaoIA {
        <<enumeration>>
        VERDADEIRO_POSITIVO
        FALSO_POSITIVO
        VERDADEIRO_NEGATIVO
        FALSO_NEGATIVO
    }

    %% Classes Principais
    class Usuario {
        -String id
        -String nome
        -String email
        -PerfilAcesso perfil
        -Boolean isAtivo
        +autenticar()
        +atualizarPerfil()
        +desativarConta()
    }

    class RegraFiltragem {
        -String id
        -String nome
        -String descricao
        -String severidadeMinima
        -String severidadeMaxima
        -String origemAlerta
        -String categoriaEvento
        -String padraoConhecido
        -Boolean isAtiva
        +avaliarCriterios()
        +alternarStatusAtividade()
    }

    class Alerta {
        -String id
        -String ipOrigem
        -String ipDestino
        -DateTime timestampEnvio
        -String tipoEvento
        -String logsBrutos
        -StatusAlerta statusOperacional
        -String severidadeOriginal
        +validarEstruturaPayload()
        +atualizarStatus()
    }

    class AnaliseIA {
        -String id
        -ClassificacaoIA classificacaoSugerida
        -String justificativaTecnica
        -String resumoExecutivo
        +processarLogsAnaliticos()
        +gerarResumoAutomatizado()
    }

    class Notificacao {
        -String id
        -String canalDestino
        -String payloadMensagem
        -DateTime dataEnvio
        +montarCargaUtil()
        +dispararMensagem()
    }

    class RegistroHistorico {
        -String id
        -DateTime timestampAcao
        -String decisaoTomada
        -String justificativaHumana
        +persistirTrilhaAuditoria()
        +recuperarLogsFiltrados()
    }

    class Relatorio {
        -DateTime dataInicial
        -DateTime dataFinal
        -String formatoExportacao
        +calcularMTTR()
        +consolidarMetricasVolumetria()
        +gerarArquivoFisico()
    }

    %% Relacionamentos (Associações que substituem atributos estrangeiros)
    Usuario "1" -- "0..*" RegistroHistorico : realiza
    Usuario "1" -- "0..*" Relatorio : extrai
    
    Alerta "0..*" -- "1..*" RegraFiltragem : passa por
    Alerta "1" -- "0..1" AnaliseIA : recebe
    Alerta "1" -- "0..1" Notificacao : dispara
    Alerta "1" -- "0..*" RegistroHistorico : possui
    ```