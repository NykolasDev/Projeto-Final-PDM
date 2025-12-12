# ⚽ FutMatch

<div align="center">

![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![Node](https://img.shields.io/badge/node-%3E%3D16.0.0-brightgreen.svg)
![React Native](https://img.shields.io/badge/react--native-0.73.0-blue.svg)
![Expo](https://img.shields.io/badge/expo-SDK%2054-000020.svg?logo=expo)

**Plataforma completa para organizar, encontrar e participar de partidas de futebol**

Conectando jogadores, criando partidas inesquecíveis! 🎯

[Funcionalidades](#-funcionalidades) • [Instalação](#-instalação) • [API](#-api-endpoints) • [Mobile](#-aplicativo-mobile) • [Contribuir](#-contribuindo)

</div>

---

## 📋 Sobre o Projeto

O **FutMatch** é uma plataforma completa de gerenciamento de partidas de futebol, desenvolvida como um monorepo que inclui:

- **Backend/Web**: API RESTful em Node.js + Express com interface web responsiva
- **Mobile**: Aplicativo React Native (Expo) para iOS e Android

A solução permite que jogadores criem, busquem, filtrem e participem de partidas de diferentes modalidades (Society, Salão, Campo, Areia), com sistema de favoritos, busca avançada e controle de vagas em tempo real.

### 🎯 Objetivo

Facilitar a organização e descoberta de partidas de futebol, conectando jogadores e permitindo que encontrem partidas próximas com informações detalhadas sobre local, horário, tipo de jogo, número de participantes e requisitos.

---

## ✨ Funcionalidades

### 🏆 Principais Recursos

#### Backend/Web
- ✅ **CRUD Completo de Partidas**
  - Criar, visualizar, editar e excluir partidas
  - Validação robusta de dados (frontend e backend)
  - Middleware de segurança e rate limiting
  
- ✅ **Sistema de Participação**
  - Endpoint dedicado para entrar em partidas
  - Controle automático de vagas disponíveis
  - Validação de partida cheia
  
- ✅ **Busca e Filtros Avançados**
  - Busca por localização/bairro (text search)
  - Filtro por tipo de jogo (Society, Salão, Campo, Areia)
  - Filtro por data
  - Índices otimizados no MongoDB
  
- ✅ **Interface Web Moderna**
  - Design responsivo (mobile-first)
  - Tema claro/escuro (dark mode)
  - Notificações em tempo real
  - Validação de formulários em tempo real

#### Mobile (React Native)
- ✅ **Telas Principais**
  - **Home**: Lista todas as partidas disponíveis com pull-to-refresh
  - **Busca**: Filtros avançados por localização, tipo e data
  - **Criar Partida**: Formulário completo com validação
  - **Detalhes**: Visualização completa da partida
  - **Favoritos**: Gerenciamento de partidas salvas
  
- ✅ **Recursos Mobile**
  - Navegação com React Navigation (Bottom Tabs + Stack)
  - Armazenamento local (AsyncStorage) para favoritos
  - Cache inteligente de partidas
  - Integração com localização (Expo Location)
  - UI moderna com Linear Gradient e ícones
  - Tratamento de erros e estados de loading

---

## 🏗️ Arquitetura

```
FutMatch/
├── futmatch-nodejs/              # Backend + Web
│   ├── controllers/              # Controladores da API
│   │   └── matchController.js
│   ├── services/                 # Lógica de negócio
│   │   └── matchService.js
│   ├── models/                   # Modelos Mongoose
│   │   └── Match.js
│   ├── routes/                   # Rotas Express
│   │   └── matchRoutes.js
│   ├── public/                   # Frontend estático
│   │   ├── css/
│   │   │   └── styles.css
│   │   ├── js/
│   │   │   └── script.js
│   │   ├── img/
│   │   └── index.html
│   ├── config.js                 # Configurações
│   ├── server.js                 # Servidor Express principal
│   ├── env.example               # Exemplo de variáveis de ambiente
│   └── package.json
│
├── futmatch-mobile/              # Aplicativo Mobile
│   ├── src/
│   │   ├── screens/              # Telas do app
│   │   │   ├── HomeScreen.js
│   │   │   ├── SearchScreen.js
│   │   │   ├── CreateMatchScreen.js
│   │   │   ├── MatchDetailScreen.js
│   │   │   └── FavoritesScreen.js
│   │   ├── components/           # Componentes reutilizáveis
│   │   │   └── MatchCard.js
│   │   ├── services/             # Serviços de API e storage
│   │   │   ├── matchService.js
│   │   │   └── storageService.js
│   │   ├── config/               # Configurações
│   │   │   └── api.js
│   │   └── utils/                # Utilitários
│   │       ├── formatters.js
│   │       └── matchCache.js
│   ├── App.js                    # Componente raiz
│   ├── package.json
│   └── app.json                  # Configuração Expo
│
└── README.md                     # Este arquivo
```

---

## 🚀 Tecnologias Utilizadas

### Backend
- **Node.js** 16+ - Runtime JavaScript
- **Express.js** 4.18+ - Framework web minimalista
- **Mongoose** 8.0+ - ODM para MongoDB
- **Express Validator** 7.0+ - Validação de dados
- **Helmet** 7.1+ - Segurança HTTP headers
- **CORS** 2.8+ - Controle de acesso cross-origin
- **Express Rate Limit** 7.1+ - Proteção contra spam/DoS
- **Morgan** 1.10+ - HTTP request logger
- **dotenv** 16.3+ - Gerenciamento de variáveis de ambiente

### Frontend Web
- **HTML5, CSS3, JavaScript (Vanilla)**
- **Font Awesome** - Ícones
- **Google Fonts (Poppins)** - Tipografia moderna
- **LocalStorage API** - Armazenamento local (favoritos e tema)

### Mobile
- **React Native** 0.73.0 - Framework mobile
- **Expo SDK** 54 - Plataforma de desenvolvimento
- **React Navigation** 6.x - Navegação (Bottom Tabs + Native Stack)
- **AsyncStorage** 1.21+ - Armazenamento local assíncrono
- **Expo Linear Gradient** 12.7+ - Gradientes visuais
- **Expo Location** 16.5+ - Serviços de localização
- **React Native Gesture Handler** 2.14+ - Gestos nativos
- **React Native Safe Area Context** 4.8+ - Áreas seguras

### Banco de Dados
- **MongoDB** - Banco de dados NoSQL orientado a documentos
- **Índices otimizados** para busca por texto, tipo, data e status

---

## 📦 Instalação

### Pré-requisitos

- **Node.js** 16.0.0 ou superior ([Download](https://nodejs.org/))
- **npm** (vem com Node.js) ou **yarn**
- **MongoDB** 4.4+ (local ou [MongoDB Atlas](https://www.mongodb.com/cloud/atlas))
- **Git** para clonar o repositório

**Para Mobile (opcional):**
- **Expo Go** app ([iOS](https://apps.apple.com/app/expo-go/id982107779) | [Android](https://play.google.com/store/apps/details?id=host.exp.exponent))
- Ou **Android Studio** / **Xcode** para desenvolvimento nativo

---

### 🎯 Passo a Passo

#### 1. Clone o repositório

```bash
git clone https://github.com/seu-usuario/FutMatch.git
cd FutMatch
```

#### 2. Configure o Backend

```bash
cd futmatch-nodejs

# Instale as dependências
npm install

# Configure as variáveis de ambiente
cp env.example .env

# Edite o arquivo .env com suas configurações
# Veja a seção "Configuração" abaixo
```

#### 3. Configure o MongoDB

**Opção A: MongoDB Local**
```bash
# Instale o MongoDB Community Edition
# Inicie o serviço MongoDB
mongod

# Ou use Docker
docker run -d -p 27017:27017 --name mongodb mongo:latest
```

**Opção B: MongoDB Atlas (Recomendado para produção)**
1. Crie uma conta em [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)
2. Crie um cluster gratuito (M0)
3. Configure IP whitelist (0.0.0.0/0 para desenvolvimento)
4. Copie a connection string
5. Cole no arquivo `.env` como `MONGO_URI`

#### 4. Inicie o Backend

```bash
cd futmatch-nodejs

# Desenvolvimento (com auto-reload)
npm run dev

# Produção
npm start
```

O servidor estará rodando em `http://localhost:8080`

#### 5. Configure o Mobile (Opcional)

```bash
cd futmatch-mobile

# Instale as dependências
npm install

# Aplique patches para Windows (se necessário)
npm run patch:expo
npm run fix:windows

# Configure a URL da API
# Edite: src/config/api.js
# Altere para: http://<SEU_IP_LOCAL>:8080/api

# Inicie o Expo
npm start

# Escaneie o QR code com Expo Go ou pressione:
# - 'a' para Android
# - 'i' para iOS
# - 'w' para Web
```

---

## ⚙️ Configuração

### Variáveis de Ambiente (Backend)

Crie um arquivo `.env` na pasta `futmatch-nodejs`:

```env
# Servidor
PORT=8080
NODE_ENV=development

# MongoDB
MONGODB_URI=mongodb://localhost:27017/futmatch
# Ou para Atlas:
# MONGODB_URI=mongodb+srv://usuario:senha@cluster.mongodb.net/futmatch?retryWrites=true&w=majority

# CORS
CORS_ORIGIN=*
CORS_METHODS=GET,POST,PUT,DELETE,OPTIONS
CORS_ALLOWED_HEADERS=Content-Type,Authorization,x-auth-token
CORS_EXPOSED_HEADERS=x-auth-token

# Rate Limiting
RATE_LIMIT_WINDOW_MS=900000
RATE_LIMIT_MAX_REQUESTS=100

# JWT (para futuras implementações)
JWT_SECRET=your_jwt_secret_here_change_in_production
```

### Configuração Mobile

Edite `futmatch-mobile/src/config/api.js`:

```javascript
const API_BASE_URL = 'http://192.168.1.100:8080/api'; // Use seu IP local
// ou para produção:
// const API_BASE_URL = 'https://seu-dominio.com/api';
```

**Como descobrir seu IP local:**
- **Windows**: `ipconfig` → IPv4 Address
- **Linux/Mac**: `ifconfig` ou `ip addr`

---

## 🔌 API Endpoints

Base URL: `http://localhost:8080/api`

### Partidas

| Método | Endpoint | Descrição | Autenticação |
|--------|----------|-----------|--------------|
| `GET` | `/matches` | Lista todas as partidas ativas | Não |
| `GET` | `/matches/:id` | Busca partida por ID | Não |
| `POST` | `/matches` | Cria nova partida | Não |
| `PUT` | `/matches/:id` | Atualiza partida existente | Não |
| `DELETE` | `/matches/:id` | Exclui partida | Não |
| `POST` | `/matches/:id/join` | Entra na partida (incrementa currentPlayers) | Não |
| `GET` | `/matches/search` | Busca com filtros (location, type, date) | Não |

### Exemplos de Requisição

#### Criar Partida

```bash
POST /api/matches
Content-Type: application/json

{
  "name": "Pelada do Fim de Semana",
  "type": "Society",
  "date": "2024-12-25T18:00:00.000Z",
  "time": "18:00",
  "location": "Arena Central",
  "neighborhood": "Centro",
  "maxPlayers": 10,
  "price": 25.00,
  "description": "Partida amigável, todos os níveis são bem-vindos!",
  "requirements": ["colete", "chuteira"],
  "createdBy": "João Silva"
}
```

**Resposta de Sucesso (201):**
```json
{
  "success": true,
  "data": {
    "_id": "507f1f77bcf86cd799439011",
    "name": "Pelada do Fim de Semana",
    "type": "Society",
    "date": "2024-12-25T18:00:00.000Z",
    "time": "18:00",
    "location": "Arena Central",
    "neighborhood": "Centro",
    "maxPlayers": 10,
    "currentPlayers": 0,
    "price": 25.00,
    "description": "Partida amigável, todos os níveis são bem-vindos!",
    "requirements": ["colete", "chuteira"],
    "active": true,
    "createdBy": "João Silva",
    "createdAt": "2024-12-20T10:00:00.000Z",
    "updatedAt": "2024-12-20T10:00:00.000Z"
  },
  "message": "Partida criada com sucesso"
}
```

#### Entrar na Partida

```bash
POST /api/matches/507f1f77bcf86cd799439011/join
```

**Resposta de Sucesso (200):**
```json
{
  "success": true,
  "data": {
    "_id": "507f1f77bcf86cd799439011",
    "currentPlayers": 1,
    "maxPlayers": 10,
    "isFull": false
  },
  "message": "Você entrou na partida com sucesso"
}
```

**Resposta de Erro (400) - Partida Cheia:**
```json
{
  "success": false,
  "error": "Partida está cheia"
}
```

#### Buscar Partidas

```bash
GET /api/matches/search?location=Centro&type=Society&date=2024-12-25
```

**Resposta:**
```json
{
  "success": true,
  "data": [
    {
      "_id": "507f1f77bcf86cd799439011",
      "name": "Pelada do Fim de Semana",
      ...
    }
  ],
  "count": 1
}
```

### Códigos de Status HTTP

- `200` - Sucesso
- `201` - Criado com sucesso
- `400` - Requisição inválida (validação falhou)
- `404` - Recurso não encontrado
- `429` - Muitas requisições (rate limit excedido)
- `500` - Erro interno do servidor

---

## 📊 Estrutura de Dados

### Modelo de Partida (Match)

```javascript
{
  _id: ObjectId,                    // ID único gerado pelo MongoDB
  name: String,                     // Nome da partida (obrigatório, max 100 chars)
  location: String,                 // Local da partida (obrigatório, max 200 chars)
  neighborhood: String,             // Bairro (opcional, max 100 chars)
  date: Date,                       // Data da partida (obrigatório, deve ser futura)
  time: String,                     // Horário no formato HH:MM (obrigatório)
  type: String,                     // Tipo: "Society" | "Salão" | "Campo" | "Areia"
  maxPlayers: Number,               // Máximo de jogadores (2-22)
  currentPlayers: Number,           // Jogadores atuais (default: 0)
  price: Number,                    // Valor por jogador (default: 0)
  description: String,              // Descrição (opcional, max 1000 chars)
  requirements: [String],           // Array: ["colete", "chuteira", "bola", "agua"]
  active: Boolean,                  // Status ativo/inativo (default: true)
  createdBy: String,                // Criador da partida (max 100 chars)
  createdAt: Date,                  // Data de criação (automático)
  updatedAt: Date                   // Data de atualização (automático)
}
```

### Índices MongoDB

O modelo inclui índices otimizados para:
- Busca por texto (`location`, `neighborhood`)
- Filtro por tipo e status ativo
- Ordenação por data
- Performance em consultas frequentes

---

## 🎮 Como Usar

### Web Interface

1. Acesse `http://localhost:8080`
2. Visualize todas as partidas disponíveis
3. Use os filtros para buscar por localização, tipo ou data
4. Clique em "Criar Partida" para adicionar uma nova
5. Clique em "Entrar na Partida" para participar
6. Adicione partidas aos favoritos (salvas no LocalStorage)

### Aplicativo Mobile

1. Abra o app no Expo Go ou emulador
2. **Home**: Veja todas as partidas disponíveis
3. **Busca**: Use filtros avançados para encontrar partidas específicas
4. **Criar**: Preencha o formulário para criar uma nova partida
5. **Detalhes**: Toque em uma partida para ver informações completas
6. **Favoritos**: Salve partidas para acesso rápido

---

## 📜 Scripts Disponíveis

### Backend (`futmatch-nodejs`)

```bash
npm start              # Inicia servidor em produção
npm run dev            # Desenvolvimento com nodemon (auto-reload)
npm run simple         # Servidor simplificado (sem validações extras)
npm run dev-simple     # Servidor simplificado com nodemon
npm test               # Executa testes com Jest
npm run test-api       # Testa endpoints da API
npm run setup          # Script de configuração inicial
```

### Mobile (`futmatch-mobile`)

```bash
npm start              # Inicia Expo Dev Tools
npm run android        # Inicia no Android
npm run ios            # Inicia no iOS
npm run web            # Inicia no navegador
npm run start:clear    # Inicia limpando cache
npm run clean          # Limpa cache do Expo/Metro
npm run clean:all      # Limpa cache completo
npm run fix:windows    # Aplica correções para Windows
npm run patch:expo     # Aplica patches no Expo CLI
```

---

## 🧪 Testes

### Backend

```bash
cd futmatch-nodejs
npm test
```

Os testes incluem:
- Validação de modelos
- Testes de endpoints
- Testes de integração

### Teste Manual da API

```bash
cd futmatch-nodejs
npm run test-api
```

---

## 🔒 Segurança

### Implementações de Segurança

- ✅ **Validação de Dados**: Frontend e backend com Express Validator
- ✅ **Rate Limiting**: Proteção contra spam e ataques DoS
- ✅ **CORS**: Configurado adequadamente para produção
- ✅ **Helmet**: Headers de segurança HTTP
- ✅ **Sanitização**: Dados validados e sanitizados antes de salvar
- ✅ **Validação de Schema**: Mongoose valida todos os campos
- ✅ **Middleware de Erros**: Tratamento centralizado de erros

### Recomendações para Produção

1. Configure `CORS_ORIGIN` com domínios específicos (não use `*`)
2. Use variáveis de ambiente seguras (não commite `.env`)
3. Configure HTTPS/SSL
4. Implemente autenticação JWT (planejado)
5. Use MongoDB Atlas com IP whitelist
6. Configure rate limiting mais restritivo
7. Implemente logging e monitoramento

---

## 🚀 Deploy

### Backend (Heroku)

```bash
# Instale o Heroku CLI
heroku login

# Crie a aplicação
heroku create futmatch-api

# Adicione MongoDB Atlas
heroku config:set MONGODB_URI="sua-connection-string"

# Configure outras variáveis
heroku config:set NODE_ENV=production
heroku config:set PORT=80

# Faça deploy
git push heroku main
```

### Backend (Vercel)

```bash
# Instale o Vercel CLI
npm i -g vercel

# Configure
vercel

# Deploy em produção
vercel --prod
```

### Backend (Docker)

```dockerfile
FROM node:16-alpine
WORKDIR /app
COPY package*.json ./
RUN npm ci --only=production
COPY . .
EXPOSE 8080
CMD ["npm", "start"]
```

```bash
docker build -t futmatch-backend .
docker run -p 8080:8080 --env-file .env futmatch-backend
```

### Mobile

#### Expo Application Services (EAS)

```bash
cd futmatch-mobile

# Instale EAS CLI
npm install -g eas-cli

# Configure
eas login
eas build:configure

# Build para produção
eas build --platform android
eas build --platform ios

# Publique
eas update
```

#### Build Local (Android APK)

```bash
cd futmatch-mobile
npm run android -- --variant release
```

---

## 🛠️ Solução de Problemas

### Backend não inicia

- Verifique se o MongoDB está rodando
- Confirme a `MONGO_URI` no `.env`
- Verifique se a porta 8080 está disponível
- Veja os logs: `npm run dev`

### Mobile não conecta ao backend

- Verifique o IP no `src/config/api.js`
- Confirme que o backend está rodando
- Teste a URL no navegador: `http://<IP>:8080/api/matches`
- Desative firewall temporariamente para teste

### Erros no Expo/Metro

```bash
cd futmatch-mobile
npm run clean:all
npm install
npm run fix:windows  # Se estiver no Windows
npm start
```

### Cache do Expo

```bash
npm run start:clear
# ou
npm run clean
```

### Problemas no Windows

- Veja `SOLUCAO-ERRO-WINDOWS.md`
- Execute `npm run fix:windows`
- Execute `fix-expo-windows.js`

**Documentação adicional:**
- `COMO-EXECUTAR-CORRETO.md` - Guia detalhado de execução
- `COMO-RESOLVER-ERRO.md` - Soluções comuns
- `SOLUCAO-*.md` - Guias específicos de troubleshooting

---

## 🤝 Contribuindo

Contribuições são sempre bem-vindas! 

### Como Contribuir

1. **Fork** o projeto
2. Crie uma **branch** para sua feature (`git checkout -b feature/AmazingFeature`)
3. **Commit** suas mudanças (`git commit -m 'Add some AmazingFeature'`)
4. **Push** para a branch (`git push origin feature/AmazingFeature`)
5. Abra um **Pull Request**

### Padrões de Código

- Siga as convenções do JavaScript/Node.js/React Native
- Use ESLint/Prettier (se configurado)
- Adicione comentários quando necessário
- Mantenha o código limpo e legível
- Teste suas alterações
- Atualize a documentação se necessário

### Reportar Bugs

Abra uma [Issue](https://github.com/seu-usuario/FutMatch/issues) com:
- Descrição clara do problema
- Passos para reproduzir
- Comportamento esperado vs. atual
- Screenshots (se aplicável)
- Ambiente (OS, Node version, etc.)

---

## 📝 Licença

Este projeto está sob a licença **MIT**. Veja o arquivo `LICENSE` para mais detalhes.

```
MIT License

Copyright (c) 2024 FutMatch Team

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.
```

---

## 👥 Autores

- **FutMatch Team** - *Desenvolvimento inicial*

---

## 🗺️ Roadmap

### Próximas Funcionalidades

- [ ] Sistema de autenticação e autorização (JWT)
- [ ] Perfis de usuário
- [ ] Chat entre participantes
- [ ] Notificações push (mobile)
- [ ] Sistema de avaliações e reviews
- [ ] Histórico de partidas
- [ ] Integração com mapas (Google Maps/Mapbox)
- [ ] Pagamentos online
- [ ] Compartilhamento em redes sociais
- [ ] Modo offline no mobile
- [ ] Testes automatizados (E2E)
- [ ] CI/CD pipeline

---

## 🙏 Agradecimentos

- Comunidade de desenvolvedores Node.js e React Native
- Todos os contribuidores do projeto
- Usuários que testam e reportam bugs
- Mantenedores das bibliotecas open-source utilizadas

---

## 📞 Suporte

- **Issues**: [GitHub Issues](https://github.com/seu-usuario/FutMatch/issues)
- **Documentação**: Veja os arquivos `.md` na raiz do projeto
- **Email**: contato@futmatch.com (exemplo)

---

## 📚 Documentação Adicional

- `INICIO-RAPIDO.md` - Guia de início rápido
- `GUIA-RAPIDO.md` - Guia rápido de referência
- `COMO-EXECUTAR.md` - Instruções detalhadas de execução
- `COMO-EXECUTAR-CORRETO.md` - Guia corrigido e atualizado
- `INICIAR-BACKEND.md` - Como iniciar o backend
- `COMO-EXECUTAR-MOBILE.md` - Como executar o app mobile
- `COMO-INSTALAR-EXPO.md` - Instalação do Expo
- `COMO-RESOLVER-ERRO.md` - Solução de problemas
- `SOLUCAO-*.md` - Guias específicos de solução

---

<div align="center">

**Desenvolvido com ❤️ para a comunidade de futebol!** ⚽

⭐ Se este projeto foi útil, considere dar uma estrela!

[⬆ Voltar ao topo](#-futmatch)

</div>
