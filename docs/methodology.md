<p align="right"><a href="methodology.fr.md">Français</a></p>

# Methodology — South Africa (2014–2025)

## Data and cleaning

VIIRS DNB monthly (VCMSLCFG) and annual VNL V2, harmonised DMSP–VIIRS, daily Black Marble, GHSL/WorldPop, Sentinel-5P NO₂/SO₂, MODIS LST, World Bank. Cleaning: pixels valid if cf_cvg ≥ 2, unit-month kept if ≥ 80% of pixels observed, spikes replaced, background and gas flares masked.

## 📈 Use case 1 — Time dynamics

- **Question** — Is activity accelerating or slowing down, net of seasonality?
- **Data** — VIIRS VCMSLCFG (monthly), VIIRS VNL V2 (annual), Harmonised DMSP–VIIRS (Li et al., 2020)
- **Method** — Robust STL (period 12) on log(sum of lights); Theil–Sen slope and Mann–Kendall test on annual composites; anomaly and break detection.
- **Validation** — Trend significance (Mann–Kendall) and monthly/annual consistency (**p-value = 0.0088**)
- **Uncertainty** — 95% CI of annual growth: +0.6% to +3.0%
- **Limits** — Cloud cover and short summer nights; light is not value added.
- **Status** — `experimental` · Confidence: high
- **References** — Cleveland et al. (1990) STL; Sen (1968); Elvidge et al. (2017).
- **Dashboard page** — [`#time`](https://paul-reitz.github.io/NTL_South_Africa_Project/?country=ZAF#time)

**Results of this run**

- `F02` Between 2014 and 2025, night-time light in South Africa changed by +2.1% per year (95% CI: +0.6% to +3.0%). Over the last 12 months, the seasonally adjusted level is +3.0% relative to the previous 12 months. (confidence high: significant trend (p < 0.01; n = 12))
- `F66` Validation: Trend significance (Mann–Kendall) and monthly/annual consistency (p-value = 0.0088). Uncertainty: 95% CI of annual growth: +0.6% to +3.0% Limitations: Cloud cover and short summer nights; light is not value added. Status: experimental statistic; confidence high.

## 🗺️ Use case 2 — Regional growth and convergence

- **Question** — Which regions take off, which fall behind?
- **Data** — VIIRS VNL V2, GHSL / WorldPop, Sentinel-5P NO₂
- **Method** — Robust growth per unit (Theil–Sen, Mann–Kendall), growth/stagnation/decline classes, β- and σ-convergence, Herfindahl index.
- **Validation** — Rank correlation with tropospheric NO₂ (independent source) (**Spearman ρ = 0.66**)
- **Uncertainty** — Class assigned only if |slope| ≥ threshold and p < α; CI of β (robust errors).
- **Limits** — Small units: noise and light blooming between neighbours.
- **Status** — `experimental` · Confidence: medium
- **References** — Barro & Sala-i-Martin (1992) convergence; Henderson, Storeygard & Weil (2012).
- **Dashboard page** — [`#regions`](https://paul-reitz.github.io/NTL_South_Africa_Project/?country=ZAF#regions)

**Results of this run**

- `F03` Of 52 ADM2 units, 33 show significant growth, 16 are stagnating and 3 are declining. Light remains concentrated: Gauteng accounts for 20% of national light. (confidence medium: classification of 52 units, threshold ±1%/yr and p < 0.10)
- `F04` Across ADM2 units, light per capita converges: the least-lit units are catching up. (confidence medium: β = −0.064 [−0.084; −0.045], n = 52)
- `F24` Gauteng (ADM1, 2025): share of national light 19.9%, annual growth -0.7% (CI -2.1% to -0.0%, class Stagnation), light per capita 0.401, population 0.87 M, in the dark 26%, estimated GDP (experimental) 73.77 bn USD.
- `F25` KwaZulu-Natal (ADM1, 2025): share of national light 17.6%, annual growth +3.9% (CI +2.4% to +6.1%, class Growth), light per capita 0.526, population 0.59 M, in the dark 10%, estimated GDP (experimental) 65.11 bn USD.

## 💹 Use case 3 — Light–GDP relationship

- **Question** — Can growth be estimated before its release, and regional GDP?
- **Data** — VIIRS, Real GDP (World Bank, WDI)
- **Method** — log(light) ~ log(GDP) in levels and growth, OLS with HAC errors; out-of-sample nowcast; regional GDP = national GDP allocated pro rata of light.
- **Validation** — Out-of-sample tracking of official growth (**correlation / MAE (pp) = -0.54 / 1.7**)
- **Uncertainty** — 95% CI of the elasticity: -0.19 to 4.11; 80% and 95% prediction intervals.
- **Limits** — Short annual sample; regional GDP is an experimental statistic to be checked against regional accounts.
- **Status** — `experimental` · Confidence: medium
- **References** — Henderson et al. (2012) AER; Chen & Nordhaus (2011) PNAS; Gibson et al. (2021) JDE.
- **Dashboard page** — [`#time`](https://paul-reitz.github.io/NTL_South_Africa_Project/?country=ZAF#time)

**Results of this run**

- `F05` The elasticity of light with respect to real GDP is 1.96 in levels (95% CI: −0.19 to 4.11, R² = 0.36, 12 years) and −0.27 in growth rates (CI: −0.98 to 0.45). Out of sample, light growth tracks GDP growth with a correlation of −0.54 (mean absolute error: 1.7 percentage points of growth). (confidence medium: n = 12, significant but wide CI (4.31))
- `F36` Light–real GDP elasticity in levels: β = 1.96 (95% CI -0.19 to 4.11, R² = 0.36, n = 12, confidence medium: n = 12, significant but wide CI (4.31)). +1% GDP ↔ +β% light.
- `F37` Light–real GDP elasticity in growth rates: β = -0.27 (95% CI -0.98 to 0.45, R² = 0.01, n = 11, confidence low: n = 11, not significant (p = 0.47)). +1% GDP ↔ +β% light.
- `F38` Light–real GDP elasticity in long DMSP–VIIRS series: β = 0.87 (95% CI 0.58 to 1.15, R² = 0.88, n = 30, confidence high: n = 30, p < 0.01, narrow CI). +1% GDP ↔ +β% light.

## ⚡ Use case 4 — Shocks and resilience

- **Question** — How deep was a shock, and how fast the recovery?
- **Data** — VIIRS (monthly), Black Marble VNP46A2 (daily), event catalogue
- **Method** — Gap to the pre-shock level on the seasonally adjusted series; structural breaks; daily Black Marble index.
- **Validation** — Does the trough exceed ordinary variability? (**trough (main shock) = -10.4% — no**)
- **Uncertainty** — Pre-shock month-to-month variability (robust SD); unexplained breaks flagged.
- **Limits** — Shocks hitting poorly lit activities (agriculture, daytime services) are underestimated.
- **Status** — `experimental` · Confidence: low
- **References** — Román et al. (2018); Elvidge et al. (2020) COVID-19 lockdown lights.
- **Dashboard page** — [`#shocks`](https://paul-reitz.github.io/NTL_South_Africa_Project/?country=ZAF#shocks)

**Results of this run**

- `F06` The most pronounced shock in the seasonally adjusted series is “COVID-19”: trough of -10.4% (09/2020), return to the pre-shock level after 7 months. (confidence low: trough compared with pre-shock month-to-month variability)
- `F40` COVID-19 (2020-03-01 → 2021-06-30): trough of -10.4% on 2020-09-01, back to the pre-shock level after 7 months. Distinguishable from noise: no.
- `F41` Structural breaks: 2017-02-01 (11.8 %); 2022-07-01 (-13.3 %); 2024-07-01 (8.6 %). Without a known event within ±6 months: 3.
- `F42` Hardest-hit regions (trough): Western Cape -18.7 % (covid19), Mpumalanga -15.5 % (covid19), Gauteng -15.2 % (covid19), Free State -14.2 % (covid19), North West -13.8 % (covid19).

## ⚖️ Use case 5 — Inequality and electrification

- **Question** — Where do people without electricity live?
- **Data** — VIIRS VNL V2, GHSL / WorldPop, GHSL SMOD, electricity access (WDI)
- **Method** — Population-weighted Gini and Theil; population of inhabited pixels below the detection threshold; sensitivity to three thresholds; bootstrap CI of the Gini change.
- **Validation** — Gap with the World Bank electricity-access rate (**mean gap (pp) = -5.6**)
- **Uncertainty** — Range across radiance thresholds; bootstrap CI of the Gini.
- **Limits** — Proxy of outdoor lighting, not of connection: a connected but dimly lit household looks “in the dark”.
- **Status** — `experimental` · Confidence: medium
- **References** — Theil (1967); Falchetta et al. (2020) electricity access from lights.
- **Dashboard page** — [`#inequality`](https://paul-reitz.github.io/NTL_South_Africa_Project/?country=ZAF#inequality)

**Results of this run**

- `F07` The Gini coefficient of light per capita (ADM2) is 0.23 in 2025 (no significant change since 2014). About 0.50 million people live in inhabited areas with no detectable light (18% of the inhabited population). (confidence medium: sensitive to the radiance threshold (from 0.50 to 0.54 M depending on the threshold); a proxy for outdoor lighting, not for grid connection)
- `F43` Gini of light per capita (ADM2): 0.226 in 2014 → 0.229 in 2025 (change 0.003, bootstrap CI -0.086 to 0.064). Theil T 0.082; between-region share 50%.
- `F44` People in inhabited areas without detectable light: 0.48 M (20%) in 2014 → 0.50 M (18%) in 2025. Urban/rural light-per-capita ratio 0.3. Proxy of electricity access, sensitive to the threshold.
- `F45` Average gap between the share of people in lit areas and the World Bank electricity-access rate: -5.6 points.

## 🏭 Use case 6 — Industrial zones

- **Question** — Where is industry, and is its activity growing?
- **Data** — VIIRS VNL V2, GHSL BUILT-S, Sentinel-5P NO₂/SO₂, MODIS MOD11A2, OpenStreetMap
- **Method** — Concordance of six signals per pixel (≥ 3 including light), 8-connected clusters, typology and confidence.
- **Validation** — Comparison with the reference list (n/a) (**precision / recall / F1 = not available**)
- **Uncertainty** — Per-cluster confidence from the number of strong signals; isolated sites to verify.
- **Limits** — Sentinel-5P (≈ 5 km) and MODIS (1 km) resolution: signals describe a neighbourhood.
- **Status** — `experimental` · Confidence: low
- **References** — Elvidge et al. (2016) gas flares; Pesaresi et al. (2023) GHSL.
- **Dashboard page** — [`#industry`](https://paul-reitz.github.io/NTL_South_Africa_Project/?country=ZAF#industry)

**Results of this run**

- `F08` 400 industrial clusters detected from concordant satellite signals: 40 heavy industry, 77 business parks & logistics, 221 oil & gas sites and 62 isolated sites to verify. They emit 22.3% of national light (latest year); their light changes by -1.4% per year. Gauteng has the most industrial activity. (confidence low: no reference list available to validate the detection)
- `F46` 400 industrial clusters (≥ 3 of 6 signals): Oil, gas & flares 221, Business park & logistics 77, Isolated site to verify 62, Heavy industry 40. Share of national light: 22.3%; annual growth -1.4%. No validation available.
- `F47` IND-001 — Oil, gas & flares in City of Johannesburg (Gauteng) (3252.52 km², 3 signals, confidence low); IND-004 — Oil, gas & flares in Gert Sibande (Mpumalanga) (155.875 km², 4 signals, confidence medium); IND-002 — Oil, gas & flares in Sedibeng (Gauteng) (204.035 km², 3 signals, confidence low); IND-003 — Oil, gas & flares in Nkangala (Mpumalanga) (179.31 km², 4 signals, confidence medium); IND-006 — Oil, gas & flares in Nkangala (Mpumalanga) (113.52 km², 4 signals, confidence medium); IND-005 — Isolated site to verify in Sedibeng (Gauteng) (133.3 km², 3 signals, confidence low); IND-015 — Oil, gas & flares in City of Cape Town (Western Cape) (22.36 km², 2 signals, confidence low); IND-018 — Oil, gas & flares in Fezile Dabi (Free State) (15.695 km², 3 signals, confidence low); IND-032 — Oil, gas & flares in City of Cape Town (Western Cape) (10.32 km², 3 signals, confidence low); IND-008 — Heavy industry in Sedibeng (Gauteng) (40.85 km², 4 signals, confidence medium)
- `F48` Gauteng: 86 industrial cluster(s), 3,946.3 km², 64.3% of the region's light.

## 🏖️ Use case 7 — Seasonal tourism

- **Question** — Which areas live from tourism, and how does the season evolve?
- **Data** — VIIRS (monthly), hotel nights or WDI arrivals
- **Method** — Summer excess net of comparable units at the same latitude; one-sided test; season index base 100; seasons overlapping Ramadan flagged.
- **Validation** — Correlation with international tourist arrivals (WDI) (**r = -0.28**)
- **Uncertainty** — p-value per unit; 2020–2021 excluded from the classification.
- **Limits** — Any summer activity (diaspora, second homes, festivals) is captured, not only tourism.
- **Status** — `experimental` · Confidence: low
- **References** — Seasonal light analyses of tourism, e.g. Hu et al. (2021).
- **Dashboard page** — [`#tourism`](https://paul-reitz.github.io/NTL_South_Africa_Project/?country=ZAF#tourism)

**Results of this run**

- `F09` 1 of 52 units show a net summer light excess of at least 10%: City of Cape Town (Western Cape). The median net excess reaches +13% in the most touristic zone. The season index (base 100 = 2019) falls to 103 in 2020 and stands at 41 in 2025. (confidence low: correlation of -0.28 with international tourist arrivals (WDI) (7 years))
- `F58` 1 tourist zone(s) out of 52 ADM2 units (net summer excess ≥ 10%, peak months [12, 1]): City of Cape Town (Western Cape) (+13%, confidence high).
- `F59` Season index (base 100 = 2019): 2014: 30, 2015: 5, 2016: 65, 2017: 113, 2018: 77, 2019: 100, 2020: 103, 2021: 105, 2022: 75, 2023: 68, 2024: 99, 2025: 41. Years when Ramadan overlaps the season: 2021, 2022, 2023, 2024, 2025.
- `F60` Correlation between the season index and international tourist arrivals (WDI): -0.28 (7 years; in growth rates: 0.13).

## 🏙️ Use case 8 — Urbanisation signals

- **Question** — Where do cities spread, where do villages get electrified, and where does population grow without light?
- **Data** — VIIRS VNL V2, GHSL GHS-POP / WorldPop, GHSL GHS-BUILT-S R2023A, urban population (WDI)
- **Method** — Lit area (pixels above the threshold) and population per unit; Theil–Sen growth rates; newly lit pixels (dark two years in a row at the start, lit two years in a row at the end), split between electrification of inhabited areas and new settlements; light/population typology.
- **Validation** — Rank correlation with GHSL built-up area growth (independent source) (**Spearman ρ = 0.80**)
- **Uncertainty** — Persistence required over two years to limit noise; ± 1 pp margin between growth rates before classifying.
- **Limits** — Light measures outdoor lighting, not urbanisation in the administrative sense; blooming widens cities; GHSL population is interpolated between epochs.
- **Status** — `experimental` · Confidence: high
- **References** — Zhou et al. (2015) urban extent from lights; Pesaresi et al. (2023) GHSL; Min et al. (2013) village electrification.
- **Dashboard page** — [`#urban`](https://paul-reitz.github.io/NTL_South_Africa_Project/?country=ZAF#urban)

**Results of this run**

- `F61` National lit area: +6.8% per year; population: +1.0% per year. Classes (ADM2): Electrified urbanisation 45, Unlit growth 3, Balanced growth 2, Stable or declining 2.
- `F62` Between 2014 and 2025: 51,243 km² newly lit, of which 1,415 km² already inhabited (electrification, ≈ 49k people) and 49,828 km² of new settlements; 1,756 km² lost their light.
- `F63` Fastest lit-area expansion: Alfred Nzo (Eastern Cape) (+23.7%/yr), O.R.Tambo (Eastern Cape) (+21.2%/yr), Umkhanyakude (KwaZulu-Natal) (+19.2%/yr), Umzinyathi (KwaZulu-Natal) (+18.7%/yr), Amathole (Eastern Cape) (+17.3%/yr), Joe Gqabi (Eastern Cape) (+13.4%/yr). Unlit growth (population faster than light): City of Cape Town (Western Cape), City of Johannesburg (Gauteng), Ekurhuleni (Gauteng).
- `F64` Spearman rank correlation between lit-area growth and GHSL built-up growth: 0.80 (p = 0.000, 52 units).

## General limits of night-time lights

- **What lights measure** — Upward radiance emitted around 01:30: agriculture, daytime trade, poorly lit services and the rural informal economy are poorly captured.
- **Saturation and blooming** — DMSP saturates in city centres (DN 63) and “blooms” beyond lit areas; VIIRS is much better, but blooming still inflates the lit area of cities.
- **Gas flares and isolated sites** — The automatic mask may remove isolated mines, ports or power plants, and miss small flares; candidates are exported for verification.
- **Clouds, seasons, moon** — Cloudy months are only partially observed; STL removes average seasonality but not an abnormal season (snow, late monsoon).
- **Product breaks** — DMSP and VIIRS are not directly comparable: the harmonised long series (Li et al., 2020) is a modelled product, to be read for trends only.
- **NTL–GDP elasticity** — Estimated on 10 to 30 annual observations: wide intervals, possible instability, a non-causal relationship that varies with the level of development.
- **Access to electricity** — “Inhabited without light” ≠ “not connected”: a connected household with low consumption is invisible; the indicator depends strongly on the radiance threshold and the population data.
- **Administrative boundaries** — geoBoundaries/GAUL may differ from official boundaries; small ADM2 units are sensitive to light spilling over from neighbouring units.
- **Industrial zones** — Detection relies on thresholds: a power plant, a port or a large shopping centre can meet the signals; a dimly lit factory without visible emissions is missed. Sentinel-5P (≈ 5 km) and MODIS (1 km) are coarser than VIIRS: NO₂/SO₂/heat signals describe a neighbourhood, not a building.
- **Summer tourism** — The summer excess captures any rise in summer light (second homes, diaspora visits, festivals, construction), not only tourism; at high latitudes, very short summer nights reduce VIIRS observations. Ramadan changes night-time activity: the summers concerned are flagged.
- **Urbanisation** — The lit area depends on the detection threshold and on light blooming around cities; a connected but dimly lit neighbourhood stays invisible. Population (GHSL/WorldPop) is modelled from censuses: its growth is not an independent observation, and years between two epochs are interpolated.


---
<sub>Generated by the notebook on 2026-10-29 · version 2.1.0</sub>
