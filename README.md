<div align="center">

# JARVIS OS

**Infrastructure d'Intelligence Artificielle Distribuée et Souveraine**  
**Cluster Multi-Machines · Zero-Cloud · On-Premise · RGPD Natif**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![CI](https://github.com/Turbo31150/jarvis-linux/actions/workflows/ci.yml/badge.svg)](https://github.com/Turbo31150/jarvis-linux/actions/workflows/ci.yml)
[![Python](https://img.shields.io/badge/Python-3.11+-3776AB?logo=python&logoColor=white)](https://python.org)
[![CUDA](https://img.shields.io/badge/CUDA-Enabled-76B900?logo=nvidia&logoColor=white)](https://developer.nvidia.com/cuda-zone)
[![React](https://img.shields.io/badge/React-19-61DAFB?logo=react&logoColor=black)](https://react.dev)
[![Docker](https://img.shields.io/badge/Docker-Swarm-2496ED?logo=docker&logoColor=white)](https://docs.docker.com/engine/swarm/)

*Un système d'orchestration agentique 100 % local — de l'interface vocale temps réel au trading haute fréquence automatisé — sans aucune dépendance cloud.*

**Créé par [Franck Delmas](https://www.linkedin.com/in/franck-delmas-80bb231b1/) · Toulouse**

</div>

---

## Résumé Exécutif

**JARVIS OS** est un écosystème d'IA distribuée et souveraine conçu pour libérer les entreprises de leur dépendance au cloud (OpenAI, Azure, AWS). Il orchestre un cluster de cinq machines spécialisées, 249 agents publics autonomes et ~1 000 handlers MCP actifs, offrant une interface vocale à moins de 300 ms de latence, un moteur de décision par consensus multi-IA et un système de trading algorithmique haute précision.

L'ensemble des communications inter-nœuds transite exclusivement via `127.0.0.1` — architecture **Zero-Cloud**, sécurité de niveau militaire, conformité RGPD native.

### Indicateurs clés (banc de test personnel)

| Indicateur | Mesure |
|---|---|
| 🤖 **Agents autonomes publics** | 249 agents (96 patterns OpenClaw) |
| 🧠 **Handlers MCP actifs** | ~1 000 handlers (`v1/chat/completions`) |
| 🎙️ **Latence vocale** | < 300 ms (streaming continu, Whisperflow CUDA) |
| 📝 **Latence transcription** | < 2 s (inférence GPU, modèle Whisper distil) |
| 🗣️ **Commandes vocales** | 2 658 reconnues nativement |
| 🔗 **Chaînes Domino** | 835 workflows d'auto-réparation |
| 📈 **Consensus trading** | Vote 6 modèles LLM → MEXC Futures |
| ⏱️ **Uptime validé** | 99 jours continus |
| 🔐 **Chiffrement** | AES-256 (SQLCipher) sur toutes les bases |

---

## Architecture du Cluster

```
┌──────────────────────────────────────────────────────────────────┐
│                         JARVIS OS CLUSTER                        │
│                    (Zero-Cloud · 127.0.0.1 only)                 │
│                                                                  │
│  M1 — Master          M2 — Worker         M3 — Server           │
│  Orchestration         Inférence           Persistance           │
│  MCP · Whisperflow     LLM locaux          SQLCipher AES256      │
│  602 handlers          LM Studio           Git · Backups         │
│  <300ms latence        5 GPUs pooling      Chiffrement end2end   │
│                                                                  │
│  M4 — Automation       M5 — Interface                           │
│  n8n · DERNI           React 19 · Electron                      │
│  MEXC Futures          Dashboard Cyberpunk                      │
│  Trading algo          WebSocket temps réel                     │
└──────────────────────────────────────────────────────────────────┘
         ↕ Tous les flux : ws://127.0.0.1 uniquement ↕
```

### Description des nœuds

| Nœud | Rôle | Technologies clés |
|---|---|---|
| **M1** Master | Orchestration cognitive, pipeline vocal | MCP 602 handlers, Whisperflow CUDA, routage agents |
| **M2** Worker | Inférence LLM locale | LM Studio, Ollama, Docker, pool GPU dynamique |
| **M3** Server | Persistance & gouvernance des données | SQLCipher AES256, Git versioning, backups chiffrés |
| **M4** Automation | Trading algo, scripts, automatisation | n8n (32 nœuds), DERNI ULTIMATE, MEXC Futures API |
| **M5** Interface | UI utilisateur, contrôle cluster | React 19, Vite 6, Electron, WebSockets temps réel |

---

## Stack Cognitif — 9 Couches

| # | Couche | Technologies |
|---|---|---|
| 1 | **Hardware** | Cluster multi-GPU Linux + Windows, 5 GPUs mutualisés |
| 2 | **OS** | Ubuntu/Debian optimisé + Windows hybride + kernel params |
| 3 | **Data** | SQLite3 distribué `BASE-SQL3-COMMUNE`, SQLCipher AES256 |
| 4 | **Inference** | LM Studio, Ollama, CUDA, load balancing dynamique |
| 5 | **Protocol** | MCP (Model Context Protocol) — 602 handlers standardisés |
| 6 | **Agents** | 249 agents publics (OpenClaw 96 patterns) + agents internes |
| 7 | **Orchestration** | Claude Agent SDK, JARVIS Core, consensus multi-IA |
| 8 | **Pipeline** | Domino Chains — 835 workflows n8n + Python asyncio |
| 9 | **Interface** | Whisperflow CUDA temps réel + Dashboard WebSocket Cyberpunk |

---

## Agents Spécialisés

| Agent | Modèle | Temp / Top_P | Spécialisation |
|---|---|---|---|
| `ia-deep` | Qwen3-30B | 1.3 | Raisonnement complexe, analyse codebase, refactoring |
| `ia-fast` | Qwen2.5-7B | 1.0 | Inférence rapide, routage d'intentions, complétion |
| `ia-check` | Mistral-7B | 0.8 | Audit de code, validation syntaxe, détection régressions |
| `ia-trading` | FinLlama-13B | 1.0 | Analyse quantitative, signaux marché crypto |
| `ia-system` | Phi3-Mini | 0.7 | Monitoring cluster, diagnostic thermique, uptime |
| `ia-bridge` | Gemini-Flash | 0.9 | Seul agent autorisé à accéder au web externe |
| `ia-consensus` | Agrégateur natif | N/A | Arbitrage et pondération des votes multi-IA |

---

## Moteur de Consensus Multi-IA

Lorsqu'une décision critique est requise, `ia-consensus` interroge en parallèle les agents workers et applique une matrice de pondération :

```
Consensus FORT   (Score ≥ 0.66)  →  🟢  Action exécutée automatiquement
Consensus MOYEN  (Score ≥ 0.40)  →  🟠  Contre-évaluation ou vérification humaine
Consensus FAIBLE (Score  < 0.40)  →  🔴  Rejet + journalisation dans la stack d'audit
```

---

## Pipeline Vocal — Whisperflow CUDA

Contrairement aux architectures classiques (mode batch), Whisperflow implémente un **streaming continu** via WebSockets inversés :

```
[ Microphone ]
      │ (flux audio PCM continu)
      ▼
[ WebSocket ws://127.0.0.1:8181/ws ]
      │
      ▼
[ Whisperflow CUDA — Nœud M1 ]  →  latence transcription < 2s
      │
      ▼
[ Analyseur lexical (SequenceMatcher / Jaccard, seuil ≥ 0.75) ]
      │
      ▼
[ Cascade Domino → n8n / MCP Handlers ]  →  latence totale < 300ms
```

- 2 658 commandes vocales reconnues nativement
- Déclenchement instantané sans transition CLI
- 835 chaînes Domino activables par la voix

---

## Système de Trading — DERNI ULTIMATE

Opéré sur M4 via une instance n8n conteneurisée (32 nœuds d'exécution logique) sur les marchés MEXC Futures :

| Cycle | Fréquence | Action |
|---|---|---|
| **SCAN global** | Toutes les 30s | Filtre les paires avec volume 24h > 1 000 000 USDT |
| **SIGNAL** | Toutes les 5 min | Calcul BREAKOUT / REVERSAL / BOUNCE / MOMENTUM + FVG — seuil ≥ 70/100 |
| **ANCRAGE** | Toutes les 15s | Alignement `high24Price` / `lower24Price` pour optimiser le spread |
| **PROTECTION** | Latence 10s | Placement automatique TP/SL dès confirmation d'ordre |

**Niveaux de sortie :**
- TP1 : +1.5% (sécurisation partielle)
- TP2 : +3.0% (prise de profit intermédiaire)
- TP3 : +7.0% (cible de tendance)
- SL : -1.2% (invalidation stricte de structure)

---

## Déploiement Plug-and-Play

Le système est livré préconfiguré avec une optimisation de base à 64 % :

```bash
# Prérequis : Ubuntu 22.04+, Python 3.11+, CUDA 11.8+, Docker
git clone https://github.com/Turbo31150/jarvis-linux.git
cd jarvis-linux
pip install -r requirements.txt
cp .env.example .env       # Configurer les variables locales
make install               # Détection matériel + activation agents
```

**Processus automatique :**
1. Détection du matériel disponible
2. Adaptation des paramètres (CPU-only → multi-GPU)
3. Activation des agents et outils communs
4. Vérification de la connectivité inter-nœuds
5. Mise à disposition immédiate des fonctionnalités

> Scalable d'un laptop CPU jusqu'à un cluster multi-GPU. Minimum recommandé : 1× NVIDIA GPU (8 GB VRAM) pour le mode agent complet.

---

## Sécurité & Auto-Healing

### Sécurité
- **Réseau fermé** : `127.0.0.1` exclusivement — `localhost` contractuellement banni (risque DNS)
- **Chiffrement** : SQLCipher AES-256 sur toutes les bases (config, journaux, mémoires agents)
- **MCP handlers** : 602 points d'accès standardisés — les agents ne font que ce qu'on leur autorise
- **Authentication** : `tokenMode: notRequired` (réseau local isolé uniquement)

### Auto-Healing
- **Monitoring thermique** : Alerte à 75°C · Unload automatique à 85°C (via Ollama / LM Studio API)
- **Surveillance asyncio** : Boucles Python toutes les 5 min — redémarrage silencieux des nœuds en erreur
- **Réallocation GPU** : Distribution dynamique de la charge entre les nœuds disponibles
- **Synchronisation** : Réplication des sauvegardes en temps réel sur tous les nœuds

---

## Interface Utilisateur (M5)

- **Framework** : React 19 + Vite 6, packagé Electron
- **Design** : Esthétique Cyberpunk haute densité — métriques GPU/CPU temps réel
- **Transport** : WebSockets `ws://127.0.0.1` — synchronisation instantanée du cluster
- **Multi-OS** : Fonctionne sous Linux et Windows (hybride)

---

## Comparaison — Cloud vs JARVIS OS

| Critère | Cloud IA (OpenAI / Azure) | JARVIS OS |
|---|---|---|
| **Coût à l'échelle** | Variable (jusqu'à 500k€/an) | Fixe (matériel + maintenance) |
| **Souveraineté** | Données sur serveurs US (CLOUD Act) | 100% on-premise, RGPD natif |
| **Latence vocale** | 800 ms – 2 secondes | < 300 ms |
| **Agents simultanés** | Limité par quotas API | 249+ agents natifs autonomes |
| **Auditabilité** | Boîte noire opaque | Transparence totale + logs |
| **Déploiement** | SaaS managed | Plug-and-play sur votre matériel |
| **Auto-réparation** | Non | Oui (asyncio + monitoring) |
| **Portabilité** | Cloud only | Windows / Linux hybride |

---

## Roadmap

- [ ] **Scalabilité** — Ajout simplifié de nœuds M6, M7 (auto-discovery)
- [ ] **Modularité** — Load-ready dynamique selon la charge en temps réel
- [ ] **Indépendance absolue** — Suppression de toute dépendance non maîtrisée
- [ ] **Whisper GPU M5** — Migration complète distil-large-v3 CUDA (en cours)
- [ ] **SSH inter-machines** — Automation complète M1↔M2↔M4↔M5
- [ ] **Backup SQL auto** — Cron quotidien chiffré sur M3
- [ ] **Dashboard unifié** — Conky `jarvis-main.conf` + métriques cluster WebSocket

---

## Présentation & Démo

Le dossier [`demo/`](demo/) rassemble le **dossier de présentation professionnel complet** —
captures réelles de production, en local, zéro cloud. Voir l'[**index complet des livrables**](demo/).

### ⚡ Actions rapides

| Je veux… | Ouvrir |
|---|---|
| 📊 **Voir les graphiques** (audit + benchmarks) | [`demo/rapport-visuel.html`](demo/rapport-visuel.html) |
| 📕 **Lire le dossier complet** (6 sections) | [`demo/pack/PACK_PRESENTATION.pdf`](demo/pack/PACK_PRESENTATION.pdf) |
| 🔍 **Vérifier les chiffres** (traçabilité) | [`demo/pack/AUDIT_COHERENCE.pdf`](demo/pack/AUDIT_COHERENCE.pdf) |
| 🎬 **Pipeline vidéo** (flux, skill, scripts) | [`demo/PIPELINE-DEMO-VIDEO.html`](demo/PIPELINE-DEMO-VIDEO.html) |
| 🎞️ **Storyboard** (Linux → aujourd'hui) | [`demo/pack/STORYBOARD-COMPLET.pdf`](demo/pack/STORYBOARD-COMPLET.pdf) |
| 📣 **Distribuer / publier** (formats réseaux) | [`demo/pack/DISTRIBUTION-MONTAGE-IA.pdf`](demo/pack/DISTRIBUTION-MONTAGE-IA.pdf) |
| 🗣️ **Script de narration** | [`demo/narration-scene-complete.txt`](demo/narration-scene-complete.txt) |

### Chiffres vérifiés (banc interne complet)

Triade d'agents emboîtée **961 / 1 354 / 1 435** · Benchmarks constants : **4 413** appels ·
**99,6 %** succès · **~1,1 s** latence médiane · **51 tok/s** · WER **10,51 %**.
Traçabilité complète dans l'[audit de cohérence](demo/pack/AUDIT_COHERENCE.pdf).

---

## Utilisation & Normes

- **Zero-Cloud** — toutes les communications inter-nœuds transitent par `127.0.0.1`, aucune donnée ne quitte le parc.
- **RGPD natif** — hébergement on-premise, souveraineté totale des données, zéro sous-traitant cloud.
- **Licence MIT** — code réutilisable librement, voir [LICENSE](LICENSE).
- **Reproductibilité** — chiffres figés sur le décompte vérifié, chaque total traçable en une commande (cf. audit).
- **0 jeton facturé** — modèles locaux (qwen3.5-9b via LM Studio) + cascade de secours gratuite.

---

## Structure du Projet

```
jarvis-linux/
├── core/          # Orchestration centrale, MCP, consensus
├── scripts/       # Scripts système, PTT vocal, auto-healing
├── modules/       # Agents spécialisés (trading, voice, system)
├── infra/         # Docker, systemd, déploiement cluster
├── docs/          # Documentation technique
├── tests/         # Tests d'intégration et de performance
├── .github/       # CI/CD, dependabot
└── PRESENTATION.md # Présentation professionnelle complète
```

---

## Licence

Ce projet est distribué sous licence **MIT**. Voir [LICENSE](LICENSE).

---

## Contact

**Franck Delmas** — CTO & Architecte Systèmes IA  
🔗 LinkedIn : [franck-delmas-80bb231b1](https://www.linkedin.com/in/franck-delmas-80bb231b1/)  
🐙 GitHub : [@Turbo31150](https://github.com/Turbo31150)  
📧 Email : miningexpert31@gmail.com
