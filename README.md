# ⚽ FutMatch

Plataforma completa para organizar, encontrar e participar de partidas de futebol. Este repositório é um monorepo com backend/web em Node.js + MongoDB e aplicativo mobile em React Native (Expo).

---

## 📂 Estrutura
```
FutMatch/
├─ futmatch-nodejs/   # API + web (Express + MongoDB + frontend estático)
└─ futmatch-mobile/   # App mobile (Expo/React Native)
```

Docs adicionais úteis:
- `INICIO-RAPIDO.md`, `GUIA-RAPIDO.md`
- `COMO-EXECUTAR.md`, `COMO-EXECUTAR-CORRETO.md`, `INICIAR-BACKEND.md`
- `COMO-EXECUTAR-MOBILE.md`, `COMO-INSTALAR-EXPO.md`
- Guias de troubleshooting: `COMO-RESOLVER-ERRO.md`, `SOLUCAO-*.md`, `SOLUCAO-ERRO-WINDOWS.md`

---

## 🚀 Stack
- Backend/Web: Node.js 16+, Express, Mongoose, Helmet, CORS, Express-Validator, Rate Limiting
- Mobile: React Native 0.73 (Expo SDK 54), React Navigation, Async Storage, Linear Gradient, Location
- Banco: MongoDB (local ou Atlas)

---

## 🧭 Começando Rápido

### 1) Clonar
```bash
git clone https://github.com/seu-usuario/FutMatch.git
cd FutMatch
```

### 2) Backend + Web
```bash
cd futmatch-nodejs
npm install
cp env.example .env   # ou copie manualmente

# editar .env com sua URI do Mongo e porta
npm run dev           # desenvolvimento (nodemon)
# npm start           # produção
```
Acesse: `http://localhost:8080`

Variáveis principais (`futmatch-nodejs/.env`):
```
PORT=8080
MONGO_URI=mongodb://localhost:27017/futmatch
CORS_ORIGIN=*
CORS_METHODS=GET,POST,PUT,DELETE,OPTIONS
RATE_LIMIT_WINDOW_MS=900000
RATE_LIMIT_MAX_REQUESTS=100
```

### 3) Mobile (Expo)
Pré-requisitos: Node 18+, Android Studio ou app Expo Go.
```bash
cd futmatch-mobile
npm install
npm run patch:expo     # aplicado também no postinstall
npm run fix:windows    # recomendável no Windows
npm start              # abre o Expo Dev Tools
# ou: npm run android | npm run web
```
- Ajuste `src/config/api.js` para apontar o backend (`http://<seu-ip>:8080`).
- Se der erro no Metro/Expo, veja `SOLUCAO-*.md` e `fix-expo-windows.js`.

---

## 🔌 API (resumo)
Base: `http://localhost:8080/api`
```
GET    /matches             # listar partidas
GET    /matches/:id         # detalhes
POST   /matches             # criar
PUT    /matches/:id         # atualizar
DELETE /matches/:id         # excluir
POST   /matches/:id/join    # entrar na partida
GET    /matches/search      # filtros/busca
```

---

## 📜 Scripts úteis
### Backend (`futmatch-nodejs`)
- `npm run dev` – desenvolvimento com nodemon
- `npm start` – produção
- `npm test` – testes com Jest
- `npm run test-api` – smoke de endpoints

### Mobile (`futmatch-mobile`)
- `npm start` / `npm run android` / `npm run web`
- `npm run start:clear` – inicia limpando cache
- `npm run clean` / `npm run clean:all` – limpa caches Expo/Metro
- `npm run fix:windows` – ajustes para Windows

---

## 🧪 Testes
```bash
cd futmatch-nodejs
npm test
```

---

## 🤝 Contribuição
- Abra issues e PRs com uma descrição clara.
- Padrões: JavaScript/Node.js/React Native; mantenha código limpo e testado.
- Para novas features: `git checkout -b feature/sua-feature`, commit, PR.

---

## 🛠️ Dicas de solução de problemas
- Cache Expo/Metro: `npm run start:clear` (mobile) ou scripts `limpar-cache*.ps1`.
- Problemas no Windows: `SOLUCAO-ERRO-WINDOWS.md`, `fix-expo-windows.js`.
- Expo CLI quebrada: `patch-expo-cli.js` e `COMO-INSTALAR-EXPO.md`.
- Erros comuns do backend: ver `COMO-EXECUTAR-CORRETO.md` e logs do `npm run dev`.

---

## 📄 Licença
MIT — veja `LICENSE` (se disponível). Use, modifique e contribua com crédito.
