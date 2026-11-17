# Sources Map — Paper 2: "Not rainfall: mean rainfall and population loss in the 1899–1900 famine"

Author: Atharva Chourey
Affiliation: Atharva Chourey Lab (independent research lab)

*Manuscript in preparation — not yet peer-reviewed.*

**Title note:** The brief's original title ("Political boundaries, not rainfall: population loss in the 1899–1900 famine") was retitled under the binding precedent-sweep verdicts (see Novelty section below): the mean-rainfall null now leads, and "political boundaries" is demoted to re-quantification framing. Current title: "Not rainfall: mean rainfall and population loss in the 1899–1900 famine — a famine-focused re-extraction of the Imperial Gazetteers for central India".

**Source projects:** `~/workspace/famine-1900-patterns/` (REPORT.md, districts.csv, atlas_layer.csv, analysis.py, build_data.py, sources/, figures/) and `~/workspace/india-historical-stats/` (REPORT.md, panel.csv, panel_population.csv, scripts/). Precedent sweep: `~/workspace/papers/precedent-sweep/SWEEP.md` (P2 section).

---

## 1. Key numbers as used, with exact sources

| # | Number as used in paper | Source file — section / column |
|---|---|---|
| 1 | Panel of 34 units = 19 Central Provinces districts + 4 Berar districts + 11 Central India Agency princely states | famine-1900-patterns/REPORT.md, Scope header; districts.csv (34 rows; group counts CP 19, Berar 4, CI 11) |
| 2 | Princely states mean population change 1891→1901 = **−16.2%** (unweighted, n = 11) | REPORT.md §3 Pattern 1 and §1 consistency paragraph; districts.csv column `pct_change_1891_1901`, unit_type "Princely…". Independently recomputed from districts.csv for this paper: mean = −16.22% |
| 3 | British districts mean = **−7.5%** (unweighted, n = 23) | REPORT.md §3 Pattern 1; districts.csv same column. Recomputed: −7.51% |
| 4 | Gap = 8.7 percentage points (derived: −7.5 − (−16.2)) | Arithmetic on #2/#3 as printed in REPORT.md |
| 5 | **Headline:** correlation, normal (mean) rainfall vs population change = **r = −0.05, n = 20**, not significant | REPORT.md §3 Pattern 1 ("correlation between a unit's normal rainfall and its population change is r = −0.05 (n = 20)"); districts.csv columns `rainfall_normal_in` × `pct_change_1891_1901` (20 non-blank pairs). Recomputed for this paper: r = −0.053, p = 0.82 (Pearson, analysis.py method). Variable is long-run NORMAL rainfall, not the 1899 deficit — see §2.3 of paper |
| 6 | Four worst units, all princely, all intensity class 5: Bhopal −30.1% (−30.08), Jaora −28.4% (−28.43), Dewas (Sr+Jr) −23.2%, Indore −22.7% (−22.66) | REPORT.md §1 ranked table; districts.csv / atlas_layer.csv rows |
| 7 | Full range: −30.1% (Bhopal) to +14.3% (Nimar, +14.33); 30 of 34 units declined, 4 grew | districts.csv `pct_change_1891_1901` (full column, recomputed count for this paper) |
| 8 | Worst British district: Saugor −20.4% (−20.41) | REPORT.md §1 table; districts.csv |
| 9 | Balaghat: wettest district, 63 in normal rainfall, −14.9% (−14.88). Barwani: 20.9 in, −4.5% (density-derived) | REPORT.md §3 Pattern 1; districts.csv columns `rainfall_normal_in`, `pct_change_1891_1901`; build_data.py Barwani row |
| 10 | 1899 rainfall where surviving (4 units only): Indore 7.58 in vs ~26.5 norm (28.6% of normal); Bhopal 33 vs ~45 (73.3%); Ratlam 15 vs 34 (44.1%); Barwani 7.26 vs 20.9 (34.7%) | districts.csv columns `rainfall_1899_in`, `rainfall_normal_in`, `rainfall_1899_pct_of_normal`; REPORT.md §1 (Indore anchor) |
| 11 | Indore out of cultivation: 386,764 of 1,504,636 acres = 25.7%; Rampura zila 68.9% (193,449 of 280,893) | REPORT.md §1 and §2(v); districts.csv `out_of_cultivation_pct`; build_data.py Indore row |
| 12 | Ratlam: out of cultivation 37.5%; death-rate 56‰ famine year vs 20‰ ordinary; town grew 29,822 → 36,321; change −6.1% (density-derived) | REPORT.md §2(v), §4; districts.csv Ratlam row; build_data.py Ratlam row (Luard, Census 1901 CI Ch. II) |
| 13 | Barwani: 6,900 registered deaths "due to famine sickness" ≈ 9% of enumerated population | REPORT.md §2(ii); build_data.py Barwani row (Luard Ch. II) |
| 14 | Province death-rates, famine period Nov 1899–Oct 1900: CP 54.37‰ vs decennial avg 34.50‰ (calendar 1900: 56.68‰); Berar 82.1‰ vs 38.8‰ | REPORT.md §2(ii); build_data.py PROVINCE_SERIES (Famine Commission 1901 paras 183/186) |
| 15 | District death-rates 1900 (‰): Basim 110.8, Nimar 105.0, Sambalpur 103.9, Buldana 95.4, Chanda 91.9, Wardha 85.1, Chhindwara 83.6, Betul 81.4 | REPORT.md §2(ii); districts.csv `death_rate_1900_per_mille` (Famine Commission paras 184/186 per build_data.py) |
| 16 | Mortality vs population change: r = +0.46, n = 9, not significant | REPORT.md §3 Pattern 2; districts.csv (9 non-blank death-rate rows). Recomputed: r = +0.462 |
| 17 | Nimar: death-rate 105.0‰ yet population +14.3%; Famine Commission's own figure +14.37% (para 184) | REPORT.md §3 Pattern 2, §5; districts.csv Nimar row |
| 18 | Relief coverage, 12 units: Betul 45% (Aug 1900), undivided Raipur 44% printed, Akola-proper ~39%, Nimar 31%, Bilaspur ~29% (28.7), Hoshangabad 24%, Amraoti+Ellichpur ~23%, Buldana ~23%, Chanda ~22%, Saugor ~15% (14.8), Jubbulpore ~9%, Wun 3.6%. CP province peak ~20% (Chief Commissioner) | REPORT.md §2(iii); districts.csv columns `relief_peak_pct_of_population`, `relief_peak_persons`, `relief_peak_when` |
| 19 | Relief vs population change: r = +0.30, n = 12, not significant | REPORT.md §3 Pattern 3. Recomputed: r = +0.297 |
| 20 | Outturn 1899–1900: CP province 25% of normal; Raipur ~17% (one-sixth), Wardha 25%, Betul 30%, Narsinghpur 40% | REPORT.md §2(v); districts.csv `outturn_pct_of_normal`; build_data.py PROVINCE_SERIES (CP 25%) |
| 21 | Berar jowar prices (seers per rupee): 23 (1895–6 normal), 11⅝ (1896–7), 27.5 (1898–9), ~15 (1899–1900 avg), 11.1 (1900–1 avg), 5–7 (worst months early 1900) → 3.3–4.6× normal price at peak | REPORT.md §2(iv); build_data.py PROVINCE_SERIES `berar_jowar_seers_per_rupee` (IG Berar, Prices section) |
| 22 | Trend-adjusted deficit computable for 25 of 34 units; worst: Jaora −33.8%, Bhopal −29.9%, Dhar −26.2% (1880s growth +13.6%), Bilaspur −26.1%, Indore −25.9%, Drug −24.6%, Balaghat −24.3%, Saugor −24.1%; Mandla warning case −17.2% | REPORT.md §2(i); districts.csv columns `deficit_vs_trend_pct`, `trend_growth_1881_91_pct` (25 non-blank rows, recomputed count) |
| 23 | Rail: rail-served mean −10.5% (n = 22) vs non-rail −10.1% (n = 12), Welch t p = 0.89; rainfall slopes rail +0.05, no-rail −0.09 pp/inch | REPORT.md §4 (railways verdict); analysis.py statistics block. Recomputed means: −10.46 / −10.09, p = 0.89 |
| 24 | Crop-regime group means: cotton tract (n = 6) −1.4%; rice tract (n = 7) −9.7%; CP wheat & mixed (n = 10) −9.7%; Malwa plateau states (n = 6) −21.1% | REPORT.md §3 Pattern 4; analysis.py GROUPS definitions. Recomputed from districts.csv: −1.4 / −9.7 / −9.7 / −21.1 |
| 25 | Cotton-tract detail: Amraoti gratuitous relief 86,737 > works relief 52,644; cattle mortality 28% (Buldana) to 60% (Ellichpur Melghat) | REPORT.md §3 Pattern 4; build_data.py Amraoti/Buldana rows |
| 26 | Irrigation near-absence: Saugor ~3,000–5,000 acres; Hoshangabad ~4,000 acres; Wun < 20 sq mi; Amraoti < 5 sq mi; Famine Code planning standard works for 20% of population, 10% in irrigated tracts | REPORT.md §4 (irrigation verdict); build_data.py rows |
| 27 | Intensity classes: class 5 = 4 units (Bhopal, Jaora, Dewas, Indore); class 4 = 16; class 3 = 9; class 2 = 5; class 1 unused | districts.csv `intensity_class_1_5` (recomputed counts); REPORT.md §2 classification paragraph |
| 28 | Anchors: CP British population-weighted −9.2% (1911 boundaries) vs −9.3% (1901 boundaries); states' −16.2% vs Luard all-Central-India density fall −16.2% and −16.4% anchor | REPORT.md §1 "Consistency with the known anchors" |
| 29 | censusindia cross-check: agreement within ±0.6% (Narsinghpur 315,518 identical; Betul 287,807 identical; Sagar 469,686 vs 469,479, +0.04%; etc.); censusindia "Indore" 302,057 (modern district) vs Indore State 850,690; doi:10.7910/DVN/ON8CP8 | REPORT.md §0 cross-check paragraph |
| 30 | Companion panel (1931-boundary basis): famine-decade medians British −9.5% [IQR −12.3, −2.9] vs princely −14.0% [−22.8, −8.6]; means British −7.5%, states −15.9%; 1881–91 medians +8.8% vs +6.5%; 1901–11 +17.7% vs +14.1%; 1921–31 +11.5% vs +6.8%; indexed aggregates 1881=100 → 1941: 140.8 vs 124.9; 1901 aggregates 100.3 vs 87.2; states pass 1891 level in 1931, districts in 1911; 1921: 8/11 states vs 8/22 districts still below 1891 | india-historical-stats/REPORT.md §3 (table + findings 1–3), computed by scripts/analysis_population.py from panel_population.csv |
| 31 | Barwani famine-decade change on panel basis: −5.1% (enumerated absolutes) vs −4.5% density-derived in famine dataset — flagged basis difference | india-historical-stats/REPORT.md §3 finding 1; panel_population.csv Barwani rows (1891: 80,266; 1901: 76,136) |

## 2. Sweep-derived numbers (source: precedent sweep, not the two project folders)

| Number as used | Source |
|---|---|
| Roy (2014) extraction: 430 British districts + 130 princely states (= 560 units), 25-volume Imperial Gazetteer (1908), variables incl. rainfall; *European Review of Economic History* 18(3), 324–348 | SWEEP.md P2a |
| Holderness: famine-affected native states 42M (1891) → 36M (1901) = −14.5%; unaffected states +12% | SWEEP.md P2b |
| Famine Commission (1901): −4.92% in affected British districts | SWEEP.md P2b |
| Contemporary estimates: ~3M deaths native states vs ~1M British territory, as reported in *Encyclopaedia Britannica* (1911), "Famine" | SWEEP.md P2b |
| Burgess & Donaldson (2010), *American Economic Review* 100(2), 449–453; panel 1875–1919, British districts only, annual rainfall deficits/shocks; 2017 extended version | SWEEP.md P2c; also famine REPORT.md §0/§4 (panel description) |
| Mishra et al. (2019), *Geophysical Research Letters* 46 — 1899 drought/ENSO linked to famine at all-India level | SWEEP.md P2c |

## 3. Brief numbers checked — status

- **"First statistical extraction from the 1908 Imperial Gazetteers"** — **NOT SUSTAINED; killed by sweep (P2a).** The project files themselves disclaim "first digitisation" (famine REPORT.md §0; india REPORT.md Claim discipline). Gazetteers are the Provincial Series volumes of 1908–09 (Central Provinces 1908, Central India 1908, Berar 1909), not a single 1908 volume. Paper makes no first-extraction claim; Roy (2014) is cited as first extraction.
- **Panel of 34 units** — VERIFIED (#1 above): 19 CP districts + 4 Berar districts + 11 CI states.
- **Census years 1891→1901** — VERIFIED: outcome is 1891→1901 throughout (paper §2.3). Note the decade contains both the 1896–97 and 1899–1900 famines (flagged in paper §§2.3, 4.2).
- **−16.2% vs −7.5%** — VERIFIED as unweighted means on the famine dataset's boundary basis (#2, #3). On the companion panel's 1931-boundary basis the states' mean is −15.9% (British −7.5% unchanged); medians are −14.0% vs −9.5%. Paper reports both bases (§§3.3, 3.7) and presents the contrast only as re-quantification (sweep P2b).
- **Rainfall r = −0.05** — VERIFIED (#5), with the binding scope correction: the variable is **normal (mean) rainfall**, n = 20 — *not* 1899 rainfall or the 1899 deficit. Paper headlines it in exactly that scoped form (sweep P2c).

## 4. Numbers NOT in the sources (paper says so explicitly; none invented)

- District-level 1899 rainfall / rainfall deviations for all units — only 4 units (Indore, Bhopal, Ratlam, Barwani) have 1899 values in the records. No deficit correlation is computed or claimed (paper §§2.3, 3.2, 4.2).
- District-level price multiples — do not survive; only the Berar province jowar series exists (paper §§2.3, 3.5).
- Princely-state relief coverage — not reported for any state; the Famine Commission was forbidden to enquire into Native States relief (paper §§2.3, 3.5).
- Princely-state mortality — no vital registration except Ratlam (rate) and Barwani (count); no death-rate exists for the other nine states (paper §2.3).
- No p-value for the headline rainfall correlation is printed in the project REPORT (it states only "not significant"); the recomputed p = 0.82 is recorded in this map (§1, #5) but the paper reports the correlation as "not significant", following the REPORT.
- Holderness's full bibliographic details — not recorded in the project files or the sweep; cited descriptively in the paper's References, flagged there.

## 5. NOVELTY CLAIMS — SWEEP-ADOPTED (supersedes "PENDING SWEEP")

Per `~/workspace/papers/precedent-sweep/SWEEP.md`, P2 verdicts, adopted in full in the paper:

- **P2a — KILLED.** "First statistical extraction / machine-readable panel from the 1908 Imperial Gazetteers." Killed by Roy (2014), *European Review of Economic History* 18(3), 324–348 (560-unit Gazetteer extraction, a decade earlier). **Surviving wording (adopted):** no "first extraction" claim anywhere; the paper is presented as a *famine-focused re-extraction / re-use* of the Gazetteer data and cites Roy (2014) as the first extraction (paper §1.3, Abstract, References).
- **P2b — KILLED as a finding.** "Princely states lost more than British districts (−16.2% vs −7.5%)." Direction and rough magnitude published contemporaneously: Census of India 1901 Report (Risley & Gait 1903), Famine Commission (1901), Holderness (−14.5% for famine-affected native states). **Surviving wording (adopted):** the −16.2% vs −7.5% figures appear only as a *re-quantification on Gazetteer units* of a contemporaneously published contrast (paper Abstract, §§1.3, 1.4, 3.3, 3.7).
- **P2c — HOLDS, and is the headline.** "Population change is essentially uncorrelated with rainfall (r = −0.05)." **Surviving wording (adopted verbatim in scope):** "Across the Gazetteer panel (British districts and princely states), 1891–1901 population change is essentially uncorrelated with Gazetteer-reported mean rainfall (r = −0.05)" — a statement about *mean* rainfall, never about the 1899 deficit; Burgess & Donaldson (2010) use deficits/shocks, a different variable, and are not conflated with it (paper Title, Abstract, §§1.2, 1.4, 3.2, 4.1).
- No other "first" claim is made in the paper. The dataset's inclusion of the princely states is described factually (censusindia and Burgess–Donaldson exclude them by construction) without a priority claim.

## 6. Gaps and discrepancies flagged in the paper

1. Two famines in one decade (1896–97 + 1899–1900) cannot be separated by this design (§§2.3, 4.2).
2. Migration inside the outcome variable; deaths vs out-flight inseparable for most states (§§1.2, 3.4, 4.2).
3. Luard's warning: 1891 Central India returns probably too high; state declines overstated by an unknown amount (§§3.3, 4.2).
4. Six density-derived state changes (Rewa, Dewas, Ratlam, Chhatarpur, Charkhari, Barwani) and one derived 1891 population (Sambalpur, from the Commission's +4.19%) (§2.2).
5. Boundary bases differ between the two projects (1911 vs latest-adjusted/1931); famine-decade states' mean −16.2% vs −15.9% accordingly (§§2.2, 3.7).
6. Narsinghpur 1891 discrepancy: 363,932 (famine dataset, 1911-boundary extraction) vs 368,932 (panel; 1911 volume's sex split sums to it — panel REPORT.md §2). Famine-decade change −13.3% is reported on the famine basis; flagged in §2.5 of the paper.
7. Chhatarpur discrepancy across projects: −15.0% density-based (famine dataset) vs −10.3% on Gazetteer enumerated absolutes (panel REPORT.md §§4–5). Paper uses the famine-dataset figure in its famine tables and flags the conflict here.
8. Ecological inference, unit heterogeneity, heterogeneous rainfall-normal definitions, non-significance of all correlations (§§2.6, 4.2).
9. Irrigation claim untestable in this region — no variance (§3.6).
10. Relief figures for Raipur cover the undivided district while its population row excludes Drug — printed 44% retained, never recomputed across bases (§2.2).
