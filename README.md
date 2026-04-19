# Notificacao Grupos - Backend API

Este é um projeto Spring Boot para gerenciamento de voos e autenticação de usuários. A API permite operações CRUD em voos e autenticação básica.

## Tecnologias Utilizadas

- **Java 17**
- **Spring Boot 3.3.3**
- **Maven** para gerenciamento de dependências
- **Docker** para containerização
- **Swagger/OpenAPI** para documentação da API

## Pré-requisitos

- Java 17 ou superior
- Maven 3.6+
- Docker (opcional, para execução em container)

## Como Executar

### Opção 1: Usando Maven

1. Clone o repositório
2. Navegue até o diretório do projeto
3. Execute o comando:

```bash
mvn spring-boot:run
```

### Opção 2: Usando Docker

1. Construa a imagem:

```bash
docker build -t notificacao-grupos .
```

2. Execute o container:

```bash
docker run -p 3333:3333 notificacao-grupos
```

A aplicação estará disponível em `http://localhost:3333`

## Endpoints da API

### Autenticação

- **POST** `/api/login`
  - Autentica usuário
  - Body: `{ "username": "admin", "password": "password123" }`

### Voos (Flights)

- **GET** `/api/flights` - Lista todos os voos
- **GET** `/api/flights/{id}` - Obtém voo por ID
- **POST** `/api/flights` - Cria novo voo
- **PUT** `/api/flights/{id}` - Atualiza voo existente
- **DELETE** `/api/flights/{id}` - Remove voo

### Documentação Swagger

- **URL**: `http://localhost:3333/swagger-ui.html`
- Documentação interativa da API

## Modelo de Dados - Flight

```json
{
  "id": 1,
  "seat": "12A",
  "num": "AV-001",
  "entrada": 10,
  "saida": 12,
  "orig": "GRU - São Paulo",
  "dest": "CDG - Paris",
  "status": "Ativo"
}
```

### Status Possíveis
- `Ativo`
- `Inativo`
- `Pendente`

## Dados Iniciais

A aplicação vem com 7 voos pré-cadastrados para demonstração.

## Configuração de Segurança

- Autenticação básica HTTP
- CORS configurado para origens específicas
- Endpoints de login e documentação permitidos sem autenticação

## Implantação

### Render.com

O projeto está configurado para implantação no Render usando Docker.

1. Conecte o repositório ao Render
2. Configure o serviço web com Docker
3. Defina a porta 3333
4. Implante

## Desenvolvimento

### Estrutura do Projeto

```
src/
├── main/
│   ├── java/
│   │   └── com/aerolinea/transporte/notificacao_grupos/
│   │       ├── config/          # Configurações de segurança e CORS
│   │       ├── controller/      # Controladores REST
│   │       ├── model/           # Modelos de dados
│   │       ├── service/         # Lógica de negócio
│   │       └── NotificacaoGruposApplication.java
│   └── resources/
│       └── application.yaml     # Configurações da aplicação
└── test/                        # Testes
```

### Executar Testes

```bash
mvn test
```

### Build do Projeto

```bash
mvn clean package
```

O JAR executável será gerado em `target/notificacao-grupos-0.0.1-SNAPSHOT.jar`

## Contribuição

1. Faça fork do projeto
2. Crie uma branch para sua feature (`git checkout -b feature/nova-feature`)
3. Commit suas mudanças (`git commit -am 'Adiciona nova feature'`)
4. Push para a branch (`git push origin feature/nova-feature`)
5. Abra um Pull Request

## Licença

Este projeto está sob a licença MIT. Veja o arquivo LICENSE para mais detalhes.

## Contato

Para dúvidas ou sugestões, entre em contato com a equipe de desenvolvimento.

## Backend Preview
admin
password123

<p align="center">
  <img 
    src="https://github.com/user-attachments/assets/2bffa5d6-2247-4518-901d-ff3db9f824ae" 
    alt="Backend preview" 
    width="900"
  />
</p>
