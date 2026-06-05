# JARVIS OS — Présentation Professionnelle

> *Document de présentation pour recruteurs, clients et partenaires techniques.*  
> *Franck Delmas · CTO & Architecte Systèmes IA · Toulouse*

---

## Qui suis-je ?

Autodidacte « production-first », je conçois et déploie depuis plusieurs années des infrastructures d'IA **100 % locales et souveraines** (on-premise), pensées pour la confidentialité des données et la conformité RGPD.

Mon approche : ne jamais dépendre d'un fournisseur cloud externe pour les traitements sensibles. Chaque composant que je construis tourne sur du matériel maîtrisé, avec un code auditable.

---

## JARVIS OS — Ce que j'ai réellement construit

JARVIS OS est un **écosystème d'orchestration multi-agents** que je développe et exploite sur mon propre cluster GPU. Ce n'est pas une démonstration ou un proof-of-concept : c'est un système en production continue, que j'utilise quotidiennement.

### Ce qui est démontrable et publié

| Composant | Dépôt / Description |
|---|---|
| **Orchestration centrale** | `jarvis-core` — routing MCP, consensus multi-LLM, agent factory |
| **Cluster GPU** | `jarvis-cluster` — load balancing, failover, health monitoring |
| **Voice pipeline** | `jarvis-whisper-flow` — STT/TTS on-premise, Whisper CUDA < 300ms |
| **Toolkit MCP** | `jarvis-mcp-toolkit` — 835 handlers standardisés |
| **Browser automation** | `jarvis-browser-mcp` — CDP, scraping, publication sociale |
| **Trading** | `TradeOracle` — signaux crypto, backtests, MEXC Futures |
| **Applications** | `passcerfa-site`, `babysmart-platform` — produits finaux intégrés |

### Architecture technique

- **Cluster** : 3 nœuds GPU actifs (M1, M2, M5) + 1 nœud Windows (M4)
- **Modèles locaux** : Qwen3.5, DeepSeek-R1, Gemma, Mistral, Phi3 via LM Studio/Ollama
- **Protocole** : Model Context Protocol (MCP) — standard ouvert Anthropic
- **Consensus** : Vote multi-modèles pour les décisions critiques (trading, déploiement)
- **Auto-healing** : Détection et redémarrage automatique des modules en erreur
- **Sécurité** : Réseau fermé (127.0.0.1), chiffrement AES-256, RGPD by design

---

## Compétences démontrées dans le code

| Domaine | Technologies |
|---|---|
| **Architectures multi-agents** | MCP, Claude Agent SDK, consensus LLM |
| **Inférence locale** | LM Studio, Ollama, CUDA, quantification GGUF |
| **Cluster Linux multi-GPU** | Docker Swarm, systemd, NVIDIA drivers |
| **Voice & Audio** | Whisper (distil-large-v3), Piper TTS, pipewire |
| **Automatisation** | n8n, Playwright, CDP, Python scripting |
| **Backend** | Python 3.11+, SQLite3, PostgreSQL, Redis |
| **Frontend** | React 19, Electron, WebSockets, Conky/Lua |
| **Souveraineté & RGPD** | Architecture zero-cloud, données locales |

---

## Ce que je propose

### Pour un recruteur (CDI / Freelance)

Architecte systèmes IA disponible pour des missions de :
- Conception d'infrastructures IA on-premise (alternative cloud)
- Orchestration multi-agents et automatisation complexe
- Intégration de LLM locaux dans des workflows métier
- Conseil en souveraineté numérique et conformité RGPD

### Pour un client / partenaire

Je peux déployer une version de JARVIS OS adaptée à vos besoins :
- Infrastructure IA clé-en-main sur votre matériel
- Migration depuis des solutions cloud coûteuses
- Formation et accompagnement technique

---

## Métriques de production (banc de test personnel)

Ces chiffres sont mesurés sur mon cluster en conditions réelles :

- **~1 000 agents** MCP actifs en parallèle
- **< 300 ms** de latence vocale bout-en-bout (Whisper CUDA streaming)
- **2 658 commandes** vocales reconnues nativement
- **835 chaînes Domino** d'exécution auto-réparantes
- **6 modèles LLM** votant en consensus pour les décisions trading

> Ces métriques reflètent mon environnement de développement (cluster maison). Les performances sur infrastructure client dépendent du matériel disponible.

---

## Liens

- **GitHub** : [github.com/Turbo31150](https://github.com/Turbo31150)
- **Repository principal** : [jarvis-linux](https://github.com/Turbo31150/jarvis-linux)
- **LinkedIn** : [Franck Delmas](https://www.linkedin.com/in/franck-delmas-80bb231b1/)
- **Email** : miningexpert31@gmail.com

---

*Licence MIT — Code source disponible sur GitHub*
