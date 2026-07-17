% JARVIS OS — Report de présentation (livrables)
% Dossier `demo/` · M1
% 17/07/2026 04:01

# Report de présentation — JARVIS OS

> **Objet** : registre à jour de tous les livrables de présentation (PDF + vidéos) générés
> dans `demo/`, prêt pour diffusion professionnelle. Chiffres d'agents **figés sur le
> décompte vérifié** (sommes arithmétiques exactes, cf. `pack/AUDIT_COHERENCE.md`).
> Généré automatiquement le 17/07/2026 04:01.

## 1. Décompte d'agents — chiffres officiels (vérifiés)

Le nombre d'agents est une **triade emboîtée** de périmètres, pas trois valeurs concurrentes.
Chaque total est traçable en une commande.

| Chiffre | Périmètre | Source vérifiable | Somme |
|---|---|---|---|
| **961** | Agents indexés (cœur cowork) | `jarvis-cowork/agent-index.json` | 848 + 82 + 28 + 3 = **961** ✔ |
| **1 354** | Toutes couches (entreprise) | consolidation registres | 961 + 58 + 71 + 169 + 95 = **1 354** ✔ |
| **1 435** | Inventaire OMEGA (le plus large) | `inventaire-complet-1435-agents.md` | 11 catégories = **1 435** ✔ |

**Façade Claude Code** : **129** agents chargés en session M1 (natifs + plugins) ; le strict
`~/.claude/agents/*.md` = **58** fichiers (sous-ensemble retenu dans le 1 354). Le **6** =
Omega Master Agents (sous-ensemble des 58).

> ⚠️ **À ne jamais utiliser comme fait** : « 928 » (= capacité de parallélisme, slogan
> `jarvis-linux`) et « 900+ » (badge écosystème global). Réservés à l'annexe transparence.
> Chiffre *headline* recommandé : **« jusqu'à 1 435 agents / composants »**.

## 2. Livrables PDF

| Fichier | Taille | Rôle |
|---|---|---|
| `pack/PACK_PRESENTATION.pdf` | 212K | Dossier de présentation complet (6 sections : archi, benchmarks, hardware, widget, écosystème agents) |
| `pack/AUDIT_COHERENCE.pdf` | 88K | **Audit de cohérence des chiffres** (agents 961/1354/1435, GPU/VRAM, thermique) — traçabilité des corrections |
| `pack/DISTRIBUTION-MONTAGE-IA.pdf` | 92K | **Fiche distribution & montage IA** (AI Studio/Veo, Gemini, NotebookLM) — workflow 0-coût + formats par réseau |
| `pack/STORYBOARD-COMPLET.pdf` | 40K | Storyboard chapitré base Linux → aujourd'hui (9 chapitres + narrations) |
| `PIPELINE-DEMO-VIDEO.pdf` | 108K | Documentation du pipeline vidéo (flux, skill, scripts, artefacts) |
| `REPORT_PRESENTATION.pdf` | 72K | Ce report (registre des livrables) — auto-généré |
| `pack/PACK_PRESENTATION.html` | 68K | Version HTML autonome du dossier (embed-resources) |

## 3. Livrables vidéo (versions canoniques)

| Fichier | Durée | Taille | Rôle |
|---|---|---|---|
| `presentation-complete-jarvis.mp4` | 7:36 | 59M | **Master** — présentation complète narrée (intro Linux → système → widget → pilotage → production live monstrueuse → dossier) |
| `short-jarvis-916.mp4` | 0:52 | 1,8M | **Short 9:16** vertical (Shorts/Reels/TikTok) — hook + widget live + titres |
| `live-production-jarvis.mp4` | 2:00 | 7,1M | **Production live** — todoliste monstrueuse 18 tâches pending→done + qwen réel + voix off |
| `montage-maitre-jarvis.mp4` | 4:22 | 15M | Montage maître (enchaînement des scènes) |
| `scene-jarvis.mp4` | 0:48 | 40M | Scène système / agents / widget plein écran |
| `showcase-widget.mp4` | 1:53 | 4,8M | Showcase du widget bureau |
| `live-production-jarvis.mp4` | 2:00 | 7,1M | Capture live production temps réel |
| `jarvis-os-widget.mp4` | 0:18 | 2,8M | Boucle widget « Ce que le système fait » |
| `intro-linux-base.mp4` | 0:17 | 908K | Intro — base Linux |
| `pack/pilote-widget.mp4` | 0:53 | 2,7M | Pilotage guidé du widget |
| `pack/preuve-widget-pack.mp4` | 1:31 | 2,3M | Preuve de fonctionnement widget |

**Format court réseaux** : `jarvis-os-widget.gif` (boucle) + narrations `narration-*.mp3` /
`.txt` (voix off française, edge-tts).

## 4. Documents d'accompagnement

| Fichier | Rôle |
|---|---|
| `pack/AUDIT_COHERENCE.md` | 16K | Audit de cohérence des chiffres (agents, GPU/VRAM, thermique) — base des corrections appliquées |
| `pack/youtube-metadata.md` | 8,0K | Métadonnées YouTube (titre, description, tags) |
| `PIPELINE-DEMO-VIDEO.html` | 16K | Doc pipeline navigable (liens file:// cliquables) |

## 5. Statut cohérence

- ✅ Triade **961 / 1 354 / 1 435** cohérente et arithmétiquement exacte dans tout le pack.
- ✅ **129 vs 58** réconciliés (façade session vs `.md` stricts) — section 5 + annexe.
- ✅ **928** relégué à l'annexe « chiffres à réconcilier (transparence) », plus présenté comme fait.
- ✅ GPU/VRAM, thermique, benchmarks (4 413 appels, 99,6 %, WER 10,51 %, 51 tok/s…) constants.

**Verdict** : dossier prêt pour présentation professionnelle. Chiffre à mettre en avant : **1 435 agents/composants**.

---
*Report auto-généré — `demo/build-report.sh` · 17/07/2026 04:01*
