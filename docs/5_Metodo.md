<img width="1357" height="1278" alt="3plantuml4152026" src="https://github.com/user-attachments/assets/417077e7-8d8a-43e0-95c7-0f8ee3a2fc78" />

@startuml

class Aluno {
  +int idAluno
  +String nome
  +String cpf
  +String email
  +String telefone
  +String endereco
  +String rfid
  +String status
  +cadastrar()
  +editar()
  +buscarPorId()
  +verificarAdimplencia()
  +validarRFID()
}

class Plano {
  +int idPlano
  +String nome
  +String tipo
  +float valor
  +boolean ativo
  +criar()
  +editar()
  +ativar()
  +desativar()
  +listar()
}

class Pagamento {
  +int idPagamento
  +Date data
  +float valor
  +String formaPagamento
  +String status
  +registrar()
  +gerarBoleto()
  +consultarStatus()
  +listarPorAluno()
}

class Acesso {
  +int idAcesso
  +DateTime dataHora
  +boolean autorizado
  +registrarEntrada()
  +validarAcesso()
  +listarHistorico()
}

class Aula {
  +int idAula
  +String nome
  +DateTime horario
  +int capacidadeMaxima
  +criar()
  +editar()
  +listarHorarios()
  +verificarDisponibilidade()
}

class Agendamento {
  +int idAgendamento
  +Date dataReserva
  +String status
  +reservar()
  +cancelar()
  +confirmar()
  +listarPorAluno()
}

class Presenca {
  +int idPresenca
  +Date data
  +boolean presente
  +registrar()
  +listarPorAula()
  +listarPorAluno()
}

class AvaliacaoFisica {
  +int idAvaliacao
  +Date data
  +float peso
  +float imc
  +float percentualGordura
  +String observacoes
  +String anexo
  +registrar()
  +editar()
  +anexarArquivo()
  +listarPorAluno()
}

class Notificacao {
  +int idNotificacao
  +String tipo
  +Date dataEnvio
  +String status
  +String mensagem
  +enviar()
  +listarPorAluno()
  +marcarComoLida()
}

class Instrutor {
  +int idInstrutor
  +String nome
  +String especialidade
  +registrarPresenca()
  +registrarAvaliacao()
  +listarAulas()
}

class Recepcionista {
  +int idRecepcionista
  +String nome
  +cadastrarAluno()
  +registrarPagamento()
}

class Gerente {
  +int idGerente
  +String nome
  +gerarRelatorio()
  +gerenciarPlano()
}

Aluno "1" --> "1"    Plano          : contrata
Aluno "1" --> "0..*" Pagamento      : realiza
Aluno "1" --> "0..*" Acesso         : gera
Aluno "1" --> "0..*" Agendamento    : faz
Aluno "1" --> "0..*" AvaliacaoFisica : possui
Aluno "1" --> "0..*" Notificacao    : recebe

Agendamento "0..*" --> "1"    Aula    : referencia
Presenca    "0..*" --> "1"    Aula    : registrada em
Presenca    "0..*" --> "1"    Aluno   : pertence a

Instrutor    "1" --> "0..*" Presenca       : registra
Instrutor    "1" --> "0..*" AvaliacaoFisica : realiza
Recepcionista "1" --> "0..*" Pagamento     : registra
Gerente       "1" --> "0..*" Plano         : gerencia

@enduml
