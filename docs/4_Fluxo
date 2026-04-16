@startuml
class Aluno {

}

class Plano {
}

class Pagamento {

}

class Acesso {

}

class Aula {

}

class Agendamento {

}

class Presenca {

}

class AvaliacaoFisica {

}

class Notificacao {

}

abstract class Funcionario {

}

class Instrutor {

}

class Recepcionista {
}

class Gerente {
}

Funcionario <|-- Instrutor
Funcionario <|-- Recepcionista
Funcionario <|-- Gerente

Aluno "1" -- "1" Plano : contrata
Aluno "1" -- "0..*" Pagamento : contrata
Aluno "1" -- "0..*" Acesso : gera
Aluno "1" -- "0..*" Agendamentos : realiza
Aluno "1" -- "0..*" Presenca : possui
Aluno "1" -- "0..*" AvaliacaoFisica : possui
Aluno "1" -- "0..*" Aula : agenda
Aluno "1" -- "0..*" Notificacao : recebe

Aula "1" -- "0..*" Agendamento : possui
Aula "1" -- "0..*" Presenca : registra

Instrutor "1" -- "0..*" Aula : ministra
Instrutor "1" -- "0..*" AvaliacaoFisica : realiza
Instrutor "1" -- "0..*" Presenca : registra


@enduml
