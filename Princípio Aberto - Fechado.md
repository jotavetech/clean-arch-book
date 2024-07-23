Diz o seguinte:

_Um artefato de software deve ser aberto para extensão, mas fechado para modificação._

O comportamento  de um artefato de software deve ser extensível sem que isso modifique esse artefato.

Quando extensões simples nos requisitos forçam mudanças massivas no software, os arquitetos desse sistema de software estão em meio a um fracasso espetacular. 

#### Experimento Mental

Imagine que você trabalha em um sistema que exibe um resumo financeiro em uma página web, os dados da página são roláveis, e os números negativos aparecem em vermelho.

Mas agora pedem pra você fazer uma mudança no sistema, você terá que mudar como os dados são apresentados e transformar em um relatório. Agora é necessário escrever um código novo, mas quando o código antigo teria que mudar? Zero seria o ideal.

Um exemplo: 
![[open-closed.jpg]]

A classe ```Calculator``` é estendida com seus métodos, assim qualquer mudança nas subclasses de calculadora científica ou de negócios não deve mudar o comportamento da superclasse. 

#### Conclusão

Seu objetivo é fazer com que o sistema seja fácil de estender sem que a mudança cause um alto impacto. Assim, particionamos o sistema em componentes e organizamos esses componentes em uma hierarquia de dependências que proteja os componentes de nível mais alto das mudanças em componentes de nível mais baixo.
