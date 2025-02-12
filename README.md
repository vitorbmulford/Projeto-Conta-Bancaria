Sistema de Gerenciamento de Contas Bancárias

Este projeto é um sistema simples de gerenciamento de contas bancárias implementado em JavaScript. Inclui classes para gerenciar informações de clientes e contas bancárias, bem como funcionalidades para realizar operações bancárias comuns, como depósito, saque e transferência de fundos.

Instalação

Para utilizar este projeto, você precisará ter o Node.js instalado em seu sistema. Você pode baixar a versão mais recente do Node.js no site oficial: https://nodejs.org/.

Após instalar o Node.js, clone o repositório e execute o projeto:

git clone https://github.com/seu-usuario/sistema-de-gerenciamento-de-contas-bancarias.git
cd sistema-de-gerenciamento-de-contas-bancarias
node index.js

Uso

A principal funcionalidade do sistema é fornecida pelas classes Cliente e ContaCorrente. Aqui está um exemplo de como utilizar o sistema:

import { Cliente } from "./Cliente.js";
import { ContaCorrente } from "./Conta_Corrente.js";

// Cria um novo cliente
const cliente1 = new Cliente("Vitor Bebiano Mulford", 54463499895);

// Cria uma nova conta bancária para o cliente
const contaCliente1 = new ContaCorrente(1001, cliente1);

// Deposita fundos na conta
contaCliente1.depositar(500);

// Saca fundos da conta
contaCliente1.sacar(200);

// Transfere fundos para outra conta
const contaCliente2 = new ContaCorrente(1002, new Cliente("Prentice Neto", 32001132876));
contaCliente1.transferir(300, contaCliente2);

API

A classe Cliente possui as seguintes propriedades e métodos:

    nome: O nome do cliente.
    _cpf: O número de CPF (Cadastro de Pessoas Físicas) do cliente.
    get cpf(): Um método getter que retorna o número de CPF do cliente.
    constructor(nome, cpf): O método construtor que inicializa o nome e o número de CPF do cliente.

A classe ContaCorrente possui as seguintes propriedades e métodos:

    static numeroDeContas: Uma propriedade estática que mantém o controle do número de contas bancárias criadas.
    agencia: O número da agência bancária.
    _cliente: O cliente associado à conta bancária.
    _saldo: O saldo atual da conta bancária.
    set cliente(novoValor): Um método setter que permite definir o cliente associado à conta bancária, mas apenas se novoValor for uma instância da classe Cliente.
    get cliente(): Um método getter que retorna o cliente associado à conta bancária.
    get saldo(): Um método getter que retorna o saldo atual da conta bancária.
    sacar(valor): Um método que permite sacar fundos da conta bancária, até o saldo atual.
    depositar(valor): Um método que permite depositar fundos na conta bancária.
    transferir(valor, conta): Um método que permite transferir fundos de uma conta bancária para outra.

Testes

Para executar os testes deste projeto, você pode usar o seguinte comando:

node index.js

Isso executará o código no arquivo index.js, que inclui alguns exemplos de uso das classes Cliente e ContaCorrente.
