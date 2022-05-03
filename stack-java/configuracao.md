# Configuração

## Java JDK

A primeira etapa é instalarmos o JDK versão 8 ou superior, o Eclipse IDE para testarmos nosso primeiro programa de exibição de boas vindas.



#### Instalando o JDK no Windows

{% hint style="info" %}
Algumas IDEs como o [VSCode](https://code.visualstudio.com/docs/java/java-tutorial) já consegue baixar e instalar o JDK e realizar a configuração de forma fácil.
{% endhint %}

* Busque no Google por Java [JDK xxx](https://www.oracle.com/br/java/technologies/javase/javase8-archive-downloads.html) (versão desejada)
* Selecione a opção **.exe** de acordo com o seu sistema operacional. No meu exemplo eu baixei a versão: [jdk-8u202-windows-x64.exe](https://www.oracle.com/br/java/technologies/javase/javase8-archive-downloads.html#license-lightbox)
* Role um pouco baixa e visualizará a lista de opções de download de acordo com o seu sistema operacional.

![](<../.gitbook/assets/image (14).png>)

* Depois você precisará realizar um login no site da [Oracle](https://login.oracle.com/mysso/signon.jsp).

![](<../.gitbook/assets/image (58).png>)

* Após realizar o download, executar o instalador para instalar o Java no Windows. Este processo instalará tanto o **JDK** quanto a **JRE**.

![](<../.gitbook/assets/image (33).png>)

{% hint style="warning" %}
Evite mudar o diretório de instalação
{% endhint %}

* Em seu explorer deve ter algo mais ou menos assim:

![](<../.gitbook/assets/image (35).png>)

* Precisamos agora validar se a instalação também já configurou nossa variável de ambiente para poder executar o Java pelo Prompt de comando ou PowerShell do Windows.
* Abre o Prompt de comando e execute o comando `java -version`.

![](<../.gitbook/assets/image (49).png>)

{% hint style="info" %}
Não iremos configurar as variáveis de ambiente pois não é um pré-requisito para desenvolver em Java considerando que iremos usufruir das mais poderosas IDEs para aumentar nossa produtividade em codificar na linguagem.
{% endhint %}

## Eclipse IDE

Vamos baixar umas das IDEs mais utilizada para projetos Java.

* Acesse o site para baixar o [Eclipse for Java EE Developers](https://www.eclipse.org/downloads/packages/release/kepler/sr2/eclipse-ide-java-ee-developers).
* Identifique a versão do seu sistema operacional.

![](<../.gitbook/assets/image (57).png>)

* Na sua pasta download deverá os executáveis do Java e do Eclipse, basta iniciar a instalação

![](<../.gitbook/assets/image (44).png>)

* A opção recomendada é **Eclipse IDE for Enterprise Java and Web Developers**

![](<../.gitbook/assets/image (6).png>)

{% hint style="warning" %}
Esta etapa é opcional, crie o diretório **C:\dev\tools** para extrair o eclipse.
{% endhint %}

![A instalação dura em média de 3 a 5 minutos](<../.gitbook/assets/image (24).png>)

Um ícone deve ser criado na sua área de tabalho, caso contrário basta acessar a pasta onde extraiu (**C:\dev\tools\eclipse)** o eclipse e executar.

![](<../.gitbook/assets/image (21).png>)

* **Workspace**: O eclipse costuma organizar nossos projetos por área de desenvolvimento denominados de Worspaces. Você também pode organizar seus projetos por finalidade exemplo: estudo, freela, projetos e etc.

No exemplo abaixo foi criando uma workspace para estudos em **C:\dev\ws\estudos**

![](<../.gitbook/assets/image (30).png>)

Bem-vindo ao **Eclipse IDE**

![](<../.gitbook/assets/image (38).png>)

## Postgre SQL

**PostgreSQL** é um sistema de banco de dados poderoso e em código aberto para Windows, Mac e Linux. Ele consiste em um processo de servidor que lê e grava os arquivos de banco de dados reais, e um conjunto de programas cliente que se comunicam com o servidor. O mais comumente utilizado é o comando **psql**, que permite ao usuário executar consultas SQL e visualizar os seus resultados.

Link para instalação [PostgreSQL Database](https://www.enterprisedb.com/downloads/postgres-postgresql-downloads).

![https://www.enterprisedb.com/downloads/postgres-postgresql-downloads](<../.gitbook/assets/image (45).png>)



![](<../.gitbook/assets/image (36).png>)

O processo de instalação é bem simples, sempre _**Next, Next e Next.**_

Nesta etapa iremos instalar 3 componentes do PostgreSQL

* O PostgreSQL Database Server
* PgAdmin para interagir sobre o banco de dados
* O Commando Line Tools para executar instrução via terminal

![](<../.gitbook/assets/image (29).png>)

Hora de definir o usuário e senha, por recomendação defina ambos como **postgres**

&#x20;****&#x20;

![](<../.gitbook/assets/image (16).png>)

Após a instalação concluída, iremos iniciar o Postgres através do **PgAdmin** localizando no menu iniciar.

&#x20;

![](<../.gitbook/assets/image (7).png>)

### GitHub desktop

Link para download do [GitHub Desktop](https://desktop.github.com) - [https://desktop.github.com/](https://desktop.github.com)

![](<../.gitbook/assets/image (26).png>)
