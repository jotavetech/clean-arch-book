
Defende que é melhor depender de abstrações do que de implementações.

#### Abstrações Estáveis

Em uma interface abstrata, toda mudança corresponde a uma mudança em suas implementações concretas. Por outro lado, as mudanças nas implementações concretas normalmente não requerem mudanças na interface que implementam.

- *Não se refira a classes concretas voláteis*: Refira-se a interfaces abstratas. 
- *Não derive de classes concretas voláteis:* Em linguagens estaticamente tipadas, a herança é o relacionamento de código-fonte mais forte e rígido de todos, e consequentemente deve ser usado com muito cuidado. Em linguagens dinamicamente tipadas, a herança não representa um problema muito grande, mas ainda é uma dependência. 
- *Nunca mencione o nome de algo que seja concreto e volátil.*

```java
// Abstração
public interface PaymentProcessor {
    void processPayment(double amount);
}

// Implementação concreta específica do PayPal
public class PaypalProcessor implements PaymentProcessor {
    @Override
    public void processPayment(double amount) {
        // Lógica específica do PayPal
        System.out.println("Processing payment through PayPal: " + amount);
    }
}

// Código cliente que depende da abstração PaymentProcessor
public class CheckoutService {
    private PaymentProcessor paymentProcessor;

    public CheckoutService(PaymentProcessor paymentProcessor) {
        this.paymentProcessor = paymentProcessor;
    }

    public void completeCheckout(double amount) {
        paymentProcessor.processPayment(amount);
    }
}

// Uso do CheckoutService com PaypalProcessor
public class Main {
    public static void main(String[] args) {
        PaymentProcessor paypalProcessor = new PaypalProcessor();
        CheckoutService checkoutService = new CheckoutService(paypalProcessor);
        checkoutService.completeCheckout(100.0);
    }
}
```

A classe `CheckoutService` não depende de uma implementação concreta específica, como `PaypalProcessor`. Em vez disso, `CheckoutService` depende da abstração `PaymentProcessor`, o que permite substituir `PaypalProcessor` por qualquer outra implementação de `PaymentProcessor` no futuro sem alterar o código de `CheckoutService`.


