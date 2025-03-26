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

## Exercicio 3: FAça uma classe caixa com aos atributos, largura, altura e profundidade. Faça sobrecarga de métodos e construtores que atendam estas chamadas
<h3>
    <ol>
        <li>Construtores com 3 assinatura diferente</li>
        <li>Metódos com 3 assinaturas diferente</li>
    </ol>
</h3>

````java
public class Caixa {
    private double largura,altura,profundidade;

    public Caixa(double x){
        this.largura = x;
        this.altura = x;
        this.profundidade = x;
    }
    public Caixa(){
        this.largura = 0;
        this.altura = 0;
        this.profundidade = 0;
    }
    public Caixa(double x,double y, double z){
        this.largura = x;
        this.profundidade = y;
        this.altura = z;
    }

    public double volume(){
        double volume = largura * altura * profundidade;
        return volume;
    }
    public double volume(double x){
        this.largura = this.profundidade = this.altura = x;
        double volume = this.largura * this.profundidade * this.altura;
            if(volume == (largura * altura * profundidade)){
                System.out.println("O x é igual a multiplicação de largura,altura e profundidade");
                return volume;
            }
        System.out.println("O valor de x não é igual a multiplicação de largura, altura e profundidade");
            return volume;
    }
    public double volume(double x,double y, double z){
        this.largura = x;
        this.altura = y;
        this.profundidade =z;
        double volume = largura * altura * profundidade;

        System.out.println("O valor do volume da caixa é: ");
        return volume;
    }
}
class TesteCaixa {
    public static void main(String[] args) {
        Caixa c1 = new Caixa();
        Caixa c2 = new Caixa(12.3);
        Caixa c3 = new Caixa(9.9,2.2,5.3);

        System.out.println(c2.volume());
        System.out.println(c2.volume(12.3));
        System.out.println(c2.volume(3.2,3.2,4.3));;

    }
}
````

# Encapsulamento

<li>Public -> Pode acessar fora da classe</li>
<li>Private -> Somente tem acesso na própria classe</li>
<li>Protected -> Somente tem acesso é a própria classe ou filha</li>
