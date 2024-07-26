O ISP diz que interfaces específicas são melhores do que uma única interface de propósito geral. A interface funciona como um contrato: nós definimos o comportamento da interface na forma de diferentes métodos que ela possui. Cada classe que deseja compartilhar o comportamento dessa interface precisa implementar os métodos dela. 

Por exemplo:
![[isp.png]]
Na situação ilustrada, há vários Tasks que usam as operações de OPS, vamos supor que a Task1 use apenas a op1, a Task2 use apenas a op2 e a Task3 use apenas a op3. Essa dependência significa que uma mudança no código-fonte em qualquer método forçará qualquer Task, mesmo que não esteja usando a operação, a ser reimplantada. 

Esse problema pode ser resolvido com a ISP:

![[isp2.png]]

Assim cada classe dependerá de sua interface específica, mas não dependerá de OPS.

Depender de algo que contém itens desnecessários pode causar problemas inesperados.

