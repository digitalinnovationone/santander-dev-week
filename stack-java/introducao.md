# Introdução

Interessada em dispositivos eletrônicos inteligentes, a Sun Microsystems financiou uma pesquisa interna com o codinome Green em 1991. O projeto resultou no desenvolvimento de uma linguagem baseada em C e C++ que seu criador, James Gosling, chamou de Oak (carvalho) em homenagem a uma árvore que dava para a janela do seu escritório na Sun.

Hoje a linguagem Java é mantida pela [Oracle Inc.](https://www.oracle.com/java/technologies/downloads/) e já esta na sua versão 18 do JDK.

![](<../.gitbook/assets/image (41).png>)

## Orientada a Objetos

Em programação orientada da objetos, um objeto é uma abtração do mundo real composto por um identificador (_nome_), atributos (_propriedades_) e métodos (_comportamentos_) definidos em uma classe.

Em Java, uma classe é descrita em um arquivo com a extensão `.java`. Abaixo iremos explorar algumas expressões utilizadas na programação orientada a objetos e uma ilustração de estrutura de uma classe Student e a criação de objetos a partir desta classe.

* **Instanciar** _(new)_**:** É o ato de criar um objeto a partir de estrutura definida em uma classe.
* **Comportamentos** _(behavior)_**:** Também conhecido como **ações** ou **métodos**, é toda parte comportamental que um objeto dispõe.
* **Características** _(states)_**:** Também conhecido como **atributos** ou **propriedades**, é toda informação que representa o estado do objeto.
* **Identificador** (identity): Propósito existencial aos objetos que serão criados.&#x20;
* **Classe** _(class)_: A estrutura e ou a representação que direciona a criação dos objetos de mesmo tipo.

![](<../.gitbook/assets/image (22).png>)

Para ilustrar as etapas de desenvolvimento orientada a objetos em Java, iremos reproduzir a imagem acima em forma de código para explicar que primeiro criamos a estrutura correspondente para assim podermos cria-los com as características e possibilidade de realização de ações (comportamentos) como se fosse no "mundo real".

```java
// Criando a classe Student
// Com todas as características e compartamentos aplicados

public class Student {
    String name;
    int age;
    Color color;
    Sex sex;

    void eating(Food food){
      //NOSSO CÓDIGO AQUI
    }
    void drinking(Eat eat){
      //NOSSO CÓDIGO AQUI
    }
    void running(){
      //NOSSO CÓDIGO AQUI
    }
}

```

```java
// Criando objetos a partir da classe Student

public class School {
    public static void main(String[] args) throws Exception {
      Student student1 = new Student();
      student1.name= "John";
      student1.age= 12;
      student1.color= Color.FAIR;
      student1.sex= Sex.MALE;

      Student student2 = new Student();
      student2.name= "Sophia";
      student2.age= 10;
      student2.color= Color.FAIR;
      student2.sex= Sex.FEMALE;

      Student student3 = new Student();
      student3.name= "Lily";
      student3.age= 11;
      student3.color= Color.DARK;
      student3.sex= Sex.FEMALE;
    }
}


```

{% hint style="info" %}
O que queremos ilustrar aqui é que em linguagem orientada a objetos, nós desenvolvedores focamos na estrutura da classe e é a aplicação que fica encarregada da criação dos objetos através de interação dos usuários na aplicação.
{% endhint %}

