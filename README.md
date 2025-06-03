# Nested Module Federation Example

This project demonstrates **nested module federation** using Webpack 5.  
It includes four independent apps where modules are consumed both directly and indirectly:

- **Dashboard** (main host)
- **Kiwi** (remote consumed by Dashboard)
- **Image Caption** (remote consumed by Kiwi)
- **Hello World** (remote consumed by Dashboard)

## 🔗 Federation Graph

```
Dashboard
├── Kiwi
│ └── Image Caption
└── Hello World
```

---

## 📁 Project Structure

```
├── dashboard
├── kiwi
├── image-caption
└── hello-world
```

Each folder is an independent Webpack module federation project with its own development and production configs.

---

## 📦 Setup

Install dependencies for all projects:

```bash
cd dashboard && npm install
cd ../kiwi && npm install
cd ../image-caption && npm install
cd ../hello-world && npm install
```

## 🚀 Running Projects

🛠 Development Mode (Recommended)

Start each app in this order (each in a separate terminal):

```bash
# Terminal 1
cd image-caption
npm run dev

# Terminal 2
cd ../kiwi
npm run dev

# Terminal 3
cd ../hello-world
npm run dev

# Terminal 4
cd ../dashboard
npm run dev
```

Then open:
📍 http://localhost:9000

📦 Production Mode (Build & Serve)
Run the following to simulate a full production build:

```bash
cd image-caption && npm run build && npm start
cd ../kiwi && npm run build && npm start
cd ../hello-world && npm run build && npm start
cd ../dashboard && npm run build && npm start
```

Then open:
📍 http://localhost:9000

## 🧩 Scripts

Each project includes:

npm run dev – Development mode with hot reload (webpack-dev-server)

npm run build – Production build (webpack)

npm start – Serve production build via Express

## 🛠 Tech Stack

Webpack 5

Module Federation Plugin

Express

Sass (SCSS)

HTML Webpack Plugin

Mini CSS Extract Plugin

Babel

## ✅ Tips

Run all remotes before running the dashboard (host).

Use npm run dev for development with faster feedback and HMR.

Use npm run build && npm start for testing final builds.

Each app should expose and consume modules via ModuleFederationPlugin.
