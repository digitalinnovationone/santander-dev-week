# Tecnologias

Quando falamos em programar em Java devemos dominar além dos fundamentos da linguagem, um conjunto de ferramentas e frameworks exclusivos. Abaixo iremos listar as tecnologias que iremos utilizar, mas claro, cientes que além de disponibilidade de outras ferramentas, existem também recursos similares e com a mesma proposta.

* **Java JDK**: Kit de Ferramentas para desenvolvimento na linguagem.
* **Eclipse IDE**: Programa para edição, depuração compilação, testes e execução de programas Java
* **Hibernate**: Framework baseado no conceito de ORM para a persitência de dados em um banco relacional.
* **Spring Framework:** Plataforma para desenvolvimento de aplicações Java baseado nos padrões de projeto de inversão de controle e injeção de dependências.
* **Postgres**: Banco de dados relacional utilizado em projetos de grande porte
* **Swagger**: Ferramenta de documentação de APIs e Webservices
* **Github**: Repositório e gerenciador de versionamento de código fonte
* **Maven**: Sistema para gestão de dependência e distribuição de uma aplicação
* **REST**: Arquitetura para transferência de dados representativos como JSON
* **Heroku**: Plataforma para hospedagem de aplicações com fácil integração com Github&#x20;

![](<../.gitbook/assets/image (5).png>)

## Arquitetura

O projeto Banckline será desenvolvida na arquitetura do Spring Framework + Springboot estruturado no padrão MVC para prover uma API Rest para movimentações financeiras simples.

### Spring Framework

Framework open source desenvolvido para a plataforma Java baseado nos padrões de projetos inversão de controle e injeção de dependência.

Sua estrutura é composta por módulos afins de reduzir a complexidade no desenvolvimento aplicações simples ou corporativa.

![](<../.gitbook/assets/image (25).png>)



#### Spring versus JavaEE <a href="#spring-versus-javaee" id="spring-versus-javaee"></a>

![](<../.gitbook/assets/image (15).png>)

​

> Olhando um pouco a história, há muito, mas muito tempo atrás, o Java EE era realmente muito complicado e nem era necessário entrar numa discussão, usar o Spring era um caminho mais simples e mais fácil de evoluir. Aí chegou a versão 5 do Java EE e a discussão voltou a ficar um pouco mais quente.

#### O Spring Framework é estruturado em dois pilares

**Inversion of Control ou IoC**, trata-se do redirecionamento do fluxo de execução de um código retirando parcialmente o controle sobre ele e delegando-o para um container. O principal propósito é minimizar o acoplamento do código.

**Injeção de dependência** é um padrão de desenvolvimento com a finalidade de manter baixo o nível de acoplamento entre módulos de um sistema.

> Para desfrutrar dos recursos oferecidos pelo Spring Framework, precisamos compreender três conceitos essenciais.

* **Beans**: Objeto que é instanciado (criado), montado e gerenciado por um container através do princípio da inversão de controle.
* **Scopes**: Controle da existência de nossos objetos **Components** da aplicação em uma esfera de utilização: _**Singleton, Prototype, Reques, Session, Global**_
* **Autowired:**  Um recurso em forma de **** anotação (indicação) onde deverá ocorrer uma injeção automática de dependência.

### Springboot

Enquanto que o Spring Framework é baseado no padrão de injeção de dependências, o Springboot foca na configuração automática.

![](<../.gitbook/assets/image (46).png>)

Dado que a maior parte das configurações necessárias para o início de um projeto são sempre as mesmas, por que não iniciar um projeto com todas estas configurações já definidas?\


![](https://files.gitbook.com/v0/b/gitbook-legacy-files/o/assets%2F-MgwMOcm4UygF4VcCNIq%2F-MjhPknYh9WpufWi69TG%2F-MjhVu18mraAn7n0rG6V%2FImagem1.gif?alt=media\&token=c33ed917-35be-47f3-bfcd-e6b0ae5a23e7)

#### Starters

Os starters são dependências que agrupam outras dependências com um propósito em comum. Dessa forma, somente uma configuração é realizada no seu gerenciador de dependências

![](<../.gitbook/assets/image (32).png>)

#### Alguns Starters

**spring-boot-starter-\***

* **data-jpa**: Integração ao banco de dados via JPA - Hibernate.&#x20;
* **data-mongodb**: Interação com banco de dados MongoDB.&#x20;
* **web**: Inclusão do container Tomcat para aplicações REST.&#x20;
* **web-services**: Webservices baseados na arquitetura SOAP.
* **batch**: Implementação de JOBs de processos.&#x20;
* **test**: Disponibilização de recursos para testes unitários como JUnit&#x20;
* **openfeign**: Client HTTP baseado em interfaces&#x20;
* **actuator**: Gerenciamento de monitoramento da aplicação.

