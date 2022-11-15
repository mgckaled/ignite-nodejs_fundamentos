<!-- markdownlint-disable MD010 -->
<!-- markdownlint-disable MD033 -->
<!-- markdownlint-disable MD041 -->

<div align="center">
   <img alt="Node.js" src=".github/assets/nodejs-logo.jpg" width="40%"/>
</div>
<br>

<div align="center">
   <a href="https://github.com/mgckaled">
      <img alt="Made by mgckaled" src="https://img.shields.io/badge/made%20by-mgckaled-yellow">
   </a>
   <img alt="GitHub Repo Size" src="https://img.shields.io/github/repo-size/mgckaled/ignite-nodejs_fundamentos">
   <img alt="GitHub Language Count" src="https://img.shields.io/github/languages/count/mgckaled/ignite-nodejs_fundamentos">
   <a href="https://github.com/mgckaled/ignite-nodejs_fundamentos/commits/main">
      <img alt="GitHub Last Commit" src="https://img.shields.io/github/last-commit/mgckaled/ignite-nodejs_fundamentos">
   </a>  
</div>
<br>

<div align="center">
  <a>
    <img alt="NodeJS" src="https://img.shields.io/badge/node.js-6DA55F?style=for-the-badge&logo=node.js&logoColor=white"/>
    <img alt="Insomnia" src="https://img.shields.io/badge/Insomnia-black?style=for-the-badge&logo=insomnia&logoColor=5849BE"/>
  <a/>
</div>

<br>

# Ignite Node.js - Fundamentos do Node.js

<div align="center">

[**Conceitos**](#conceitos) &nbsp;&nbsp;**•**&nbsp;&nbsp;
[**Tecnologias**](#tecnologias) &nbsp;&nbsp;**•**&nbsp;&nbsp;
[**Licença**](#licença)

</div>

## Conceitos

### O que é Node.js?

- Plataforma ou ambiente open-source que permite execução da linguagem javascript do lado do servidor. De acordo com sua definição oficial, o Node é um runtime, que nada mais é do que um conjunto de códigos, API's, ou seja, são bibliotecas responsáveis pelo tempo de execução (é o que faz o seu programa rodar) que funciona como um interpretador de JavaScript fora do ambiente do navegador web.
- Pricipalmente composto por 6 bibliotecas 3 ferramentas:
  - B1 **_v8_**: O V8 é o engine open-source de JavaScript e WebAssembly de alto desempenho do Google. Ele foi escrito em C++ e usado tanto no Chrome quanto em ambientes similares ao Chrome, e no Node.js. O V8 possui a implementação completa para ECMAScript e WebAssembly. Mas ele não depende de um navegador, na verdade, o V8 pode ser executado de forma independente e incorporado a qualquer aplicativo C++.
  - B2 **_libuv_**: libuv é uma biblioteca C originalmente escrita para Node.js para abstrair operações de I/O sem bloqueio. O modelo de I/O assíncrona orientada a eventos é integrado. Ele permite que a CPU e outros recursos sejam usados ​​simultaneamente enquanto ainda executam operações de I/O, resultando em uso eficiente de recursos e rede
  - B3 **_llhttp_**: A análise HTTP é tratada por uma biblioteca leve de TypeScript e C chamada llhttp. Ela foi projetado para não fazer _syscalls_ ou _alocations_, portanto, possui um _footprint_ de memória muito pequena por solicitação.
  - B4 **_c-ares_**: Para algumas solicitações de DNS assíncronas, o Node.js usa uma biblioteca C chamada c-ares. Ele é exposto através do módulo DNS em JavaScript como a família de funções `resolve()`. A função `lookup()`, que é o que o resto do núcleo usa, faz uso de chamadas `getAddrInfo(3)` encadeadas em libuv. A razão para isso é que c-ares suporta `/etc/hosts`, `/etc/resolv.conf` e `/etc/svc.conf`, mas não coisas como mDNS.
  - B5 **_OpenSSL_**: O OpenSSL é usado extensivamente nos módulos `tls` e `crypto`. Ele fornece implementações _batte-tested_ de muitas funções criptográficas das quais a web moderna depende para ter segurança.
  - B6 **_zlib_**: Para compactação e descompactação rápidas, o Node.js conta com a biblioteca zlib padrão da industria, também conhecida por seu uso em **gzip** e **libpng**. O Node.js usa zlib para possibilitar a compressão e descompressão de interface assíncronas e síncronas.
  - F1 **_npm_**: gerenciador de bibliotecas e módulos (_Node Package Manager_)
  - F2 **_gyp_**: O sistema de compilação é tratado pelo **gyp**, um gerador de projeto baseado em python copiado da V8. Ele pode gerar arquivos de projeto para uso com sistemas de compilação em várias plataformas. O Node.js requer um sistema de compilação porque grande parte dele — e suas dependências — são escritas em linguagens que exigem compilação.
  - F3 **_gtest_**: O código nativo pode ser testado usando gtest, que é retirado do Chromium. Ele permite testar C/C++ sem precisar de um executável de nó existente para inicializar.

### O que o Node.js veio resolver?

- Criado por Ryan Dahl
- Barra de progresso do _flickr_ não incorporava
- Tecnologias da época não davam um bom suporte ao processo de **I/O**.

### Características do Node.js

- Arquitetura Event Loop - _Call Stack_
- _**Single-Thread**_: apenas uma thread é responsável por executar o código Javascript da aplicação, enquanto que nas outras linguagens a execução é multi-thread.
- _Non-blocking I/O_
- Módulos próprios
  - `http`
  - `dns`
  - `fs`
  - `buffer`
- mais informações sobre características do Node.js [aqui](https://www.opus-software.com.br/node-js/#).

### O que são gerenciadores de pacotes?

- `npm` e `yarn`
- serve para instalar bibliotecas e módulos
- Disponibilizar bibliotecas. Devs podem desenvolver bibliotecas e compatilhar com outros programadores.
- Geralmente o Yarn é mais rápido do que o NPM

### Frameworks

- Express
- Egg.js
- Nest.js
- Adonis.js

## Conceitos API Rest

### O que é API?

- _Application Programming Interface_ (Interface de Programação de Aplicativos)
- Conjunto de especificações de possíveis interações entre aplicações
- Documentação para desenvolvedor. É necessário o desenvolvedor utilizar uma boa documentação, é importante que ele saiba as rotas que ele pode acessar e os tipo de retorno que pode ter.

### O que é REST

- _Representation State Transfer_ (Transferência Representacional de Estado)
- É um modelo de arquiterura
- Composto por 6 regras:

  - _**Client-Server**_ - regra básica de uma arquitetura _REST_ (divisão Servidor/Cliente)
  - _**Stateless**_ - ser _stateless_ é a capacidade que um servidor tem de processar requisições de um cliente sem precisar usufruir de nenhum dado já previamente guardado nele. Logo, o envio de dados ao servidor deve conter TODA informação necessária para ser compreendida e processada.
  - _**Cache**_ - A interface Cache fornece um mecanismo de armazenamento persistente para pares de objetos de solicitação(_request_)/resposta(_response_) que são armazenados em cache na memória de longa duração.
  - _**Interface Uniforme**_

    - Indenticação dos recursos
      - <http://enderecoservidor.com.br/products>
      - <http://enderecoservidor.com.br/clients>
    - Representação dos Recursos
      - `JSON`
      - `HTML`
      - `XML`
      - outros
    - Mensagens auto-descritivas. É importante descrever mensagens para esclarecer os clientes.
    - HATEOAS (_Hypertext As The Engine Of Application State_). Siginifica retornar links dentro da requisição. Ex:

      - ```json
        {
        	"id": 1,
        	"user": "marcelkaled",
        	"created_at": "2020-10-10",
        	"commentsLink": "api/users/1/comments"
        }
        ```

  - _**Camadas**_ - implica na existencia de camadas de segurança entre cliente/servidor
  - _**Código Sob Demanda**_ - opcional. Permite que as funcionalidades do cliente sejam extendidas na forma de _scripts_ ou mini-apps

> Qual a diferença entre stateless e Stateful? - A diferença mais importante é que o stateless é um widget estático, ou seja, não temos como gerenciar o estado dele. E o stateful é completamente dinâmico e nos dá o poder de torná-lo mutável através da gerência de estados

## Métodos de Requisições - HTTP Verbs

- `GET` - Leitura
- `POST` - Criação
- `PUT` - Atualização
- `DELETE` - Deleção
- `PATCH` - Atualização parcial

## HTTP Codes

- `1XX`: Informativo - a solicitação foi aceita ou o processo continua em andamento.
- `2XX`: Confirmação
  - `200` - Requisição bem sucedida
  - `201` - Created - Geralmente usado para `POST` após uma inserção
- `3XX`: Redirecionamento
  - `301` - Moved Permanently
  - `302` - Moved
- `4XX`: Erro do Cliente
  - `400` - Bad Request
  - `401` - Unauthorized
  - `403` - Forbidden
  - `404` - Not Found
  - `422` - Unprocessable Entity
- `5XX`: Erro no Servidor - O servidor falhou ao concluir a solicitação
  - `500` - Internal Server Error
  - `502` - Bad Gateway

## Tecnologias

- `express`: o [Express](https://expressjs.com/pt-br/) é um framework para aplicativo da web do Node.js mínimo e flexível que fornece um conjunto robusto de recursos para aplicativos web e móvel. Ele é um micro-framework e é focado na construção de APIs ou servidores HTTP que podem servir páginas estáticas.
- `nodemon`: o [Nodemon](https://www.npmjs.com/package/nodemon) é uma biblioteca que ajuda no desenvolvimento de sistemas com o Node. js reiniciando automaticamente o servidor. Imagine a seguinte situação, você está desenvolvendo uma aplicação com o Node, e criou uma rota, para acessá-la, é preciso reiniciar o servidor.
- `Insomnia`: [Insomnia](https://insomnia.rest/) é um framework Open Source para desenvolvimento/teste de API Clients. Ele pode ser usado para envio de requisições REST, SOAP, GraphQ e GRPC. Com esta ferramenta torna-se possível realizar a documentação, automação e com a sua versão CLI tools é possível implementar testes em pipeline

## Licença

Distribuído sob a licença _MIT_. Veja [LICENSE](LICENSE) para mais informações.

---

<h5 align="center">
  &copy;2022 - <a href="https://github.com/mgckaled/">Marcel Kaled</a>
</h5>
