Os princípios de SOLID nos dizem como organizar as funções e estruturas de dados em classes e como essas classes devem ser interconectadas. 

Objetivo dos princípios é a criação de estruturas de software de nível médio (de módulo) que:

- Tolerem mudanças;
- Sejam fáceis de entender;
- Sejam a base dos componentes que possam ser usados em muitos sistemas de software. 

SRP: (Single Responsibility Principle)

A melhor estrutura de software deve ser altamente influenciada pela estrutura social da organização que o utiliza, de modo que cada módulo de software tenha apenas uma razão para mudar. 

OCP: (Open-Closed Principle)

Para que os sistemas de software sejam fáceis de mudar, eles devem ser projetados de modo a permitirem que o comportamento desses sistemas mude pela adição de um novo código ao invés da alteração do código já existente. 

LSP: (Liskov Substitution Principle)

Para criar sistemas de software a partir de partes intercambiáveis, essas partes devem aderir a um contrato que permite que elas sejam substituídas umas pelas outras. 

ISP: (Interface Segregation Principle)

Projetistas de softwares devem evitar depender de coisas que não usam. 

DIP: (Dependency Inversion Principle)

O código que implementa uma política de alto nível não deve depender do código que implementa detalhes de nível mais baixo. São os detalhes que devem depender das políticas. 