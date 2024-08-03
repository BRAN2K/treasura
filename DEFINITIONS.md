# **Definições do projeto**

##### **Treasura**

Uma aplicação web para gerenciar a vida financeira de seus usuários.

##### **Legenda:**

- [USE], significa que o tópico em questão tem 75% de chance de ser usado
- [MAYBE], significa que o tópico em questão está sendo avaliada a chance de uso,
- [DONT?]Texto vermelho translúcido, significa que o tópico em questão tem 25% de chance de ser usado, mas ainda não é suficiente para desconsiderá-lo

## **Estrutura do Projeto**

### **1. Planejamento Inicial**

#### **Escopo**

Aplicação web para gerenciamento da vida financeira de seus usuários. A aplicação será desenvolvida com foco principal para usuários mobile e posteriormente para usuários Desktop, ou seja, utilizando o conceito mobile-first.

#### **Frentes**

Backend e Frontend

---

### **2 Arquitetura do Sistema**

#### **Separação das Frentes**

Repositório único, com pastas separadas para cada frente do projeto. Para facilitar a separação lógica dos projetos, considerar utilizar [Lerna](https://lerna.js.org/).

#### **Design Patterns**

##### **Frontend**

- **[USE] Component-Based Architecture**  
  componentes reutilizáveis
  - [what-is-component-based-architecture](https://www.mendix.com/blog/what-is-component-based-architecture/#:~:text=Component%2Dbased%20architecture%20is%20a,application%20without%20modifying%20other%20components.)
  - [react-component-architecture-for-job-interviews](https://medium.com/@yuribett/react-component-architecture-for-job-interviews-c6ad2e3ed5fc)
- **[USE] Flux/Redux**: gerenciamento de estado
  - [an-introduction-to-the-flux-architectural-pattern](https://www.freecodecamp.org/news/an-introduction-to-the-flux-architectural-pattern-674ea74775c9/)
  - [flux-and-redux](https://medium.com/@sidathasiri/flux-and-redux-f6c9560997d7)
  - [redux](https://redux.js.org/)
- **[USE] Atomic Design**: criar um design system consistente e reutilizável
  - [como-criar-componentes-react-com-uma-arquitetura-escal](https://medium.com/rd-shipit/como-criar-componentes-react-com-uma-arquitetura-escal%C3%A1vel-usando-atomic-design-74a67aaf47e0)
- **[MAYBE] Container-Presentational Pattern**: separar a lógica de negócios (containers) da lógica de apresentação (presenters). Observação: talvez não faça sentido utilizá-lo, já que o Atomic Design desempenha um papel mais moderno e que o englobe, ler o artigo do tópico do Atomic Design.
  - [container-presentational-pattern-react](https://tsh.io/blog/container-presentational-pattern-react/)
  - [container-presentational-pattern-react-3ofp](https://dev.to/deesouza/container-presentational-pattern-react-3ofp)
- **[USE] Layout Components Pattern**: helps developers organize their application’s structure and layout
  - [react-design-patterns-layout-components-pattern](https://medium.com/@vitorbritto/react-design-patterns-layout-components-pattern-455c98e0bf92)
- **[DONT?] Compound Component Pattern**: avoid prop drilling and write elegant components with implicit state sharing
  - [react-design-patterns-compound-component-pattern](https://medium.com/@vitorbritto/react-design-patterns-compound-component-pattern-ec247f491294)
- **[DONT?] Provider Pattern**: structured way of managing and passing data through your component tree
  - [react-design-patterns-provider-pattern](https://medium.com/@vitorbritto/react-design-patterns-provider-pattern-b273ba665158)

##### **Backend**

- **[MAYBE] Repository Pattern**: Para abstração das operações do banco de dados.
  - [entendendo-o-repository-pattern](https://renicius-pagotto.medium.com/entendendo-o-repository-pattern-fcdd0c36b63b)
  - [aplicando-repository-pattern-com-nodejs-typescript-e-typeorm](https://charlesodev.medium.com/aplicando-repository-pattern-com-nodejs-typescript-e-typeorm-e7d9c6253e31)
  - [generic-repository-with-typescript-and-node-js](https://medium.com/@erickwendel/generic-repository-with-typescript-and-node-js-731c10a1b98e)
- **[USE] Service Layer**: Para encapsular lógica de negócios.
  - [serviceLayer](https://martinfowler.com/eaaCatalog/serviceLayer.html)
  - [revolutionizing-software-development-unveiling-the-power-of-clean-architecture-with-typescript](https://medium.com/@deivisonisidoro_94304/revolutionizing-software-development-unveiling-the-power-of-clean-architecture-with-typescript-5ee968357d35)
  - [Build cleaner backends in TypeScript](https://youtube.com/playlist?list=PLkyPUqu7ThxYMATLWT2R5iLOj7jCOtHBH&si=APY8Eot-f9TnhwCz)
- **[USE] MVC (Model-View-Controller)**:
  - [mvc-and-restful-api-service](https://softwareengineering.stackexchange.com/questions/324730/mvc-and-restful-api-service)
  - [mvc-pattern-in-nodejs-and-express-old-but-gold](https://medium.com/@jonoyanguren/-46c21bee365a)
  - [implementation-of-mvc-rest-apis-in-expressjs](https://medium.com/analytics-vidhya/implementation-of-mvc-rest-apis-in-expressjs-c7eb6a097b9f)

#### **Diagrama de Arquitetura**

<!-- Detalhar melhor quais são esses diagramas -->

Criação de diagramas UML

#### **Estrutura de Projeto**

<!-- Aprofundar o nível técnico sobre essa definição. Talvez ela já esteja sendo definida em outros pontos do documento e pode ser removida. -->

Quero o projeto o mais organizado possível, a estrutura deve ser algo fácil de entender e também escalável para novas funcionalidades, logo o código precisa ser bem desacoplado.

—

### **3. Padrões de Código**

#### **Linters e Formatters**

- ESLint e Prettier para cada frente
- [Husky](https://typicode.github.io/husky/get-started.html) para garantir que os commits estejam necessariamente nos padrões dos linters e formatters

#### **Normas de Nomeação**

##### **Variáveis**

- Use `camelCase`
- Nomes descritivos e significativos (e.g., `userBalance` em vez de `ub`)
- Usar `UPPER_SNAKE_CASE` para constantes (e.g., `const MAX_RETRIES`)

##### **Funções**

- Use verbos para funções (e.g., `calculateTotal`, `fetchUserData`).
- Usar camelCase para funções (`function getUserName()`).

##### **Classes**

- Use PascalCase para classes e componentes (e.g., `UserProfile`, `TransactionService`).
- Nomes de classes devem ser substantivos.

#### Versionamento Semântico (SemVer)

**Major.Minor.Patch (1.0.0):**

- **Major**: Mudanças incompatíveis na API.
- **Minor**: Funcionalidades adicionadas de forma compatível.
- **Patch**: Correções de bugs compatíveis.

#### Padrão de Commits

Git + Github + [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)

---

### 4. Documentação

#### Código

**Comentários TSDoc**: Facilita a geração de documentação automática e entendimento do código.
**Swagger/OpenAPI**: Padrões para documentar APIs RESTful, facilitando a integração e uso.
**Wiki e Tutoriais**: Utilizar plataformas como Confluence ou GitHub para centralizar e organizar a documentação.

---

### 5. Frontend

#### Linguagens e Frameworks

- **Linguagem**: TypeScript
- **Frameworks/Bibliotecas**: NextJS + [MaterialUI](https://mui.com/material-ui/) + Emotion

#### Design System

Pelo fato de que usaremos MUI, esse seção não precisa de tanta atenção no momento. Quando a aplicação estiver mais madura, podemos pensar em algo.

---

### 6. Backend

#### Linguagens e Frameworks

- **Linguagem**: TypeScript (Node.js)
- **Frameworks**: Express.js

#### Autenticação e Autorização

- [NextAuth](https://next-auth.js.org/)

#### Segurança

- Validações de entrada.
- Proteção contra XSS, CSRF.
- Encriptação de dados.

---

### 7. Banco de Dados

#### Tipo

- Non-relational: [MongoDB](https://www.mongodb.com/products/platform/atlas-database)

#### Modelagem

- Diagrama ER para modelar relações entre dados.

#### ORM/ODM

- [Mongoose ODM](https://www.npmjs.com/package/mongoose)

---

### 8. CI/CD (Continuous Integration / Continuous Deployment) e Infraestrutura

- [Github Actions](https://docs.github.com/pt/actions), [Travis CI](https://www.travis-ci.com/) ou [Cloud Build](https://cloud.google.com/build?hl=pt_br) (caso os serviços fiquem hospedados no GCP) para construção das pipelines
- [Digital Ocean](https://www.digitalocean.com/), [Heroku](https://www.heroku.com/) ou [Cloud Run](https://cloud.google.com/run?hl=pt_br) para implantação da aplicação em produção e staging.
- Vou precisar que o projeto tenha 3 ambientes. Um de desenvolvimento local, um de staging (pré-produção) e por último, um de produção
- Vou precisar que o código seja pensado para ser executado nesses três ambientes (utilização de variável de ambiente para mudar comportamente do código de acordo com o ambiente)

#### Pipelines

1. Build
2. Testes Automatizados (Unitários / Integração)
3. Deploy (para QA e Produção)

---

### 9. Testes

#### Frontend

Jest com [React Testing Library](https://testing-library.com/docs/react-testing-library/intro/) para testes unitários e [MAYBE] end-to-end com [Cypress](https://www.cypress.io/).

#### Backend

[Jest](https://jestjs.io/pt-BR/docs/getting-started) para testes unitários. [Supertest](https://www.npmjs.com/package/supertest) para testes de integração.

---

### 10. Gerenciamento do Projeto

O projeto vai ser realizado por mim e outros desenvolvedores, portanto, usaremos [Jira](https://community.atlassian.com/t5/Jira-questions/Connecting-GitHub-and-Jira/qaq-p/2121715) para se organizar.

---

### 11. Ferramentas de Design:

#### Canva Pro

Ferramenta para design gráfico que pode ser útil na criação de materiais visuais para o projeto.

#### Figma

Ferramenta colaborativa para design de interfaces, excelente para prototipar a UI/UX da aplicação.

### 11. Notas extras importantes

- Motivação do projeto: Estou fazendo esse projeto a fim de satisfazer uma necessidade minha, na qual eu não encontrei uma aplicação que satisfaça minhas necessidades para gerir minha vida financeira. Além disso, vou utilizar essa aplicação como um portfólio e quem sabe se ela for pra frente, não aconteça de eu vender ou conseguir algum investidor.
