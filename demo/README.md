<div align="center">

# JARVIS OS — Présentation & Démo

**Dossier de présentation professionnel complet** — captures réelles de production, en local, zéro cloud.

*Généré automatiquement · dossier `demo/` · M1 · 17/07/2026*

</div>

---

## ⚡ Actions rapides

| Je veux… | Ouvrir |
|---|---|
| 📊 **Voir les graphiques** (audit + benchmarks) | [`rapport-visuel.html`](rapport-visuel.html) |
| 📕 **Lire le dossier complet** (6 sections) | [`pack/PACK_PRESENTATION.pdf`](pack/PACK_PRESENTATION.pdf) · [HTML](pack/PACK_PRESENTATION.html) |
| 🎬 **Comprendre le pipeline vidéo** | [`PIPELINE-DEMO-VIDEO.html`](PIPELINE-DEMO-VIDEO.html) · [PDF](PIPELINE-DEMO-VIDEO.pdf) |
| 🔍 **Vérifier les chiffres** (traçabilité) | [`pack/AUDIT_COHERENCE.pdf`](pack/AUDIT_COHERENCE.pdf) |
| 🎞️ **Storyboard** (Linux → aujourd'hui) | [`pack/STORYBOARD-COMPLET.pdf`](pack/STORYBOARD-COMPLET.pdf) |
| 📣 **Distribuer / publier** (formats réseaux) | [`pack/DISTRIBUTION-MONTAGE-IA.pdf`](pack/DISTRIBUTION-MONTAGE-IA.pdf) |
| 🗣️ **Script de narration** | [`narration-scene-complete.txt`](narration-scene-complete.txt) |

---

## 📂 Tous les livrables

### Rapports & registres (racine `demo/`)

| Fichier | Format | Rôle |
|---|---|---|
| [`rapport-visuel.html`](rapport-visuel.html) | HTML | **Rapport visuel pro** — graphiques audit &amp; benchmarks (fiabilité 99,6 %, triade agents, thermique GPU, statut cohérence) — SVG autonome, zéro dépendance |
| [`REPORT_PRESENTATION.md`](REPORT_PRESENTATION.md) | Markdown | Registre à jour de tous les livrables (PDF + vidéos), chiffres d'agents vérifiés |
| [`REPORT_PRESENTATION.pdf`](REPORT_PRESENTATION.pdf) | PDF | Version PDF diffusable du registre |
| [`REPORT_PRESENTATION.html`](REPORT_PRESENTATION.html) | HTML | Version web autonome du registre |
| [`PIPELINE-DEMO-VIDEO.html`](PIPELINE-DEMO-VIDEO.html) | HTML | Documentation navigable du pipeline vidéo (flux, skill, scripts, artefacts) |
| [`PIPELINE-DEMO-VIDEO.pdf`](PIPELINE-DEMO-VIDEO.pdf) | PDF | Version PDF du pipeline vidéo |
| [`narration-scene-complete.txt`](narration-scene-complete.txt) | Texte | Script de la narration (voix off française, edge-tts) |

### Pack de présentation (`demo/pack/`)

| Fichier | Format | Rôle |
|---|---|---|
| [`PACK_PRESENTATION.pdf`](pack/PACK_PRESENTATION.pdf) · [`.md`](pack/PACK_PRESENTATION.md) · [`.html`](pack/PACK_PRESENTATION.html) | PDF/MD/HTML | **Dossier complet** — 6 sections : archi, benchmarks, hardware, widget, écosystème agents |
| [`AUDIT_COHERENCE.pdf`](pack/AUDIT_COHERENCE.pdf) · [`.md`](pack/AUDIT_COHERENCE.md) | PDF/MD | **Audit de cohérence des chiffres** (agents 961/1354/1435, GPU/VRAM, thermique) — traçabilité |
| [`DISTRIBUTION-MONTAGE-IA.pdf`](pack/DISTRIBUTION-MONTAGE-IA.pdf) · [`.md`](pack/DISTRIBUTION-MONTAGE-IA.md) | PDF/MD | Fiche distribution &amp; montage IA (AI Studio/Veo, Gemini, NotebookLM) — workflow 0-coût |
| [`STORYBOARD-COMPLET.pdf`](pack/STORYBOARD-COMPLET.pdf) · [`.md`](pack/STORYBOARD-COMPLET.md) | PDF/MD | Storyboard chapitré (9 chapitres + narrations) |
| [`youtube-metadata.md`](pack/youtube-metadata.md) | Markdown | Métadonnées YouTube (titre, description, tags) |

---

## 📈 Chiffres officiels (banc de test interne complet)

> Périmètre étendu, **distinct** du décompte public (« 249 agents publics » du README racine).
> La triade est emboîtée — trois périmètres, pas trois valeurs concurrentes — chaque total est traçable en une commande.

| Chiffre | Périmètre | Somme |
|---|---|---|
| **961** | Agents indexés (cœur cowork) | 848 + 82 + 28 + 3 = **961** |
| **1 354** | Toutes couches (entreprise) | 961 + 58 + 71 + 169 + 95 = **1 354** |
| **1 435** | Inventaire OMEGA (le plus large) | 11 catégories = **1 435** |

**Chiffre *headline* recommandé** : *« jusqu'à 1 435 agents / composants »*.

### Benchmarks vérifiés (✅ constants dans tout le dossier)

| Métrique | Valeur |
|---|---|
| Appels LLM mesurés | **4 413** |
| Taux de succès | **99,6 %** (4 397 ok / 16 err) |
| Latence interactive médiane | **~1,1 s** (1 114 ms) |
| Débit max | **51 tok/s** (cascade gratuite) |
| WER transcription | **10,51 %** |

---

## 🗣️ Narration (extrait)

> « JARVIS OS. Un système d'exploitation autonome, conçu, développé et opéré sur une seule machine.
> Ce que vous voyez n'est pas une maquette. C'est la production réelle, capturée en direct. »
>
> — script complet dans [`narration-scene-complete.txt`](narration-scene-complete.txt)

---

*Livrables auto-générés — `demo/build-report.sh` &amp; `pack/build-pack.sh`. Les versions vidéo canoniques
(master narré, short 9:16, production live, montage maître) sont conservées hors dépôt public en raison de leur poids.*
