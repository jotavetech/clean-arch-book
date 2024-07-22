
**POO é uma mistura de encapsulamento, herança e polimorfismo.**

#### Encapsulamento

É um princípio de design de código, que nos orienta a esconder as funcionalidades do nosso código dentro de pequenos métodos ou funções.

Nos permite estabelecer um limite em torno de um conjunto coeso de dados e funções, fora desse limite, os dados estão ocultos e apenas algumas funções são conhecidas. 

Foram incluídas as palavra-chave public, private e protected para lidar com a visibilidade das propriedades e métodos das classes. 

Impede que dados sejam acessados sem nenhum tipo de verificação ou permissão.

![[encapsulamento.png]]



#### Herança

A herança é a redeclaração de um grupo de variáveis e funções dentro de um escopo fechado. 

Na herança temos a **superclasse***, que concede as características para outras classes, e a **subclasse**, que herda as características da superclasse, implementando funções únicas e específicas. 

![[heranca.jpg]]
#### Polimorfismo

O polimorfismo é um mecanismo por meio do qual selecionamos as funcionalidades utilizadas de forma dinâmica por um programa ao decorrer da sua execução. Assim os mesmos atributos e objetos podem ser utilizados em objetos distintos porém com suas implementações lógicas diferentes. 

Exemplo, as subclasses Diretor, Vendedor e Funcionaria, todas vem da superclasse pessoa, que possuí um método ```Viajar()```, mas o comportamento desse método muda de acordo com o tipo de pessoa. 

Nesse exemplo, o diretor viaja para fazer parcerias, o vendedor viaja para fazer vendas e o funcionário viaja para fazer férias. 

![[polimorfismo.jpg]]

#### Inversão de dependência

Definições:

1. Módulos de alto nível não devem depender de módulos de baixo nível e ambos devem depender de abstrações.
2. Abstrações não devem depender de detalhes, mas detalhes devem depender de abstrações.

A camada de domínio da sua aplicação não deveria se importar com a maneira que um dado é persistido no banco de dados, e o inverso também, o banco de dados possuí dados, não importa como ou quem os utiliza. 

Depender de abstrações assegura o princípio de responsabilidade única: permite que classes dependam menos umas das outras. 

Com a ID buscamos simplificar os componentes que formam nosso sistema, fazendo com que eles saibam o mínimo possível sobre outros componentes. 

![[dependencyinversion.png]]

