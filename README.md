# GoldWitch (casinowick)

Node.js / Express casino — deploy on **Railway** (not GitHub Pages).

## Deploy in 3 steps

### 1) Put this repo on GitHub
Use the full project (all folders). Do **not** only upload root files. Never commit `.env`.

### 2) Railway
1. [railway.app](https://railway.app) → **New Project**
2. **Add MySQL**
3. **Deploy from GitHub** → select this repo
4. Open the **web service** → **Variables** → add:

| Name | Value |
|---|---|
| `APP_NAME` | `GoldWitch.com` |
| `APP_ABBREVIATION` | `GoldWitch` |
| `APP_SECURE` | `false` |
| `APP_ENV` | `production` |
| `SESSION_SECRET` | any long random string |

MySQL variables (`MYSQLHOST`, `MYSQLUSER`, …) are usually linked automatically from the MySQL plugin.

On boot the app **creates the database, migrates tables, and starts**.

### 3) After first deploy
1. Copy your public URL (`https://….up.railway.app`)
2. Set variable `APP_URL` to that URL → redeploy
3. Point Drakon / PayPal callbacks to that same domain

## Local (optional)

```bash
cp .env.example .env
npm install
npm run init
npm run build
npm run start:local
```

## Important
`*.github.io` = GitHub Pages = **README only**. Your live casino URL comes from **Railway**.
