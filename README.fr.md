<p align="right"><a href="README.md">English</a> · <b>Français</b></p>

<p align="center"><a href="https://paul-reitz.github.io/NTL_South_Africa_Project/fr/"><img src="assets/fr/banner.png" alt="Lumières nocturnes : huit cas d'usage — Afrique du Sud" width="100%"></a></p>

<p align="center"><img src="assets/flag.png" alt="Drapeau — Afrique du Sud" height="54"><br><b>Afrique du Sud</b> · 2014–2025</p>

<p align="center">Transformer les lumières nocturnes observées par satellite en éclairages pour <b>Afrique du Sud</b> — <b>huit cas d'usage</b> au service des statistiques et des politiques publiques : dynamiques économiques, croissance régionale, prévision du PIB, chocs et résilience, inégalités et électrification, zones industrielles, tourisme saisonnier, urbanisation — avec un <b>tableau de bord public</b> et un <b>agent IA</b> qui ne répond qu'à partir des chiffres publiés.</p>

<p align="center">
  <a href="https://paul-reitz.github.io/NTL_South_Africa_Project/fr/"><img src="https://img.shields.io/badge/tableau%20de%20bord-en%20ligne-00704A?logo=githubpages&logoColor=white" alt="Ouvrir le tableau de bord"></a>
  <a href="https://colab.research.google.com/github/paul-reitz/NTL_South_Africa_Project/blob/main/notebooks/NTL_8_use_cases_FR.ipynb"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open in Colab"></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/licence-MIT-3F7FC7" alt="MIT"></a>
  <a href="README.md"><img src="https://img.shields.io/badge/langues-FR%20%7C%20EN-F5C242" alt="FR | EN"></a>
  <a href="docs/methodology.fr.md"><img src="https://img.shields.io/badge/donn%C3%A9es-VIIRS%20%C2%B7%20Black%20Marble-0B121B?logo=nasa&logoColor=white" alt="VIIRS"></a>
  <a href="https://paul-reitz.github.io/NTL_South_Africa_Project/fr/?country=ZAF#assistant"><img src="https://img.shields.io/badge/agent%20IA-Groq%20%7C%20Gemini%20%7C%20Ollama-6E40C9" alt="Agent IA"></a>
  <a href="CHANGELOG.md"><img src="https://img.shields.io/badge/mis%20%C3%A0%20jour-2026--10--29-555" alt="mis à jour"></a>
</p>

<p align="center"><a href="https://paul-reitz.github.io/NTL_South_Africa_Project/fr/"><img src="https://img.shields.io/badge/OUVRIR%20LE%20TABLEAU%20DE%20BORD-%E2%96%B6-00704A?style=for-the-badge&logo=googlechrome&logoColor=white" alt="Ouvrir le tableau de bord" height="42"></a>&nbsp;&nbsp;<a href="https://colab.research.google.com/github/paul-reitz/NTL_South_Africa_Project/blob/main/notebooks/NTL_8_use_cases_FR.ipynb"><img src="https://img.shields.io/badge/EX%C3%89CUTER%20LE%20NOTEBOOK%20DANS%20COLAB-%E2%96%B6-3F7FC7?style=for-the-badge&logo=googlecolab&logoColor=white" alt="Exécuter le notebook dans Colab" height="42"></a></p>

<p align="center"><a href="https://paul-reitz.github.io/NTL_South_Africa_Project/fr/"><b>https://paul-reitz.github.io/NTL_South_Africa_Project/fr/</b></a></p>


## ✨ En un coup d'œil

<sub>Chiffres clés de l'exécution, 2014–2025. Chacun est accompagné de son niveau de confiance et de sa méthode sur le tableau de bord.</sub>

<table>
<tr>
<td align="center" width="25%"><h3>+2,1 %</h3><b>Croissance annuelle de la lumière</b><br><sub>2014–2025, pente robuste (Theil–Sen)</sub></td>
<td align="center" width="25%"><h3>+3,0 %</h3><b>12 derniers mois vs 12 précédents</b><br><sub>série désaisonnalisée, jusqu'à 12/2025</sub></td>
<td align="center" width="25%"><h3>1,96</h3><b>Élasticité lumière–PIB</b><br><sub>IC 95 % −0,19 à 4,11 · confiance moyenne</sub></td>
<td align="center" width="25%"><h3>0,23</h3><b>Gini de la lumière par habitant</b><br><sub>unités ADM2, 2025</sub></td>
</tr>
<tr>
<td align="center" width="25%"><h3>500 k</h3><b>Personnes dans le noir</b><br><sub>18 % de la population habitée, 2025</sub></td>
<td align="center" width="25%"><h3>20 %</h3><b>Part de la 1ʳᵉ région</b><br><sub>Gauteng, 2025</sub></td>
<td align="center" width="25%"><h3>400</h3><b>Grappes industrielles</b><br><sub>22 % de la lumière nationale</sub></td>
<td align="center" width="25%"><h3>1</h3><b>Zones touristiques</b><br><sub>surcroît estival max, +13 % (City of Cape Town (Western Cape))</sub></td>
</tr>
<tr>
<td align="center" width="25%"><h3>+6,8 %</h3><b>Surface éclairée</b><br><sub>croissance annuelle ; population +1,0 %/an</sub></td>
</tr>
</table>


## ⚡ Un choc vu de l'espace

<p align="center"><img src="assets/fr/shock.gif" alt="Série mensuelle nationale désaisonnalisée — COVID-19. Creux : −10,4 % (09/2020)." width="100%"><br><sub>Série mensuelle nationale désaisonnalisée — COVID-19. Creux : −10,4 % (09/2020).</sub></p>


## 🧭 Huit cas d'usage

<sub>Chaque carte ouvre la page correspondante du tableau de bord.</sub>

<table>
<tr>
<td width="50%" valign="top">
<a href="https://paul-reitz.github.io/NTL_South_Africa_Project/fr/?country=ZAF#time"><img src="assets/fr/uc1.png" alt="Cas d'usage 1 — Dynamiques temporelles" width="100%"></a>
<h3>📈 1 · Dynamiques temporelles</h3>
<p><b>Question</b> — <i>L'activité accélère-t-elle ou ralentit-elle, hors effet de saison ?</i></p>
<p><b>Résultat</b> — Entre 2014 et 2025, la lumière nocturne de Afrique du Sud a évolué de +2,1 % par an (IC 95 % : +0,6 % à +3,0 %). Sur les 12 derniers mois, le niveau désaisonnalisé est +3,0 % par rapport aux 12 mois précédents.</p>
<p><a href="https://paul-reitz.github.io/NTL_South_Africa_Project/fr/?country=ZAF#time">Ouvrir la page →</a></p></td>
<td width="50%" valign="top">
<h3>🗺️ 2 · Croissance régionale et convergence</h3>
<p><b>Question</b> — <i>Quelles régions décollent, lesquelles décrochent ?</i></p>
<p><b>Résultat</b> — Sur 52 unités ADM2, 33 sont en croissance significative, 16 stagnent et 3 déclinent. L'activité lumineuse reste concentrée : Gauteng concentre 20 % de la lumière nationale.</p>
<p><a href="https://paul-reitz.github.io/NTL_South_Africa_Project/fr/?country=ZAF#regions">Ouvrir la page →</a></p></td>
</tr>
<tr>
<td width="50%" valign="top">
<a href="https://paul-reitz.github.io/NTL_South_Africa_Project/fr/?country=ZAF#time"><img src="assets/fr/uc3.png" alt="Cas d'usage 3 — Relation lumières–PIB" width="100%"></a>
<h3>💹 3 · Relation lumières–PIB</h3>
<p><b>Question</b> — <i>Peut-on estimer la croissance avant sa publication, et le PIB régional ?</i></p>
<p><b>Résultat</b> — L'élasticité de la lumière au PIB réel est de 1,96 en niveaux (IC 95 % : −0,19 à 4,11, R² = 0,36, 12 années) et de −0,27 en taux de croissance (IC : −0,98 à 0,45).</p>
<p><a href="https://paul-reitz.github.io/NTL_South_Africa_Project/fr/?country=ZAF#time">Ouvrir la page →</a></p></td>
<td width="50%" valign="top">
<a href="https://paul-reitz.github.io/NTL_South_Africa_Project/fr/?country=ZAF#shocks"><img src="assets/fr/uc4.png" alt="Cas d'usage 4 — Chocs et résilience" width="100%"></a>
<h3>⚡ 4 · Chocs et résilience</h3>
<p><b>Question</b> — <i>Quelle a été la profondeur d'un choc, et la vitesse de récupération ?</i></p>
<p><b>Résultat</b> — Le choc le plus marqué dans la série désaisonnalisée est « COVID-19 » : creux de -10,4 % (09/2020), retour au niveau d'avant-choc après 7 mois.</p>
<p><a href="https://paul-reitz.github.io/NTL_South_Africa_Project/fr/?country=ZAF#shocks">Ouvrir la page →</a></p></td>
</tr>
<tr>
<td width="50%" valign="top">
<h3>⚖️ 5 · Inégalités et électrification</h3>
<p><b>Question</b> — <i>Où vivent les populations privées d'électricité ?</i></p>
<p><b>Résultat</b> — Le Gini de la lumière par habitant (ADM2) vaut 0,23 en 2025 (évolution non significative depuis 2014). Environ 0,50 million(s) de personnes vivent dans des zones habitées sans lumière détectable (18 % de la population habitée).</p>
<p><a href="https://paul-reitz.github.io/NTL_South_Africa_Project/fr/?country=ZAF#inequality">Ouvrir la page →</a></p></td>
<td width="50%" valign="top">
<a href="https://paul-reitz.github.io/NTL_South_Africa_Project/fr/?country=ZAF#industry"><img src="assets/fr/uc6.png" alt="Cas d'usage 6 — Zones industrielles" width="100%"></a>
<h3>🏭 6 · Zones industrielles</h3>
<p><b>Question</b> — <i>Où est l'industrie, et son activité progresse-t-elle ?</i></p>
<p><b>Résultat</b> — 400 grappes industrielles détectées par concordance de signaux satellitaires : 40 d'industrie lourde, 77 zones d'activités et de logistique, 221 sites d'hydrocarbures et 62 sites isolés à vérifier.</p>
<p><a href="https://paul-reitz.github.io/NTL_South_Africa_Project/fr/?country=ZAF#industry">Ouvrir la page →</a></p></td>
</tr>
<tr>
<td width="50%" valign="top">
<h3>🏖️ 7 · Tourisme saisonnier</h3>
<p><b>Question</b> — <i>Quelles zones vivent du tourisme, et comment évolue la saison ?</i></p>
<p><b>Résultat</b> — 1 unités sur 52 ont un surcroît de lumière estival net d'au moins 10 % : City of Cape Town (Western Cape). Le surcroît net médian atteint +13 % dans la zone la plus touristique. L'indice de saison (base 100 = 2019) tombe à 103 en 2020 et vaut 41 en 2025.</p>
<p><a href="https://paul-reitz.github.io/NTL_South_Africa_Project/fr/?country=ZAF#tourism">Ouvrir la page →</a></p></td>
<td width="50%" valign="top">
<h3>🏙️ 8 · Signaux d'urbanisation</h3>
<p><b>Question</b> — <i>Où les villes s'étendent-elles, où les villages s'électrifient-ils, et où la population croît-elle sans lumière ?</i></p>
<p><b>Résultat</b> — Surface éclairée nationale : +6,8 % par an ; population : +1,0 % par an. Classes (ADM2) : Urbanisation électrifiée 45, Croissance non éclairée 3, Croissance équilibrée 2, Stable ou en déclin 2.</p>
<p><a href="https://paul-reitz.github.io/NTL_South_Africa_Project/fr/?country=ZAF#urban">Ouvrir la page →</a></p></td>
</tr>
<tr>
<td width="50%" valign="top"><h3>🤖 Agent IA</h3><p><i>Interrogez les résultats en langage naturel — chaque chiffre est cité.</i></p><p><a href="https://paul-reitz.github.io/NTL_South_Africa_Project/fr/?country=ZAF#assistant">Ouvrir la page →</a></p></td>
</tr>
</table>


## 📊 Le tableau de bord

<sub>Bilingue (FR/EN), fichiers statiques, thèmes clair et sombre, adapté au mobile.</sub>

<table><tr><td width="76%"><a href="https://paul-reitz.github.io/NTL_South_Africa_Project/fr/"><img src="assets/fr/dashboard_tour.gif" alt="Le tableau de bord" width="100%"></a></td><td width="24%"><img src="assets/fr/screen_mobile.png" alt="mobile" width="100%"></td></tr></table>


<details>
<summary><b>Captures d'écran</b> (9)</summary>
<br>

<table>
<tr><td width="33%" align="center"><a href="https://paul-reitz.github.io/NTL_South_Africa_Project/fr/?country=ZAF#overview"><img src="assets/fr/screen_overview.png" alt="overview" width="100%"></a><br><sub><code>#overview</code></sub></td><td width="33%" align="center"><a href="https://paul-reitz.github.io/NTL_South_Africa_Project/fr/?country=ZAF#map"><img src="assets/fr/screen_map.png" alt="map" width="100%"></a><br><sub><code>#map</code></sub></td><td width="33%" align="center"><a href="https://paul-reitz.github.io/NTL_South_Africa_Project/fr/?country=ZAF#time"><img src="assets/fr/screen_time.png" alt="time" width="100%"></a><br><sub><code>#time</code></sub></td></tr>
<tr><td width="33%" align="center"><a href="https://paul-reitz.github.io/NTL_South_Africa_Project/fr/?country=ZAF#regions"><img src="assets/fr/screen_regions.png" alt="regions" width="100%"></a><br><sub><code>#regions</code></sub></td><td width="33%" align="center"><a href="https://paul-reitz.github.io/NTL_South_Africa_Project/fr/?country=ZAF#shocks"><img src="assets/fr/screen_shocks.png" alt="shocks" width="100%"></a><br><sub><code>#shocks</code></sub></td><td width="33%" align="center"><a href="https://paul-reitz.github.io/NTL_South_Africa_Project/fr/?country=ZAF#inequality"><img src="assets/fr/screen_inequality.png" alt="inequality" width="100%"></a><br><sub><code>#inequality</code></sub></td></tr>
<tr><td width="33%" align="center"><a href="https://paul-reitz.github.io/NTL_South_Africa_Project/fr/?country=ZAF#industry"><img src="assets/fr/screen_industry.png" alt="industry" width="100%"></a><br><sub><code>#industry</code></sub></td><td width="33%" align="center"><a href="https://paul-reitz.github.io/NTL_South_Africa_Project/fr/?country=ZAF#tourism"><img src="assets/fr/screen_tourism.png" alt="tourism" width="100%"></a><br><sub><code>#tourism</code></sub></td><td width="33%" align="center"><a href="https://paul-reitz.github.io/NTL_South_Africa_Project/fr/?country=ZAF#urban"><img src="assets/fr/screen_urban.png" alt="urban" width="100%"></a><br><sub><code>#urban</code></sub></td></tr>
</table>
</details>


## 🤖 L'agent IA

- **Ancré dans les résultats.** L'agent répond uniquement à partir des faits numérotés exportés avec le tableau de bord (`agent_context.json`, F01, F02…) : les mêmes dans le notebook et sur le site.
- **Sourcé.** Chaque phrase chiffrée cite son fait, par ex. `[F12]` ; les citations renvoient à la page du tableau de bord concernée, et les citations inconnues sont supprimées.
- **Un véritable agent à six outils.** Il planifie, appelle ses outils (*function calling*) et enchaîne plusieurs étapes : 🔎 `search_facts`, 🏆 `rank_units`, 📍 `unit_profile`, ⚖️ `compare_units`, 📈 `make_chart` (graphiques dans la conversation) et 🗺️ `map_action` (il pilote la carte : année, rideau avant/après, zoom, couches). Chaque étape est affichée ; les résultats d'outils sont cités `[D2]`.
- **Des notes en un clic.** Note pour un décideur, fiche pays ou réponse parlementaire — structurées, sourcées, exportables en Markdown ou PDF.
- **Le modèle de votre choix.** Groq (`openai/gpt-oss-120b` par défaut), Google Gemini ou un modèle local Ollama, avec réponses en continu ; sans modèle, un planificateur hors ligne exécute les mêmes outils.
- **Garde-fous.** Outils en lecture seule, cinq appels d'outils au plus par question, données jamais traitées comme des instructions (résistance à l'injection de consignes), limitation du débit.
- **Vos clés restent chez vous.** Sur le site, la clé d'un visiteur reste dans son navigateur et n'est envoyée qu'au fournisseur choisi ; dans le notebook, les clés viennent des Secrets Colab. Aucune clé n'est jamais publiée.


## 🛠️ Fonctionnement

```mermaid
flowchart LR
  A["🛰️ Satellites<br/>VIIRS · Black Marble<br/>Sentinel-5P · MODIS"]
  A2["📚 Données ouvertes<br/>GHSL · WorldPop<br/>OSM · Banque mondiale"]
  B["🌍 Earth Engine<br/>zonal stats"]
  C["📓 Notebook<br/>nettoyage · STL<br/>économétrie"]
  D["🧭 8 cas<br/>d'usage"]
  E["📦 Exports<br/>JSON · CSV<br/>GeoJSON · PNG"]
  F["📊 Tableau<br/>de bord FR/EN"]
  G["🤖 Agent IA<br/>faits cités"]
  H["🚀 GitHub<br/>Pages"]
  A --> B
  A2 --> B
  B --> C --> D --> E
  E --> F --> H
  E --> G --> H
  classDef green fill:#00704A,stroke:#00553A,color:#fff
  classDef gold fill:#F5C242,stroke:#b8901f,color:#05080d
  classDef blue fill:#3F7FC7,stroke:#2b5f99,color:#fff
  class A,A2,B blue
  class C,D,E green
  class F,G,H gold
```


## 🚀 Démarrage rapide

1. **Ouvrir le notebook dans Colab** — [NTL_8_use_cases_FR.ipynb](https://colab.research.google.com/github/paul-reitz/NTL_South_Africa_Project/blob/main/notebooks/NTL_8_use_cases_FR.ipynb).
2. **Choisir le pays** — section 2 : `ISO3 = "TUN"` (tout code ISO 3166-1 alpha-3) et la période ; `SYNTHETIC_TEST = True` exécute tout sans Earth Engine.
3. **Tout exécuter** — *Exécution → Tout exécuter*. Le tableau de bord est exporté dans `dashboard/` et, avec `PUBLISH = True`, publié sur GitHub Pages en un seul appel.

> [!TIP]
> Les clés et jetons se placent dans les **Secrets Colab** (icône 🔑) : `GITHUB_TOKEN` (fine-grained, limité à ce dépôt : *Contents*, *Pages* — plus *Administration* pour créer le dépôt et sa description), et facultativement `GROQ_API_KEY` ou `GEMINI_API_KEY`. Un projet Cloud Earth Engine est nécessaire pour un pays réel.


## 🛰️ Sources de données

| Jeu de données | Fournisseur · ID Earth Engine | Utilisation | Référence |
|---|---|---|---|
| **VIIRS VNL V2 (annual)** | NOAA/EOG · `NOAA/VIIRS/DNB/ANNUAL_V21`, `ANNUAL_V22` | niveaux annuels, cartes, inégalités | Elvidge, C. D. et al. (2021). Annual time series of global VIIRS nighttime lights. *Remote Sensing* 13(5). |
| **VIIRS DNB monthly (VCMSLCFG)** | NOAA/EOG · `NOAA/VIIRS/DNB/MONTHLY_V1/VCMSLCFG` | séries mensuelles, saisonnalité, chocs, tourisme | Elvidge, C. D. et al. (2017). VIIRS night-time lights. *Int. J. Remote Sensing* 38(21). |
| **Black Marble VNP46A2 (daily)** | NASA · `NASA/VIIRS/002/VNP46A2` | indice quotidien des chocs | Román, M. O. et al. (2018). NASA's Black Marble nighttime lights product suite. *RSE* 210. |
| **DMSP-OLS / harmonised DMSP–VIIRS** | NOAA NGDC · Li et al. (sat-io) | série longue depuis 1992 (élasticité au PIB) | Li, X. et al. (2020). A harmonized global nighttime light dataset 1992–2018. *Scientific Data* 7, 168. |
| **GHSL R2023A (POP, SMOD, BUILT-S)** | European Commission JRC · `JRC/GHSL/P2023A/*` | population, urbain/rural, bâti non résidentiel | Schiavina, M. et al. (2023); Pesaresi, M. et al. (2023). GHSL R2023A. JRC. |
| **WorldPop** | WorldPop · `WorldPop/GP/100m/pop` | population (variante) | WorldPop (2018). Global High Resolution Population Denominators. |
| **Sentinel-5P TROPOMI NO₂ / SO₂** | ESA Copernicus · `COPERNICUS/S5P/OFFL/L3_NO2`, `L3_SO2` | contrôle de l'activité, signaux industriels | Veefkind, J. P. et al. (2012). TROPOMI on the ESA Sentinel-5 Precursor. *RSE* 120. |
| **MODIS LST (MOD11A2)** | NASA · `MODIS/061/MOD11A2` | chaleur de surface des sites industriels | Wan, Z. (2014). New refinements and validation of the MODIS LST products. *RSE* 140. |
| **OpenStreetMap** | OpenStreetMap contributors · Overpass API | liste de référence des zones industrielles | © OpenStreetMap contributors, ODbL. |
| **World Bank WDI** | World Bank · `NY.GDP.MKTP.KD`, `NV.IND.TOTL.KD`, `EG.ELC.ACCS.ZS`… | PIB réel, valeur ajoutée industrielle, accès à l'électricité | World Bank (2026). World Development Indicators. |
| **geoBoundaries / FAO GAUL** | William & Mary geoLab · FAO | limites administratives | Runfola, D. et al. (2020). geoBoundaries. *PLoS ONE* 15(4). |


## 📐 Méthodologie et normes de qualité

Méthodologie complète : [docs/methodology.fr.md](docs/methodology.fr.md) · rapport qualité : [docs/QUALITY.fr.md](docs/QUALITY.fr.md).

- **Principes fondamentaux de la statistique officielle (ONU)** — pertinence, impartialité, normes professionnelles, transparence des sources et méthodes, accès ouvert aux résultats.
- **Cadre d'évaluation de la qualité des données (DQAF)** — intégrité, rigueur méthodologique, exactitude et fiabilité, utilité, accessibilité.
- **GSBPM** — chaque section du notebook correspond à une phase du modèle générique du processus statistique.
- **FAIR** — trouvable (URL stables, fichier de citation), accessible (formats ouverts), interopérable (CSV, JSON, GeoJSON), réutilisable (licence, provenance dans `manifest.json`).
- **Statistiques expérimentales** — les estimations par les lumières complètent, sans jamais les remplacer, les statistiques officielles ; elles sont étiquetées *expérimentales*, avec leur incertitude.


| Cas d'usage | Statut | Confiance | Validation |
|---|---|---|---|
| 📈 1 · Dynamiques temporelles | `Expérimental` | élevée | p-value = 0,0088 |
| 🗺️ 2 · Croissance régionale et convergence | `Expérimental` | moyenne | Spearman ρ = 0,66 |
| 💹 3 · Relation lumières–PIB | `Expérimental` | moyenne | corrélation / EAM (points) = -0,54 / 1,7 |
| ⚡ 4 · Chocs et résilience | `Expérimental` | faible | creux (choc principal) = -10,4 % — non |
| ⚖️ 5 · Inégalités et électrification | `Expérimental` | moyenne | écart moyen (points) = -5,6 |
| 🏭 6 · Zones industrielles | `Expérimental` | faible | précision / rappel / F1 = non disponible |
| 🏖️ 7 · Tourisme saisonnier | `Expérimental` | faible | r = -0,28 |
| 🏙️ 8 · Signaux d'urbanisation | `Expérimental` | élevée | Spearman ρ = 0,80 |


## 🗂️ Structure du dépôt

```text
.
├── assets/          # images et animations générées à partir des données
├── dashboard/       # → le site est sur la branche gh-pages
├── docs/            # méthodologie et rapport qualité (EN/FR)
├── .github/         # modèles d'issues et de pull requests
├── notebooks/       # le(s) notebook(s) Colab
├── src/             # package d'analyse
├── src_fr/          # package d'analyse (messages en français)
├── CHANGELOG.md     # notes de version
├── CITATION.cff     # citer ce travail
├── CONTRIBUTING.md  # contribuer
├── LICENSE          # MIT (code)
├── README.fr.md     # cette page (français)
└── README.md        # version anglaise
```


## 🔐 Sécurité

- Les jetons et clés d'API ne sont **jamais** écrits sur disque, affichés, journalisés, versionnés ni publiés ; la publication passe par l'API REST GitHub avec un jeton en mémoire, et chaque message d'erreur est expurgé.
- Utiliser un **jeton fine-grained** limité à ce dépôt, avec une date d'expiration ; le révoquer dès qu'il n'est plus utile.
- Chaque fichier est analysé avant chaque envoi ; la publication est annulée si un motif de jeton est trouvé.
- Le site est statique (ni serveur, ni base de données) ; l'assistant IA s'exécute dans le navigateur du visiteur.


## 📝 Citer ce travail

Voir [`CITATION.cff`](CITATION.cff) (bouton *Cite this repository* de GitHub), ou :

```bibtex
@software{ntl_zaf_2026,
  author  = {{African Development Bank} and {Data Innovation for Africa (DI4A)}},
  title   = {Night-time lights: eight use cases — Afrique du Sud — statistics & public policy, public dashboard and AI agent},
  year    = {2026},
  version = {2.1.0},
  url     = {https://github.com/paul-reitz/NTL_South_Africa_Project}
}
```


## ⚖️ Licence

© AfDB-DI4A (Banque africaine de développement — Data Innovation for Africa). **Toute réutilisation des résultats, cartes, graphiques ou images doit mentionner la source : « Source : AfDB-DI4A ».** Code : [MIT](LICENSE). Les données et images dérivées suivent la licence de chaque source (par exemple, les produits VIIRS de l'EOG, GHSL, WorldPop, geoBoundaries et les WDI de la Banque mondiale sont diffusés sous CC BY 4.0, OpenStreetMap sous ODbL) — consulter la licence de chaque source avant réutilisation.


## 🙏 Remerciements

Développé par la **Banque africaine de développement (BAD)** et **Data Innovation for Africa (DI4A)**. Lumières nocturnes : Earth Observation Group (Payne Institute, Colorado School of Mines) et NASA Black Marble, traitées avec Google Earth Engine.


---
<p align="center"><sub>Généré par le notebook le 2026-10-29 · version 2.1.0 · <a href="https://github.com/paul-reitz/NTL_South_Africa_Project">paul-reitz/NTL_South_Africa_Project</a></sub></p>
