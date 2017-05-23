# Webservice

## Introdução
> API é uma **interface de aplicações voltada para aplicações**, ou seja uma API é criada quando uma **empresa de software tem a intenção de que outros criadores de software desenvolvam produtos associados ao seu serviço**. Exemplo: Google MAPS, ele possui milhões de endereços cadastrados e o google disponibiliza esses dados por meio de uma API.

- Caracteristicas
  - Permite a **interoperável**(_diferentes sistemas e linguagens se comunicão de forma padronizada via json ou xml_) entre sistemas e linguagens.
  - Utiliza **protocolo** **HTTP** para _comunicação_
  - Baseado em padrões mantidos pla **W3C**

## Documentação
> Existem algums padrões para documentação e criação.

- W3C
- Swagger
- Blueprint

- Ferramentas
  - SOAPUI 

# SOAP

## Introdução
> **Protocolo** de _troca_ de **dados** baseado em **XML** para **enviar** e **receber**.

## Caracteristicas
- **Independente** de _plataforma_ ou _linguagem_ ou seja pode ser usado com php, java c#, mac, windows, linux.

## Arquitetura
- **SOAP**
  - **Protocolo** de _troca_ de mensagens na internet.
- **XML**
  - Linguagem de **marcação** para descrever os dados.
- **WSDL**
  - É uma **descrição** no formato **xml**, ele fala qual so os **métodos**, **dados** com seus **tipos**(int, string) a serem **recebidos** e os **dados** de **resposta**.
- **UDDI**
  - Registro e descoberta de serviços, ou seja, ele faz uma mapeamento dos serviços e informa a quem quer utilizar.

- Resumindo: (TDD)
  - **SOAP** _TRANSPORTA_
  - **WSDL** _DESCREVE_
  - **UDDI** _DESCOBRE_ SERVIÇOS

## Estrutura
- **Envelope**
  - É **obrigatório**
  - Define **inicio** e **fim** da mensagem
- **Header**
  - É **opcional**
  - Pode colocar informações **opcionais** utilizadas no _processamento_
    - Exemplo: Envia o token do usuário logado para validação.
- **Body**
  - É **obrigatório**
  - **Conteudo da mensagem** em _formato_ **XML**
    - Exemplo: No cadastro de usuário você envia o nome, sexo, email, senha.
![Estrutura SOAP](http://i.imgur.com/hC1sVOY.png)

## WSDL
> É uma **descrição** no formato **xml**, ele fala qual so os **métodos**, **dados** com seus **tipos**(int, string) a serem **recebidos** e os **dados** de **resposta**.

- Define os seguintes objetos:
  - **Tipos de dados** suportados (int, string, float)
  - **Formato** de como vai **receber** os dados e como vai **responder**. 
    - Exemplo: Ele diz: Me **envia** o codigo_produto(string), preço(float). Vou **responder** para você com nome_produto(string) e categoria(string).
    
## UDDI 
- Pode ser comparado a um **CATALOGO TELEFONICO**
- Reune as seguintes informações
  - Nomes
  - Endereços


# REST

# RESTFULL
