
Na programação funcional, as variáveis são inicializadas, mas nunca são modificadas. Varias linguagens funcionais não variam.

Do ponto de vista arquitetural esse é um ponto muito importante, pois todas as condições de corrida, de impasse e problemas de atualizações simultâneas vem de variáveis mutáveis. Em outras palavras, todos os problemas que enfrentamos em aplicações que exigem várias threads e processadores não podem acontecer com variáveis imutáveis. 

Imutabilidade é aplicável? Sim, se você tiver acesso a armazenamento e processamento infinito. Ela é praticável se certas concessões forem feitas.

#### Segregação de Mutabilidade

Uma das concessões mais comuns em relação à imutabilidade é segregar a aplicação em componentes mutáveis e imutáveis. Os componentes imutáveis realizam suas tarefas de forma totalmente funcional, sem variáveis mutáveis, e se comunicam com componentes não totalmente funcionais, que permitem que o estado das variáveis seja alterado. 
![[sgemutabilidade.png]]
Já que mudar o estado expõe esses componentes a todos os problemas de concorrência, é uma prática comum usar algum tipo de memória transacional para proteger as variáveis mutáveis de atualizações concorrentes e condições de corridas.

Ela simplesmente trata as variáveis na memória do mesmo jeito que um banco de dados trata registros no disco, protegendo essas variáveis com um esquema baseado em transação ou repetição. 

#### Event Sourcing

Os limites de armazenamento e poder de processamento vem rapidamente aumentando, quanto maiores forem a memória e a velocidade das nossas máquinas, menos precisaremos de um estado mutável. 

Imagine uma aplicação bancária que indica os saldos em conta do cliente, a cada transação o programa altera o saldo quando operações de deposito ou saque são executadas.

Mas agora imagine, se ao invés de armazenar o saldo, apenas as transações sejam armazenadas, e quando o cliente solicitasse apenas retornamos um calculo de tudo, esse esquema não requer variáveis mutáveis. 

Essa abordagem parece absurda, já que ao longo do tempo não íamos ter mais capacidade de armazenamento e processamento suficiente. Mas talvez esse esquema não tenha que funcionar pra sempre, podemos fazer com que essas informações só durem o tempo de vida razoável da aplicação.

Essa é a ideia por trás do _event sourcing_ que é uma estratégia para armazenar as transações mas não o estado. Quando o estado for solicitado, simplesmente aplicamos todas as transações desde o início. 

Se temos armazenamento e poder de processamento suficientes, podemos tornar nossas aplicações inteiramente imutáveis e portanto, inteiramente funcionais. 



