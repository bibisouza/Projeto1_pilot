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
1. **RF001 - Cadastro de Usuários**: O sistema deve permitir o cadastro de novos usuários, informando nome, email e senha.
2. **RF002 - Login de Usuários**: O sistema deve permitir que usuários cadastrados façam login informando email e senha.
3. **RF003 - Personalizar Perfil**: O sistema deve permitir que o usuário personalize seu perfil, adicionando foto, apelido biografia.
4. **RF004 -Registro de séries na biblioteca pessoal**: O sistema deve permitir que o usuário resgistre séries em sua biblioteca pessoal, podendo definir o status da série(Assistindo, Finalizada, Abandonada, Quero Assitir).
5. **RF005 - Avaliação de séries**: O sistema deve permitir que o usuário avalie séries atrribuindo uma nota de 1 a 5 estrelas, com a opção de escrever uma resenha associada à avaliação.
6. **RF006 - Busca de séries**: O sistema deve permitir que o usuário busque séries pelo seu nome, diretor, gênero, personagens ou atores envolvidos.
7. **RF007 - Criação de Listas Personalizadas**: O sistema deve permitir que o usuário crie listas personalizadas selecionando séries.
8. **RF008 - Estatísticas do Usuário**: O sistema deve gerar estatísticas do perfil, com base na quantidade de séries assistidas, tempo total de minutos assistidos, gêneros mais assistidos, atores mais assistidos.


#### 3.2 Requisitos Não Funcionais 
1. **RNF001 - Desempenho**: O sistema deve responder às requisições em até 2 segundos em média, proporcionando uma navegação fluída.
2. **RNF002 - Segurança**: O sistema deve proteger dados sensíveis dos usuários, utilizando práticas como criptografia de senhas e conexões seguras.
3. **RNF003 - Disponibilidade**: O sistema deve ficar disponível 99% do tempo, considerando manutenções programas.
4. **RNF004 - Usabilidade**: A interface deve ser responsiva, intuitiva e acessível, funcionando em diferentes dispositivos e sistemas operacionais.
5. **RNF005 - Esacalabilidade**: O sistema deve ser capaz de suportar o crescimento contínuo do número de usuários e da quantidade de dados, sem comprometer seu desempenho.

#### 3.3 Regras de Negócio
1. **RN001**: Um pedido não pode ser finalizado se não houver ao menos um item (produto ou serviço).
2. **RN002**: A quantidade de produtos em estoque não pode ficar negativa. 
3. **RN003**: Para cada pedido de banho e tosa, é obrigatório associar pelo menos um animal de estimação do cliente.
4. **RN004**: É obrigatório registrar a forma de pagamento no momento do fechamento do pedido (dinheiro, cartão de crédito, etc.).

---

### Modelos e Diagramas

#### 4.1 Casos de Uso
- **UC01**: Cadastrar Cliente
- **UC02**: Cadastrar Produto
- **UC03**: Criar Pedido
- **UC04**: Atualizar Status do Pedido
- **UC05**: Gerar Relatório de Vendas

Cada caso de uso descreve o fluxo de ações, pré-condições e pós-condições para cada funcionalidade crítica do sistema.

#### 4.2 Diagrama de Classe (Definir o diagrama de pelo menos um caso de uso)
O diagrama de classe deve representar as principais entidades do sistema, como **Cliente**, **Produto**, **Pedido**, **ItemPedido**, **Serviço** e **Relatório**, mostrando relacionamentos, atributos e métodos relevantes.

#### 4.3 Diagramas de Sequência (Definir o fluxo de pelo menos um caso de uso)
Podem ser detalhados os fluxos:
- **Fluxo de Criação de Pedido** (mostrando interação entre Atendente, Sistema, Estoque, etc.)
- **Fluxo de Emissão de Relatório** (mostrando como os dados são buscados no banco de dados).

---

### Rastreabilidade de Requisitos 

#### 5.1 Matriz de Rastreabilidade 
A matriz de rastreabilidade deve indicar a relação entre cada requisito e seus artefatos correspondentes (caso de uso, diagramas, componentes do sistema, etc.). Por exemplo:

| Requisito | Caso de Uso | Componente/Classe | Status       |
|-----------|------------|--------------------|--------------|
| RF001     | UC01        | Cliente           | Atendido     |
| RF002     | UC02        | Produto           | Atendido     |
| RF003     | UC03        | Pedido            | Em progresso |
| ...       | ...         | ...               | ...          |

---

### Conclusão 
Este documento serve como base para o desenvolvimento do sistema de pedidos para o petshop. Futuras revisões devem ser registradas no histórico de versões para manter o controle de mudanças e melhorias contínuas.
