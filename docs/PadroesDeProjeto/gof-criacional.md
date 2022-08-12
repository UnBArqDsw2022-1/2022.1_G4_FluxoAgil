# GOF - Factory Method

## Histórico de versões

| Data       | Versão | Descrição            | Autor(a)                                          | Revisor(a) |
| ---------- | ------ | -------------------- | ------------------------------------------------- | ---------- |
| 10/08/2022 | 1.0    | Criação do documento | [Matheus Pinheiro](https://github.com/matheuscvp) |            |
|            |        |                      |                                                   |            |

## Introdução

Padrões GoF são todos aqueles que propõem soluções para problemas recorrentes no desenvolvimento de software utilizando a progamação orientada a objetos. Os padrões criacionais utilizam da abstração do processo de instanciação, fazendo com que um sistema tenha independencia na criação de objetos.

## Metodologia

Para a escolha dos padrões Gof criacionais, durante a planning, a equipe se dividiu para que cada individuo ficar com ao menos um padrão sendo o mesmo Gof ou GRASP, logo a escolha ficaria a cargo do encarregado do artefato. Neste artefato em questão ficaram responsáveis os alunos, Matheus Pinheiro e Matheus Maia.

## Participantes

- [Mateus Maia](https://github.com/mateusmaiamaia)
- [Matheus Pinheiro](https://github.com/matheuscvp)

## GoF's Criacionais

### Factory Method

O <b>Factory Method</b> é um padrão criacional, onde uma interface será fornecida para a criação de objetos em uma superclasse, mas permite que subclasses alterem o tipo de objetos que serão criados.

```java
// Product
abstract class Plan{
    protected double rate;

    abstract void getRate();

    public void calculateBill(int units){
        System.out.println("Bill: " + units * rate);
    }
}

// Concrete Product
class DomesticPlan extends Plan{
    public void getRate(){
        rate = 3.50;
    }
}

class CommercialPlan extends Plan{
    public void getRate(){
        rate = 7.50;
    }
}

class InstitutionalPlan extends Plan{
    public void getRate(){
        rate = 5.50;
    }
}

// Creator
class PlanFactory{
    public static Plan getPlan(String planType){
        switch(planType.toLowerCase()){
            case "domestic":
                return new DomesticPlan();
            case "commercial":
                return new CommercialPlan();
            case "institutional":
                return new InstitutionalPlan();
            default:
                return null;
        }
    }
}

class GenerateBill{
    public static void main(String[] args){
        Plan plan = PlanFactory.getPlan("domestic");

        plan.getRate();

        plan.calculateBill(100);
    }
}
```

Como exemplificado acima a classe "Plan" irá declarar os métodos getRate e calculateBill, que serão implementados nas subclasses, com suas respectivas diferenças.

### Abstract Factory

O <b>Abstract Factory</b> é um padrão criacional que permite que você produza famílias de objetos relacionados sem ter que especificar suas classes concretas.

```java
// Abstract Product
interface Bank {
    String getBankName();
}

// Concrete Product
class ItauBank implements Bank {
    private final String bankName;

    public ItauBank() {
        bankName = "Itau";
    }

    public String getBankName() {
        return bankName;
    }
}

class BradescoBank implements Bank {
    private final String bankName;

    public BradescoBank() {
        bankName = "Bradesco";
    }

    public String getBankName() {
        return bankName;
    }
}

// Abstract Product 
abstract class Loan {
    protected double rate;
    abstract void setInterestRate(double rate);
    public void calculateLoanPayment(double loanAmount, int years) {
        double EMI;
        int n = years * 12;

        rate = rate /1200;

        EMI = ((rate*Math.pow((1+rate), n))/((Math.pow((1+rate), n))-1))*loanAmount;

        System.out.println("EMI: " + EMI);
    }
}

// Concrete Product
class HomeLoan extends Loan {
    public void setInterestRate(double rate) {
        this.rate = rate;
    }
}

class CarLoan extends Loan {
    public void setInterestRate(double rate) {
        this.rate = rate;
    }
}

// Abstract Factory
interface AbstractFactory {
    public abstract Bank getBank(String bankName);
    public abstract Loan getLoan(String loanType);
}

// Concrete Factory
class BankFactory implements AbstractFactory {
    public Bank getBank(String bankName) {
        switch(bankName.toLowerCase()) {
            case "itau":
                return new ItauBank();
            case "bradesco":
                return new BradescoBank();
            default:
                return null;
        }
    }

    public Loan getLoan(String loanType) {
        return null;
    }
}

class LoanFactory implements AbstractFactory {
    public Bank getBank(String bankName) {
        return null;
    }

    public Loan getLoan(String loanType) {
        switch(loanType.toLowerCase()) {
            case "home":
                return new HomeLoan();
            case "car":
                return new CarLoan();
            default:
                return null;
        }
    }
}

class FactoryCreator {
    public static AbstractFactory getFactory(String factoryType) {
        switch(factoryType.toLowerCase()) {
            case "bank":
                return new BankFactory();
            case "loan":
                return new LoanFactory();
            default:
                return null;
        }
    }
}

class GenerateBill {
    public static void main(String args[])throws IOException {
        
        const String bankName = "itau";
        const String loanType = "home";
        const double loanAmount = 100000;
        const int years = 10;
        const double rate = 3.5;

        AbstractFactory bankFactory = FactoryCreator.getFactory("Bank");
        Bank bank = bankFactory.getBank(bankName);


        AbstractFactory loanFactory = FactoryCreator.getFactory("Loan");
        Loan loan = loanFactory.getLoan(loanName);
        loan.getInterestRate(rate);

        // Calculate the EMI
        loan.calculateLoanPayment(loanAmount,years);
  }
}
```

Como exemplificado acima a classe "AbstractFactory" irá ser a responsável por criar as fábricas de Loan e Bank, onde cada terá a responsabilidade de criar os objetos solicitados.

## Referências

Java T point. Disponível em <https://www.javatpoint.com>. Acesso em 10 de Agosto de 2022.

Refactoring Guru. Disponível em <https://refactoring.guru/design-patterns>. Acesso em 10 de Agosto de 2022.
