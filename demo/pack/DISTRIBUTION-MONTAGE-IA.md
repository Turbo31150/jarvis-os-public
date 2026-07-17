# DISTRIBUTION & MONTAGE IA — Présentation vidéo JARVIS OS

**But** : la vidéo maîtresse (~5 min, 1920×1080) + un short 9:16 sont **déjà produits en local** (ffmpeg + edge-tts, 0 token, watermark-free, droits 100 % à toi). Cette fiche répond à deux questions :
**(a)** que gagne-t-on en habillage/montage rapide via IA externes gratuites, et **(b)** comment distribuer sur tous les réseaux à coût ≈ 0.

> Priorité setup : **Google AI Studio / Veo · Gemini · NotebookLM**. Compléments : CapCut, Descript.
> Règle : le master local reste la **source de vérité** (sans watermark). Les IA Google servent d'**accélérateurs d'habillage** et de **générateurs de métadonnées/sous-titres**, pas de remplaçant.

---

## 1. Tableau récapitulatif

| Outil | Ce qu'il fait POUR NOUS | Coût | Limite 2026 (vérifiée) | Auth |
|---|---|---|---|---|
| **Google AI Studio + Veo 3.1** | Génère des **inserts/B-roll cinématiques** (transitions, plans d'illustration) à intercaler dans le master ffmpeg ; extension par chaînage 8 s→~2 min | Gratuit | **720p max** (1080p = Ultra payant), **8 s/clip**, **watermark visible "Veo"** + SynthID invisible ; ~10 clips/mois (Vids) ou ~50 crédits/j (Flow) | OAuth Google (navigateur) |
| **Gemini (app + API)** | **Titres, descriptions, hashtags, chapitres**, résumés, **sous-titres multilingues**, découpage sémantique (repérer les segments à couper pour le short) | Gratuit | API free : ~**1 500 req/j**, 10 RPM, 250k TPM (Flash) ; vidéo ≤ 90 min/prompt, ≤ 8 h/j ; **Pro devient payant depuis avr. 2026** → rester sur Flash | API key **OU** OAuth. ⚠️ **CLI bloque en non-interactif** — utiliser l'API key directe ou OAuth interactif |
| **NotebookLM** | Transforme le **PDF de présentation** (PACK_PRESENTATION.pdf) en **Audio Overview** (podcast partageable) et **Video Overview** (slides narrées / cinématique) ; **Short Video Overview = 9:16 ~60 s** généré direct du PDF | Gratuit | Sorties multiples/notebook, multilingue ; **download MP4/MP3** natif ; partage par **lien public** | **OAuth Google navigateur uniquement** (pas d'API non-interactive) |
| **CapCut** (complément) | Sous-titres animés stylés, templates verticaux pour le short | Free (limité) | Auto-captions & export sans watermark/4K **passés en payant** en 2025-2026 ; free = quota mensuel + watermark sur certaines features | Compte CapCut |
| **Descript** (complément recommandé) | Sous-titres (burn-in **ou** SRT/VTT export), édition "par le texte" | Free | **1 h média/mois**, captions illimités, export SRT/VTT gratuit | Compte Descript |

---

## 2. Ce que ces IA apportent EN PLUS du master local

Le master ffmpeg est nickel pour la structure et la voix off. Les IA ajoutent surtout :

1. **Sous-titres burn-in + fichiers SRT/VTT** (Gemini transcrit, ou Descript free) → +40 % de rétention en feed muet. Le SRT sert aussi à YouTube/LinkedIn/multilingue.
2. **Métadonnées prêtes à coller** (Gemini) : 5 variantes de titre, description SEO, 10-15 hashtags par réseau, chapitres horodatés. Zéro rédaction manuelle.
3. **Version "podcast" et "slides narrées"** du même contenu (NotebookLM depuis le PDF) → un 2ᵉ format de distribution sans re-tourner (LinkedIn audio, YouTube auto-généré, lien partageable).
4. **B-roll d'habillage** (Veo) pour casser la monotonie des captures d'écran — mais **720p + watermark**, donc réservé aux transitions courtes, jamais au plan principal.
5. **Traductions** (Gemini) pour des sous-titres EN/ES et toucher un public international à coût nul.

---

## 3. Workflow montage rapide (étapes concrètes)

```
master local (1920×1080, ffmpeg)  ←  SOURCE DE VÉRITÉ, sans watermark
        │
        ├─(A) Gemini API/app : uploader le master ou son .txt narration
        │        → titres × réseau + description + hashtags + chapitres + SRT
        │
        ├─(B) Descript (free) OU Gemini : générer sous-titres → burn-in short + SRT long
        │
        ├─(C) [optionnel] Veo (AI Studio) : 2-3 inserts B-roll 8 s → intercaler via ffmpeg
        │        concat  →  ⚠️ 720p+watermark : garder très court, coin masqué
        │
        └─(D) NotebookLM : charger PACK_PRESENTATION.pdf
                 → Audio Overview (partage) + Video Overview + Short 9:16 ~60 s
```

**Commandes de finition locale** (le montage lourd reste ffmpeg, gratuit) :

```bash
# Burn-in du SRT généré par l'IA dans le master
ffmpeg -i master.mp4 -vf "subtitles=captions.srt:force_style='FontSize=22'" -c:a copy master-sub.mp4

# Dériver le short 9:16 depuis le master 16:9 (crop centré 1080×1920)
ffmpeg -i master-sub.mp4 -vf "crop=ih*9/16:ih,scale=1080:1920" -t 60 short-9x16.mp4

# Intercaler un insert Veo (après remise à niveau + fondu)
ffmpeg -i insert-veo.mp4 -vf scale=1920:1080,fade=t=in:0:10 insert-norm.mp4
# puis concat via demuxer -f concat
```

---

## 4. Distribution par réseau

| Réseau | Format | Durée | Fichier à poster | Rôle des IA |
|---|---|---|---|---|
| **YouTube (long)** | 16:9 1920×1080 | ~5 min | `master-sub.mp4` | Gemini → titre + description SEO + **chapitres** + tags ; SRT en piste sous-titres |
| **YouTube Shorts** | 9:16 1080×1920 | ≤ 3 min | `short-9x16.mp4` | Gemini → hook + hashtags ; ou **NotebookLM Short Overview** direct |
| **LinkedIn** | **16:9 ou 1:1** (desktop-first, paysage performe mieux) | 30 s–3 min idéal | `master-sub.mp4` recadré 1:1 + SRT | Gemini → post texte pro + 3-5 hashtags ; **NotebookLM Audio Overview** = alt "écoute" |
| **TikTok** | 9:16 1080×1920 | 15 s–60 s (sweet spot) | `short-9x16.mp4` | Gemini → accroche + hashtags tendance |
| **Instagram Reels** | 9:16 1080×1920 | ≤ 20 min, viser 30-60 s | `short-9x16.mp4` | Gemini → légende + hashtags ; **Mirra MCP** pour publier (OAuth déjà en place) |
| **Threads** | multi-ratio (pas forcé 9:16) | court | `short-9x16.mp4` ou 1:1 | Gemini → texte d'accroche ; Mirra MCP |

> **Publication** : IG / Threads / TikTok / YouTube → **Mirra MCP** (OAuth déjà connecté sur le cluster). **LinkedIn n'est PAS dans l'OAuth Mirra** → publier via automation navigateur (BrowserOS / CDP local). Voir skills `mirra-omnichannel-publish` et `mirr-content-pipeline`.

---

## 5. Pièges & limites 2026 (à ne pas ignorer)

- **Veo watermark** : tout clip Veo gratuit porte un **watermark "Veo" visible** (+ SynthID invisible, robuste au recrop). Retrait interdit par les CGU et de toute façon SynthID reste. → **usage B-roll court uniquement**, jamais le plan de fond principal. Le master local, lui, est 100 % propre.
- **Veo 720p** : le 1080p natif exige Ultra payant. Upscaler un insert 720p→1080p dégrade. Master local prime en 1080p.
- **Gemini CLI non-interactif** : bloque sur prompt d'auth dans un service/cron. → utiliser **l'API key directe** (`gemini-2.5-flash`) ou l'app en **OAuth interactif**. Ne jamais scripter la CLI en daemon.
- **Gemini Pro payant depuis avril 2026** : rester sur **Flash** (gratuit, ~1 500 req/j). Le daily limit a fondu fin 2025 (250→parfois 20-50 selon config) → vérifier le quota réel dans AI Studio avant un batch.
- **NotebookLM = OAuth Google navigateur seul** : aucune API non-interactive fiable → étape **manuelle/semi-auto** (BrowserOS). Ne pas scripter en cron aveugle.
- **Droits/musique** : ne pas coller de musique protégée sur les inserts ; les visuels Veo restent utilisables commercialement mais **doivent conserver SynthID** (CGU). Contenu principal = tes propres captures, aucun risque.
- **CapCut free se restreint** : auto-captions + export sans watermark désormais souvent payants → préférer **Descript free (SRT/VTT)** puis burn-in ffmpeg local, gratuit et propre.

---

## 6. Plan d'action 0-coût (5-7 étapes)

1. **Geler le master** : confirmer `master.mp4` (1080p, sans watermark) comme source unique dans `demo/pack/`.
2. **Sous-titres** : Descript free (ou Gemini) → export `captions.srt` ; burn-in ffmpeg → `master-sub.mp4`.
3. **Short** : crop ffmpeg 9:16 → `short-9x16.mp4` (60 s max), re-burn des sous-titres gros format.
4. **Métadonnées** : Gemini Flash (API key) sur la narration → titres × réseau, descriptions, hashtags, chapitres YouTube (fichier `youtube-metadata.md` existant à enrichir).
5. **NotebookLM** : charger `PACK_PRESENTATION.pdf` → générer Audio Overview (lien partageable) + Short Video Overview 9:16 comme **format alternatif gratuit**.
6. **(optionnel) Veo** : 2-3 inserts B-roll 8 s dans AI Studio → intercaler, watermark masqué/coupé, jamais en plan principal.
7. **Publier** : IG/Threads/TikTok/YouTube via **Mirra MCP** ; LinkedIn via **BrowserOS/CDP** ; coller les métadonnées Gemini par réseau.

---

## Sources

- [Google Veo 3.1 gratuit — 10 vidéos/mois, limites AI Studio (bonega.ai)](https://bonega.ai/en/blog/google-veo-3-1-free-4k-ai-video-generation-2026)
- [Veo 3 in Google AI Studio: limites, accès gratuit, workflow](https://www.veo3ai.io/blog/google-ai-studio-veo-3-limits-free-workflow-2026)
- [Veo — Commercial rights, watermarks, SynthID (Flowith)](https://flowith.io/blog/veo-faq-commercial-rights-watermarks/)
- [Veo 3 AI videos get visible watermarks, not just SynthID (BGR)](https://www.bgr.com/tech/those-amazing-veo-3-videos-will-finally-tell-you-they-were-made-with-ai/)
- [What's new in NotebookLM: Video Overviews & Studio (blog.google)](https://blog.google/innovation-and-ai/models-and-research/google-labs/notebooklm-video-overviews-studio-upgrades/)
- [NotebookLM Short Video Overviews — 9:16 ~60 s (notebooklm-guide.com)](https://notebooklm-guide.com/notebooklm-short-video-overviews)
- [How to download NotebookLM Audio & Video Overviews (MP3/MP4)](https://www.nlmtools.com/blog/notebooklm-download-audio-video)
- [Gemini API — Video understanding (ai.google.dev)](https://ai.google.dev/gemini-api/docs/video-understanding)
- [Gemini API Free Tier 2026: 1 500 req/j, 1M TPM (TokenMix)](https://tokenmix.ai/blog/gemini-api-free-tier-limits)
- [Google Gemini API free tier tightened — Pro payant avr. 2026 (Apiyi)](https://help.apiyi.com/en/google-gemini-api-free-tier-changes-april-2026-guide-en.html)
- [CapCut captions aren't free anymore — Descript alternative](https://www.descript.com/blog/article/capcut-captions-arent-free-anymore-heres-a-better-option)
- [Social media video aspect ratios & sizes — 2026 guide (Kapwing)](https://www.kapwing.com/resources/social-media-video-aspect-ratios-and-sizes-the-2025-guide/)
- [Social media video specs guide (Sprout Social)](https://sproutsocial.com/insights/social-media-video-specs-guide/)

*Fiche générée le 2026-07-17. Le master local (ffmpeg + edge-tts) reste la source de vérité sans watermark ; les IA Google sont des accélérateurs gratuits, pas des remplaçants.*
