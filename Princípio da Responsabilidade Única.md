 Podemos descrever o SRP como:
 
 _Um módulo deve ser responsável por um, e apenas um, ator._

#### Sintomas de sua violação

##### Sintoma 1: Duplicação Acidental

![[srp1.png]]

Nessa classe ```Funcionario``` podemos observar que existe um método específico para cada ator mas eles acoplaram esses atores uns aos outros, isso pode fazer que uma ação da equipe do RH, por exemplo, prejudique algum comportamento da equipe DBA ou Contabilidade. 

##### Sintoma 2: Fusões

Imagine que as equipes de DBAs e CTO determine uma simples mudança no esquema da tabela do ```Funcionario``` na base de dados. Imagine também que a equipe de RH e COO determine a realização de uma mudança no formato do relatório de horas..

Dois desenvolvedores, provavelmente de equipes diferentes, verificam a classe e começam a fazer mudanças, no final as mudanças acabam colidindo, o resultado é uma fusão. 

#### Soluções

Uma solução para esse tipo de problema é separar os dados das funções, criar uma classe simples de ```FuncionarioData```, sem métodos, e criar novas classes com apenas o código-fonte necessário para cada função específica. 

A desvantagem dessa solução é que agora os desenvolvedores tem mais 3 outras classes para rastrear, uma forma de solucionar isso é usar o padrão ```Facade```, criando uma classe ```FuncionarioFacade``` que é responsável por iniciar e delegar as funções para as classes. 


