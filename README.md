# ⚽ FutMatch

Sistema completo de gerenciamento de partidas de futebol com aplicativo mobile React Native (Expo) e backend Node.js.

## 📋 Sobre o Projeto

O **FutMatch** é uma aplicação completa para gerenciamento de partidas de futebol, permitindo que jogadores criem, busquem e participem de partidas. Desenvolvido com React Native (Expo) para mobile e Node.js/Express para backend.

## ✨ Funcionalidades

- ✅ **CRUD Completo de Partidas** - Criar, visualizar, editar e excluir partidas
- ✅ **Sistema de Participação** - Entrar em partidas com controle de vagas
- ✅ **Busca e Filtros** - Buscar por localização, tipo e data
- ✅ **Sistema de Favoritos** - Salvar partidas favoritas
- ✅ **Interface Responsiva** - Design moderno e intuitivo
- ✅ **API REST Completa** - Backend robusto com validação

## 🏗️ Estrutura do Projeto

```
FutMatch/
├── futmatch-nodejs/        # Backend Node.js/Express
│   ├── controllers/        # Controladores da API
│   ├── services/           # Lógica de negócio
│   ├── models/             # Modelos MongoDB
│   ├── routes/             # Rotas da API
│   ├── public/             # Frontend web (HTML/CSS/JS)
│   └── server.js           # Servidor Express
│
├── screens/                # Telas do app mobile
├── components/             # Componentes React Native
├── config/                 # Configurações
├── App.js                  # Componente principal
└── package.json            # Dependências do Expo
```

## 🚀 Como Executar

### Pré-requisitos

- **Node.js** 16+ instalado
- **MongoDB** rodando (local ou MongoDB Atlas)
- **Expo Go** instalado no celular ([Android](https://play.google.com/store/apps/details?id=host.exp.exponent) | [iOS](https://apps.apple.com/app/expo-go/id982107779))

### 1. Instalar Dependências

```bash
# Instalar dependências do app mobile
npm install

# Instalar dependências do backend
cd futmatch-nodejs
npm install
cd ..
```

### 2. Configurar Backend

```bash
cd futmatch-nodejs

# Copiar arquivo de exemplo
cp env.example .env

# Editar .env com suas configurações
# MongoDB URI, porta, etc.
```

### 3. Iniciar Backend

```bash
cd futmatch-nodejs
npm start
```

O backend estará rodando em `http://localhost:8080`

### 4. Configurar IP da API (IMPORTANTE!)

**Para testar no celular físico**, você precisa usar seu IP local:

1. Descubra seu IP:
   ```bash
   # Windows
   ipconfig
   
   # Mac/Linux
   ifconfig
   ```

2. Edite `config/api.js`:
   ```javascript
   // Para dispositivo físico Android/iOS, use seu IP:
   return 'http://192.168.1.100:8080/api'; // Substitua pelo seu IP
   
   // Para emulador Android, use:
   return 'http://10.0.2.2:8080/api';
   
   // Para simulador iOS, use:
   return 'http://localhost:8080/api';
   ```

### 5. Iniciar Expo

```bash
npm start
```

### 6. Escanear QR Code

1. Abra o app **Expo Go** no celular
2. Escaneie o QR code que aparece no terminal
3. O app será carregado!

## 📱 Comandos Disponíveis

```bash
# Mobile (raiz do projeto)
npm start          # Inicia Expo (gera QR code)
npm run android    # Abre emulador Android
npm run ios        # Abre simulador iOS (Mac)
npm run web        # Abre no navegador

# Backend (pasta futmatch-nodejs)
npm start          # Inicia servidor
npm run dev        # Inicia com nodemon (auto-reload)
```

## 🔧 Configuração da API

O arquivo `config/api.js` controla a URL da API. Configure conforme sua plataforma:

- **Emulador Android**: `http://10.0.2.2:8080/api` (já configurado)
- **Simulador iOS**: `http://localhost:8080/api` (já configurado)
- **Dispositivo Físico**: `http://SEU_IP:8080/api` (você precisa configurar)

## 🐛 Solução de Problemas

### Erro "Unexpected token '<'"

Isso acontece quando a API retorna HTML em vez de JSON:

1. Verifique se o backend está rodando: `http://localhost:8080/api/matches`
2. Configure o IP correto em `config/api.js`
3. Certifique-se de que celular e computador estão na mesma rede Wi-Fi

### Erro "Network request failed"

1. Verifique se o backend está rodando
2. Confirme o IP em `config/api.js`
3. Verifique se o firewall não está bloqueando a porta 8080

### Expo não encontra módulos Node.js

O arquivo `metro.config.js` já está configurado para excluir a pasta `futmatch-nodejs`. Se ainda houver problemas:

```bash
# Limpar cache e reinstalar
rm -rf node_modules
npm cache clean --force
npm install
```

## 🛠️ Tecnologias Utilizadas

### Mobile
- React Native
- Expo
- React Navigation
- AsyncStorage

### Backend
- Node.js
- Express.js
- MongoDB/Mongoose
- CORS, Helmet, Rate Limiting

## 📝 Licença

MIT License

## 👥 Autor

FutMatch Team

---

**Desenvolvido com ❤️ para a comunidade de futebol!** ⚽
