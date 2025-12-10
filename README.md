# ⚽ FutMatch

<div align="center">

![FutMatch Logo](https://img.shields.io/badge/FutMatch-Sistema%20de%20Partidas-green)
![Version](https://img.shields.io/badge/version-1.0.0-blue)
![License](https://img.shields.io/badge/license-MIT-green)

**Sistema completo de gerenciamento de partidas de futebol**

Conectando jogadores, criando partidas inesquecíveis! 🎯

[Funcionalidades](#-funcionalidades) • [Instalação](#-instalação) • [Uso](#-como-usar) • [API](#-api-endpoints) • [Contribuir](#-contribuindo)

</div>

---

## 📋 Sobre o Projeto

O **FutMatch** é uma aplicação web completa para gerenciamento de partidas de futebol, permitindo que jogadores criem, busquem e participem de partidas. Desenvolvido com Node.js e MongoDB, oferece uma interface moderna e intuitiva.

### 🎯 Objetivo

Facilitar a organização de partidas de futebol, conectando jogadores e permitindo que encontrem partidas próximas, com informações detalhadas sobre local, horário, tipo de jogo e número de participantes.

---

## ✨ Funcionalidades

### 🏆 Principais Recursos

- ✅ **CRUD Completo de Partidas**
  - Criar, visualizar, editar e excluir partidas
  - Validação completa de dados (frontend e backend)
  
- ✅ **Sistema de Participação**
  - Botão "Entrar na Partida" em cada card
  - Controle automático de vagas disponíveis
  - Validação de partida cheia
  
- ✅ **Busca e Filtros Avançados**
  - Busca por localização/bairro
  - Filtro por tipo de jogo (Society, Futsal, Campo, Beach Soccer)
  - Filtro por data
  
- ✅ **Sistema de Favoritos**
  - Salvar partidas favoritas
  - Acesso rápido via modal
  
- ✅ **Interface Moderna e Responsiva**
  - Design limpo e intuitivo
  - Tema claro/escuro (dark mode)
  - Totalmente responsivo (mobile-first)
  - Notificações em tempo real
  
- ✅ **API REST Completa**
  - Endpoints documentados
  - Validação robusta
  - Tratamento de erros

---

## 🏗️ Arquitetura

```
FutMatch/
├── futmatch-nodejs/        # Aplicação Node.js
│   ├── controllers/        # Controladores da API
│   ├── services/           # Lógica de negócio
│   ├── models/             # Modelos de dados (Mongoose)
│   ├── routes/             # Rotas da API
│   ├── public/             # Frontend (HTML, CSS, JS)
│   │   ├── css/            # Estilos
│   │   ├── js/             # JavaScript
│   │   └── index.html      # Página principal
│   ├── config.js           # Configurações
│   ├── server.js           # Servidor Express
│   └── package.json        # Dependências
│
└── README.md
```

---

## 🚀 Tecnologias Utilizadas

### Backend
- **Node.js** 16+ - Runtime JavaScript
- **Express.js** - Framework web
- **Mongoose** - ODM para MongoDB
- **Express Validator** - Validação de dados
- **Helmet** - Segurança HTTP
- **CORS** - Controle de acesso
- **Rate Limiting** - Proteção contra spam

### Frontend
- **HTML5, CSS3, JavaScript (Vanilla)**
- **Font Awesome** - Ícones
- **Google Fonts (Poppins)** - Tipografia
- **LocalStorage** - Armazenamento local (favoritos e tema)

### Banco de Dados
- **MongoDB** - Banco de dados NoSQL

---

## 📦 Instalação

### Pré-requisitos

- **Node.js** 16 ou superior
- **npm** (vem com Node.js)
- **MongoDB** (local ou MongoDB Atlas)

---

### 🎯 Passo a Passo

1. **Clone o repositório**
```bash
git clone https://github.com/seu-usuario/FutMatch.git
cd FutMatch/futmatch-nodejs
```

2. **Instale as dependências**
```bash
npm install
```

3. **Configure o ambiente**
```bash
# Copie o arquivo de exemplo
cp env.example .env

# Edite o .env com suas configurações
# MongoDB URI, porta, etc.
```

4. **Execute a aplicação**
```bash
# Desenvolvimento (com nodemon - auto-reload)
npm run dev

# Produção
npm start
```

5. **Acesse a aplicação**
```
http://localhost:8080
```

---

## ⚙️ Configuração

### Variáveis de Ambiente

Crie um arquivo `.env` na pasta `futmatch-nodejs`:

```env
# Porta do servidor
PORT=8080

# MongoDB
MONGO_URI=mongodb://localhost:27017/futmatch

# CORS
CORS_ORIGIN=*
CORS_METHODS=GET,POST,PUT,DELETE,OPTIONS

# Rate Limiting
RATE_LIMIT_WINDOW_MS=900000
RATE_LIMIT_MAX_REQUESTS=100
```

### MongoDB

**Opção 1: MongoDB Local**
```bash
# Instale o MongoDB
# Inicie o serviço MongoDB
mongod
```

**Opção 2: MongoDB Atlas (Cloud)**
1. Crie uma conta em [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)
2. Crie um cluster gratuito
3. Copie a connection string
4. Cole no arquivo `.env` como `MONGO_URI`

---

## 🎮 Como Usar

### Criar uma Partida

1. Preencha o formulário "Criar Nova Partida"
2. Informe:
   - Nome da partida
   - Tipo de jogo (Society, Futsal, Campo, Beach Soccer)
   - Data e horário
   - Local e bairro
   - Número máximo de jogadores
   - Valor por jogador (opcional)
   - Descrição e requisitos
3. Clique em "Criar Partida"

### Entrar em uma Partida

1. Navegue pela lista de partidas disponíveis
2. Clique no botão **"Entrar na Partida"** no card da partida desejada
3. O sistema automaticamente:
   - Incrementa o contador de jogadores
   - Valida se há vagas disponíveis
   - Atualiza a interface em tempo real

### Buscar Partidas

- Use a barra de busca para filtrar por localização
- Selecione o tipo de jogo no dropdown
- Escolha uma data específica
- Os resultados são filtrados em tempo real

### Favoritos

1. Clique no botão "Adicionar aos Favoritos" em qualquer partida
2. Acesse seus favoritos pelo botão no header
3. Gerencie suas partidas favoritas facilmente

---

## 🔌 API Endpoints

### Partidas

| Método | Endpoint | Descrição |
|--------|----------|-----------|
| `GET` | `/api/matches` | Lista todas as partidas ativas |
| `GET` | `/api/matches/:id` | Busca partida por ID |
| `POST` | `/api/matches` | Cria nova partida |
| `PUT` | `/api/matches/:id` | Atualiza partida existente |
| `DELETE` | `/api/matches/:id` | Exclui partida |
| `POST` | `/api/matches/:id/join` | Entra na partida |
| `GET` | `/api/matches/search` | Busca com filtros |

### Exemplo de Requisição

**Criar Partida:**
```bash
POST /api/matches
Content-Type: application/json

{
  "name": "Pelada do Fim de Semana",
  "type": "Society",
  "date": "2024-12-25",
  "time": "18:00",
  "location": "Arena Central",
  "neighborhood": "Centro",
  "maxPlayers": 10,
  "price": 25.00,
  "description": "Partida amigável, todos os níveis",
  "requirements": ["colete", "chuteira"]
}
```

**Entrar na Partida:**
```bash
POST /api/matches/123/join
```

**Resposta de Sucesso:**
```json
{
  "success": true,
  "data": {
    "_id": "123",
    "name": "Pelada do Fim de Semana",
    "currentPlayers": 1,
    "maxPlayers": 10,
    ...
  },
  "message": "Você entrou na partida com sucesso"
}
```

---

## 🎨 Interface

### Características do Design

- **Tema Claro/Escuro:** Alternância com um clique
- **Responsivo:** Funciona perfeitamente em mobile, tablet e desktop
- **Notificações:** Feedback visual para todas as ações
- **Validação em Tempo Real:** Formulários com validação instantânea
- **Animações Suaves:** Transições e efeitos visuais

### Paleta de Cores

- **Verde Principal:** `#1a472a` (cor do gramado)
- **Verde Secundário:** `#2d8a4e`
- **Branco:** `#ffffff` (linhas do campo)
- **Fundo Claro:** `#f0f4f0`
- **Fundo Escuro:** `#121212`

---

## 🧪 Testes

```bash
cd futmatch-nodejs
npm test
```

---

## 📊 Estrutura de Dados

### Modelo de Partida

```javascript
{
  _id: ObjectId,
  name: String,
  location: String,
  neighborhood: String,
  date: Date,
  time: String,
  type: String, // "Society", "Salão", "Campo", "Areia"
  maxPlayers: Number,
  currentPlayers: Number,
  price: Number,
  description: String,
  requirements: Array, // ["colete", "chuteira", "bola", "agua"]
  active: Boolean,
  createdBy: String,
  createdAt: Date,
  updatedAt: Date
}
```

---

## 🔒 Segurança

### Implementado

- ✅ **Validação de Dados:** Frontend e backend
- ✅ **Rate Limiting:** Proteção contra spam
- ✅ **CORS:** Configurado adequadamente
- ✅ **Helmet:** Headers de segurança
- ✅ **Sanitização:** Dados validados antes de salvar
- ✅ **Express Validator:** Validação robusta de entrada

---

## 🚀 Deploy

### Heroku

```bash
# Instale o Heroku CLI
heroku login

# Crie a aplicação
heroku create futmatch-app

# Adicione MongoDB
heroku addons:create mongolab:sandbox

# Faça deploy
git push heroku main
```

### Vercel

```bash
# Instale o Vercel CLI
npm i -g vercel

# Faça deploy
vercel --prod
```

### Docker

```dockerfile
FROM node:16-alpine
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 8080
CMD ["npm", "start"]
```

```bash
docker build -t futmatch .
docker run -p 8080:8080 futmatch
```

---

## 📝 Scripts Disponíveis

```bash
# Desenvolvimento (com nodemon)
npm run dev

# Produção
npm start

# Testes
npm test

# Testar API
npm run test-api
```

---

## 🤝 Contribuindo

Contribuições são sempre bem-vindas! 

1. Fork o projeto
2. Crie uma branch para sua feature (`git checkout -b feature/AmazingFeature`)
3. Commit suas mudanças (`git commit -m 'Add some AmazingFeature'`)
4. Push para a branch (`git push origin feature/AmazingFeature`)
5. Abra um Pull Request

### Padrões de Código

- Siga as convenções do JavaScript/Node.js
- Adicione comentários quando necessário
- Mantenha o código limpo e legível
- Teste suas alterações

---

## 📝 Licença

Este projeto está sob a licença MIT. Veja o arquivo `LICENSE` para mais detalhes.

---

## 👥 Autores

- **FutMatch Team** - *Desenvolvimento inicial*

---

## 🙏 Agradecimentos

- Comunidade de desenvolvedores
- Todos os contribuidores
- Usuários que testam e reportam bugs

---

## 📞 Suporte

- **Issues:** [GitHub Issues](https://github.com/seu-usuario/FutMatch/issues)
- **Documentação:** Consulte `futmatch-nodejs/README.md`
- **Email:** contato@futmatch.com

---

<div align="center">

**Desenvolvido com ❤️ para a comunidade de futebol!** ⚽

⭐ Se este projeto foi útil, considere dar uma estrela!

[⬆ Voltar ao topo](#-futmatch)

</div>
