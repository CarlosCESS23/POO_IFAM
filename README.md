# POO_IFAM
## Construtores

<li>O Construtor é responsável por iniciar o objeto imediatamente após sua criação</li>
<li>O construtor tem o mesmo nome da classe</li>
<li>O Construtor pode ser iniciado sem ou com parâmetro</li>

## Exercicio 1 : Faça uma classe Retagunlo que atenda:

<h3>
    <ol>
        <li>Atributos: Largura,Altura,Comprimento</li>
        <li>Metodo: Area, volume, setters e getters</li>
        <li>Crie o objeto retangulo e efetue o teste</li>
    </ol>
</h3>

`````java
package Exercicio.Retang;

public class Retangulo {
    private float altura,largura,comprimento;

    public Retangulo(float altura, float largura, float comprimento){
        this.altura = altura;
        this.largura = largura;
        this.comprimento = comprimento;
        System.out.println("Retangulo criado!!!");
    }
    public String calcularArea(){
        float area = largura*altura;
        String dados = "O Valor da área é: " + area;
        return dados;
    }
    public String calcularVolume(){
        float volume = largura * altura * comprimento;
        String dados = "O Valor do volume desse retangulo é: " + volume;

        return dados;
    }
    public float getAltura(){
        return this.altura;
    }
    public float getComprimento(){
        return this.comprimento;
    }
    public void setlargura(float largura){
        this.largura = largura;
    }
    public void setComprimento(float comprimento) {
        this.comprimento = comprimento;
    }

    public void setAltura(float altura) {
        this.altura = altura;
    }
}

class TesteRetangulo{
    public static void main(String[] args) {
        Retangulo r1 = new Retangulo(6,8,9);
        System.out.println(r1.calcularArea());

        System.out.println(r1.getComprimento());
    }
}

``````


## Exercicio 2 : Faça uma classe ContaCorrente que atenda:

<h3>
<ol>
<li>Atributos: Nome do Corretista,Número de Conta, Saldo de Conta</li>
<li>Que tenha classe construtora</li>
<li>Metódos: Sacar, Depositar,Consultar</li>
</ol>

</h3>

````java
public class ContaCorrente {
    private String corretista;
    private int noConta;
    private int saldoConta;

    public ContaCorrente(String nome,int nconta){
        this.corretista = nome;
        this.noConta = nconta;
    }
    public void depositar(int valor){
        System.out.println("Saldo antigo: " + saldoConta);
        saldoConta += valor;
        System.out.println("Valor atual: " + saldoConta);
    }
    public int getValor(){
        return this.saldoConta;
    }
    public void sacar(int valor){
        if(saldoConta<valor) {
            System.out.println("Valor inserido abaixo do teu saldo");
            return;
        }
        System.out.println("Valor que você tem antes de sacar: " +saldoConta);
        saldoConta -=valor;
        System.out.println("Valor que você tem depois que sacou\nObrigado!!!");
    }

}
````

# Encapsulamento

<li>Public -> Pode acessar fora da classe</li>
<li>Private -> Somente tem acesso na própria classe</li>
<li>Protected -> Somente tem acesso é a própria classe ou filha</li>
