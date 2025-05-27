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
O sistema de pedidos para o petshop se encaixa como uma solução integrada para lojas de animais, permitindo o cadastro de produtos (ração, brinquedos, medicamentos, etc.), serviços (banho, tosa, consultas), clientes e pedidos. A expectativa é que esse sistema seja acessível via web, facilitando o dia a dia dos funcionários e clientes.

#### 2.2 Funções do Produto 
1. **Gerenciamento de Pedidos**: Permite criar, atualizar e finalizar pedidos.
2. **Controle de Estoque**: Monitora quantidade de produtos, exibindo alertas de reposição.
3. **Cadastro de Clientes e Animais**: Armazena dados de clientes (proprietários) e de seus animais de estimação.
4. **Relatórios**: Gera relatórios de vendas, clientes e produtos para análise gerencial.

#### 2.3 Características dos Usuários
- **Atendentes**: Responsáveis pelo cadastro e acompanhamento de pedidos, além de atender solicitações de clientes.
- **Administradores**: Responsáveis pela configuração do sistema, gerenciamento de estoque e emissão de relatórios.
- **Clientes**: Podem, no futuro, ter acesso a um portal para criar e acompanhar pedidos online (funcionalidade opcional).

#### 2.4 Restrições Gerais
- O sistema deve operar em navegadores modernos (Chrome, Firefox, Edge).
- O banco de dados deve ser acessível somente dentro da rede da empresa (por questões de segurança).
- As integrações externas (se necessárias) devem seguir protocolos seguros (HTTPS/TLS).

---

### Requisitos Específicos

#### 3.1 Requisitos Funcionais 
1. **RF001 - Cadastro de Clientes**: O sistema deve permitir o cadastro de novos clientes com informações básicas (nome, telefone, endereço).
2. **RF002 - Cadastro de Produtos**: O sistema deve permitir incluir, alterar e excluir produtos do estoque.
3. **RF003 - Criar Pedido**: O sistema deve permitir criar pedidos contendo um ou mais itens (produtos/serviços) relacionados a um cliente.
4. **RF004 - Atualizar Status do Pedido**: O sistema deve permitir alterar o status do pedido (em aberto, em processamento, concluído).
5. **RF005 - Emitir Relatórios**: O sistema deve gerar relatórios de vendas por período e por categoria de produto.

#### 3.2 Requisitos Não Funcionais 
1. **RNF001 - Desempenho**: O sistema deve responder às requisições em até 2 segundos em média.
2. **RNF002 - Segurança**: Todo acesso ao sistema deve exigir autenticação de usuário e senha.
3. **RNF003 - Disponibilidade**: O sistema deve ficar disponível 95% do tempo em horário comercial (8h às 18h).
4. **RNF004 - Usabilidade**: A interface deve ser responsiva e intuitiva, facilitando o uso em diferentes dispositivos.

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
