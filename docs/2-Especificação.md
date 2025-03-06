# Especificações do Projeto

## Documentação de Contexto

Este projeto visa apresentar uma solução para melhorar a comunicação e gestão de projetos de construção, focando especialmente no planejamento e orçamento de materiais. A especificação foi desenvolvida a partir de uma análise detalhada das necessidades dos usuários, considerando personas, histórias de usuários, requisitos funcionais e não funcionais, e restrições que guiam o desenvolvimento do sistema.

## Definição do Problema

O **"Sua Obra Aqui"** surge para enfrentar os desafios comuns de quem precisa gerenciar e controlar a compra de materiais de construção de forma precisa e eficiente. Usuários como Lucas e Kayky têm dificuldades em planejar e orçar suas construções, e Diogo precisa de uma forma prática de gerenciar o cadastro de produtos. O objetivo do projeto é simplificar esses processos, reduzindo custos e otimizando o tempo, oferecendo uma interface intuitiva e eficiente.

## Ideia de Solução

A solução proposta é um software que permite o planejamento e orçamento de obras de forma automatizada e eficiente. O sistema inclui funcionalidades para cadastro, consulta e gestão de materiais, bem como ferramentas para comparar preços e visualizar alternativas sustentáveis. Com uma interface acessível, o software busca proporcionar uma experiência agradável e simplificada, ajudando profissionais a gerenciar dados de produtos e gerar relatórios para melhor controle do projeto.

## Técnicas e Ferramentas Utilizadas

A especificação do projeto foi elaborada com base nas seguintes técnicas e ferramentas:

1. **Diagrama de Personas:** Para identificar as principais características e necessidades dos usuários.
2. **Histórias de Usuário:** Para definir funcionalidades essenciais a partir da perspectiva do usuário.
3. **Requisitos Funcionais e Não Funcionais:** Para estabelecer as funcionalidades específicas e características técnicas do sistema.
4. **Técnicas de Priorização de Requisitos:** Para organizar a implementação das funcionalidades com base em importância e urgência.

Esses elementos ajudarão a garantir que a solução final atenda às expectativas dos usuários e resolva os problemas identificados de maneira eficaz.


## Personas

### Primeira Persona

Lucas Chiodi
Idade: 24 anos
Profissão: Engenheiro de software

História e Objetivos: Lucas Chiodi é um engenheiro de software recém-formado, com cinco anos de experiência no mercado e muitos planos para o futuro. Aos 24 anos, ele decidiu investir na realização de um antigo sonho: construir sua própria casa. Casado há dois anos, Lucas quer estruturar uma base sólida para sua família, criando um lar aconchegante e personalizado. Com a rotina de trabalho e a vontade de manter os custos sob controle, ele busca uma maneira prática de gerenciar a compra de materiais de construção.

Lucas está em busca de uma empresa que ofereça um software para facilitar o planejamento e orçamento de tudo o que precisa. Ele valoriza a organização e quer uma plataforma que o ajude a encontrar fornecedores confiáveis e comparar preços, para que o projeto de construção do seu lar se torne realidade de forma eficiente e acessível.
### Segunda Persona

Kayky Almeida
Idade: 29 anos
Profissão: Militar

História e Objetivos: Kayky é um Militar do Exército que, após anos mudando de residências devido ao seu trabalho, decidiu finalmente investir em sua própria casa. Ele quer criar um lar personalizado para si e sua companheira, unindo uma estética rústica e minimalista. Como seu pai era um mestre de obras, Kayky sabe que o processo de busca e compra de materiais pode ser demorado e desafiador, então ele procura uma empresa que possa facilitar essa tarefa com um software de busca e orçamento. Seu objetivo é simplificar o processo para manter o projeto dentro do orçamento e garantir a qualidade dos materiais, sem perder o controle dos detalhes.

Necessidades: Kayky precisa de um serviço que ofereça um software intuitivo para busca e orçamento de materiais de construção. Ele valoriza a precisão e a transparência, buscando uma plataforma que ofereça alternativas sustentáveis e uma visão geral dos produtos para comparar qual será o melhor.

### Terceira Persona

Diogo Ramos
Idade: 45 anos
Profissão: Administrador de Banco de Dados

História e Objetivos: Diogo é administrador do banco de dados do projeto "Sua Obra Aqui". Uma das funções de diogo é cadastrar os novos produtos do projeto e excluir os que não serão mais utilizados. Basicamente, ele possui permissões especiais dentro do software para que possa realizar essas funções.

Necessidades: Diogo deseja que uma parte do software seja separada especialmente para o cadastro de novos produtos e exclusão dos antigos, para que consiga realizar sua função de forma automática, facilitando seu trabalho.

## Histórias de Usuários

Com base na análise das personas forma identificadas as seguintes histórias de usuários:

|     EU COMO...     |          QUERO/PRECISO ...         |                                     PARA ...                                       |
|--------------------|------------------------------------|------------------------------------------------------------------------------------|
|Lucas Chiodi        | Um software para realizar o planejamento e orçamento  da minha obra         | Planejar minha obra de forma automatizada |
|Kayky Almeida       | Um software para realizar o planejamento e orçamento  da minha obra         | Planejar minha obra de forma automatizada |
|Diogo Ramos         | Parte do software seja direcionado para manipulação e criação dos produtos  | Facilitar seu trabalho no projeto         |

Apresente aqui as histórias de usuário que são relevantes para o projeto de sua solução. As Histórias de Usuário consistem em uma ferramenta poderosa para a compreensão e elicitação dos requisitos funcionais e não funcionais da sua aplicação. Se possível, agrupe as histórias de usuário por contexto, para facilitar consultas recorrentes à essa parte do documento.

> **Links Úteis**:
> - [Histórias de usuários com exemplos e template](https://www.atlassian.com/br/agile/project-management/user-stories)
> - [Como escrever boas histórias de usuário (User Stories)](https://medium.com/vertice/como-escrever-boas-users-stories-hist%C3%B3rias-de-usu%C3%A1rios-b29c75043fac)
> - [User Stories: requisitos que humanos entendem](https://www.luiztools.com.br/post/user-stories-descricao-de-requisitos-que-humanos-entendem/)
> - [Histórias de Usuários: mais exemplos](https://www.reqview.com/doc/user-stories-example.html)
> - [9 Common User Story Mistakes](https://airfocus.com/blog/user-story-mistakes/)



## Requisitos

As tabelas que se seguem apresentam os requisitos funcionais e não funcionais que detalham o escopo do projeto. Para determinar a prioridade de requisitos, aplicar uma técnica de priorização de requisitos e detalhar como a técnica foi aplicada.

### Requisitos Funcionais

|ID    | Descrição do Requisito  | Prioridade |
|------|-----------------------------------------|----|
|RF-001| Permitir que o usuário cadastre tarefas | ALTA | 
|RF-002| Emitir um relatório de tarefas no mês   | MÉDIA |

### Requisitos não Funcionais

|ID     | Descrição do Requisito  |Prioridade |
|-------|-------------------------|----|
|RNF-001| O sistema deve ser responsivo para rodar em um dispositivos móvel | MÉDIA | 
|RNF-002| Deve processar requisições do usuário em no máximo 3s |  BAIXA | 

Com base nas Histórias de Usuário, enumere os requisitos da sua solução. Classifique esses requisitos em dois grupos:

- [Requisitos Funcionais
 (RF)](https://pt.wikipedia.org/wiki/Requisito_funcional):
 correspondem a uma funcionalidade que deve estar presente na
  plataforma (ex: cadastro de usuário).
- [Requisitos Não Funcionais
  (RNF)](https://pt.wikipedia.org/wiki/Requisito_n%C3%A3o_funcional):
  correspondem a uma característica técnica, seja de usabilidade,
  desempenho, confiabilidade, segurança ou outro (ex: suporte a
  dispositivos iOS e Android).
Lembre-se que cada requisito deve corresponder à uma e somente uma
característica alvo da sua solução. Além disso, certifique-se de que
todos os aspectos capturados nas Histórias de Usuário foram cobertos.

## Restrições

O projeto está restrito pelos itens apresentados na tabela a seguir.

|ID| Restrição                                                                                                          |
|--|--------------------------------------------------------------------------------------------------------------------|
|01| O projeto deverá ser entregue até o final do semestre                                                              |
|02| Obrigatoriamente deverá ser utilizado um banco de dados utilizando um SGBD(Não deverá ser utilizado local storage) |
|03| O projeto deve solucionar um problema comum                                                                        |
|04| O projeto deve conter no mínimo 4 processos completos                                                              |
|04| O projeto dever ter pelo menos 1 obejtivo geral e 2 objetivos específicos                                          |
