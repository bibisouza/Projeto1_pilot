### Histórico de versões 

| Autor | Versão | Data       | Descrição                               |
|-------|-------|------------|------------------------------------------|
| Beatriz, Paula e Pedro  | 1.0   | 27/05/2025 | Primeira versão do documento             |


### Introdução 

#### 1.1 Propósito 
O propósito deste documento é fornecer uma visão geral do aplicativo "Pilot" que funciona como uma rede social para amantes de série, detalhando seus objetivos, funcionalidades e requisitos. Ele servirá como guia para a equipe de desenvolvimento e para as partes interessadas, garantindo clareza e consenso sobre o que será entregue.

#### 1.2 Escopo
O aplicativo de rede social abrangerá:
- Fórum onde os usuários podem conversar sobre as séries;
- Registrar quais séries o usuário está assistindo;
- Registrar o episódio no qual o usuário parou de assistir;
- Avaliação de séries;
- Personalização do próprio perfil no aplicativo;
- Visualização do perfil de outros usuários

#### 1.3 Visão Geral
O documento apresenta inicialmente um panorama do projeto, descrevendo a ideia do sistema e suas principais funcionalidades. Em seguida, detalha requisitos funcionais e não funcionais, regras de negócio, além de diagramas de caso de uso e de classes. Por fim, traz a rastreabilidade dos requisitos e as considerações finais.

---

### Descrição Geral 

#### 2.1 Perspectiva do Produto
O "Pilot" é um aplicativo para aparelhos mobile que tem como objetivo facilitar que o usuário registre quais séries está assistindo, em qual episódio ele está e encontre outros usuários que têm gostos parecidos. A expectativa é que o aplicativo esteja nas principais lojas de aplicativo (App Store e Google Play) e é desejável que ele tenha uma versão web também.

#### 2.2 Funções do Produto 
1. **Registro e login**: Permite o registro e login no sistema.
2. **Séries cadastradas**: Tem uma base de dados de séries já cadastradas e informações sobre elas.
3. **Gerenciamento de Séries no perfil do usuário**: Permite marcar/desmarcar uma série como assistida ou assistindo, avaliá-la, marcá-la como favorita, adicionar uma review à ela e criar listas de séries.
4. **Gerenciamento do dados no seu perfil**: Permite que o usuário altere certos dados no seu perfil.
4. **Fórum**: Local destinado à interação com outros usuários, as conversas são divididas por tema (série ou episódio/temporada de uma série) e podem ser marcadas como spoilers.
5. **Perfil de outros usuários**: Permite que o usuário acesso o perfil de outros usuários e veja seus dados público (não sensíveis)

#### 2.3 Características dos Usuários
- **Usuário**: Pode gerenciar as séries no seu perfil, ver o perfil e seguir outros usuários, comentar em reviews de outros usuários e gerenciar os dados de seu perfil.

#### 2.4 Restrições Gerais
- O sistema deve operar em dispositivos móveis modernos e estar presente nas principais lojas de aplicativos.
- O banco de dados deve ser acessível somente por meio das funções permitidas pelo aplicativo.
- As integrações externas (se necessárias) devem seguir protocolos seguros (HTTPS/TLS).

---

### Requisitos Específicos

#### 3.1 Requisitos Funcionais 
1. **RF001 - Cadastro de usuários**: O sistema deve permitir o cadastro de novos usuários, informando nome, email e senha.
2. **RF002 - Login de usuários**: O sistema deve permitir que usuários cadastrados façam login informando email e senha.
3. **RF003 - Personalizar perfil**: O sistema deve permitir que o usuário personalize seu perfil, adicionando foto, apelido biografia.
4. **RF004 - Registro de séries na biblioteca pessoal**: O sistema deve permitir que o usuário resgistre séries em sua biblioteca pessoal, podendo definir o status da série(Assistindo, Finalizada, Abandonada, Quero Assitir).
5. **RF005 - Avaliação de séries**: O sistema deve permitir que o usuário avalie séries atrribuindo uma nota de 1 a 5 estrelas, com a opção de escrever uma resenha associada à avaliação.
6. **RF006 - Busca de séries**: O sistema deve permitir que o usuário busque séries pelo seu nome, diretor, gênero, personagens ou atores envolvidos.
7. **RF007 - Criação de listas personalizadas**: O sistema deve permitir que o usuário crie listas personalizadas de séries.
8. **RF008 - Estatísticas do usuário**: O sistema deve registrar estatísticas do perfil, como: quantidade de séries assistidas, tempo total de minutos assistidos, gêneros mais assistidos, atores mais assistidos.
9. **RF009 - Seguir ou desseguir usuários**: O sistema deve permitir que os usuários sigam e deixem de seguir outros usuários na plataforma.
10. **RF010 - Sugestão de séries**: O sistema deve sugerir séries aos usuários com base em suas estatíticas de séries assistidas, avaliações e gêneros favoritos.
11. **RF011 - Criar resenhas**: O usuário pode criar resenhas sobre episódios ou temporadas de uma série, onde ele especifica o status da série (assitindo ou assistida), a nota, a resenha escrita e as categorias (tensão, drama, romance, etc).

#### 3.2 Requisitos Não Funcionais 
1. **RNF001 - Desempenho**: O sistema deve responder às requisições em até 2 segundos em média, proporcionando uma navegação fluída.
2. **RNF002 - Segurança**: O sistema deve proteger dados sensíveis dos usuários, utilizando práticas como criptografia de senhas e conexões seguras.
3. **RNF003 - Disponibilidade**: O sistema deve ficar disponível 99% do tempo, considerando manutenções programas.
4. **RNF004 - Usabilidade**: A interface deve ser responsiva, intuitiva e acessível, funcionando em diferentes dispositivos e sistemas operacionais.
5. **RNF005 - Esacalabilidade**: O sistema deve ser capaz de suportar o crescimento contínuo do número de usuários e da quantidade de dados, sem comprometer seu desempenho.
6. **RNF006 - Manutenibilidade**: O código-fonte do sistema deve ser modular, documentado e constatemente mantido e atualizado.

#### 3.3 Regras de Negócio
1. **RN001 - Idade mìnima para cadastro**: Um usuário deve ter no mínimo 13 anos para se cadastrar no aplicativo.
2. **RN002 - Visibilidade de resenhas com spoiler**: Se uma resenha for marcada como "spoiler" pelo usuário, seu conteúdo deve ser ocultado por padrão para outros usuários até que eles explicitamente cliquem para visualizá-lo.
3. **RN003 - Assinatura premium**: A assinatura premium requer uma 
pagamento anual de X reais.
Usários com a assinatura premium terão acesso a funcionaludades exlusivas como:
    - Remoção de anúncios
    - Maior personalização no perfil
    - Estatísticas sobre o seu perfil
    - Retrospectiva anual
4. **RN004 - Registro de séries na biblioteca pessoal**: Ao registrar uma série a sua biblioteca pessoal, o usuário deve definir o status da série entre as opções disponíveis (Assistindo ou assistido).
5. **RN005 - Limite de avaliações por série**: Um usuário só pode atribuir uma única nota de avaliação (de 1 a 5 estrelas) por série. Caso o usuário queira mudar a nota, ele deve editar a avaliação existente, e a nova nota substituirá a anterior.
6. **RN006 - Sessão de notícias**: O Aplicativo possui uma sessão para que o usuário possa visualizar as notícias mais recentes sobre séries.
7. **RN007 - Informações sobre a série**: O sistema deve possuir uma tela com informações de cada uma das séries disponíveis no catálogo. A tela possui a nota da série, onde assistir ela, sinopse, a média de duração dos episódios, a sua avaliação geral, tags (drama, terror, etc), número de temporadas e episódios, título, roteirista(s) e sinopse do episódio e uma sessão com o elenco da série.
8. **RN008 - Séries favoritas no perfil**: O usuário, ao personalizar o perfil, pode escolher 3 séries para serem suas favoritas e que ficaram expostas com destaque no seu perfil.
9. **RN009 - Notificações**: O usuário receberá notificações de outros usuários, de notícias e sobre resenhas feitas no app.
10. **RN010 - Perfil de usuário**: O usuário possui um perfil com suas informações, as informações são: Nome, apelido, seguidores, seguidos, biografia, séries favoritas, recentes, watchlist e listas.
11. **RN012 - Watchlist**: O usuário possui uma whatchlist que pode ser visualizada no perfil de cada usuário.

### Modelos e Diagramas

#### 4.1 Casos de Uso

- **UC01**: Cadastrar-se no sistema
Ator: Visitante
Descrição: Permite que o usuário realize o cadastro no sistema.
Pré-condições: O usuário não pode estar autenticado no sistema.
Fluxo principal:
1. O visitante acessa a tela de cadastro;
2. Os campos obrigatórios são preenchidos: nome, e-mail e senha;
3. O sistema valida os dados;
4. O sistema cria a conta e redireciona o usuário para a tela de login ou para o sistema já autenticado.
Pós-condições: O novo usuário está cadastrado e pode fazer login.
Requisito relacionado: RF001

- **UC02**: Fazer login
Atores: Usuário, sistema
Descrição: Permite que os usuários cadastrados acessem sua conta.
Pré-condições: O usuário já deve ter uma conta registrada.
Fluxo principal:
1. O usuário acessa a tela de login;
2. São preenchidos os campos de e-mail e senha;
3. O sistema valida as credenciais;
4. O sistema autentica o usuário e o redireciona à página inicial.
Pós-condições: O usuário está autenticado e tem acesso às funcionalidades restritas.
Requisito relacionado: RF002

- **UC03**: Personalizar perfil
Atores: Usuário, sistema
Descrição: Permite que o usuário edite seu perfil, adicionando foto, apelido e biografia.
Pré-condições: O usuário deve estar autenticado.
Fluxo principal:
1. O usuário acessa as configurações de perfil;
2. Insere ou altera imagem, apelido e/ou biografia;
3. O sistema valida os dados;
4. O sistema salva as alterações.
Pós-condições: O perfil é atualizado com os novos dados.
Requisito relacionado: RF003

- **UC04**: Registrar série na biblioteca pessoal
Ator: Usuário
Descrição: Permite ao usuário adicionar uma série à sua biblioteca e definir o status (Assistindo, Finalizada, Abandonada, Quero Assistir).
Pré-condições: O usuário deve estar autenticado.
Fluxo principal:
1. O usuário busca ou encontra a série desejada;
2. Seleciona a opção "Adicionar à biblioteca";
3. Define o status da série;
4. O sistema adiciona a série à biblioteca do usuário.
Pós-condições: A série é registrada na biblioteca pessoal com o status escolhido.
Requisito relacionado: RF004

- **UC05**: Avaliar série
Ator: Usuário
Descrição: Permite ao usuário avaliar uma série com nota de 1 a 5 estrelas e escrever uma resenha.
Pré-condições: A série deve estar na biblioteca pessoal do usuário.
Fluxo principal:
1. O usuário acessa a página da série;
2. Escolhe a nota (1 a 5 estrelas);
3. Escreve uma resenha (opcional);
4. Envia a avaliação;
5. O sistema salva e exibe a avaliação no perfil do usuário e na página da série.
Pós-condições: A avaliação é registrada e associada ao perfil do usuário e à série.
Requisito relacionado: RF005

- **UC06**: Buscar séries
Ator: Usuário
Descrição: Permite buscar séries por nome, diretor, gênero, personagens ou atores.
Pré-condições: Nenhuma
Fluxo principal: 
1. O usuário acessa a barra de busca;
2. Digita um termo (nome, ator, gênero, etc);
3. O sistema retorna os resultados relevantes.
Pós-condições: As séries relacionadas ao termo buscado são exibidas.
Requisito relacionado: RF006

- **UC07**: Criar listas personalizadas
Ator: Usuário
Descrição: Permite que o usuário crie listas com séries selecionadas manualmente.
Pré-condições: O usuário deve estar autenticado.
Fluxo principal: 
1. O usuário acessa a área de listas;
2. Clica em "Criar nova lista";
3. Define título, descrição e seleciona as séries;
4. Salva a lista.
Pós-condições: Uma nova lista é adicionada ao perfil do usuário.
Requisito relacionado: RF007

- **UC08**: Visualizar estatísticas do perfil
Ator: Usuário
Descrição: Exibe estatísticas baseadas nas séries assistidas (quantidade, tempo, gênero, atores mais vistos).
Pré-condições: O usuário deve ter ao menos uma série registrada.
Fluxo principal: 
1. O usuário acessa seu perfil;
2. O sistema calcula e exibe estatísticas como:
    - Total de séries/temporadas assistidas
    - Tempo total 
    - Gêneros mais frequentes
    - Atores mais recorrentes
Pós-condições: As estatísticas são exibidas de forma visual ao usuário.
Requisito relacionado: RF008

![Diagrama De Classe](images/Casos.png)
![Diagrama De Classe05](images/UC05.png)
![Diagrama De Classe06](images/UC06.png)
![Diagrama De Classe07](images/UC07.png)
![Diagrama De Classe08](images/UC08.png)

#### 4.2 Diagrama de Classe (Definir o diagrama de pelo menos um caso de uso)
![Diagrama De Classe](images/Clae.png)

#### 4.3 Diagramas de Sequência (Definir o fluxo de pelo menos um caso de uso)

![Diagrama De Sequencia](images/DiagramasSegundaParte.jpeg)

### Rastreabilidade de Requisitos 

#### 5.1 Matriz de Rastreabilidade 

| Requisito ID | Descrição do Requisito                                        | Caso de Uso Relacionado                   | Diagrama Relacionado (Sugestão)     | Componente/Módulo do Sistema (Sugestão) | Status de Implementação | Status de Teste | Observações                                                                                                                                                                                                                                                                                                                                                                                                      |
| :----------- | :------------------------------------------------------------ | :---------------------------------------- | :---------------------------------- | :-------------------------------------- | :---------------------- | :-------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **RF001** | Cadastro de usuários: O sistema deve permitir o cadastro de novos usuários, informando nome, email e senha. | UC01: Cadastrar-se no sistema             | Diagrama de Classes (Usuário), Diagrama de Sequência (Cadastro) | Módulo de Autenticação/Usuário        | A Definir             | A Definir       | Requer validação de dados e regras de negócio como a idade mínima (RN001).                                                                                                                                                                                                                                                                                                                                      |
| **RF002** | Login de usuários: O sistema deve permitir que usuários cadastrados façam login informando email e senha. | UC02: Fazer login                         | Diagrama de Sequência (Login)       | Módulo de Autenticação                | A Definir             | A Definir       | Deve integrar com a camada de segurança para validação de credenciais.                                                                                                                                                                                                                                                                                                                                            |
| **RF003** | Personalizar perfil: O sistema deve permitir que o usuário personalize seu perfil, adicionando foto, apelido e biografia. | UC03: Personalizar perfil                 | Diagrama de Classes (Perfil do Usuário) | Módulo de Perfil/Usuário              | A Definir             | A Definir       |                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **RF004** | Registro de séries na biblioteca pessoal: O sistema deve permitir que o usuário registre séries em sua biblioteca pessoal, podendo definir o status da série (Assistindo, Finalizada, Abandonada, Quero Assistir). | UC04: Registrar série na biblioteca pessoal | Diagrama de Classes (Série, Biblioteca), Diagrama de Estado (Status da Série) | Módulo de Biblioteca/Série            | A Definir             | A Definir       | Inclui a regra de negócio RN004, que trata da atualização automática do status e registro de episódio/temporada.                                                                                                                                                                                                                                                                                                |
| **RF005** | Avaliação de séries: O sistema deve permitir que o usuário avalie séries atribuindo uma nota de 1 a 5 estrelas, com a opção de escrever uma resenha associada à avaliação. | UC05: Avaliar série                       | Diagrama de Classes (Avaliação, Resenha) | Módulo de Avaliação/Série             | A Definir             | A Definir       | Deve considerar a regra de negócio RN005 (única nota por série) e RN002 (visibilidade de spoilers).                                                                                                                                                                                                                                                                                                             |
| **RF006** | Busca de séries: O sistema deve permitir que o usuário busque séries pelo seu nome, diretor, gênero, personagens ou atores envolvidos. | UC06: Buscar séries                       | Diagrama de Classes (Série, Ator, Gênero) | Módulo de Busca/Série                 | A Definir             | A Definir       | Necessita de uma base de dados de séries bem estruturada para a busca eficiente.                                                                                                                                                                                                                                                                                                                               |
| **RF007** | Criação de listas personalizadas: O sistema deve permitir que o usuário crie listas personalizadas de séries. | UC07: Criar listas personalizadas         | Diagrama de Classes (Lista)         | Módulo de Listas                      | A Definir             | A Definir       |                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **RF008** | Estatísticas do usuário: O sistema deve registrar estatísticas do perfil, como: quantidade de séries assistidas, tempo total de minutos assistidos, gêneros mais assistidos, atores mais assistidos. | UC08: Visualizar estatísticas do perfil   | Diagrama de Atividades (Cálculo de Estatísticas) | Módulo de Estatísticas/Perfil         | A Definir             | A Definir       | Depende do registro de dados precisos na biblioteca pessoal.                                                                                                                                                                                                                                                                                                                                                   |
| **RF009** | Seguir ou desseguir usuários: O sistema deve permitir que os usuários sigam e deixem de seguir outros usuários na plataforma. | (Não detalhado nos UC fornecidos, mas implícito) | Diagrama de Classes (Seguidores)    | Módulo de Rede Social/Usuário         | A Definir             | A Definir       | Requer um Caso de Uso específico para "Seguir/Deixar de Seguir Usuário".                                                                                                                                                                                                                                                                                                                                      |
| **RF010** | Sugestão de séries: O sistema deve sugerir séries aos usuários com base em suas estatísticas de séries assistidas, avaliações e gêneros favoritos. | (Não detalhado nos UC fornecidos, mas implícito) | Diagrama de Componentes (Motor de Recomendação) | Módulo de Recomendação                | A Definir             | A Definir       | Envolve algoritmos de recomendação e processamento de dados do usuário.                                                                                                                                                                                                                                                                                                                                        |
| **RNF001** | Desempenho: O sistema deve responder às requisições em até 2 segundos em média, proporcionando uma navegação fluída. | N/A                                       | Diagrama de Implantação             | Arquitetura Geral                     | A Definir             | A Definir       | Crucial para a experiência do usuário. Impacta design de banco de dados e otimização de código.                                                                                                                                                                                                                                                                                                                    |
| **RNF002** | Segurança: O sistema deve proteger dados sensíveis dos usuários, utilizando práticas como criptografia de senhas e conexões seguras. | N/A                                       | Arquitetura de Segurança, Diagrama de Implantação | Módulo de Segurança                   | A Definir             | A Definir       | Aplica-se a todos os módulos que tratam de dados do usuário.                                                                                                                                                                                                                                                                                                                                                     |
| **RNF003** | Disponibilidade: O sistema deve ficar disponível 99% do tempo, considerando manutenções programas. | N/A                                       | Diagrama de Implantação             | Infraestrutura/Hosting                | A Definir             | A Definir       | Requer monitoramento e estratégias de recuperação de desastres.                                                                                                                                                                                                                                                                                                                                                |
| **RNF004** | Usabilidade: A interface deve ser responsiva, intuitiva e acessível, funcionando em diferentes dispositivos e sistemas operacionais. | N/A                                       | Mockups/Protótipos de Interface | Camada de Interface do Usuário        | A Definir             | A Definir       | Deve ser validado através de testes de usabilidade.                                                                                                                                                                                                                                                                                                                                                              |
| **RNF005** | Escalabilidade: O sistema deve ser capaz de suportar o crescimento contínuo do número de usuários e da quantidade de dados, sem comprometer seu desempenho. | N/A                                       | Diagrama de Implantação             | Arquitetura Geral                     | A Definir             | A Definir       | Impacta a escolha de tecnologias e o design da infraestrutura.                                                                                                                                                                                                                                                                                                                                                   |
| **RNF006** | Manutenibilidade: O código-fonte do sistema deve ser modular, documentado e constantemente mantido e atualizado. | N/A                                       | N/A                                 | Padrões de Codificação/DevOps         | A Definir             | A Definir       | Requer boas práticas de desenvolvimento e documentação.                                                                                                                                                                                                                                                                                                                                                        |

### Conclusão 
Este documento serve como base para o desenvolvimento do sistema ArtHub. Futuras revisões devem ser registradas no histórico de versões para manter o controle de mudanças e melhorias contínuas.
