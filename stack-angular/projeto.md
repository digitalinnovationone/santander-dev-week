# Projeto

Esta etapa do projeto consiste em criar uma aplicação web que se comunicará via requisições https baseadas na arquitetura REST em nossa Brankline-API desenvolvida com Springboot e disponibilzada no Heroku.

![](<../.gitbook/assets/image (17).png>)

Iremos explorar recursos essenciais em um desenvolvimento utilizando Angular conforme abaixo:

* Angular 13: [https://angular.io/](https://angular.io)&#x20;
* Angular HttpClient: [https://angular.io/api/common/http/HttpClient](https://angular.io/api/common/http/HttpClient)&#x20;
* Angular Router: [https://angular.io/api/router](https://angular.io/api/router)&#x20;
* Bootstrap 5: [https://getbootstrap.com/](https://getbootstrap.com)&#x20;

### Criando o projeto com angular-cli

Vamos criar no diretório **c:\estudos** o projeto **bankline-app** utilizando a _interface de linha de comandos_ o `angular-cli`.

* Primeiramente iremos confirmar se estamos com o node e npm instalados

```javascript
node --version

e 

npm --version
```

* Depois precisaremos instalar o **angular-cli**

```
npm install -g @angular/cli
```

* Em seguida será possível executar os comandos angular pelo terminal

```
// obtendo a versão do Angular CLI

ng --version

//gerando uma nova aplicação
//é importante que este comando segue executado em c:\estudos
//deste forma já teremos um recurso de teste e o TypeScript configurado

ng new bankline-app

//após abrir o projeto no VSCode
ng serve -o
```

Conhecendo os arquivos do nosso projeto:

![](<../.gitbook/assets/image (54).png>)

* **node\_modules:** pasta contendo todas as dependências do projeto
* **src**: pasta que contém todo o código fonte do projeto
* **.editorconfig**: arquivo de configuração do VSCode para projeto Angular
* **.gitignore**: arquivo que configuramos para determinar pastas, extensões e arquivos que não devem ser sincronizados com github
* **angular.json**: Arquivo para as configurações do angular
* **package.json**: arquivo para configurar definições e dependências do projeto
* **README.md**: Arquivo que contém a descrição de nosso projeto.
* **tsconfig.json**: Arquivo de configuração do TypeScript, exemplo qual versão do JavaScript você deseja compilar
* **tsconfig.spec.json**: Arquivo de configuração para testes da aplicação.
* **src/app:** Pasta principal contendo todos arquivos para a criação das funcionalidades da aplicação.
* **src/assets:** Pasta que contém arquivos javascript, css, imagens adicionais.&#x20;
* **src/environments:** Diretório pertinente aos ambientes da aplicação
* **src/favicon.ico:** Ícone da aplicação
* **src/index.html:** Página principal da aplicação
* **src/main.ts:** Arquivo principal da aplicação
* **src/polyfills.ts**: Arquivo responsável por carregar os módulos da aplicação.
* **src/styles.css**: Arquivo para estilização global da aplicação.&#x20;
* **src/teste.ts**: Arquivo para carregar nossos testes

### Construção do app

Após analisar a estrutura do projeto criado, iremos ajustes alguns arquivos e criar nossos components, services e demais recursos necessários.

* Criando o componente para exibir as movimentações

```
ng g c components/movimentacao-list
```

* Criando o componente para adicionar uma nova movimentação

```
ng g c components/movimentacao-new
```

* Configurando a rota para exibir nossos novos componentes

```javascript
// localize o arquivo src/app/app-routing.module.ts

import { MovimentacaoNewComponent } from './components/movimentacao-new/movimentacao-new.component';
import { MovimentacaoListComponent } from './components/movimentacao-list/movimentacao-list.component';

const routes: Routes = [

  { path: 'movimentacoes-new', component: MovimentacaoNewComponent },
  { path: 'movimentacoes', component: MovimentacaoListComponent },
  { path: '', redirectTo: 'movimentacoes', pathMatch: 'full' },

];
```

* Removendo conteúdo gerado pelo Angular e exibir nossos componentes:

```html
<!-- Toolbar -->
<div class="toolbar" role="banner">
  <img
    width="40"
    alt="Angular Logo"
    src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNTAgMjUwIj4KICAgIDxwYXRoIGZpbGw9IiNERDAwMzEiIGQ9Ik0xMjUgMzBMMzEuOSA2My4ybDE0LjIgMTIzLjFMMTI1IDIzMGw3OC45LTQzLjcgMTQuMi0xMjMuMXoiIC8+CiAgICA8cGF0aCBmaWxsPSIjQzMwMDJGIiBkPSJNMTI1IDMwdjIyLjItLjFWMjMwbDc4LjktNDMuNyAxNC4yLTEyMy4xTDEyNSAzMHoiIC8+CiAgICA8cGF0aCAgZmlsbD0iI0ZGRkZGRiIgZD0iTTEyNSA1Mi4xTDY2LjggMTgyLjZoMjEuN2wxMS43LTI5LjJoNDkuNGwxMS43IDI5LjJIMTgzTDEyNSA1Mi4xem0xNyA4My4zaC0zNGwxNy00MC45IDE3IDQwLjl6IiAvPgogIDwvc3ZnPg=="
  />
  <span>{{ title }}</span>
    <div class="spacer"></div>
    <a aria-label="Angular on twitter" target="_blank" rel="noopener" href="https://twitter.com/angular" title="Twitter">
      <svg id="twitter-logo" height="24" data-name="Logo" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 400 400">
        <rect width="400" height="400" fill="none"/>
        <path d="M153.62,301.59c94.34,0,145.94-78.16,145.94-145.94,0-2.22,0-4.43-.15-6.63A104.36,104.36,0,0,0,325,122.47a102.38,102.38,0,0,1-29.46,8.07,51.47,51.47,0,0,0,22.55-28.37,102.79,102.79,0,0,1-32.57,12.45,51.34,51.34,0,0,0-87.41,46.78A145.62,145.62,0,0,1,92.4,107.81a51.33,51.33,0,0,0,15.88,68.47A50.91,50.91,0,0,1,85,169.86c0,.21,0,.43,0,.65a51.31,51.31,0,0,0,41.15,50.28,51.21,51.21,0,0,1-23.16.88,51.35,51.35,0,0,0,47.92,35.62,102.92,102.92,0,0,1-63.7,22A104.41,104.41,0,0,1,75,278.55a145.21,145.21,0,0,0,78.62,23" fill="#fff"/>
      </svg>
    </a>
    <a aria-label="Angular on YouTube" target="_blank" rel="noopener" href="https://youtube.com/angular" title="YouTube">
      <svg id="youtube-logo" height="24" width="24" data-name="Logo" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="#fff">
        <path d="M0 0h24v24H0V0z" fill="none"/>
        <path d="M21.58 7.19c-.23-.86-.91-1.54-1.77-1.77C18.25 5 12 5 12 5s-6.25 0-7.81.42c-.86.23-1.54.91-1.77 1.77C2 8.75 2 12 2 12s0 3.25.42 4.81c.23.86.91 1.54 1.77 1.77C5.75 19 12 19 12 19s6.25 0 7.81-.42c.86-.23 1.54-.91 1.77-1.77C22 15.25 22 12 22 12s0-3.25-.42-4.81zM10 15V9l5.2 3-5.2 3z"/>
      </svg>
    </a>
</div>

<div class="content" role="main">
  <router-outlet></router-outlet>
</div>



```

* Adicionando a biblioteca do Bootstrap pelo angular-cli

```
1. no terminal, pare a aplicação com CTRL+C

2. ng add @ng-bootstrap/ng-bootstrap
```

{% hint style="danger" %}
Se ao tentar instalar o bootstrap apresentar algum erro, execute os comandos abaixo e repita o processo acima.

`npm config set legacy-peer-deps true`
{% endhint %}

* Criando uma variável que representará as nossas movimentações

```javascript
// movimentacao-list.component.ts

movimentacoes:any;
```

* Estruturando a tabela que exibibirá as movimentações

```html
// movimentacao-list.component.html

<table class="table table-striped">
    <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">Data Hora</th>
      <th scope="col">Descrição</th>
      <th scope="col">Valor</th>
      <th scope="col">Tipo</th>
    </tr>
    </thead>
    <tbody>
    <tr *ngFor="let item of movimentacoes; index as i">
      <th scope="row">{{ i + 1 }}</th>
      <td>{{ item.dataHora }}</td>
      <td>{{ item.descricao }}</td>
      <td>{{ item.valor }}</td>
      <td>{{ item.tipo }}</td>
    </tr>
    </tbody>
  </table>
```

![](<../.gitbook/assets/image (47).png>)

### Back-end C**ORS**

Antes de pensar em utilizar a API, verifique se foi habilitado o recurso de **CORS.**

_Cross-Origin Resource Sharing_ ou _CORS_ é um mecanismo que permite que recursos restritos em uma página da web sejam recuperados por outro domínio fora do domínio ao qual pertence o recurso que será recuperado

```java
// WebConfig.java

package com.dio.santander.bankline.api.config;

import org.springframework.context.annotation.Configuration;
import org.springframework.web.servlet.config.annotation.CorsRegistry;
import org.springframework.web.servlet.config.annotation.EnableWebMvc;
import org.springframework.web.servlet.config.annotation.WebMvcConfigurer;

@Configuration
@EnableWebMvc
public class WebConfig implements WebMvcConfigurer {

    @Override
    public void addCorsMappings(CorsRegistry registry) {
        registry.addMapping("/**");
    }
}
```

****

### Integrando com nossa API

Iremos agora implementar mais uma camada da aplicação, os serviços que estarão interagindo com a nossa api REST.

* Criando o serviço de movimentações

```
ng g s services/movimentacao
```

* Como iremos trabalhar com requisições HTTPs e formulário, já vamos adicionando duas dependências no projeto.

```javascript
// app.module.ts

import { FormsModule } from '@angular/forms';
import { HttpClientModule } from '@angular/common/http';

@NgModule({
  imports: [
    FormsModule,
    HttpClientModule
  ],
  
})
```

* Criando nosso primeiro recurso para obter as movimentações já realizadas

```javascript
// movimentacao.service.ts

import { Injectable } from '@angular/core';
import { HttpClient } from '@angular/common/http';
import { Observable } from 'rxjs';

//mude para sua aplicação
const baseUrl = 'http://localhost:8080';

@Injectable({
  providedIn: 'root'
})
export class MovimentacaoService {
  constructor(private http: HttpClient) { }
  
  list(): Observable<any> {
    return this.http.get(`${baseUrl}/movimentacoes`);
  }
  
}
```

* Agora será necessário determinar que quando o componente de listagem de movimentações for carregado seja realizada uma requisição à nossa API.

```javascript
// movimentacao-list.component.ts

import { Component, OnInit } from '@angular/core';
import { MovimentacaoService } from 'src/app/services/movimentacao.service';

@Component({
  selector: 'app-movimentacao-list',
  templateUrl: './movimentacao-list.component.html',
  styleUrls: ['./movimentacao-list.component.css']
})


export class MovimentacaoListComponent implements OnInit {
  movimentacoes:any;

  constructor(private movimentacaoService: MovimentacaoService) { }

  ngOnInit(): void {
    this.listMovimentacoes();
  }
  listMovimentacoes(): void {
    this.movimentacaoService.list()
      .subscribe(
        data => {
          this.movimentacoes = data;
          console.log(data);
        },
        error => {
          console.log(error);
        });
  }

}


```

![](<../.gitbook/assets/image (50).png>)

### Formatando campos na tela

Para formatação de valores do tipo data e monetário por exemplo, o Angular dispõe de um recurso denominado de Pipe.

Vamos ajustar alguns arquivos para formatar os campos Data Hora e Valor.

* Adicionado algumas configurações no módulo do projeto

```javascript
// app.module.ts

import { LOCALE_ID } from '@angular/core';
import { registerLocaleData } from '@angular/common';
import localePt from '@angular/common/locales/pt';

registerLocaleData(localePt);
... 

 providers: [{provide: LOCALE_ID, useValue: 'pt-BR'}],
```

* Adicionando as formatações nos campos Data Hora e Valor

```html
// movimentacao-list.component.html

<td>{{ item.dataHora | date: 'dd/MM/yyyy HH:mm:ss' }}</td>
<td>{{ item.valor | currency:'BRL' }}</td>
```

* Aplicando estilo com base em uma condição em nossos registros.

```html
// movimentacao-list.component.html

<td [ngStyle]="{'color':item.tipo === 'RECEITA' ? 'blue' : 'red'}">{{ item.valor | currency:'BRL' }}</td
```

* Adicionando o botão Novo na página de movimentação.

```html
// movimentacao-list.component.html

//link tem o mesmo estilo que um button

<a class="btn btn-outline-primary btn-sm">Nova Movimentação</a>

```

* Centralizando o conteúdo da página

```html
// movimentacao-list.component.html

<div class="container">

//conteúdo já existente

</div>
```

* Configurando a rota para a página para cadastrar uma nova movimentação.

```java
// movimentacao-list.component.html

<a routerLink="/movimentacoes-new">Novo</a>

```

### Nova Movimentação

O primeiro passo é exibir os campos de entrada para gerar uma nova movimentação conforme conteúdo abaixo:

```html
// movimentacao-new.component.html
<div class="container">
    <div class="jumbotron">
        <h1 class="display-6">Movimentação</h1>
        <p class="lead-1">Inclusão de uma nova movimentação</p>
        <hr class="my-2">
        
        
            <div class="col-md-3">
              <label for="iData" class="form-label">Data</label>
              <input type="date" class="form-control" id="iData">
            </div>
            <div class="col-md-9">
              <label for="iCorrentista" class="form-label">Correntista</label>
              <select id="iCorrentista" class="form-select">
                <option selected>Choose...</option>
                <option>...</option>
              </select>
            </div>
            <div class="col-12">
              <label for="iDescricao" class="form-label">Descrição</label>
              <input type="text" class="form-control" id="iDescricao" placeholder="Informe uma descrição">
            </div>
            <div class="col-md-3">
              <label for="iTipo" class="form-label">Tipo Movimentação</label>
              <select id="iTipo" class="form-select">
                <option selected>Tipos</option>
                <option>...</option>
              </select>
            </div>
            <div class="col-md-2">
              <label for="iValor" class="form-label">R$ Valor</label>
              <input type="text" class="form-control" id="iValor">
            </div>
            <div class="d-grid gap-2 d-md-flex ">
                <button class="btn btn-outline-primary me-md-2" type="button">Confirmar</button>
                <a routerLink="/movimentacoes" class="btn btn-outline-secondary">Cancelar</a>
              </div>
         
      </div>

</div>


```

Observe que alguns campos são opções já definidas como **Correntista** e **Tipo Movimentação**, estes dois são campos de seleção em nossa página.

* Preenchendo as opções do **Tipo Movimentação**

```html
<select id="iTipo" class="form-select">
    <option selected>RECEITA</option>
    <option>DESPESA</option>
</select>
```

* Para preencher o campo seleção do campo Correntista precisamos trazer os dados da nossa API, sendo assim, iremos realizar alguns procedimentos adicionais:

```
// criando o serviço para acessar os recursos de Correntista

ng g s services/correntista
```

{% hint style="info" %}
A estrutura dos services são muito semelhantes, e para criar um componente no Angular você precisar para a aplicar a aplicação e utilizar o terminal.
{% endhint %}

```javascript
// services/correntista.service.ts

import { Injectable } from '@angular/core';
import { HttpClient } from '@angular/common/http';
import { Observable } from 'rxjs';
const baseUrl = 'http://localhost:8080';
@Injectable({
  providedIn: 'root'
})
export class CorrentistaService {
  constructor(private http: HttpClient) { }
  
  list(): Observable<any> {
    return this.http.get(`${baseUrl}/correntistas`);
  }
  
```

* Vamos solicitar para o nosso componente `movimentacao-new.component.ts` conectar a nossa API para buscar os **correntistas** do banco de dados.

```javascript
// compoenents/movimentacao-new.component.ts

import { Component, OnInit } from '@angular/core';
import { CorrentistaService } from 'src/app/services/correntista.service';
import { MovimentacaoService } from 'src/app/services/movimentacao.service';

@Component({
  selector: 'app-movimentacao-new',
  templateUrl: './movimentacao-new.component.html',
  styleUrls: ['./movimentacao-new.component.css']
})
export class MovimentacaoNewComponent implements OnInit {
  correntistas:any;

  constructor(
    private movimentacaoService: MovimentacaoService,
    private correntistaService: CorrentistaService,
    ) { }

  ngOnInit(): void {
    this.exibirCorrentistas();
  }
  exibirCorrentistas(): void {
    this.correntistaService.list()
      .subscribe(
        data => {
          this.correntistas = data;
          console.log(data);
        },
        error => {
          console.log(error);
        });
  }

}

```

* Agora iremos exibir os nossos correntistas na tela de nova movimentação

```html
// movimentacao-new.component.html
 <select id="iCorrentista" [(ngModel)]="correntista" class="form-select">
   <option *ngFor="let c of correntistas" [ngValue]="c">{{c.cpf}}-{{c.nome}}</option>
 </select>
```

* Para poder identificar qual foi o correntista selecionado, agora iremos criar uma variável `correntista` em nosso componente **movimentacao-new.component.ts**.

```javascript
correntista:any;
```

![](<../.gitbook/assets/image (56).png>)

Para finalizar a nossa tela da movimentação, precisaremos agora somente definir uma máscara no campos **R$ Valor**, iremos instalar o componente `ng2-currency-mask` conforme procedimento no próprio site do **npm**.

Link: [https://www.npmjs.com/package/ng2-currency-mask](https://www.npmjs.com/package/ng2-currency-mask)

### Incluindo uma movimentação

Com a tela devidamente estruturada é hora de incluir nossa primeira movimentação pela a aplicação.

```javascript
// services/movimentacao.service.ts

// adicionando o método de inclusão (POST) via API
create(movimentacao:any): Observable<any> {
    return this.http.post(`${baseUrl}/movimentacoes`,movimentacao);
 }
```

```javascript
// components/movimentacao-new.components.ts

// criando o método para ser chamado na tela e assim incluir a movimentação

save(): void {
    console.log(this.correntista)
    const movimentacao = {
      valor:this.valor,
      descricao:this.descricao,
      tipo:this.tipo,
      idConta:this.correntista.id,
      dataHora:this.dataHora

    };
    console.log(movimentacao);
    this.movimentacaoService.create(movimentacao)
      .subscribe(
        response => {
          console.log(response);
        },
        error => {
          console.log(error);
        });
  }
```

Para finalizar, agora só é preciso executar o método `save` no click do botão **Confirmar**.

```html
// components/movimentacao-new.components.html

<button class="btn btn-outline-primary me-md-2 btn-sm" type="button" (click)="save()">Confirmar</button>

//(click)="save()"                                
```

### Movimentações por Correntista

Precisamos ter uma interação constante com a API Back-end, e isso será via swagger. Verifique se temos um serviço para listar as movimentações por correntistas, caso não existe, é necessário criar uma nova funcionalidade no back-end.

```java
// MovimentacaoRepository.java

public MovimentacaoRepository{
     ...
     public List<Movimentacao>findByIdConta(Integer idConta);
}
```

```java
// MovimentacaoController.java

public class MovimentacaoController {
        ... 
        @GetMapping("/{idConta}")
	public List<Movimentacao> findAll(@PathVariable("idConta") Integer idConta){
		return repository.findByIdConta(idConta);
	}
}
```

* Refinando nossa tela de consulta de movimentações

```html
<div class="container">
  <div class="jumbotron">
    <h1 class="display-6">Movimentações</h1>
    <p class="lead-1">Listagem das movimentações por correntista</p>
    <hr class="my-2">
    <div class="input-group">
      <select  id="iCorrentista" [(ngModel)]="correntista" class="form-select">
        <option *ngFor="let c of correntistas" [ngValue]="c" >{{c.cpf}}-{{c.nome}}</option>
      </select>
    <button class="btn btn-outline-secondary me-md-2 btn-sm" type="button" (click)="listMovimentacoes()">Buscar</button>
    <a class="btn btn-outline-primary btn-sm" routerLink="/movimentacoes-new">Nova Movimentação</a>
    <a class="btn btn-outline-primary btn-sm" routerLink="/correntistas">Correntistas</a>
  </div>
<table class="table table-striped">
    <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">Data Hora</th>
      <th scope="col">Descrição</th>
      <th scope="col">Valor</th>
      <th scope="col">Tipo</th>
    </tr>
    </thead>
    <tbody>
    <tr *ngFor="let item of movimentacoes; index as i">
      <th scope="row">{{ i + 1 }}</th>
      <td>{{ item.dataHora | date: 'dd/MM/yyyy HH:mm:ss' }}</td>
      <td>{{ item.descricao }}</td>
      <td [ngStyle]="{'color':item.tipo === 'RECEITA' ? 'blue' : 'red'}">{{ item.valor | currency:'BRL' }}</td>
      <td>{{ item.tipo }}</td>
    </tr>
    </tbody>
  </table>
  </div>
</div>htm
```

* Criando o serviço para listar as movimentações por correntista

```java
// services/movimentacao.service.ts

findByIdConta(idConta:any): Observable<any> {
    return this.http.get(`${baseUrl}/movimentacoes/${idConta}`);
  }
```

```javascript
// components/movimentacao-list.component.ts

import { Component, OnInit } from '@angular/core';
import { CorrentistaService } from 'src/app/services/correntista.service';
import { MovimentacaoService } from 'src/app/services/movimentacao.service';

@Component({
  selector: 'app-movimentacao-list',
  templateUrl: './movimentacao-list.component.html',
  styleUrls: ['./movimentacao-list.component.css']
})


export class MovimentacaoListComponent implements OnInit {
  movimentacoes:any;
  correntistas:any;
  correntista:any={};
  constructor(
    private movimentacaoService: MovimentacaoService,
    private correntistaService: CorrentistaService,
    ) { }
  ngOnInit(): void {
    this.exibirCorrentistas();
  }
  
  listMovimentacoes(): void {
    this.movimentacaoService.findByIdConta(this.correntista.id)
      .subscribe(
        data => {
          this.movimentacoes = data;
          console.log(data);
        },
        error => {
          console.log(error);
        });
  }
  exibirCorrentistas(): void {
    this.correntistaService.list()
      .subscribe(
        data => {
          this.correntistas = data;
          console.log(data);
        },
        error => {
          console.log(error);
        });
  }
  
}

```

### Correntistas

Após a finalização da funcionalidade de movimentação, agora é necessário também gerenciarmos os correntistas pela aplicação. O processo é muito semelhante a etapa anterior.

```
//terminal

ng g c components/correntista
```

```javascript
// app-routing.module.ts

import { CorrentistaComponent } from './components/correntista/correntista.component';
const routes: Routes = [
     ...
     { path: 'correntistas', component: CorrentistaComponent },
]
```

Navegação simples para a rota `correntistas` e **CorrentistaComponent**

```html
// movimentacao-list.component.html

<a class="btn btn-outline-primary btn-sm" routerLink="/correntistas">Correntistas</a>
```

Tela para inclusão e listagem de correntistas

```html
// components/correntista.component.html

<div class="container">
  <div class="jumbotron">
    <h1 class="display-6">Correntistas</h1>
    <p class="lead-1">Cadastro de correntista</p>
    <hr class="my-2">
  </div>
  <div class="row g-2">
    <div class="col-md-3">
      <input  class="form-control" id="iCpf" [(ngModel)]="cpf"  placeholder="CPF">
    </div>
    <div class="col-5">
      <input type="text"  class="form-control" id="iNome" [(ngModel)]="nome" placeholder="Nome do Correntista">
    </div>
    <div class="col-3">
    <div class="d-grid gap-2 d-md-flex ">
        <button class="btn btn-outline-primary me-md-2" type="button" (click)="save()" >Gravar</button>
        <a routerLink="/movimentacoes" class="btn btn-outline-danger">Voltar</a>
      </div>
    </div>
  </div>
  <p></p>
  <div *ngFor="let item of correntistas; index as i" class="card" style="width: 18rem;">
    <div class="card-body">
      <h5 class="card-title">{{item.nome}}</h5>
      <p class="card-text">Conta N° {{item.conta.numero}}</p>
      <p class="card-text">Saldo {{item.conta.saldo | currency:'BRL'}}</p>
    </div>
  </div>
</div>
```

Regra de negócio para inclusão e listagem dos correntistas

```javascript
// components/correntista.component.ts

import { Component, OnInit } from '@angular/core';
import { CorrentistaService } from 'src/app/services/correntista.service';


@Component({
  selector: 'app-correntista',
  templateUrl: './correntista.component.html',
  styleUrls: ['./correntista.component.css']
})
export class CorrentistaComponent implements OnInit {
  correntistas:any;
  cpf:any;
  nome:any;
  constructor(
    private correntistaService: CorrentistaService,
    ) { }
  ngOnInit(): void {
    this.exibirCorrentistas();
  }
  exibirCorrentistas(): void {
    this.correntistaService.list()
      .subscribe(
        data => {
          this.correntistas = data;
          console.log(data);
        },
        error => {
          console.log(error);
        });
  }
  save(): void {
    const correntista = {
      cpf:this.cpf,
      nome:this.nome
    };
    console.log(correntista);
    this.correntistaService.create(correntista)
      .subscribe(
        response => {
          console.log(response);
          this.exibirCorrentistas();
        },
        error => {
          console.log(error);
        });
  }
}

```

Criando mais uma funcionalidade no serviço de correntistas

```javascript
// services/correntista.service.ts

 create(correntista:any): Observable<any> {
    return this.http.post(`${baseUrl}/correntistas`,correntista);
  }
```

![](<../.gitbook/assets/image (40).png>)

#### Referências

{% embed url="https://angular.io/guide/event-binding" %}
Events Binding
{% endembed %}

{% embed url="https://angular.io/cli" %}
Angular Cli
{% endembed %}

{% embed url="https://angular.io/cli/generate" %}
Angular Generate
{% endembed %}

{% embed url="https://www.bezkoder.com/angular-10-spring-boot-crud" %}

{% embed url="https://getbootstrap.com/docs/5.0/forms/layout" %}
