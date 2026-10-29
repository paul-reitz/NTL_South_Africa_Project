<p align="right"><a href="methodology.md">English</a></p>

# Méthodologie — Afrique du Sud (2014–2025)

## Données et nettoyage

VIIRS DNB mensuel (VCMSLCFG) et annuel VNL V2, DMSP–VIIRS harmonisé, Black Marble quotidien, GHSL/WorldPop, Sentinel-5P NO₂/SO₂, MODIS LST, Banque mondiale. Nettoyage : pixels valides si cf_cvg ≥ 2, unité-mois gardée si ≥ 80 % de pixels observés, pics remplacés, fond et torchères masqués.

## 📈 Cas d'usage 1 — Dynamiques temporelles

- **Question** — L'activité accélère-t-elle ou ralentit-elle, hors effet de saison ?
- **Données** — VIIRS VCMSLCFG (monthly), VIIRS VNL V2 (annual), Harmonised DMSP–VIIRS (Li et al., 2020)
- **Méthode** — STL robuste (période 12) sur log(somme des lumières) ; pente de Theil–Sen et test de Mann–Kendall sur les composites annuels ; détection d'anomalies et de ruptures.
- **Validation** — Significativité de la tendance (Mann–Kendall) et cohérence mensuel/annuel (**p-value = 0,0088**)
- **Incertitude** — IC 95 % de la croissance annuelle : +0,6 % à +3,0 %
- **Limites** — Couverture nuageuse et nuits courtes en été ; la lumière n'est pas la valeur ajoutée.
- **Statut** — `experimental` · Confiance: élevée
- **Références** — Cleveland et al. (1990) STL ; Sen (1968) ; Elvidge et al. (2017).
- **Page du tableau de bord** — [`#time`](https://paul-reitz.github.io/NTL_South_Africa_Project/fr/?country=ZAF#time)

**Résultats de cette exécution**

- `F02` Entre 2014 et 2025, la lumière nocturne de Afrique du Sud a évolué de +2,1 % par an (IC 95 % : +0,6 % à +3,0 %). Sur les 12 derniers mois, le niveau désaisonnalisé est +3,0 % par rapport aux 12 mois précédents. (confiance élevée : tendance significative (p < 0,01 ; n = 12))
- `F66` Validation : Significativité de la tendance (Mann–Kendall) et cohérence mensuel/annuel (p-value = 0,0088). Incertitude : IC 95 % de la croissance annuelle : +0,6 % à +3,0 % Limites : Couverture nuageuse et nuits courtes en été ; la lumière n'est pas la valeur ajoutée. Statut : statistique expérimentale ; confiance élevée.

## 🗺️ Cas d'usage 2 — Croissance régionale et convergence

- **Question** — Quelles régions décollent, lesquelles décrochent ?
- **Données** — VIIRS VNL V2, GHSL / WorldPop, Sentinel-5P NO₂
- **Méthode** — Croissance robuste par unité (Theil–Sen, Mann–Kendall), classes croissance/stagnation/déclin, β- et σ-convergence, indice de Herfindahl.
- **Validation** — Corrélation de rang avec le NO₂ troposphérique (source indépendante) (**Spearman ρ = 0,66**)
- **Incertitude** — Classe attribuée seulement si |pente| ≥ seuil et p < α ; IC de β (erreurs robustes).
- **Limites** — Petites unités : bruit et débordement de lumière (blooming) entre voisins.
- **Statut** — `experimental` · Confiance: moyenne
- **Références** — Barro et Sala-i-Martin (1992) convergence ; Henderson, Storeygard et Weil (2012).
- **Page du tableau de bord** — [`#regions`](https://paul-reitz.github.io/NTL_South_Africa_Project/fr/?country=ZAF#regions)

**Résultats de cette exécution**

- `F03` Sur 52 unités ADM2, 33 sont en croissance significative, 16 stagnent et 3 déclinent. L'activité lumineuse reste concentrée : Gauteng concentre 20 % de la lumière nationale. (confiance moyenne : classement sur 52 unités, seuil ±1 %/an et p < 0,10)
- `F04` Entre unités ADM2, la lumière par habitant converge : les unités les moins éclairées rattrapent leur retard. (confiance moyenne : β = −0,064 [−0,084 ; −0,045], n = 52)
- `F24` Gauteng (ADM1, 2025) : part de la lumière nationale 19,9 %, croissance annuelle -0,7 % (IC -2,1 % à -0,0 %, classe Stagnation), lumière par habitant 0,401, population 0,87 M, dans le noir 26 %, PIB estimé (expérimental) 73,77 Md USD.
- `F25` KwaZulu-Natal (ADM1, 2025) : part de la lumière nationale 17,6 %, croissance annuelle +3,9 % (IC +2,4 % à +6,1 %, classe Croissance), lumière par habitant 0,526, population 0,59 M, dans le noir 10 %, PIB estimé (expérimental) 65,11 Md USD.

## 💹 Cas d'usage 3 — Relation lumières–PIB

- **Question** — Peut-on estimer la croissance avant sa publication, et le PIB régional ?
- **Données** — VIIRS, PIB réel (Banque mondiale, WDI)
- **Méthode** — log(lumière) ~ log(PIB) en niveaux et en croissance, MCO avec écarts-types HAC ; prévision hors échantillon ; PIB régional = PIB national réparti au prorata de la lumière.
- **Validation** — Suivi hors échantillon de la croissance officielle (**corrélation / EAM (points) = -0,54 / 1,7**)
- **Incertitude** — IC 95 % de l'élasticité : -0,19 à 4,11 ; intervalles de prévision 80 % et 95 %.
- **Limites** — Échantillon annuel court ; le PIB régional est une statistique expérimentale à confronter aux comptes régionaux.
- **Statut** — `experimental` · Confiance: moyenne
- **Références** — Henderson et al. (2012) AER ; Chen et Nordhaus (2011) PNAS ; Gibson et al. (2021) JDE.
- **Page du tableau de bord** — [`#time`](https://paul-reitz.github.io/NTL_South_Africa_Project/fr/?country=ZAF#time)

**Résultats de cette exécution**

- `F05` L'élasticité de la lumière au PIB réel est de 1,96 en niveaux (IC 95 % : −0,19 à 4,11, R² = 0,36, 12 années) et de −0,27 en taux de croissance (IC : −0,98 à 0,45). Hors échantillon, la croissance des lumières suit celle du PIB avec une corrélation de −0,54 (erreur absolue moyenne : 1,7 point de croissance). (confiance moyenne : n = 12, significatif mais IC large (4,31))
- `F36` Élasticité lumières–PIB réel en niveaux : β = 1,96 (IC 95 % -0,19 à 4,11, R² = 0,36, n = 12, confiance moyenne : n = 12, significatif mais IC large (4,31)). +1 % de PIB ↔ +β % de lumière.
- `F37` Élasticité lumières–PIB réel en taux de croissance : β = -0,27 (IC 95 % -0,98 à 0,45, R² = 0,01, n = 11, confiance faible : n = 11, non significatif (p = 0,47)). +1 % de PIB ↔ +β % de lumière.
- `F38` Élasticité lumières–PIB réel en série longue DMSP–VIIRS : β = 0,87 (IC 95 % 0,58 à 1,15, R² = 0,88, n = 30, confiance élevée : n = 30, p < 0,01, IC étroit). +1 % de PIB ↔ +β % de lumière.

## ⚡ Cas d'usage 4 — Chocs et résilience

- **Question** — Quelle a été la profondeur d'un choc, et la vitesse de récupération ?
- **Données** — VIIRS (monthly), Black Marble VNP46A2 (daily), catalogue d'événements
- **Méthode** — Écart au niveau d'avant-choc sur la série désaisonnalisée ; ruptures structurelles ; indice quotidien Black Marble.
- **Validation** — Le creux dépasse-t-il la variabilité ordinaire ? (**creux (choc principal) = -10,4 % — non**)
- **Incertitude** — Variabilité mensuelle d'avant-choc (écart-type robuste) ; ruptures inexpliquées signalées.
- **Limites** — Les chocs touchant des activités peu éclairées (agriculture, services de jour) sont sous-estimés.
- **Statut** — `experimental` · Confiance: faible
- **Références** — Román et al. (2018) ; Elvidge et al. (2020) lumières et confinements.
- **Page du tableau de bord** — [`#shocks`](https://paul-reitz.github.io/NTL_South_Africa_Project/fr/?country=ZAF#shocks)

**Résultats de cette exécution**

- `F06` Le choc le plus marqué dans la série désaisonnalisée est « COVID-19 » : creux de -10,4 % (09/2020), retour au niveau d'avant-choc après 7 mois. (confiance faible : creux comparé à la variabilité mensuelle d'avant-choc)
- `F40` COVID-19 (2020-03-01 → 2021-06-30) : creux de -10,4 % le 2020-09-01, retour au niveau d'avant-choc après 7 mois. Distinct du bruit : non.
- `F41` Ruptures structurelles : 2017-02-01 (11,8 %); 2022-07-01 (-13,3 %); 2024-07-01 (8,6 %). Sans événement connu à ±6 mois : 3.
- `F42` Régions les plus touchées (creux) : Western Cape -18,7 % (covid19), Mpumalanga -15,5 % (covid19), Gauteng -15,2 % (covid19), Free State -14,2 % (covid19), North West -13,8 % (covid19).

## ⚖️ Cas d'usage 5 — Inégalités et électrification

- **Question** — Où vivent les populations privées d'électricité ?
- **Données** — VIIRS VNL V2, GHSL / WorldPop, GHSL SMOD, accès à l'électricité (WDI)
- **Méthode** — Gini et Theil pondérés par la population ; population des pixels habités sous le seuil de détection ; sensibilité à trois seuils ; IC bootstrap de la variation du Gini.
- **Validation** — Écart avec le taux d'accès à l'électricité de la Banque mondiale (**écart moyen (points) = -5,6**)
- **Incertitude** — Plage selon le seuil de radiance ; IC bootstrap du Gini.
- **Limites** — Proxy de l'éclairage extérieur, pas du raccordement : un foyer raccordé mais peu éclairé paraît « dans le noir ».
- **Statut** — `experimental` · Confiance: moyenne
- **Références** — Theil (1967) ; Falchetta et al. (2020) accès à l'électricité par les lumières.
- **Page du tableau de bord** — [`#inequality`](https://paul-reitz.github.io/NTL_South_Africa_Project/fr/?country=ZAF#inequality)

**Résultats de cette exécution**

- `F07` Le Gini de la lumière par habitant (ADM2) vaut 0,23 en 2025 (évolution non significative depuis 2014). Environ 0,50 million(s) de personnes vivent dans des zones habitées sans lumière détectable (18 % de la population habitée). (confiance moyenne : sensible au seuil de radiance (de 0,50 à 0,54 M selon le seuil) ; proxy d'éclairage extérieur, pas de raccordement)
- `F43` Gini de la lumière par habitant (ADM2) : 0,226 en 2014 → 0,229 en 2025 (variation 0,003, IC bootstrap -0,086 à 0,064). Theil T 0,082 ; part entre régions 50 %.
- `F44` Habitants de zones habitées sans lumière détectable : 0,48 M (20 %) en 2014 → 0,50 M (18 %) en 2025. Rapport lumière/hab. urbain/rural 0,3. Proxy de l'accès à l'électricité, sensible au seuil.
- `F45` Écart moyen entre la part de la population en zone éclairée et le taux d'accès à l'électricité de la Banque mondiale : -5,6 points.

## 🏭 Cas d'usage 6 — Zones industrielles

- **Question** — Où est l'industrie, et son activité progresse-t-elle ?
- **Données** — VIIRS VNL V2, GHSL BUILT-S, Sentinel-5P NO₂/SO₂, MODIS MOD11A2, OpenStreetMap
- **Méthode** — Concordance de six signaux par pixel (≥ 3 dont la lumière), grappes 8-connexes, typologie et confiance.
- **Validation** — Comparaison avec la liste de référence (n.d.) (**précision / rappel / F1 = non disponible**)
- **Incertitude** — Confiance par grappe selon le nombre de signaux forts ; sites isolés à vérifier.
- **Limites** — Résolution de Sentinel-5P (≈ 5 km) et MODIS (1 km) : les signaux qualifient un voisinage.
- **Statut** — `experimental` · Confiance: faible
- **Références** — Elvidge et al. (2016) torchères ; Pesaresi et al. (2023) GHSL.
- **Page du tableau de bord** — [`#industry`](https://paul-reitz.github.io/NTL_South_Africa_Project/fr/?country=ZAF#industry)

**Résultats de cette exécution**

- `F08` 400 grappes industrielles détectées par concordance de signaux satellitaires : 40 d'industrie lourde, 77 zones d'activités et de logistique, 221 sites d'hydrocarbures et 62 sites isolés à vérifier. Elles émettent 22,3 % de la lumière nationale (dernière année) ; leur lumière évolue de -1,4 % par an. Gauteng concentre la plus forte activité industrielle. (confiance faible : aucune liste de référence pour valider la détection)
- `F46` 400 grappes industrielles (≥ 3 signaux sur 6) : Hydrocarbures et torchères 221, Zone d'activités et logistique 77, Site isolé à vérifier 62, Industrie lourde 40. Part de la lumière nationale : 22,3 % ; croissance annuelle -1,4 %. Pas de validation disponible.
- `F47` IND-001 — Hydrocarbures et torchères à City of Johannesburg (Gauteng) (3252.52 km², 3 signaux, confiance faible); IND-004 — Hydrocarbures et torchères à Gert Sibande (Mpumalanga) (155.875 km², 4 signaux, confiance moyenne); IND-002 — Hydrocarbures et torchères à Sedibeng (Gauteng) (204.035 km², 3 signaux, confiance faible); IND-003 — Hydrocarbures et torchères à Nkangala (Mpumalanga) (179.31 km², 4 signaux, confiance moyenne); IND-006 — Hydrocarbures et torchères à Nkangala (Mpumalanga) (113.52 km², 4 signaux, confiance moyenne); IND-005 — Site isolé à vérifier à Sedibeng (Gauteng) (133.3 km², 3 signaux, confiance faible); IND-015 — Hydrocarbures et torchères à City of Cape Town (Western Cape) (22.36 km², 2 signaux, confiance faible); IND-018 — Hydrocarbures et torchères à Fezile Dabi (Free State) (15.695 km², 3 signaux, confiance faible); IND-032 — Hydrocarbures et torchères à City of Cape Town (Western Cape) (10.32 km², 3 signaux, confiance faible); IND-008 — Industrie lourde à Sedibeng (Gauteng) (40.85 km², 4 signaux, confiance moyenne)
- `F48` Gauteng : 86 grappe(s) industrielle(s), 3 946,3 km², 64,3 % de la lumière de la région.

## 🏖️ Cas d'usage 7 — Tourisme saisonnier

- **Question** — Quelles zones vivent du tourisme, et comment évolue la saison ?
- **Données** — VIIRS (monthly), nuitées ou arrivées WDI
- **Méthode** — Surcroît estival net des unités comparables de même latitude ; test unilatéral ; indice de saison base 100 ; saisons recoupant le Ramadan signalées.
- **Validation** — Corrélation avec international tourist arrivals (WDI) (**r = -0,28**)
- **Incertitude** — p-valeur par unité ; années 2020–2021 exclues du classement.
- **Limites** — Toute activité estivale (diaspora, résidences secondaires, festivals) est captée, pas seulement le tourisme.
- **Statut** — `experimental` · Confiance: faible
- **Références** — Analyses saisonnières des lumières et du tourisme, par ex. Hu et al. (2021).
- **Page du tableau de bord** — [`#tourism`](https://paul-reitz.github.io/NTL_South_Africa_Project/fr/?country=ZAF#tourism)

**Résultats de cette exécution**

- `F09` 1 unités sur 52 ont un surcroît de lumière estival net d'au moins 10 % : City of Cape Town (Western Cape). Le surcroît net médian atteint +13 % dans la zone la plus touristique. L'indice de saison (base 100 = 2019) tombe à 103 en 2020 et vaut 41 en 2025. (confiance faible : corrélation de -0,28 avec international tourist arrivals (WDI) (7 années))
- `F58` 1 zone(s) touristique(s) sur 52 unités ADM2 (surcroît estival net ≥ 10 %, mois de pointe [12, 1]) : City of Cape Town (Western Cape) (+13 %, confiance élevée).
- `F59` Indice de saison (base 100 = 2019) : 2014 : 30, 2015 : 5, 2016 : 65, 2017 : 113, 2018 : 77, 2019 : 100, 2020 : 103, 2021 : 105, 2022 : 75, 2023 : 68, 2024 : 99, 2025 : 41. Années avec Ramadan chevauchant la saison : 2021, 2022, 2023, 2024, 2025.
- `F60` Corrélation entre l'indice de saison et international tourist arrivals (WDI) : -0,28 (7 années ; en croissance : 0,13).

## 🏙️ Cas d'usage 8 — Signaux d'urbanisation

- **Question** — Où les villes s'étendent-elles, où les villages s'électrifient-ils, et où la population croît-elle sans lumière ?
- **Données** — VIIRS VNL V2, GHSL GHS-POP / WorldPop, GHSL GHS-BUILT-S R2023A, population urbaine (WDI)
- **Méthode** — Surface éclairée (pixels au-dessus du seuil) et population par unité ; croissances de Theil–Sen ; pixels nouvellement éclairés (sombres deux années de suite au début, éclairés deux années de suite à la fin), séparés entre électrification de zones habitées et nouvelles implantations ; typologie lumière/population.
- **Validation** — Corrélation de rang avec la croissance de la surface bâtie GHSL (source indépendante) (**Spearman ρ = 0,80**)
- **Incertitude** — Persistance exigée sur deux années pour limiter le bruit ; marge de ± 1 point entre croissances avant de classer.
- **Limites** — La lumière mesure l'éclairage extérieur, pas l'urbanisation au sens administratif ; le débordement (blooming) élargit les villes ; la population GHSL est interpolée entre époques.
- **Statut** — `experimental` · Confiance: élevée
- **Références** — Zhou et al. (2015) étendue urbaine par les lumières ; Pesaresi et al. (2023) GHSL ; Min et al. (2013) électrification des villages.
- **Page du tableau de bord** — [`#urban`](https://paul-reitz.github.io/NTL_South_Africa_Project/fr/?country=ZAF#urban)

**Résultats de cette exécution**

- `F61` Surface éclairée nationale : +6,8 % par an ; population : +1,0 % par an. Classes (ADM2) : Urbanisation électrifiée 45, Croissance non éclairée 3, Croissance équilibrée 2, Stable ou en déclin 2.
- `F62` Entre 2014 et 2025 : 51 243 km² nouvellement éclairés, dont 1 415 km² de zones déjà habitées (électrification, ≈ 49 k habitants) et 49 828 km² de nouvelles implantations ; 1 756 km² ont perdu leur lumière.
- `F63` Plus forte extension de la surface éclairée : Alfred Nzo (Eastern Cape) (+23,7 %/an), O.R.Tambo (Eastern Cape) (+21,2 %/an), Umkhanyakude (KwaZulu-Natal) (+19,2 %/an), Umzinyathi (KwaZulu-Natal) (+18,7 %/an), Amathole (Eastern Cape) (+17,3 %/an), Joe Gqabi (Eastern Cape) (+13,4 %/an). Croissance non éclairée (population plus rapide que la lumière) : City of Cape Town (Western Cape), City of Johannesburg (Gauteng), Ekurhuleni (Gauteng).
- `F64` Corrélation de rang (Spearman) entre croissance de la surface éclairée et croissance du bâti GHSL : 0,80 (p = 0,000, 52 unités).

## Limites générales des lumières nocturnes

- **Ce que mesurent les lumières** — Radiance émise vers le haut vers 01 h 30 : l'agriculture, le commerce de jour, les services peu éclairés et l'économie informelle rurale sont mal captés.
- **Saturation et débordement** — DMSP sature au centre des villes (DN 63) et « déborde » (blooming) ; VIIRS est bien meilleur mais le débordement gonfle encore la surface éclairée des villes.
- **Torchères et sites isolés** — Le masque automatique peut retirer des mines, ports ou centrales isolés, et manquer de petites torchères ; les candidats sont exportés pour vérification.
- **Nuages, saisons, lune** — Les mois nuageux sont partiellement observés ; la STL retire la saisonnalité moyenne mais pas une saison anormale (neige, mousson tardive).
- **Ruptures de produit** — DMSP et VIIRS ne sont pas directement comparables : la série longue harmonisée (Li et al., 2020) est un produit modélisé, à lire en tendance seulement.
- **Élasticité NTL–PIB** — Estimée sur 10 à 30 points annuels : intervalles larges, instabilité possible, relation non causale et variable selon le niveau de développement.
- **Accès à l'électricité** — « Habité sans lumière » ≠ « non raccordé » : un foyer raccordé à faible consommation est invisible ; l'indicateur dépend fortement du seuil de radiance et de la population.
- **Limites administratives** — geoBoundaries/GAUL peuvent différer des limites officielles ; les petites unités ADM2 sont sensibles au débordement de la lumière des voisines.
- **Zones industrielles** — La détection repose sur des seuils : une centrale, un port ou un grand centre commercial peut cumuler les signaux ; une usine peu éclairée ou sans émissions visibles échappe à la détection. Sentinel-5P (≈ 5 km) et MODIS (1 km) sont plus grossiers que VIIRS : les signaux NO₂/SO₂/chaleur qualifient un voisinage, pas un bâtiment.
- **Tourisme estival** — Le surcroît estival mesure toute hausse de lumière en été (résidences secondaires, diaspora, fêtes, chantiers), pas seulement le tourisme ; aux hautes latitudes, les nuits d'été très courtes réduisent les observations VIIRS. Le Ramadan modifie l'activité nocturne : les étés concernés sont signalés.
- **Urbanisation** — La surface éclairée dépend du seuil de détection et du débordement de lumière (blooming) autour des villes ; un quartier raccordé mais peu éclairé reste invisible. La population (GHSL/WorldPop) est modélisée à partir des recensements : sa croissance n'est pas une observation indépendante, et les années entre deux millésimes sont interpolées.


---
<sub>Généré par le notebook le 2026-10-29 · version 2.1.0</sub>
