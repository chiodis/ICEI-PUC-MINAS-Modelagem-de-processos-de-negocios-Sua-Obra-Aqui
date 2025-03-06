## 3. Modelagem dos Processos de Negócio

### Processos Primários

Esses processos são diretamente ligados à atividade-fim do site, que é fornecer ferramentas 
para planejamento de obras e conexão entre clientes e profissionais.

#### Cadastro de Usuário

Descrição: Permite que novos usuários (clientes e profissionais de mão de obra) se cadastrem na plataforma.
Entrada: Dados pessoais do usuário, como nome, e-mail, senha e tipo de perfil (cliente ou profissional).
Saída: Usuário cadastrado com um perfil ativo no sistema.
Participantes: Clientes, profissionais de mão de obra, sistema de cadastro.
Produto de Informação: Base de usuários, perfis de clientes e profissionais.

#### Cadastro de Mão de Obra

Descrição: Profissionais podem se cadastrar na plataforma, fornecendo detalhes sobre suas especialidades e experiência.
Entrada: Informações do profissional, como especialização, experiência, certificações e avaliações anteriores (se aplicável).
Saída: Perfil profissional registrado, disponível para clientes.
Participantes: Profissionais de mão de obra, sistema de cadastro.
Produto de Informação: Perfis de mão de obra especializados.

#### Processo de Orçamento

Descrição: Ferramenta que permite ao cliente gerar orçamentos automáticos com base em dados fornecidos sobre a obra.
Entrada: Informações sobre a obra (tipo de projeto, área, materiais desejados, mão de obra necessária).
Saída: Orçamento detalhado com preços de materiais e estimativa de mão de obra.
Participantes: Clientes, sistema de orçamento, banco de dados de preços e produtos.
Produto de Informação: Orçamentos detalhados com preços de produtos e serviços.

#### Indicação de Mão de Obra Bem Avaliada

Descrição: O sistema sugere profissionais de mão de obra com boas avaliações para os clientes, com base nas notas e feedback de outros usuários.
Entrada: Avaliações de profissionais feitas por clientes.
Saída: Lista de profissionais recomendados com base em avaliações positivas.
Participantes: Clientes, sistema de recomendação, banco de dados de avaliações.
Produto de Informação: Recomendações de profissionais.

#### FAQ (Perguntas Frequentes) 

Descrição: Uma seção onde os usuários podem acessar respostas para dúvidas comuns relacionadas à obra e ao uso da plataforma.
Entrada: Perguntas recorrentes dos usuários.
Saída: Respostas automatizadas e atualizadas, acessíveis no site.
Participantes: Equipe de suporte, sistema de FAQ, usuários.
Produto de Informação: Base de conhecimento de perguntas e respostas frequentes.

### Processos Gerenciais

Esses processos garantem o monitoramento e a gestão contínua das operações da plataforma.

#### Manutenção e Atualização do Banco de Dados de Produtos e Preços
Descrição: Atualizar regularmente o banco de dados com informações sobre produtos de construção e seus preços.
Entrada: Novos preços de mercado e especificações técnicas de produtos.
Saída: Banco de dados atualizado com informações precisas e atuais de produtos.
Participantes: Equipe de atualização de dados, fornecedores, sistema de gerenciamento de banco de dados.
Produto de Informação: Lista atualizada de produtos e preços no sistema.

#### Gestão de Avaliações e Feedback de Usuários
Descrição: Coleta e gerenciamento das avaliações feitas pelos clientes sobre os profissionais cadastrados.
Entrada: Avaliações dos usuários sobre os profissionais e serviços.
Saída: Banco de dados atualizado com avaliações e feedback dos usuários.
Participantes: Clientes, sistema de avaliações, profissionais.
Produto de Informação: Dados de avaliação e feedback, relatórios de performance dos profissionais.

#### Entradas, Saídas e Participantes dos Processos. Considerações Finais:

Os processos descritos formam a base operacional do site "Sua Obra Aqui", atendendo tanto aos usuários que precisam de orientação técnica quanto aos profissionais que buscam divulgar seus serviços. Esses processos vão guiar o desenvolvimento da arquitetura de software, determinando os módulos principais, o banco de dados e o fluxo de informações.

| Processo                                           | Entrada                    | Saída                               | Participantes                        | Produto de Informação                    |
|----------------------------------------------------|----------------------------|-------------------------------------|--------------------------------------|------------------------------------------|
| Cadastro de Usuário                                | Dados pessoais do usuário  | Usuário cadastrado                 | Clientes, profissionais, sistema     | Base de usuários e perfis                |
| Cadastro de Mão de Obra                            | Informações profissionais  | Perfil profissional disponível      | Profissionais, sistema               | Perfis de mão de obra                    |
| Processo de Orçamento                              | Dados da obra              | Orçamento detalhado                | Clientes, sistema, banco de dados    | Orçamentos de obras                      |
| Indicação de Mão de Obra Bem Avaliada              | Avaliações dos usuários    | Lista de profissionais recomendados | Clientes, sistema                    | Recomendações de profissionais           |
| FAQ (Perguntas Frequentes)                         | Perguntas recorrentes      | Respostas automatizadas            | Usuários, sistema                    | Base de conhecimento                     |
| Atualização do Banco de Dados de Produtos e Preços | Novos dados de mercado     | Banco de dados atualizados         | Equipe, fornecedores, sistema        | Preços e especificações atualizados      |
| Gestão de Avaliações e Feedback                    | Avaliações dos usuários    | Banco de dados de avaliações atualizado | Clientes, sistema, profissionais | Dados de avaliação e relatórios          |



> **Links Úteis**:
> - [Modelagem de Processos AS-IS x TO-BE](https://dheka.com.br/modelagem-as-is-to-be/)
> - [20 Dicas Práticas de Modelagem de Processos](https://dheka.com.br/20-dicas-praticas-de-modelagem-de-processos/)

### 3.1. Modelagem da situação atual (Modelagem AS IS)

 No setor da construção civil, a comunicação entre clientes e profissionais de mão de obra frequentemente ocorre de forma manual e desorganizada, o que gera várias ineficiências. O processo de contratação de serviços de construção, desde a busca por profissionais até a negociação de preços, é muitas vezes informal, com falta de clareza nos contratos, orçamentos vagos e falta de padronização nas informações fornecidas. Isso gera constantes idas e vindas entre clientes e fornecedores, resultando em retrabalho, atrasos, custos adicionais e insatisfação. Além disso, o acesso a informações técnicas de produtos e serviços é muitas vezes limitado, levando a decisões mal fundamentadas por parte dos clientes, o que aumenta o risco de problemas durante a obra, como estouro de orçamento e baixa qualidade nos serviços contratados.

#### Principais Problemas:

Falta de transparência: Informações confusas sobre serviços e preços.
Orçamentos manuais: A criação de orçamentos sem base de dados atualizada e confiável leva a estimativas incorretas.
Comunicação ineficiente: Muitas vezes, não há um canal centralizado de comunicação entre cliente e profissional, o que aumenta a chance de erros e mal-entendidos.
Gestão desorganizada: O controle de fornecedores e profissionais é ineficaz, o que impede uma avaliação precisa da qualidade do serviço e leva a más experiências.

#### Solução Proposta: Automatização com a Ferramenta "Sua Obra Aqui":

A ferramenta "Sua Obra Aqui" foi concebida para resolver esses problemas ao automatizar e organizar o processo de construção, criando uma plataforma integrada que conecta clientes e profissionais de forma eficiente e transparente. A plataforma gerencia o cadastro de usuários e profissionais, permite a geração automatizada de orçamentos, centraliza avaliações de profissionais, e oferece uma base de dados com preços e especificações de produtos.

#### Soluções:

Centralização de informações: A plataforma organiza as informações dos serviços oferecidos e dos materiais disponíveis, garantindo que os usuários tenham acesso a dados claros e precisos.

Orçamentos automatizados: Com base em uma base de dados sempre atualizada, os clientes podem gerar orçamentos detalhados e precisos, eliminando o retrabalho de cálculos manuais.

Recomendação de profissionais: Através de um sistema de avaliação, os melhores profissionais são indicados para novos projetos, garantindo mais confiabilidade e satisfação dos clientes.

Comunicação integrada: A plataforma centraliza a comunicação entre clientes e profissionais, facilitando o acompanhamento das obras e reduzindo os erros por falta de alinhamento.
 
#### Limites da Solução:

Embora a ferramenta "Sua Obra Aqui" ofereça soluções práticas para muitos problemas recorrentes no setor de construção, ela possui algumas limitações:

Dependência de acesso à internet: Para aproveitar todos os recursos, os usuários precisam de conectividade constante.
Qualidade da mão de obra: Embora a plataforma ajude a encontrar profissionais, a qualidade final do trabalho ainda depende da execução do serviço, que a ferramenta em si não pode garantir.
Adaptação ao uso: Para usuários com pouca familiaridade com tecnologia, pode haver uma curva de aprendizado para utilizar a ferramenta de maneira eficaz.

#### Alinhamento com a Estratégia de Negócio:

O projeto "Sua Obra Aqui" está alinhado com o objetivo de transformar a construção civil, promovendo transparência, eficiência e inclusão. A plataforma não só resolve problemas imediatos, como também facilita o planejamento financeiro e técnico, abrindo caminho para uma experiência mais fluida e justa tanto para profissionais quanto para clientes, especialmente os de baixa renda.


### 3.2. Descrição geral da proposta (Modelagem TO BE)

Após identificar os gargalos dos modelos AS IS no setor de construção civil, a proposta de solução "Sua Obra Aqui" visa introduzir tecnologia para melhorar e organizar o processo de contratação de serviços de construção. A plataforma centraliza a comunicação entre clientes e profissionais, automatiza a criação de orçamentos com uma base de dados atualizada e confiável, e recomenda profissionais com base em avaliações, promovendo transparência, eficiência e segurança. Com esses recursos, o objetivo é eliminar as idas e saídas desnecessárias, reduzir o retrabalho, e melhorar a satisfação dos clientes ao facilitar o acesso a informações claras e padronizadas.

#### Limites da Solução : 

A eficácia da plataforma depende de conectividade constante, o que pode ser um obstáculo em áreas de acesso limitado à internet. Além disso, a qualidade do serviço final ainda depende da execução dos profissionais, algo que a tecnologia em si não pode garantir. Para usuários com pouca familiaridade digital, a adoção da plataforma pode exigir tempo e suporte.

#### Alinhamento com Estratégias e Objetivos do Negócio :

"Sua Obra Aqui" está alinhado com a estratégia de modernizar o setor de construção civil, promovendo acesso a informações, organização e transparência. Ao facilitar a comunicação e melhorar o acesso a serviços de qualidade, a plataforma busca transformar a experiência de clientes e profissionais, especialmente para aqueles de baixa renda, promovendo um setor mais inclusivo e confiável.


 




### 3.3. Modelagem dos processos

### Processo 1 - Cadastro de usuários:

#### Oportunidades de melhoria:

#### Preenchimento Automático de Dados:

Utilizar APIs para preencher automaticamente dados como endereço e nome a partir do CPF. Isso pode simplificar o processo para o usuário e reduzir o número de erros no preenchimento.

#### Validação em Tempo Real:

Implementar validação em tempo real durante o preenchimento do formulário, especialmente para CPF e telefone. Isso evita a necessidade de correção posterior.

#### Reenvio Automático de SMS:

Para casos onde o SMS não é recebido, implementar reenvio automático após um tempo definido, sem que o usuário precise solicitar o reenvio manualmente.

#### Experiência do Usuário:

Fornecer feedback claro e em tempo real sobre o status do código de verificação, com indicações visuais de erro ou sucesso, para tornar o processo mais intuitivo.

#### Segurança Adicional:

Adicionar autenticação em dois fatores (2FA) após o cadastro, ou dar a opção de habilitar 2FA para contas com mais segurança.



![PROCESSO1](https://github.com/user-attachments/assets/ebd73a3e-3eca-452a-9975-76f216faa292)

**Detalhamento do processo:**
O processo de cadastro de usuário começa quando o usuário preenche um formulário com nome, e-mail e senha. Cada campo tem suas restrições: o nome não pode ser vazio, o e-mail deve estar em um formato válido e a senha precisa ter pelo menos 8 caracteres, incluindo um número e um caractere especial. Após o envio do formulário, o sistema valida os dados. Se estiverem corretos, um código de verificação é enviado por SMS para o número fornecido. O usuário insere o código recebido para finalizar o cadastro, assegurando a precisão das informações e a segurança do acesso à conta.




**Atividade 1 - iniciar o formulário de cadastro**

|comando|destino|tipo|
| :- | :- | :- |
|preencher formulario|formulario de cadastro |default |

**Atividade 2 - Preencher o formulario**

|campo|tipo de dado|restrições** |valor default|
| :- | :- | :- | :- |
|nome|letras|somente letras ||
|email|alfanumerico|||
|senha|alfanumerico|ao menos 8 caracteres||
|confirmar senha |alfanumerico|ao menos 8 caracteres||

|Comando|Destino|tipo|
| :- | :- | :- |
|inserir os dados |validar dados|default|

**Atividade 3 – Inserir Código de Verificação:**

|campo|tipo de dado|restrições |Valor default|
| :- | :- | :- | :- |
|Inserir Código de verificação|Alfanumerico|Deve inserir o código enviado por SMS|nenhum 

|comando|destino|tipo|
| :- | :- | :- |
|enviar codigo |Validação do Código|default|




**Atividade 4 – Validação dos Dados:**

|comando|destino|tipo|
| :- | :- | :- |
|Validar Dados do Usuário|Mostrar Mensagem de Erro ou Continuar|default|

**Atividade 5 – Enviar SMS de Verificação:**

|campo|tipo de dado|restrições |Valor default ||
| :- | :- | :- | :- | :- |
|Digitar mensagem|Alfanumerico|ate 8 caracateres|||


|comando|destino|tipo|
| :- | :- | :- |
|Enviar SMS|Usuário|default |


**Atividade 6 – Validar Código SMS:**

|comando |destino|tipo|
| :- | :- | :- |
|Validar Código SMS|Reenvio ou Finalizar Cadastro|default |






**Atividade 7 – Reenvio de SMS (se necessário):**

|campo|tipo de dado|restrições |Valor default |
| :- | :- | :- | :- |
|Digitar sms novamente|Serviço|Deve reenviar o código|Nenhum||

|comando|destino|tipo|
| :- | :- | :- |
|Reenviar SMS|Inserir codigo de verificação |default|



### Processo 2 - Cadastro de produtos:

#### Oportunidades de melhorias do processo:

#### Automatização da Verificação de Dados:

Atualmente, o sistema apenas verifica os dados inseridos após o preenchimento completo do formulário. Uma melhoria seria adicionar validações automáticas em tempo real, à medida que o Administrador preenche o formulário. Isso ajudaria a evitar erros de entrada, como o preenchimento incorreto da unidade de medida ou valores de preço inadequados, de forma mais ágil.

#### Sugestões de Preenchimento Automático:
   
Se o sistema tem acesso a uma base de dados de produtos previamente cadastrados, ele poderia sugerir automaticamente informações como unidade de medida ou tipos de produtos comuns, acelerando o preenchimento do formulário.

#### Interface Mais Intuitiva:
	
O processo de preenchimento do formulário poderia ser mais eficiente ao dividir o formulário em etapas (tipo de produto, unidade de medida, preço) com uma barra de progresso, para que o Administrador saiba em que parte do processo está e o que falta preencher.

#### Integração com APIs de Cotação de Preços:
   
Para facilitar a definição de preços, o sistema poderia integrar APIs externas que forneçam referências de preços de mercado, permitindo ao Administrador definir o valor de forma mais competitiva e precisa.

#### Feedback Visual e Mensagens de Erro Claras:

Melhorar as mensagens de erro e feedback visual para o Administrador, indicando exatamente onde os erros ocorrem e fornecendo orientações claras sobre como corrigi-los. Isso reduziria o tempo gasto na correção de dados e aumentaria a eficiência.

#### Suporte a Pré-Cadastro e Edição Posterior:
	
Implementar um recurso que permita o "pré-cadastro", onde o Administrador pode salvar um rascunho de produto e finalizá-lo mais tarde. Isso seria útil caso haja necessidade de confirmar informações antes de concluir o cadastro.

#### Otimização de Performance no Banco de Dados:
	
Caso o banco de dados comece a crescer com muitos registros, a eficiência do armazenamento pode ser afetada. Implementar otimizações, como o uso de índices ou mecanismos de caching, pode melhorar a performance na etapa de armazenamento dos produtos.

#### Log de Alterações e Histórico:
	
Adicionar um registro de alterações que salve quem cadastrou ou alterou um produto, permitindo rastreabilidade e auditoria do processo, o que é especialmente importante em grandes empresas que precisam acompanhar atividades administrativas.

#### Opções de Cadastro em Massa:

Para facilitar o cadastro de múltiplos produtos, seria interessante adicionar uma opção de upload em massa via planilha (CSV, Excel). Isso seria útil em situações onde muitos produtos precisam ser cadastrados ao mesmo tempo.

#### Confirmação com Notificações:
	
O sistema poderia enviar notificações automáticas, via e-mail ou push, para o Administrador quando um produto é cadastrado com sucesso ou quando há problemas com o cadastro. Isso manteria o Administrador informado sem a necessidade de ficar verificando manualmente.


![PROCESSO2](https://github.com/user-attachments/assets/e3fa9ee5-1b5a-4703-88ca-45b7e44217b5)


**Detalhamento de Atividades:** 

O processo de cadastro de produtos começa quando um administrador inicia o formulário de cadastro. O administrador escolhe o tipo de material a ser cadastrado, define a unidade de medida apropriada, insere o preço e as demais informações, e finaliza o cadastro se todas as condições forem atendidas.

**Atividade 1 – Iniciar Formulário de Cadastro:** 



|Campo |Tipo de Dado |Restrições |Valor Default |
| - | - | - | - |
|Iniciar Formulário |Botão |Nenhuma |Não se Aplica |



|Comando |Destino |Tipo |
| - | - | - |
|Iniciar formulário |Formulário de Cadastro |Default |

**Atividade 2 – Escolher o Tipo de Material:** 



|Campo |Tipo de Dado |Restrições |Valor Default |Opções Disponíveis |
| - | - | - | - | :- |
|Tipo de material |Caixa de seleção |Deve selecionar um material entre as opções disponíveis |Nenhum |Gesso, Cimento, Areia, Brita, Telha, Piso |



|Comando |Destino |Tipo |
| - | - | - |
|Selecionar Material |Próxima etapa (unidade de medida) |default |

**Atividade 3 - Escolher a Unidade de Medida** 



|Campo |Tipo de dado |Restrições |Valor Default |Opções Disponíveis |
| - | - | - | - | :- |
|Unidade de Medida |Caixa de Seleção |Deve escolher uma unidade válida |Nenhum |Litros, Quilogramas |



|Comando |Destino |Tipo |
| - | - | - |
|Selecionar unidade |Próxima etapa (inserir preço) |default |

**Atividade 4 – Inserir o Preço** 



|Campo |Tipo de dado |Restrições |Valor default |Opções Disponíveis |
| - | - | - | - | :- |
|Preço |Caixa de Texto |Aceitar apenas números (formato moeda) |0,00 |Não se aplica |



|Comando |Destino |Tipo |
| - | - | - |
|Confirmar preço |Verificação de informações |default |

**Atividade 5 - Conferir Produto Cadastrado** 



|Campo |Tipo de Dado |Restrições |Valor default |Opções Disponíveis |
| - | - | - | - | :- |
|Conferir cadastro |Verificação automática |O sistema verifica os dados |Nenhum |Não se aplica |



|Comando |Destino |Tipo |
| - | - | - |
|Conferir cadastro |Armazenamento dos dados |default |

**Atividade 6 - Armazenar no Banco de Dados** 



|Campo |Tipo de Dado |Restrições |Valor default |Opções Disponíveis |
| - | - | - | - | :- |
|Armazenar informações |Automático |Não se aplica |Nenhum |Não se aplica |



|Comando |Destino |Tipo |
| - | - | - |
|Armazenar informações |Banco de dados |automático |

**Atividade 7 - Exibir Mensagem de Sucesso**



|Campo |Tipo de Dado |Restrições |Valor default |Opções Disponíveis |
| - | - | - | - | :- |
|Mensagem de sucesso |Texto |Não se aplica |"Cadastro concluído com sucesso!" |Não se aplic |



|Comando |Destino |Tipo |
| - | - | - |
|Exibir mensagem |Tela de confirmação |default |





### Processo 3 - Orçamento:

 #### Oportunidades de melhoria:

#### Automatizar disponibilidade:

Automatiza a verificação de disponibilidade de profissionais para que o sistema sugira automaticamente alternativas em caso de falta de profissionais.  

#### Implementação de previsão de estoque:

Implementar uma funcionalidade de previsão de estoque para evitar a necessidade de troca de materiais durante o processo.  

#### Adiciona notificações ao usuário: 
Adicionar notificações proativas para o usuário durante o processo, como atualizações de status de orçamento e estimativas de entrega.  

#### Melhorar a interface de preenchimento:
Melhorar a interface de preenchimento do formulário, facilitando a inserção de dados e reduzindo o tempo gasto pelo usuário no início do processo.  

#### Aumenta a integração entre estoque e financeiro:
Aumentar a integração entre o sistema de estoque e o financeiro, otimizando a geração de boletos e o controle de inventário.

 


![PROCESSO3](https://github.com/user-attachments/assets/395a7f04-009a-49cf-86c5-26152bcef3f4)

**Detalhamento de Atividades:** 

O processo de solicitação de orçamento inicia com o usuário clicando em "Iniciar Solicitação", que leva ao formulário. Ele preenche o nome do projeto (padrão: "Projeto Sem Nome"), tipo de obra (residencial, comercial, industrial) e área total (padrão: "0"). Após isso, insira os dados dos materiais, incluindo nome do material (padrão: "Material Genérico"), quantidade (padrão: "1"), unidade de medida (m², litros, quilos, unidades) e preço por unidade (padrão: "0,00"). O usuário verifica e adiciona materiais escolhendo da lista e confirmando a quantidade. O orçamento é detalhado com detalhes e total, permitindo ao usuário solicitar alterações ou aprovar. Na etapa de pagamento, visualize o valor do boleto e escolha um método (boleto, cartão de crédito, Pix). Por fim, o status da entrega é exibido, incluindo código do pedido e status, com a opção de atualizar e rastrear. O usuário recebe uma notificação para confirmar a coleta.

**Atividade 1 – Iniciar Solicitação de Orçamento:**

|**Elemento**|**Descrição**|
| :- | :- |
|Comando|Iniciar Solicitação (Botão)|
|Destino|<p>Formulário de Solicitação de</p><p>Orçamento</p>|
|Navegação|<p>Direciona automaticamente para a próxima etapa de preenchimento de</p><p>dados.</p>|

**Atividade 2 -Inserir Dados do Projeto:**

|**Campo**|**Tipo de Dado**|**Restrições**|**Valor Default**|<p>**Opções**</p><p>**Disponíveis**</p>|
| :- | :- | :- | :- | :- |
|Nome do Projeto|Texto|Obrigatório|"Projeto Sem Nome"|Nenhuma|
|Tipo de Obra|Caixa de Seleção|Obrigatório|"Residencial"|<p>Residencial,</p><p>Comercial, Industrial</p>|
|Descrição|Texto Longo|Opcional|"N/A"|Nenhuma|
|Área Total|Número (m²)|Obrigatório|"0"|Nenhuma|
|Navegação|<p>Após inserir os dados, o usuário pode seguir para a próxima etapa ou revisar as</p><p>informações.</p>||||


**Atividade 3 – Inserir Material e Metragem:**

|**Campo**|**Tipo de Dado**|**Restrições**|**Valor Default**|<p>**Opções**</p><p>**Disponíveis**</p>|
| :- | :- | :- | :- | :- |
|Nome do Material|Texto|Obrigatório|"Material Genérico"|Nenhuma|
|Quantidade|Número|Obrigatório|"1"|Nenhuma|
|Unidade de Medida|Caixa de Seleção|Obrigatório|"m²"|<p>m², litros, quilos,</p><p>unidades</p>|
|Preço por Unidade|Moeda|Obrigatório|"0.00"|Nenhuma|

|Navegação|<p></p><p>O sistema permite salvar e continuar para inserir mais materiais ou prosseguir para a próxima</p><p>etapa.</p>||||
| :- | :- | :- | :- | :- |





**Atividade 4 – Verificar e Adicionar Material:**

|**Campo**|<p>**Tipo de**</p><p>**Dado\***</p>|**Restrições**|**Valor Default**|<p>**Opções**</p><p>**Disponíveis**</p>|
| :- | :- | :- | :- | :- |
|Lista de Materiais|Caixa de Seleção|<p>Deve selecionar um</p><p>material</p>|"Selecionar"|<p>Materiais disponíveis no</p><p>estoque</p>|
|Quantidade|Número|Obrigatório|"1"|Nenhuma|
|<p>Verificar</p><p>Disponibilidade</p>|Botão|Nenhuma|<p>"Não</p><p>Verificado"</p>|Nenhuma|
|Navegação|<p>Após verificar, o usuário pode adicionar o material ao orçamento e seguir para a próxima</p><p>etapa.</p>||||
Comando: Verificar Disponibilidade Destino: Verificar Material no Estoque



**Atividade 5 – Aprovar ou Solicitar Alteração no Orçamento:**

|**Campo**|**Tipo de Dado**|**Restrições**|**Valor Default**|**Opções Disponíveis**|
| :- | :- | :- | :- | :- |
|Detalhes do Orçamento|Texto Longo|Visualização Apenas|"Em Análise"|Nenhuma|
|Total|Moeda|Visualização Apenas|"R$ 0,00"|Nenhuma|
|Opções de Alteração|Caixa de Seleção|Opcional|"Nenhuma"|<p>Solicitar</p><p>Mudança, Aprovar |</p>|
|Navegação|<p>O usuário pode aprovar ou solicitar mudanças antes de finalizar esta</p><p>etapa.</p>||||



**Atividade 6 – Visualizar e Efetuar Pagamento:**

|**Campo**|**Tipo de Dado**|**Restrições**|**Valor Default**|**Opções Disponíveis**|
| :- | :- | :- | :- | :- |
|Valor do Boleto|Moeda|Visualização|"R$ 0,00"|Nenhuma|
|Métodos de Pagamento|Caixa de Seleção|Obrigatório|"Boleto Bancário"|Boleto, Cartão de Crédito, Pix|
|Data de Vencimento|Data|Visualização|"+7 dias"|Nenhuma|
|Navegação|<p>O sistema permite agendar ou confirmar o pagamento para</p><p>prosseguir.</p>||||

**Atividade 7 – Visualizar Status de Entrega:**

|**Campo**|**Tipo de Dado**|**Restrições**|**Valor Default**|<p>**Opções**</p><p>**Disponíveis**</p>|
| :- | :- | :- | :- | :- |

|Código do Pedido|Texto|Obrigatório|"N/A"|Nenhuma|
| :- | :- | :- | :- | :- |
|Status da Entrega|Texto|Visualização Apenas|"Pendente"|<p>Pendente, Em Trânsito, entregue,</p><p>cancelado</p>|
|Data Estimada de Entrega|Data|Visualização Apenas|"N/A"|Nenhuma|
|Atualizar Status|Botão|Opcional|"Não Atualizado"|Nenhuma|
|Rastreamento|Link|Opcional|"Ver Detalhes"|Nenhuma|
|Navegação|<p>As atualizações no status são refletidas automaticame nte; o usuário pode acompanhar o</p><p>processo.</p>||||

**Atividade 8 -Notificar Usuário:**

|**Campo**|**Tipo de Dado**|**Restrições**|**Valor Default**|**Opções Disponíveis**|
| -: | :- | :- | :- | :- |
|Mensagem de Notificação|Texto Longo|Visualização Apenas|"Sem Notificações"|Nenhuma|
|Botão de Confirmação|Botão|Opcional|"Confirmar"|Nenhuma|
|Navegação|<p>As notificações são enviadas e confirmadas de forma fluida</p><p>pelo usuário.</p>||||




### Processo 4 - Atendimento e suporte ao cliente

#### Oportunidades de melhoria:

#### Acessar o FAQ

Implementar FAQ Dinâmico: Baseado no histórico de problemas mais comuns dos usuários, o FAQ pode ser personalizado de acordo com o perfil do cliente, exibindo as respostas mais relevantes primeiro.

#### Solicitar Suporte

Automatização da Triagem de Suporte: Implementar chatbots ou sistemas de automação para fazer uma triagem inicial das solicitações, resolvendo questões mais simples sem a necessidade de intervenção humana.

#### Analisar Situação

Análise Automatizada Assistida por Inteligência Artificial (IA): Implementar uma solução de IA que auxilie o suporte na análise da situação do cliente, identificando padrões recorrentes nos problemas relatados e sugerindo soluções com base em casos semelhantes resolvidos anteriormente. A IA também pode priorizar o problema de acordo com a urgência e impacto.

#### Reavaliar Situação

Criação de um Time de Suporte Especializado para Casos Críticos: Criar um time especializado que lida exclusivamente com casos que não foram resolvidos na primeira análise. Esse time seria composto por especialistas em diferentes áreas técnicas, capacitados para tratar problemas mais complexos.

#### Avaliação do Usuário:

Avaliação Integrada com Sugestões de Melhoria em Tempo Real: Durante a avaliação, o sistema poderia fornecer sugestões imediatas com base no feedback do cliente. Se o cliente expressar insatisfação, o sistema poderia sugerir conteúdo adicional ou conectá-lo diretamente a um agente para revisão do caso.


![PROCESSO4 JPG](https://github.com/user-attachments/assets/7baff0c4-96fa-4c39-987d-03b5e84bcc46)

#### Detalhamento das atividades

O processo de atendimento ao cliente na plataforma começa com o usuário acessando o FAQ para tentar resolver seu problema. Caso o problema não seja resolvido com as informações disponíveis no FAQ, o usuário tem a opção de solicitar suporte técnico. A solicitação é encaminhada ao time de suporte, que analisará o problema e buscará uma solução. Se o problema for resolvido, o usuário é notificado e o processo é concluído. Caso contrário, o suporte realiza uma reavaliação até que uma solução seja encontrada. Após a resolução do problema, o cliente pode avaliar o atendimento prestado.


**Atividade 1 - Acessar o FAQ**

**Descrição**: O cliente acessa a página de FAQ do site para buscar uma solução para o problema de forma autônoma.


|CAMPO|TIPO DE DADO|RESTRIÇÕES|VALOR<br>DEFAULT|
| :- | :- | :- | :- |
|Busca no FAQ|Caixa de Texto|Palavras-chave relacionadas ao problema||
|COMANDOS |DESTINO|TIPO|
| :- | :- | :- |
|BOTÃO BUSCAR|Exibe as respostas relacionadas à palavra-chave inserida|DEFAULT|





**Ação**: O sistema exibe o conteúdo relacionado à busca realizada pelo cliente.

` `**Decisão**: O cliente verifica se o problema foi resolvido. Se **sim**, o processo é concluído. Se                         **não**, o cliente continua para a próxima atividade, onde solicita suporte.

**Atividade 2 - Solicitar Suporte**

**Descrição**: Se o problema não foi resolvido pelo FAQ, o cliente tem a opção de solicitar suporte técnico preenchendo um formulário com a descrição do problema.

|CAMPO|TIPO DE DADO|RESTRIÇÕES|VALOR DEFAULT |
| :- | :- | :- | :- |
|DESCRIÇÃO DO PROBLEMA|CAIXA DE TEXTO|MÍNIMO DE 10 CARACTERES|-|
|E-MAIL DE CONTATO|CAIXA DE TEXTO|FORMATO DE -MAIL VÁLIDO|-|





|COMANDO|DESTINO|TIPO|
| :- | :- | :- |
|BOTÃO ENVIAR|Encaminhar a solicitação ao time de suporte técnico |default|



**Ação**: O cliente preenche o formulário com detalhes sobre o problema e submete ao suporte.

**Decisão**: A solicitação é encaminhada para a equipe de suporte, que dará andamento à resolução do problema.

**Atividade 3 - Analisar Situação (Suporte Técnico)**

**Descrição**: A equipe de suporte recebe a solicitação do cliente e realiza a análise do problema para identificar uma solução adequada.

|CAMPO|TIPO DE DADO|RESTRIÇÕES|VALOR DEFAULT|
| :- | :- | :- | :- |
|ID DA SOLICITAÇÃO|AUTOMÁTICO|GERADO PELO SISTEMA ||
|DESCRIÇÃO DO PROBLEMA|CAIXA DE TEXTO |FORNECIDO PELO CLIENTE||




|CAMPO|TIPO DE DADO|TIPO|
| :- | :- | :- |
|INICIAR A ANÁLISE|INICIA A INVESTIGAÇÃO DO PROBLEMA RELATADO|DEFAULT|



` `**Ação**: O suporte técnico analisa as informações fornecidas pelo cliente e tenta resolver o problema.

` `**Decisão**: Após a análise, o suporte decide se o problema foi resolvido. Se **sim**, o processo segue para a notificação do cliente. Se **não**, o problema é reavaliado.

**Atividade 4 - Reavaliar Situação**

**Descrição**: Se o problema não foi resolvido durante a primeira análise, o suporte realiza uma nova tentativa de resolução, avaliando novas possibilidades ou coletando mais informações.

|CAMPO|TIPO DE DAD0|` `RESTRIÇÕES |VALOR DEFAULT |
| :- | :- | :- | :- |
|ID DA SOLICITAÇÃO |AUTOMÁTICO|GERADO PELO SISTEMA||
|ANOTAÇÕES INTERNAS |CAIXA DE TEXTO|COMENTÁRIOS DO SUPORTE||




|COMANDOS |DESTINO |TIPO|
| :- | :- | :- |
|REAVLIAR|NOVA TENTATIVA DE RESOLVER O PROBLEMA|DEFAULT|


` `**Ação**: O suporte realiza uma nova análise do problema, revisando as anotações anteriores e buscando uma solução alternativa.

` `**Decisão**: O suporte determina se o problema foi resolvido após a reavaliação. Se **sim**, o processo continua para a notificação ao cliente. Se **não**, o suporte pode realizar novas reavaliações.



**Atividade 5 - Avaliação do Cliente**

**Descrição**: Após o suporte técnico resolver o problema, o cliente é informado e realiza uma avaliação sobre o atendimento recebido.


|CAMPO|TIPO DE DADO |RESTRIÇÕES |VALOR DEFAULT |
| :- | :- | :- | :- |
|NOTA |CAIXA DE SELEÇÃO |1 A 5 ESTRELAS ||
|COMENTÁRIO |CAIXA DE TEXTO |TEXTO OPCIONAL ||



|COMANDOS |DESTINO|TIPO|
| :- | :- | :- |
|ENVIAR AVALIAÇÃO|FINALIZA O PROCESSO DE SUPORTE E AVALIAÇÃO|DEFAULT|



**Ação**: O cliente fornece uma avaliação sobre o serviço prestado, podendo incluir comentários adicionais.

**Decisão**: O feedback do cliente é registrado e o processo de suporte é concluído.

**Atividade Final - Problema Resolvido**

**Descrição**: O suporte técnico resolve o problema do cliente e o processo de atendimento é encerrado.

|COMANDOS |DESTINO |TIPO|
| :- | :- | :- |
|CONCLUIR|FINALIZAR O ATENDIMENTO|DEFAULT|


**Ação**: O sistema registra o fechamento da solicitação de suporte e o problema é dado como resolvido, concluindo o processo.



[PROCESSO 1 - Nome do Processo](./processos/processo-1-nome-do-processo.md "Detalhamento do Processo 1.")

[PROCESSO 2 - Nome do Processo](./processos/processo-2-nome-do-processo.md "Detalhamento do Processo 2.")
