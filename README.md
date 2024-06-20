# A3-PROJECTCRUD

- Contexto Geral da Aplicação.
  
Esta aplicação é uma API para gerenciamento de produtos, construída utilizando ASP.NET Core e Entity Framework Core. A API permite realizar operações CRUD (Create, Read, Update, Delete) em produtos, e está organizada em várias camadas, cada uma com responsabilidades distintas. As principais classes e arquivos da aplicação são responsáveis por definir modelos de dados, configurar serviços, gerenciar a interação com o banco de dados, controlar as requisições HTTP e transferir dados entre diferentes partes da aplicação.

- Resumo: Classes, métodos e etc.
  
1. Products - Models
Classe: Product
Descrição: Representa um produto na aplicação.
Propriedades:
Id: Identificador único do produto (chave primária).
Name: Nome do produto.
Description: Descrição do produto (pode ser nula).
Price: Preço do produto.
2. Program - Services
Classe: Program
Descrição: Configura e inicia a aplicação, definindo serviços, middleware e pipeline de requisição HTTP.
Principais Configurações:
Serviços Adicionados:
Controladores MVC
Swagger para documentação da API
AutoMapper para mapeamento de objetos
DbContext para conexão com banco de dados MySQL
Pipeline de Requisição HTTP:
Middleware de autorização
Mapeamento de controladores
Execução da aplicação
3. Appdbcontext - Data
Classe: ApplicationDbContext
Descrição: Define o contexto do banco de dados usando Entity Framework Core.
Propriedades:
DbSet<Product>: Representa a coleção de produtos no banco de dados.
4. Controlador - Controller
Classe: ProductsController
Descrição: Controlador de API que gerencia operações CRUD em produtos.
Métodos:
GetAll(): Retorna todos os produtos.
GetById(int id): Retorna um produto específico pelo ID.
Create(CreateProductDto createProductDto): Cria um novo produto.
Update(int id, CreateProductDto updateProductDto): Atualiza um produto existente.
Delete(int id): Deleta um produto existente.
5. CreateProductDto - DTO
Classe: CreateProductDto
Descrição: Objeto de Transferência de Dados usado para criar produtos.
Propriedades:
Name: Nome do produto.
Description: Descrição do produto.
Price: Preço do produto.

- Contexto referente aos arquivos.
  
Models (Product): Define como os dados dos produtos são estruturados e armazenados no banco de dados.
Services (Program): Configura a aplicação e gerencia serviços essenciais, como conexão ao banco de dados e documentação da API.
Data (Appdbcontext): Define o contexto do banco de dados e mapeia a entidade Product para a tabela products.
Controller (ProductsController): Gerencia as requisições HTTP e implementa a lógica de negócios para operações CRUD.
DTO (CreateProductDto): Facilita a transferência de dados ao criar novos produtos, garantindo que apenas os dados necessários sejam enviados.
Essa estrutura modular facilita a manutenção, escalabilidade e entendimento da aplicação, separando claramente as responsabilidades de cada componente.
