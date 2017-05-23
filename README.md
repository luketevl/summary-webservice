# Webservice

## Introdução
> API é uma **interface de aplicações voltada para aplicações**, ou seja uma API é criada quando uma **empresa de software tem a intenção de que outros criadores de software desenvolvam produtos associados ao seu serviço**. Exemplo: Google MAPS, ele possui milhões de endereços cadastrados e o google disponibiliza esses dados por meio de uma API.

- Caracteristicas
  - Permite a **interoperável**(_diferentes sistemas e linguagens se comunicam de forma padronizada via json ou xml_) entre sistemas e linguagens.
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

> É um estilo **arquitetural** para _construção_ de **web service** escaláveis que define um conjunto de regras.

> **NORMALMENTE** a troca de informação é feito por meio de **JSON**

- Ferramentas (usados para testar um webservice rest ao invez de fazer toda a programação).
  - POSTMAN
  - NGINX
  
- Regras
  - Cliente
    - Preocupa em **como** vai **MOSTRAR** esses dados para o cliente. Tipo colocar os dados em um select, em uma `<ul></ul>
  - Servidor
    - Preocupa em **ARMAZENAR** e faz **lógica do negócio**. Tipo fazer um IF, ve se o usuário e senha estão corretos, salvar no **banco de dados**
  - Sem estado( **stateless** )
    - Servidor **não** mantem **ESTADO** sobbre a **sessão** do usuário/aplicação. Ou seja nunca fica LOGADO
    - Toda **requisição** deve ter todas as informações ( URL, METODO(get, post, patch) parametros http://google.com?nome=teste
  - Permite cache
    - Tem como escolher se quer ou não cache
    - As **respostas** podem ser armazenadas em **cache** ( NO CLIENTE)
  - Sistem em camadas
    - Cada funcionalidade pode estar em um servidor diferente.
  
## Interface uniforme

- Todas as **requisições** são feitas em uma **URL**
  - Exemplo http://graph.facebook.com/luketevl2
- Mensagens auto descritivas ou seja, as mensagems de erros são de faceis entendimentos( pois vem no padrão de escrita para todo mundo entender)
- Hipertexto como o mecanismo de estado da aplicação.

## Beneficios
 
- Escalavél (pode ter 1 ou 9999 de sistemas usando o webservice REST) pois nao possui **sessão**
- Portatil ( Pois pode ser feito para web, para smartphone, tv tudo).
- Simplica o servidor( Pois ele nao fica gerenciando se o usuário esta ou no logado)
- Maior confiança (recupera de falhas de forma legal)
- Simplicidade a implementação
- Desacoplamento da arquitetura (funcionalidades não são dependentes)
- Com **cache** diminui o número de **requisições**

# SOAP VS REST

- Requisição **SOAP**
```xml
<?xml version="1.0"?>
<soap:Envelope xmlns:soap="http://www.w3.org/2001/12/soap-envelope"
soap:encodingStyle="http://www.w3.org/2001/12/soap-encoding">
<soap:body pb="http://www.acme.com/phonebook">
<pb:GetUserDetails>
<pb:UserID>12345</pb:UserID>
</pb:GetUserDetails>
</soap:Body> </soap:Envelope>
```

- Requisição **REST**
```http
GET http://www.acme.com/phonebook/UserDetails/12345
```

## Comparativo
![Tabela comparativa SOAP vs REST](http://i.imgur.com/FREzrbj.png)


# RESTFUL

> Criado para dar **simplificidade** e **eficiencia** ao padrão **REST**

- Ele segue **INTEGRALMENTE** as recomendações **REST** ou seja pelo **METODO** (get, post, put, patch, etc) ele sabe squando vai (buscar, salvar, sobreescrever todos os dados, editar, etc).

- **Sem** o padrao **RESTFUL** ele diferencia na **URL** quando ele quer EDITAR, EXCLUIR E ALTERAR. 
- **Com** o padrao **RESTFUL** ele diferencia no **METODO**(get, post, delete, put) quando ele quer EDITAR, EXCLUIR E ALTERAR. 

![Tabela rest vs restful](http://i.imgur.com/PTns2Mn.png)

- Caracteristicas
  - **SEM ESTADO** **stateless**
  - Pode enviar receber **XML** ou **JSON**
  
  
  
  # Obvervações
  
- **SOAP** 
  - Desvantagens
    - Burocratico
    - Performance
    - Requisicao tem tamanho maior(por ser em xml)
    - **Possui** varios padroes
    - ~~chato~~
  - Vantagens
    - Altamente tipado ( voce tem que definir qual o tipo de dados que ta recebendo e enviando, string, int, real).
    - Plataforma e linguagem independentes
    - Bem descrito usando o WSDL
    
- **REST** 
  - Desvantagens
    - **FALTAM** padroes
    - **Falta segurança** pois pode passar pela URL dados secretos.
  - Vantagens
    - **Simples**
    - **Altamente escalavel**
    - **Nao possui estado** stateless
    - Curva de aprendizagem baixa
    - Utiliza protocolo HTTP para comunicação, o que deixa o trafego de dados menor.
