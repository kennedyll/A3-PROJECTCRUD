- Conxteto geral:

Esta aplicação é uma API para gerenciamento de competições escolares, construída utilizando ASP.NET Core e Entity Framework Core. A API permite realizar operações CRUD (Create, Read, Update, Delete) em competições e competidores, organizando-se em diversas camadas, cada uma com responsabilidades específicas. As principais classes e arquivos da aplicação definem modelos de dados, configuram o contexto do banco de dados, controlam as requisições HTTP e transferem dados entre diferentes partes da aplicação.

- Resumo das Classes

1. Controlador - Controller
Classe: CompeticoesController e CompetidoresController
Descrição: Controlador de API que gerencia operações CRUD em produtos.

Métodos:
GetAll(): Retorna todos os produtos.
GetById(int id): Retorna um produto específico pelo ID.
Create(CreateProductDto createProductDto): Cria um novo produto.
Update(int id, CreateProductDto updateProductDto): Atualiza um produto existente.
Delete(int id): Deleta um produto existente.

2. Data - CompeticaoBD
Classe: ApplicationDbContext
Descrição: Define o contexto do banco de dados usando Entity Framework Core.

Propriedades:
DbSet<Product>: Representa a coleção de produtos no banco de dados.

4. Competição - Models
Classe: Competicao
Descrição: Representa uma competição na aplicação.

Propriedades:
Id: Identificador único da competição (chave primária).
Esporte: Nome do esporte da competição.
NomeEquip: Nome da equipe participante.
Data: Data do evento da competição.
Competidores: Lista de competidores na competição.

5. Competidor - Models
Classe: Competidor
Descrição: Representa um competidor em uma competição.
Propriedades:

Id: Identificador único do competidor (chave primária).
Competidores: Nome do competidor.
Pontuacao: Pontuação do competidor na competição.
Colocacao: Colocação do competidor na competição.
CompeticaoId: Referência ao ID da competição a que o competidor pertence.

- Resumo

Controller (ProductsController): Gerencia as requisições HTTP e implementa a lógica de negócios para operações CRUD em produtos.

Data (CompeticaoBD): Define o contexto do banco de dados e mapeia a entidade Product para a tabela products, facilitando a comunicação e operações com o banco de dados.

Models (Competição): Define a estrutura dos dados das competições, incluindo informações como esporte, nome da equipe, data do evento e lista de competidores.

Models (Competidor): Define a estrutura dos dados dos competidores, incluindo nome, pontuação, colocação e referência à competição a que pertencem.

Essa estrutura modular facilita a manutenção, escalabilidade e entendimento da aplicação, separando claramente as responsabilidades de cada componente.
