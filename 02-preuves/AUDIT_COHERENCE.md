# AUDIT DE COHÉRENCE DES CHIFFRES — Dossier de présentation JARVIS OS

> Audit **lecture seule** des 6 sections `demo/pack/sections/*.md` (00 → 05).
> Aucun fichier de section n'a été modifié. Date : 2026-07-17.
> Légende verdict : ✅ cohérent · 🟡 à préciser (correct mais ambigu / manque de qualificatif) · 🔴 contradiction (valeurs incompatibles entre sections).

---

## 1. Tableau des chiffres clés × sections

### 1.1 Agents

| Chiffre | 00 couverture | 01 archi | 05 écosystème | Signification | Verdict |
|---|---|---|---|---|---|
| **129** Claude Code natifs | oui (« 129 agents Claude Code natifs ») | oui (§3.2 registre `~/.claude/agents/` = 129) | oui (« 129 agents Claude Code natifs, façade la plus visible ») | registre Claude Code local M1 | 🔴 voir §2.1 — contredit par le 58 de la section 05 |
| **58** Claude natifs | — | apparaît indirectement (renvoie section 5) | oui (décompte 2 : `.claude/agents/*.md` = 58) | agents `.md` natifs | 🔴 58 vs 129 pour la même notion « Claude natifs » |
| **961** index cowork | oui | (implicite via renvoi §5) | oui (décompte 1, somme 848+82+28+3 = 961 ✔) | index `jarvis-cowork/agent-index.json` | ✅ arithmétique exacte, libellé constant |
| **1 354** entreprise | oui | oui (annexe renvoi) | oui (décompte 2, somme = 1 354 ✔) | toutes couches consolidées | ✅ somme exacte (961+58+71+169+95) |
| **1 435** OMEGA | oui | oui | oui (décompte 3, somme = 1 435 ✔) | inventaire OMEGA (Legions incl.) | ✅ somme exacte |
| **928** slogan | oui (« 928 du slogan, à manier avec précaution ») | oui (§3.2 « 928 agents actifs, uptime 99,7 % ») | — | slogan `jarvis-linux` | 🟡 voir §2.2 — présenté comme fiable en 01, comme douteux en 00 |
| **900+** écosystème | — | oui (§3.2 badge/README) | — | badge OpenClaw | 🟡 4ᵉ chiffre « agents » non listé dans la note de rigueur du 00 |
| **6** Omega Master Agents | — | — | oui (décompte 3, cat. 10, `~/.claude/agents/`) | agents `~/.claude/agents/` | 🔴 même chemin que le « 129 » et le « 58 » → 3 valeurs pour `~/.claude/agents/` |

### 1.2 GPU

| Chiffre | 00 | 01 | 02 | 03 | Signification | Verdict |
|---|---|---|---|---|---|---|
| **10 GPU** (cluster) | oui (« 10 GPU ») | oui (« Total : 10 GPU », §2) | — | — | total cluster | 🔴 la somme du tableau nœuds §2 donne **12** (4+3+2+1+2), pas 10 |
| **5 GPU** (M1) | — | 4 GPU listés M1 (2060 + **2×**1660S + 3080) | « **4 GPU physiques** sur M1 » mais **5 lignes** dans le tableau | 5 GPU M1 (2060 + **3×**1660S + 3080) | GPU physiques M1 | 🔴 3 valeurs : 4 (tableau 01), « 4 » texte 02 + 5 lignes, 5 (03) |
| **5 nœuds** | oui | oui | — | (M1 seul) | topologie cluster | ✅ constant |

### 1.3 VRAM

| Chiffre | 00 | 01 | 03 | Signification | Verdict |
|---|---|---|---|---|---|
| **88 Go** cumulée | oui | oui (§2 « somme lignes = 88 G » ✔ : 34+24+10+8+12) | — | VRAM cluster totale | 🟡 la somme n'est juste que si M1=34 G (4 GPU) ; or M1 réel = 5 GPU = 40 G → vrai total = **94 G** |
| **34 G** M1 | — | oui (ligne M1 §2) | — | VRAM M1 | 🔴 incompatible avec §03 : 5 GPU M1 = 12+6+6+6+10 = **40 G** |
| **28 Go** inférence | oui (« 28 Go dédiés inférence ») | — | oui (§7 « 28 672 MiB (28 GiB) », = 3×6144+10240 ✔) | VRAM inférence hors GPU0 | ✅ cohérent — **et implique 3× 1660S**, donc 5 GPU M1 (confirme le conflit ci-dessus) |
| **68 G** slogan | oui (note : « 928 mélange agents ») ; PAS le 68 | oui (§2 « 68G description à corriger, retenir 88 G ») | — | valeur historique description | 🟡 correctement signalé comme obsolète en 01, absent du 00 |

### 1.4 Skills

| Chiffre | 00 | 01 | 05 | Signification | Verdict |
|---|---|---|---|---|---|
| **169** skills-agents | oui (« 169 skills-agents ») | — | oui (décompte 2 : `.claude/skills/` SKILL.md = 169) | skills-agents indexés | ✅ constant entre 00 et 05 |
| **53** skills | — | oui (§3.3 `~/.claude/skills/` = 53 ; annexe « retenu 53 ») | — | registre local M1 | 🟡 53 vs 169 pour « ~/.claude/skills » — dénombrements différents (dossiers vs SKILL.md) non explicité au lecteur du 00 |
| **52 / 61 / 86 / 127** | — | oui (§3.3 : 52 orchestrator, 61 core, 86 cowork, 127 agents orchestrator) | — | par périmètre dépôt | 🟡 foisonnement de valeurs skills — OK en interne §01, mais 00 n'affiche que 169 |
| **85** Skills Gemini CLI | — | — | oui (décompte 3, cat. 3) | `~/.gemini/skills/` | ✅ périmètre distinct clair |

### 1.5 Performance / benchmarks

| Chiffre | Sections | Valeur | Verdict |
|---|---|---|---|
| Appels LLM | 00, 02 (×2) | **4 413** | ✅ constant |
| Taux succès | 00, 02 | **99,6 %** (4 397 ok / 16 err) | ✅ constant (4397+16=4413 ✔) |
| Trafic local M1 | 00, 02 | **91,8 %** (65,6+26,2 ✔) | ✅ exact |
| Local total | 02 | 98,6 % (91,8+6,8 ✔) | ✅ exact |
| Fallbacks | 02 | 894 (20,3 %) | ✅ (894/4413 = 20,3 % ✔) |
| Latence interactive médiane | 00, 02 | **~1,1 s** / 1 114 ms | ✅ cohérent |
| Débit max | 00, 02 | **51 tok/s** (cloud gratuit) | ✅ constant |
| Latence « ~0,4 s » M1 hub | 02 (§2 ×2) | ~0,4 s | 🟡 vs « ~1,1 s » interactif §2 tableau (1 114 ms) — deux « meilleures latences » différentes dans la même section 02 |
| WER | 00, 02 | **10,51 %** | ✅ constant |
| RTF vitesse | 00 (« 20× »), 02 (« 20,2× ») | 20× / 20,2× | 🟡 arrondi mineur (20× vs 20,2×) |
| Coût cloud évité | 00, 02 | 1 440–2 500 $/an | ✅ constant |
| BLEU | 02 | 17,2 | ✅ (unique) |
| ~1 % petaFLOP | 00, 02 | ✅ constant | ✅ |

### 1.6 Hardware / système (00, 02, 03)

| Chiffre | Sections | Valeur | Verdict |
|---|---|---|---|
| RAM totale | 03 | 46 GiB | ✅ |
| RAM utilisée charge | 03 | 28 GiB | 🟡 collision visuelle avec « 28 Go VRAM inférence » (deux 28 sans rapport) |
| Bande passante RAM | 00, 02, 03 | **107 954 MiB/s** (~108 GB/s) | ✅ constant |
| ZRAM ratio | 00, 02, 03 | **3,07:1** | ✅ constant |
| ZRAM détail | 02 vs 03 | 02 : « 6,36 G → 1,98 G » · 03 : « 34 MiB → 9,3 MiB » | 🔴 deux jeux de chiffres bruts pour le même ratio 3,07:1 (instantanés différents non datés distinctement) |
| ZRAM taille | 03 | 24 GiB (00 dit « 24 Go ») | ✅ |
| CPU multi | 00, 02, 03 | **14 560 ev/s** | ✅ constant |
| CPU single | 02, 03 | 1 802 ev/s | ✅ |
| Scaling SMT | 02 (8,08×), 03 (8.08x) | 8,08× | ✅ |
| Fréq. courante | 03 | 4026 MHz | ✅ (unique) |
| HugePages statiques | 03 | 512 pages = 1 GiB | 🟡 §3 dit « 496 libres / 128 réservées » (512≠496+128=624) — incohérence interne §03 |
| AnonHugePages | 03 | 10,8 GiB | ✅ (interne cohérent §4/§6) |
| Disque randread/write | 02, 03 | 8 730 / 19 200 IOPS | ✅ constant |
| Uptime | 01 (§5) | 99,7 % | 🟡 aussi accolé au « 928 » douteux en §3.2 |
| Auto-réparation | 00, 01 | < 8 s | ✅ constant |
| Failover LB | 01 | < 3 s | ✅ |
| Cache hit | 01 | 96,9 % (319 tok / 233 échanges) | ✅ (unique) |

### 1.7 GPU thermique live (02 vs 03) — instantanés

| GPU | 02 (§4) | 03 (§7 live) | Verdict |
|---|---|---|---|
| RTX 2060 temp | 54 °C, fan (n/a) | 54 °C, fan 46 % | ✅ |
| 1660S #2 (actif/défaillant) | **73 °C**, 100 % charge | **74 °C**, fan 0 % défaillant | 🟡 73 vs 74 °C (instantanés proches) ; rôles décrits différemment (02 : « actif 100 % » ; 03 : « ventilo défaillant ») |
| GPU2 ventilo défaillant temp | — | §7 dit « 0% / 74°C » mais §ci-dessus (protection) dit « 88-89°C » | 🔴 74 °C vs 88-89 °C pour le même GPU2 défaillant dans la même section 03 |
| RTX 3080 | 70 °C | 72 °C | 🟡 70 vs 72 °C |
| Widget « 5 GPU » | — | — (04 : « charge des 5 GPU », KPI « 44–66 °C ») | ✅ le widget §04 dit **5 GPU** → cohérent avec §03 (5 GPU M1), **contredit** §01/§02 |

### 1.8 Divers infra

| Chiffre | Section | Valeur | Verdict |
|---|---|---|---|
| Containers Docker | 01 (§3.5 « 24 MCP »), 05 (« 26 containers ») | 26 containers actifs | ✅ (24 = serveurs MCP, distinct) |
| Scripts Python | 01 (480 core), 05 (2 533 jarvis-linux + 618 cowork) | — | 🟡 périmètres différents non reliés (480 vs 2 533) — pas contradictoire mais peut dérouter |
| Blocs bibliothèque | 00 (~10 000), 01 (~2 579 → ~9 661) | ~10 000 | ✅ (10 000 = arrondi de 9 661) |
| n8n flows | 01 | 65 flows (§3.5) / 24 h (§widget) | ✅ |
| Ports | 01 | 18800-18803, 103 ports / 23 services | ✅ |
| Widget port | 04 | 8899 | ✅ (unique) |
| KPI widget | 04 | 39 file / 181 faites / 38 analysées / 200 fiches / 44 timers | 🟡 exemple live, non relié aux autres sections (OK si étiqueté « exemple ») |

---

## 2. Analyse des contradictions majeures

### 2.1 🔴 CRITIQUE — « Agents Claude natifs » : 129 vs 58 vs 6
Trois valeurs coexistent pour des notions présentées comme identiques ou se recouvrant, toutes pointant nominalement vers `~/.claude/agents/` :
- **129** : « agents Claude Code natifs » (00, 01 §3.2, 05 conclusion) — présenté comme *la façade la plus visible*.
- **58** : `.claude/agents/*.md` (05 décompte 2).
- **6** : « Omega Master Agents » `~/.claude/agents/` (05 décompte 3, cat. 10).

Le lecteur voit « 129 agents Claude natifs » en couverture, puis la section 5 additionne **58** (pas 129) dans le total 1 354, puis compte **6** dans le total 1 435. Le 129 n'est jamais décomposé ni réconcilié avec le 58. C'est l'incohérence la plus dommageable car elle touche le chiffre le plus mis en avant (couverture + conclusion).

### 2.2 🔴 CRITIQUE — GPU cluster : « 10 GPU » vs somme réelle 12/13
- Couverture et 01 §2 affirment **« 10 GPU »**.
- Le tableau des nœuds (01 §2) additionne **12 GPU** (M1 4 + M2 3 + M5 2 + HP-A 1 + HP-B 2).
- Si l'on retient le M1 réel à **5 GPU** (§03), le cluster monte à **13 GPU**.
Le « 10 » ne correspond à aucune addition du dossier. Aucune note de transparence n'existe (contrairement au 68/88 G VRAM qui, lui, est signalé).

### 2.3 🔴 CRITIQUE — M1 : 4 GPU vs 5 GPU (et 34 G vs 40 G VRAM)
- 01 §2 : M1 = **4 GPU** (RTX 2060 + **2×** GTX 1660S + RTX 3080), **34 G**.
- 02 §4 : texte « **4 GPU physiques** sur M1 » mais **5 lignes** dans le tableau (3× 1660S).
- 03 §7 et §temp live : M1 = **5 GPU** (RTX 2060 + **3×** GTX 1660S + RTX 3080).
- 04 (widget) : « charge des **5 GPU** ».
- Le chiffre **28 Go inférence** (00 + 03) n'est atteignable qu'avec **3× 1660S** (3×6+10 = 28), donc **prouve** que M1 a bien 5 GPU. Conséquence : le tableau nœuds 01 (4 GPU / 34 G) est faux, et le total cumulé exact est **94 G**, pas 88 G.
La majorité du dossier (02 tableau, 03, 04, et le calcul 28 Go) converge sur **5 GPU / 40 G M1** ; seuls le tableau nœuds 01 et une phrase du 02 disent 4.

### 2.4 🔴 Section 03 — GPU2 défaillant : 74 °C vs 88-89 °C
Dans la **même** section 03 : le tableau de règles de protection (§7) indique le ventilo défaillant « à **88-89°C** sous charge », tandis que le tableau live juste en dessous montre GPU2 à **74°C**. Deux instantanés non distingués → paraît contradictoire.

### 2.5 🔴 ZRAM — deux jeux de chiffres bruts
Même ratio **3,07:1** mais : 02/00 → « 6,36 G → 1,98 G » ; 03 → « 34 MiB → 9,3 MiB ». Les deux donnent bien ~3,07 mais ce sont des instantanés très différents (Go vs MiB) sans horodatage distinct visible → un relecteur attentif y verra une erreur.

### 2.6 🟡 « 928 » du slogan présenté de deux façons
- 00 : explicitement « à manier avec précaution, mélange agents et parallélisme ».
- 01 §3.2 : « **928 agents actifs** (uptime 99,7 %) » sans réserve, comme un fait.
Message incohérent selon la section lue.

### 2.7 🟡 Skills 53 vs 169 vs 52/61/86/127
La couverture n'affiche que **169 skills-agents** ; l'architecture retient **53** (annexe « retenu 53 local »). Ces deux chiffres ne sont jamais mis face à face pour le lecteur (169 = SKILL.md indexés cowork ; 53 = dossiers `~/.claude/skills`). Sans note, un lecteur peut croire à une contradiction.

### 2.8 🟡 HugePages — arithmétique interne 03
§3 : « 512 pages » mais « 496 libres / 128 réservées » → 496+128 = 624 ≠ 512. Incohérence interne à corriger.

### 2.9 🟡 Latence « meilleure » : ~0,4 s vs ~1,1 s
Section 02 met en avant deux « meilleures latences prod » : le tableau §2 donne 1 114 ms (interactif court) tandis que le comparatif §2 donne « ~0,4 s » pour M1 via hub. Le 00 ne retient que ~1,1 s. À harmoniser (préciser que 0,4 s = prompt court « 60 mots », 1,1 s = interactif type).

---

## 3. Corrections recommandées (classées par gravité)

### 🔴 Gravité 1 — contradictions factuelles à corriger avant diffusion
1. **GPU cluster** : remplacer partout « 10 GPU » par le total réel des nœuds (**12**, ou **13** si M1 compté à 5) — OU ajouter une note de transparence comme pour la VRAM. Le dossier ne doit pas afficher un total qui ne correspond à aucune de ses propres additions.
2. **M1 = 5 GPU / 40 G** : corriger le tableau nœuds 01 §2 (M1 : RTX 2060 + **3×** GTX 1660S + RTX 3080, **40 G**) et la phrase « 4 GPU physiques » du 02 §4. Recalculer alors la VRAM cumulée (**94 G**, pas 88 G) et la note 68/88 en conséquence. Le chiffre 28 Go d'inférence (3× 1660S) impose 5 GPU.
3. **Agents Claude natifs 129 vs 58** : choisir une définition unique. Si « 129 » = agents Claude Code (registre complet) et « 58 » = fichiers `.md` natifs, l'expliciter dans le décompte 2 de la section 05 (ex. « 58 `.md` natifs, sur 129 agents Claude Code enregistrés ») pour que le 129 de la couverture soit traçable dans le total 1 354.
4. **GPU2 03 : 74 °C vs 88-89 °C** : dater/étiqueter les deux instantanés ou aligner (« 88-89 °C observé en pic sous charge ; 74 °C au relevé du 17/07 »).

### 🟠 Gravité 2 — cohérence de présentation
5. **« 928 »** : appliquer partout la même mise en garde que la couverture ; retirer ou nuancer « 928 agents actifs » présenté comme fait en 01 §3.2.
6. **ZRAM chiffres bruts** : n'exposer qu'un seul instantané (ou dater les deux : « run A : 6,36 G→1,98 G ; run B : 34 MiB→9,3 MiB »).
7. **HugePages 512 vs 496+128** : corriger l'arithmétique (§3 section 03).
8. **Latence 0,4 s / 1,1 s** : préciser le contexte de chaque valeur dans le 00 et le 02 pour éviter l'impression de deux « meilleures latences » concurrentes.
9. **« 900+ »** : l'ajouter à la note de rigueur du 00 (qui ne cite que 961/1354/1435/928) pour couvrir *tous* les chiffres d'agents visibles.

### 🟡 Gravité 3 — clarté / confort de lecture
10. **Skills 53 vs 169** : ajouter une ligne d'explication (169 SKILL.md indexés vs 53 dossiers locaux) là où les deux apparaissent.
11. **Les deux « 28 »** (VRAM inférence vs RAM utilisée) : préciser les unités/nature pour éviter la collision visuelle.
12. **Scripts Python 480 vs 2 533/618** : relier les périmètres (core vs jarvis-linux vs cowork) d'un mot.
13. **RTF 20× / 20,2×** et **temps 70/72 °C, 73/74 °C** : harmoniser les arrondis entre 00 et 02/03.

---

## 4. Ce qui est solide (aucune action)
Les métriques de **performance de routage** (4 413 appels, 99,6 %, 91,8 % local, 894 fallbacks, 0,26 tentative), **RAM 108 GB/s**, **ZRAM 3,07:1**, **CPU 14 560 ev/s**, **WER 10,51 %**, **51 tok/s**, **coût cloud 1 440–2 500 $/an**, **5 nœuds**, **28 Go inférence**, **auto-réparation < 8 s**, **cache hit 96,9 %** sont **parfaitement cohérents** d'une section à l'autre et arithmétiquement exacts. La couverture inclut déjà une louable « note de rigueur » sur les agents — il faut l'étendre aux GPU/VRAM et régler le 129/58.
