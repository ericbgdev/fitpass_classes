## **Aluno**
RF01, RF04, RF05, RF06, RF10
- idAluno
- nome
- cpf
- email
- telefone
- endereco
- rfid
- status

+cadastrar() +editar() +buscarPorId() +verificarInadimplencia() +validarRFID()

## **Plano**
RF01, RF02, RF04
- idPlano
- nome
- tipo
- valor
- ativo

+criar() +editar() +ativar() +desativar() +listar()

## **Pagamento**
RF03, RF04, RF09
- idPagamento
- data
- valor
- formaPagamento
- status

+registrar() +gerarBoleto() +consultarStatus() +listarPorAluno()

## **Acesso**
RF05, RF09
- idAcesso
- dataHora
- autorizado
- 
+registrarEntrada() +validarAcesso() +listarHistorico() 

## **Aula**
RF06, RF07, RF09
- idAula
- nome
- horario
- capacidadeMaxima

+criar() +editar() +listarHorarios() +verificarDisponibilidade() 

## **Agendamento**
RF06, RF10
- idAgendamento
- dataReserva
- status

+reservar() +cancelar() +confirmar() +listarPorAluno()

## **Presenca**
RF07
- idPresenca
- data
- presente

+registrar() +listarPorAula() +listarPorAluno()

## **AvaliacaoFisica**
RF08, RF10
- idAvaliacao
- data
- peso
- imc
- percentualGordura
- observacoes
- anexo

+registrar() +editar() +anexarArquivo() +listarPorAluno()

## **Notificacao**
RF10
- idNotificacao
- tipo
- dataEnvio
- status
- mensagem

+enviar() +listarPorAluno() +marcarComoLida()

## **Instrutor**
RF07, RF08
- idInstrutor
- nome
- especialidade

+registrarPresenca() +registrarAvaliacao() +listarAulas()

## **Recepcionista**
RF01, RF03
- idRecepcionista
- nome

+cadastrarAluno() +registrarPagamento()

## **Gerente**
RF02, RF09
- idGerente
- nome

+gerarRelatorio() +gerenciarPlano()
