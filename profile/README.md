<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://projet-resurgence.fr/images/banner.webp">
  <source media="(prefers-color-scheme: light)" srcset="https://projet-resurgence.fr/images/banner.webp">
  <img alt="Projet Résurgence — Bannière" src="https://projet-resurgence.fr/images/banner.jpg" width="100%">
</picture>

<div align="center">

# 🌍 Projet Résurgence

### *Serveur RP Géopolitique Post-Apocalyptique — An 2303*

[![Site Web](https://img.shields.io/badge/🌐_Site_Web-projet--resurgence.fr-0d1117?style=for-the-badge&labelColor=161b22)](https://projet-resurgence.fr)
[![Discord](https://img.shields.io/badge/💬_Discord-Rejoindre-5865F2?style=for-the-badge&labelColor=161b22)](https://discord.projet-resurgence.fr)
[![Carte Interactive](https://img.shields.io/badge/🗺️_Carte-Interactive-2ea043?style=for-the-badge&labelColor=161b22)](https://map.projet-resurgence.fr)
[![Documentation pour les Développeurs](https://img.shields.io/badge/📚_Docs-En_Ligne-f78166?style=for-the-badge&labelColor=161b22)](https://docs.projet-resurgence.fr)

---

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=22&duration=3000&pause=1000&color=58A6FF&center=true&vCenter=true&multiline=true&repeat=true&width=700&height=100&lines=Le+monde+tel+que+nous+le+connaissions+n'existe+plus.;Des+cendres+de+l'ancien+monde%2C+de+nouvelles+nations+%C3%A9mergent.;L'an+2303.+L'humanit%C3%A9+se+reconstruit." alt="Typing animation" />

</div>

---

## ⚡ L'Univers

> **An 2303.** Après une catastrophe planétaire, les vestiges de l'Humanité se réorganisent.
> De nouvelles nations émergent, forgent des alliances, se disputent des territoires et reconstruisent la civilisation.
> Chaque décision compte — diplomatie, économie, guerre — dans un monde où tout est à refaire.

<div align="center">
<table>
<tr>
<td align="center" width="200">

🏛️<br>**Gouvernements**<br><sub>Créez votre nation,<br>nommez vos ministres</sub>

</td>
<td align="center" width="200">

💰<br>**Économie**<br><sub>PIB, inflation,<br>commerce mondial</sub>

</td>
<td align="center" width="200">

⚔️<br>**Militaire**<br><sub>Armées, doctrines,<br>champs de bataille</sub>

</td>
<td align="center" width="200">

🗺️<br>**Territoires**<br><sub>Carte interactive,<br>conquête & contrôle</sub>

</td>
<td align="center" width="200">

🤝<br>**Diplomatie**<br><sub>Traités, alliances,<br>points diplomatiques</sub>

</td>
</tr>
</table>
</div>

---

## 🏗️ Architecture Technique

Toute l'infrastructure tourne sous **Docker** sur un VPS, orchestrée par un monorepo :

```
┌─────────────────────────────────────────────────────────────────┐
│                         NGINX (reverse proxy + SSL)             │
├──────────┬──────────┬──────────┬──────────┬──────────┬──────────┤
│  PAPA    │ GameAPI  │ OnlineMap│ Kanbanizer│ DocsHub  │ TechPanel│
│ (Admin)  │ (REST)   │ (Carte)  │ (Kanban)  │ (Docs)   │ (Tech)   │
├──────────┴──────────┴──────────┴──────────┴──────────┴──────────┤
│                      PostgreSQL 16                               │
├──────────┬──────────┬──────────────────────────────────────────  │
│  C.L.E.A │  M.A.R.C │  GeoJSON Listener  │  LLM Chat Wrapper   │
│  (Bot)   │  (Bot)   │  (Worker)           │  (AI)               │
└──────────┴──────────┴─────────────────────┴─────────────────────┘
```

<div align="center">

| Couche | Technologies |
|:---:|:---|
| 🌐 **Frontend** | HTML/CSS/JS · Vite · Maplib · Nginx |
| ⚙️ **Backend** | Python · Flask · SQLAlchemy · discord.py |
| 🗃️ **Base de données** | PostgreSQL 16 · Alembic (migrations) |
| 🤖 **Bots Discord** | C.L.E.A (gameplay) · M.A.R.C (gamemaster) |
| 🗺️ **Cartographie** | MapLib (C++/pybind11) · OpenMP |
| 📦 **Infra** | Docker · Docker Compose · GHCR · Let's Encrypt |

</div>

---

## 📂 Nos Repos

<div align="center">

| Repo | Description | Stack |
|:---|:---|:---:|
| [`ProjetResurgence`](https://github.com/Projet-Resurgence/ProjetResurgence) | 🏠 Monorepo & infra (docker-compose, nginx, CI/CD) | Docker |
| [`CLEA`](https://github.com/Projet-Resurgence/CLEA) | 🤖 Bot Discord principal — économie, armées, construction | Python |
| [`MARC`](https://github.com/Projet-Resurgence/MARC) | 🎮 Bot Discord Gamemaster — gestion du temps, événements | Python |
| [`GameAPI`](https://github.com/Projet-Resurgence/GameAPI) | ⚙️ API REST du jeu | Flask |
| [`PAPA`](https://github.com/Projet-Resurgence/PAPA) | 🛡️ Panel d'administration | Flask |
| [`Bots-Commons`](https://github.com/Projet-Resurgence/Bots-Commons) | 📦 Bibliothèque partagée (ORM, utils, currency) | Python |
| [`MapLib`](https://github.com/Projet-Resurgence/MapLib) | 🗺️ Moteur de rendu cartographique C++ | C++ / pybind11 |
| [`OnlineMap`](https://github.com/Projet-Resurgence/OnlineMap) | 🌍 Carte interactive web | Vite / Leaflet |
| [`Kanbanizer`](https://github.com/Projet-Resurgence/Kanbanizer) | 📋 Tableau Kanban interne | Flask |
| [`Docs-Hub`](https://github.com/Projet-Resurgence/Docs-Hub) | 📚 Documentation en ligne | Flask |
| [`TechPanel`](https://github.com/Projet-Resurgence/TechPanel) | 🔬 Panel des technologies | Flask |
| [`LLMChatWrapper`](https://github.com/Projet-Resurgence/LLMChatWrapper) | 🧠 Wrapper AI / LLM | Python |
| [`WebCalculator`](https://github.com/Projet-Resurgence/WebCalculator) | 🧮 Calculateur économique web | Flask |
| [`WebAuth-Handler`](https://github.com/Projet-Resurgence/WebAuth-Handler) | 🔐 Authentification Discord OAuth2 | Flask |
| [`projet-resurgence.github.io`](https://github.com/Projet-Resurgence/projet-resurgence.github.io) | 🌐 Site vitrine | HTML/CSS/JS |

</div>

---

## 🔗 Liens Rapides

<div align="center">

| Service | URL |
|:---:|:---:|
| 🌐 Site vitrine | [`projet-resurgence.fr`](https://projet-resurgence.fr) |
| 🛡️ Admin Panel | [`admin.projet-resurgence.fr`](https://admin.projet-resurgence.fr) |
| ⚙️ API | [`api.projet-resurgence.fr`](https://api.projet-resurgence.fr) |
| 🗺️ Carte | [`map.projet-resurgence.fr`](https://map.projet-resurgence.fr) |
| 📚 Documentation | [`docs.projet-resurgence.fr`](https://docs.projet-resurgence.fr) |
| 📋 Kanban | [`kanban.projet-resurgence.fr`](https://kanban.projet-resurgence.fr) |
| 🧮 Calculateur | [`calc.projet-resurgence.fr`](https://calc.projet-resurgence.fr) |
| 🔬 Tech Panel | [`tech.projet-resurgence.fr`](https://tech.projet-resurgence.fr) |

</div>

---

<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=14&duration=4000&pause=2000&color=8b949e&center=true&vCenter=true&repeat=true&width=500&lines=Fait+avec+%E2%98%95+et+de+la+d%C3%A9termination+post-apocalyptique" alt="Footer" />

<sub>© 2025-2026 Projet Résurgence — Tous droits réservés</sub>

</div>
