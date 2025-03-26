# POO_IFAM
## Construtores

<li>O Construtor é responsável por iniciar o objeto imediatamente após sua criação</li>
<li>O construtor tem o mesmo nome da classe</li>
<li>O Construtor pode ser iniciado sem ou com parâmetro</li>

## Exercicio 1 : Faça uma classe ContaCorrente que atenda:

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
