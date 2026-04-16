<img width="1174" height="886" alt="4plantuml4152026" src="https://github.com/user-attachments/assets/48432525-480e-4445-9c34-dedf67e69ff5" />

@startuml

class Aluno {
  +cadastrar()
  +editar()
  +buscarPorId()
  +verificarInadimplencia()
  +validarRFID()
}

class Plano {
  +criar()
  +editar()
  +ativar()
  +desativar()
  +listar()
}

class Pagamento {
  +registrar()
  +gerarBoleto()
  +consultarStatus()
  +listarPorAluno()
}

class Acesso {
  +registrarEntrada()
  +validarAcesso()
  +listarHistorico()
}

class Aula {
  +criar()
  +editar()
  +listarHorarios()
  +verificarDisponibilidade()
}

class Agendamento {
  +reservar()
  +cancelar()
  +confirmar()
  +listarPorAluno()
}

class Presenca {
  +registrar()
  +listarPorAula()
  +listarPorAluno()
}

class AvaliacaoFisica {
  +registrar()
  +editar()
  +anexarArquivo()
  +listarPorAluno()
}

class Notificacao {
  +enviar()
  +listarPorAluno()
  +marcarComoLida()
}

class Instrutor {
  +registrarPresenca()
  +registrarAvaliacao()
  +listarAulas()
}

class Recepcionista {
  +cadastrarAluno()
  +registrarPagamento()
}

class Gerente {
  +gerarRelatorio()
  +gerenciarPlano()
}

Aluno "1" --> "1"    Plano           : contrata
Aluno "1" --> "0..*" Pagamento       : realiza
Aluno "1" --> "0..*" Acesso          : gera
Aluno "1" --> "0..*" Agendamento     : faz
Aluno "1" --> "0..*" AvaliacaoFisica : possui
Aluno "1" --> "0..*" Notificacao     : recebe

Agendamento "0..*" --> "1"    Aula    : referencia
Presenca    "0..*" --> "1"    Aula    : registrada em
Presenca    "0..*" --> "1"    Aluno   : pertence a

Instrutor     "1" --> "0..*" Presenca        : registra
Instrutor     "1" --> "0..*" AvaliacaoFisica : realiza
Recepcionista "1" --> "0..*" Pagamento       : registra
Gerente       "1" --> "0..*" Plano           : gerencia

@enduml
