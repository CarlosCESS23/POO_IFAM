# Programação a Orientada a Objetos

Primeiro, deve-se entender o que seria POO.

## Programação estruturada

É preciso saber que este tipo de programação segue uma lógica e sequência de pensamento de uma máquina. Ou seja, a sua
lógica é direcionada à linguagem de máquina, já que ela realiza o que foi orientado pelo programador

Possui 3 deles:

1. Sequencial 
2. Condicional
3. Repetição

### O que seria então a programação estruturada

A estruturado segue o processo para conseguir atingir o seu final objetivo, imagine que existe um programa para ser des
envolvido onde existem várias etapas que precisam ser cumpridas. Na programação estruturada esse programa é dividido em 
vários processos pequenos e depois é resolvido o problema

###

Paradigma significa literalmente um padrão ou um método. São os métodos para resolver uum programa que é 4 tipo:

<li>Imperativo</li>
<li>Lógico</li>
<li>Funcional</li>
<li>Orientado a objeto</li>

Quando os objetos são usados como entidades base sobre as quais os métodos são aplicados, encapsulamento ou 
funcionalidades de herança são usadas, é conhecido como um paradigma orientado a objeto

### Diferença entre Paradigma orientado a objeto e Programação estruturada

Enquanto a programação estruturada obedece a uma lógica de máquina, o POO funciona de um modo mais similar ao raciocínio
humano, Os códigos são organizados de acordo com contexto

## POO

Programação Orientada a Objetos (POO) é um paradigma de programação que se baseia no conceito de <strong>'Objeto'</strong>,
que são entidades que possuem características (atributos), comportamentos(métodos) que tudo tenha o seu contexto. 
Em POO está a criação de objeto que interagem entre si para realizar tarefas, que seja fácil de manter o código, pois 
dá para reutilizar

<li>Linguagens que usam POO: Java,Python,C++,C# e entre outros</li>
<li>Justamente para ajudar a organizar os códigos para determinados contextos</li>
<li>É uma maneira de conseguir organizar o seu código de uma coisa melhor mais escalável</li>
<li>Fazer isolamento de um contexto das funções (comportamentos) dentro do código</li>

Organizado seguinte forma:

2. Classes
3. Encapsulamento
4. Herança
5. Polimorfismo


## Classe

É uma estrutura que descreve um objeto, especificando o seu contexto, atributos e comportamento que o objeto tem sentido em
ter, elas não são entidades do mundo real, mas nos ajudam a criar objetos que são entidades do mundo real.

Uma classe é uma espécie de modelo que define o que um objeto deve possuir

<li>Classes são usadas para criar objetos, que são instancias da classe</li>
<li>Cada objeto sendo da mesma classe, terá os mesmo atributos, contextos e comportamentos, mas cada um tem os seus 
próprios valores</li>

### Criação da Classe:

Para criar uma classe em Java, utiliza-se essa sintaxe:

Sintaxe:
        
        public class <nome_classe>{
            [bloco_código]

        }

Exemplo prático de criação de carro: 

```java
// Criação da classe Carro
public class Carro {
    String modelo;
    int ano;  // Esses são atributos

    // Métodos (comportamentos do carro)
    public void acelerar() {
        System.out.println("Acelerando o carro de modelo " + modelo + "!!!");
    }

    public void desacelerar() {
        System.out.println("Desacelerando o carro " + modelo + "!!!");
    }

    public void mostrarDetalhes() {
        System.out.println("Modelo: " + modelo + ", Ano: " + ano);
    }
}

// Classe principal (Main)
public class Main {
    public static void main(String[] args) {
        // Criando um objeto da classe Carro
        Carro carro1 = new Carro();
        Carro carro2 = new Carro();
        
        

        // Atribuindo valores aos atributos
        carro1.modelo = "Toyota";
        carro1.ano = 2004;
        
        carro2.modelo = "Honda";
        carro2.ano = 2008;
        
        //Acessando os valores do objeto 
        System.out.println(carro1.modelo);
        System.out.println(carro1.ano);

        System.out.println(carro2.modelo);
        System.out.println(carro2.ano);

        // Chamando os métodos
        carro1.acelerar();
        carro1.desacelerar();
        carro1.mostrarDetalhes();
    }
}
```
Esse código é uma base da criação de classes e objeto, agora vamos construir um metódo de inicialização que é construtores
que é uma forma fácil de inicializar os valores

### Metódo Construtor:

É um method que inicializa os atributos no momento que criamos o objeto, sintaxe básica:

        public class <Nome_classe>{
            
        Public <nome_classe>(parâmetro_Atributos)
            this.parâmetro = parâmetro;
        }

#### Palavra-chave: THIS
O <strong>This</strong> é uma forma de diferenciar entre atributos e variável, que podemos dizer que ESTA variável é 
um atributo desse objeto, que mais lá para frente, iremos entender o encapsulamento

Então, utilizando o mesmo código, como seria o uso de construtores?

````java
    public class Carro{
        String modelo;
        int ano;
        
        public Carro(String modelo,int ano){    //Metódo construtor
            this.modelo = modelo;
            this.ano = ano;
        }
        
        void acelerar(){
            System.out.println("Acelerando o carro de modelo "+ modelo + "!!!");
        }
        void desacelerar(){
            System.out.println("Acelerando o carro de modelo ");
        }
        void mostarDetalhes(){
            System.out.println("Modelo: " + modelo +", Ano: " + ano);
        }
}
public class Main{
    public static void main(String[] args) {
        
        Carro carro1 = new Carro("Toyota",2004); //Criação de objeto com inicialização do construtor
        Carro carro2 = new Carro("Honda",2008);
        
        carro1.acelerar();
        carro1.desacelerar();
        carro1.mostarDetalhes();
          
    }
}
````

Uma forma bem fácil, mas percebe-se que, qualquer classe pode modificar os atributos diretamente? podendo colocar os 
valores inválidos

Então, é preciso ter alguma forma de ter um bloqueio com isso, por isso que entraremos em ENCAPSULAMENTO

## Encapsulamento 🔒

É um dos princípios fundamentais do POO. Ele serve para proteger os dados de um objeto e controlar o acesso a esses dados,
garantindo que as alterações seja segura
                        
O encapsulamento é feito usando modificadores de acesso (*private*, *public*, *protected*) para definir quem pode acessar
os atributos e métodos de uma classe

<li>Private --> Somente a classe própria tem acesso</li>
<li>Protected --> Somente a classe própria e subclasses(Classes filhas) tem acesso </li>
<li>Public --> qualquer classe tem acesso </li>

Ou seja, imagine como um cofre, você não pode acessar diretamente o que está dentro, então não há como modificar os 
atributos na outras classes, então como podemos acessar as classes? utilizando esses 2 metódos mais utilizado: SETTER e 
GETTER, que são meio de controle de uma forma segura

Utilizando o mesmo código criado acima, exemplo:

````java
    public class Carro{
            private String modelo; //Usaremos encapsulamento private, ou seja, a alteração desses atributos só podem ser
            private int ano;      // feitas dentro dessa classe Carro
            
            public Carro(String modelo,int ano){    //Metódo construtor
                this.modelo = modelo;
                this.ano = ano;
                System.out.println("Objeto criado!!!");
            }
            
            void acelerar(){
                System.out.println("Acelerando o carro de modelo "+ modelo + "!!!");
            }
            void desacelerar(){
                System.out.println("Acelerando o carro de modelo ");
            }
            void mostarDetalhes(){
                System.out.println("Modelo: " + modelo +", Ano: " + ano);
            }
    }
    public class Main{
        public static void main(String[] args) {
            
            Carro carro1 = new Carro("Toyota",2004); //Criação de objeto com inicialização do construtor
            Carro carro2 = new Carro("Honda",2008);

            System.out.println(carro1.modelo);
            System.out.println(carro1.ano); // Essa parte do código vai dar erro, pois está como privado, não tem como acessar e modificar
            
            carro1.acelerar();
            carro1.desacelerar();
            carro1.mostarDetalhes();
              
        }
    }
````

Então, como fazemos as alterações? Já que iremos utilizar o private ou protected maior parte dos casos, com isso,
usaremos metódo SETTER e GETTER

### Metódo SETTER e GETTER

Setter -> é um metódo onde insere o atributo ou modifica de uma forma segura <br>
Getter -> É um metódo onde pega os valores do atributos

````java
    public class Carro{
            private String modelo; //Usaremos encapsulamento private, ou seja, a alteração desses atributos só podem ser
            private int ano;      // feitas dentro dessa classe Carro
            
            public Carro(String modelo,int ano){    //Metódo construtor
                this.modelo = modelo;
                this.ano = ano;
            }
            
            //Criando métodos SETTERS e GETTERS de Modelo
            public void setModelo(String modelo){
                this.modelo = modelo;
            }
            
            public String getModelo(){
                return this.modelo;
            }
            // Criando métodos SETTERS e GETTERS de ano
            public void setAno(int ano){
                this.ano = ano;
            }
            public int getAno(){
                return this.ano;
            }
            
            void acelerar(){
                System.out.println("Acelerando o carro de modelo "+ modelo + "!!!");
            }
            void desacelerar(){
                System.out.println("Acelerando o carro de modelo ");
            }
            void mostarDetalhes(){
                System.out.println("Modelo: " + modelo +", Ano: " + ano);
            }
    }
    public class Main{
        public static void main(String[] args) {
            
            Carro carro1 = new Carro("Toyota",2004); //Criação de objeto com inicialização do construtor
            Carro carro2 = new Carro("Honda",2008);

             System.out.println("Ano do carro1: " + carro1); 
             carro1.setAno(2002); // Utilizando metódo set e alterando de 2004 para 2002
             System.out.println("Alterado para esse ano o carro 1: " + carro1.getAno()); //Utilizando a saída, que mostrará o 2002
            
            carro1.acelerar();
            carro1.desacelerar();
            carro1.mostarDetalhes();
              
        }
    }
````

## Interface

É um contrato que define quais métodos uma classe deve implementar, sem fornecer a implementação desses métodos
É como um modelo que especifica o que uma classe deve-se fazer, é definida como um tipo abstrato usado para especificar
o comportamento de uma classe. 

<li>Define métodos, mas não implementa, (Ou seja, é somente nome do método)</li>
<li>Uma classe pode implementar várias interfaces</li>
<li>Todos os métodos são públicos e abstrato por padrão</li>
<li>Qualquer classe que implementa uma interface é obrigada a implementar um conjunto espécifico de método</li>


Ou seja, ela especifica o comportamento que uma classe deve exibir, mas não as especificidades de como ela deve-se ser 
implementada, literalmente é o PROTÓTIPO em C

Sintaxe:

        inteface{
        // somente assinatura de métodos (são definidos como abstrato de forma padrão)
        }

Ou seja, vamos utilizar o exemplo de veículo, agora não vamos usar somente classe carro, vamos criar +1
classe de bicicleta, pense, qual é uma ação que os 2 tem em comum?

Métodos de acelerar() e freiar(), os 2 tem isso em comum, então vamos criar uma interface com essa assinatura, mas não
tendo ação!!!

`````java
interface Movimento{
    String acelerar();
    String freiar();  //É como se fosse PROTOTIPO em C
}
public class Carro implements Movimento{
    @Override
    void acelerar(){
        System.out.println("Acelerando o carro mais rápido ");
    }
    @Override
    void freiar(){
        System.out.println("Desacelerando o carro!!!"); // Pegando somente os métodos
    }
    void mostarDetalhes(){
        System.out.println("Modelo: " + modelo +", Ano: " + ano);
    }
}
public class Bicicleta implements Movimento{
    @Override
    void acelerar(){
        System.out.println("Pedalando mais rápido a bicicleta!!!");
    }
    @Override
    void freiar(){
        System.out.println("Desacelerando a bicicleta");
    }
}

public class Main{
    public static void main(String[] args) {
        
        Carro carro1 =  new Carro();
        Bicicleta bicicleta1 = new Bicicleta(); //Criação dos objetos
        
        carro1.acelerar(); //A saída vai ser "Acelerando o carro mais rápido"
        bicicleta1.acelerar(); // A saída vai ser "Pedalando mais rápido a bicicleta!!!"
    }
}
``````

Percebe-se que os 2 literalmente, as frases mudam conforme a classe? Isso se chama POLIMORFISMO, pois eles tem o 
mesmo nome dos methods, mas eles literalmente mudam conforme a classe, isso iremos ver mais tarde


### Vantagens do uso de encapsulamento:
<ol>
<li>Ocultação de Dados: é uma maneira de restringir o acesso do nossos membros de dados ocultando os detalhes da 
implementação</li>
<li>Maior Flexibilidade: Podemos tornar as variáeis da classe somente leitura ou somente gravação, dependendo da situação</li>
<li>Reutilização: O encapsulamento também melhora a reutilização e é fácil de alterar conforme novos requisitos</li>
<li>Testar código é fácil: o código é faácil de testar para testes unitários</li>
</ol>

### Principal benéficio:

É a sua capacidade de proteger o estado interno de um objeto de modificação ou acesso externo. É uma maneira de esconder
os detalhes de implementação de uma classe de acesso externo e expor apenas uma interface pública que pode ser usada para
interagir com a classe. Ou seja é fornecer uma maneira de controlar e gerenciar o estado e comportamento de um objeto e
também protegeê-lo de modificação e acesso não autorizado ao mesmo tempo.


````java

class Pessoa{
    private String nome;
    private int idade;
    
    public void setNome(String nome){
        this.nome = nome;
    }
    public String getNome(){
        return this.nome;
    }
    public void setIdade(int idade){
        this.idade = idade;
    }
    public int getIdade(){
        return this.idade;
    }
}

class Main{
    public static void main(String[] args) {
        Pessoa p = new Pessoa();
        
        p.setNome("Carlos");
        p.setIdade(21);

        System.out.println("Meu nome é: " + p.getNome());
        System.out.println("Minha idade é: " + p.getIdade());
    }
}
````




