# FutMatch - Node.js

Sistema de gerenciamento de partidas de futebol migrado de Spring Boot para Node.js.

## 🚀 Funcionalidades

- ✅ Criar, editar e excluir partidas
- ✅ Buscar partidas por localização, tipo e data
- ✅ Sistema de favoritos
- ✅ Interface responsiva com tema claro/escuro
- ✅ Validação de dados no frontend e backend
- ✅ API REST completa
- ✅ Banco de dados MongoDB
- ✅ Middleware de segurança

## 📋 Pré-requisitos

- Node.js (versão 16 ou superior)
- MongoDB (local ou MongoDB Atlas)
- npm ou yarn

## 🛠️ Instalação

1. **Clone o repositório** (se aplicável)
2. **Instale as dependências:**
   ```bash
   npm install
   ```

3. **Configure as variáveis de ambiente:**
   - Copie o arquivo `env.example` para `.env`
   - Configure as variáveis conforme necessário:
   ```env
   PORT=8080
   NODE_ENV=development
   MONGODB_URI=mongodb://localhost:27017/futmatch
   ```

4. **Inicie o MongoDB:**
   - Local: Certifique-se de que o MongoDB está rodando na porta 27017
   - Atlas: Configure a string de conexão no arquivo `.env`

## 🚀 Execução

### Desenvolvimento
```bash
npm run dev
```

### Produção
```bash
npm start
```

O servidor estará disponível em: `http://localhost:8080`

## 📁 Estrutura do Projeto

```
FutMatch/
├── controllers/          # Controladores da API
│   └── matchController.js
├── models/              # Modelos de dados (Mongoose)
│   └── Match.js
├── routes/              # Rotas da API
│   └── matchRoutes.js
├── services/            # Lógica de negócio
│   └── matchService.js
├── public/              # Arquivos estáticos
│   ├── css/
│   │   └── styles.css
│   ├── js/
│   │   └── script.js
│   └── index.html
├── server.js            # Arquivo principal do servidor
├── package.json         # Dependências e scripts
└── README.md           # Este arquivo
```

## 🔧 API Endpoints

### Partidas
- `GET /api/matches` - Listar todas as partidas ativas
- `GET /api/matches/:id` - Buscar partida por ID
- `POST /api/matches` - Criar nova partida
- `PUT /api/matches/:id` - Atualizar partida
- `DELETE /api/matches/:id` - Excluir partida
- `GET /api/matches/search` - Buscar partidas com filtros
- `GET /api/matches/stats` - Estatísticas gerais

### Parâmetros de Busca
- `location` - Buscar por localização
- `type` - Filtrar por tipo (Society, Salão, Campo, Areia)
- `date` - Filtrar por data

## 🗄️ Modelo de Dados

### Match
```javascript
{
  name: String,           // Nome da partida
  location: String,       // Local da partida
  neighborhood: String,   // Bairro
  date: Date,            // Data da partida
  time: String,          // Horário (HH:MM)
  type: String,          // Tipo: Society, Salão, Campo, Areia
  maxPlayers: Number,    // Máximo de jogadores
  currentPlayers: Number, // Jogadores atuais
  price: Number,         // Preço por jogador
  description: String,   // Descrição
  requirements: [String], // Requisitos
  createdBy: String,     // Criado por
  active: Boolean        // Status ativo
}
```

## 🔒 Segurança

- Rate limiting (100 requests/15min por IP)
- Validação de dados com express-validator
- CORS configurado
- Helmet para headers de segurança
- Sanitização de entrada

## 🎨 Interface

- Design responsivo
- Tema claro/escuro
- Notificações em tempo real
- Validação de formulários
- Sistema de favoritos

## 🧪 Testes

```bash
npm test
```

## 📝 Logs

O sistema utiliza Morgan para logging de requisições HTTP.

## 🚀 Deploy

### Heroku
1. Configure as variáveis de ambiente
2. Configure o MongoDB Atlas
3. Deploy via Git

### Docker (opcional)
```dockerfile
FROM node:16-alpine
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 8080
CMD ["npm", "start"]
```

## 🤝 Contribuição

1. Fork o projeto
2. Crie uma branch para sua feature
3. Commit suas mudanças
4. Push para a branch
5. Abra um Pull Request

## 📄 Licença

Este projeto está sob a licença MIT.

## 🆚 Migração do Spring Boot

### Principais mudanças:
- **Framework**: Spring Boot → Express.js
- **ORM**: JPA/Hibernate → Mongoose
- **Banco**: H2 → MongoDB
- **Validação**: Bean Validation → express-validator
- **Estrutura**: Maven → npm
- **Configuração**: application.properties → .env

### Funcionalidades mantidas:
- ✅ Todas as operações CRUD
- ✅ Sistema de busca e filtros
- ✅ Validação de dados
- ✅ Interface de usuário
- ✅ Sistema de favoritos
- ✅ Tema claro/escuro

## 📞 Suporte

Para dúvidas ou problemas, abra uma issue no repositório.
