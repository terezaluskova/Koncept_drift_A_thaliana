# Koncept drift analýza v metabolomické predikci při chladových stresových podmínkách u rostlin
Tento repozitář obsahuje praktickou část bakalářské práce zaměřenou na problematiku koncept driftu v metabolomických predikcích u rostlin druhu Arabidopsis thaliana vystavených dvěma teplotním podmínkám (6°C a 16°C). Hlavní skript, Jupyter Notebook - Koncept_drift_arabidopsis_thaliana.ipynb. Tento repozitář demonstruje využití různých metod strojového učení, technik detekce a korekce koncept driftu a strategií zpracování dat s cílem zlepšit přesnost predikcí podmíněných environmentálním stresem.
## Přehled

Notebook `Koncept_drift_Arabidopsis_thaliana.ipynb` provádí analýzu metabolomických dat pro predikci relativní růstové rychlosti (RGR) za chladového stresu (6°C a 16°C) s využitím dat ze studie Weiszmann et al. (2023). Obsahuje:

- **Zpracování dat**: Načítání a extrakce koncentrací metabolitů a dat RGR ze souborů Excel.
- **Škálování dat**: Implementace různých metod škálování (např. StandardScaler, MinMaxScaler, Pareto, VAST atd.).
- **Detekce koncept driftu**: Použití metod DDM a EDDM z knihovny `scikit-multiflow` k detekci změn v distribuci dat.
- **Trénování a přetrénování modelů**: Použití modelů Random Forest, Lineární regrese a Support Vector Regression s přetrénováním na detekovaných vzorcích driftu.
- **Evaluace**: Hodnocení výkonu modelů pomocí metrik jako R², MAE, MSE, RMSE a SMAPE pro různé teplotní scénáře.
- **Vizualizace**: Generování boxplotů pro zobrazení distribuce dat.
- **Korekce koncept driftu**: Přetrénování dat nebo znovu použití jiné funkce škálování dat.

Analýza zkoumá pět scénářů:
1. Trénování na 6°C → testování na 6°C
2. Trénování na 6°C → testování na 16°C
3. Trénování na 16°C → testování na 6°C
4. Trénování na 16°C → testování na 16°C
5. Kombinované trénování na 6°C + 16°C → kombinované testování

## Požadavky

Pro spuštění notebooku nainstalujte požadované balíčky Pythonu pomocí následujícího příkazu:

```bash
pip install numpy scipy scikit-learn scikit-multiflow pandas matplotlib seaborn
```

Ujistěte se, že máte nainstalovaný Python 3.8 nebo novější. Notebook používá následující knihovny:
- `numpy`
- `scipy`
- `scikit-learn`
- `scikit-multiflow`
- `pandas`
- `matplotlib`
- `seaborn`

## Instalace

1. Naklonujte repozitář:
   ```bash
   git clone https://github.com/váš-uživatelský-název/název-repozitáře.git
   cd název-repozitáře
   ```

2. Nainstalujte závislosti:
   ```bash
   pip install -r requirements.txt
   ```

   Případně nainstalujte požadované balíčky ručně, jak je uvedeno výše.

## Použití

1. Umístěte požadované soubory Excel do stejného adresáře jako notebook.
2. Otevřete Jupyter Notebook:
   ```bash
   jupyter notebook Koncept_drift_arabidopsis_thaliana.ipynb
   ```
3. Spusťte buňky postupně, abyste:
   - Nainstalovali závislosti
   - Načetli a zpracovali data
   - Škálovali data
   - Vizualizovali distribuce dat
   - Detekovali koncept drift a přetrénovali modely
   - Vyhodnotili výkon modelů
   - Provedli korekci pomocí přetrénování modelu nebo změňte škálování dat

Notebook vypisuje metriky výkonu (např. R², MAE, MSE) pro každý model a scénář.

## Zdroj dat

Data pocházejí ze studie:
> Weiszmann, J., et al. (2023). Metabolome plasticity in 241 Arabidopsis thaliana accessions reveals evolutionary cold adaptation processes. *Plant Physiology*, 193(2), 980–1000. DOI: [10.1093/plphys/kiad298](https://doi.org/10.1093/plphys/kiad298)


## Struktura projektu

- `Koncept_drift_Arabidopsis_thaliana.ipynb`: Hlavní Jupyter Notebook s analytickou pipeline.
- `README.md`: Tento soubor.

## Výsledky

Notebook hodnotí tři regresní modely (Random Forest, Lineární regrese, Support Vector Regression) napříč různými teplotními scénáři s využitím DDM a EDDM pro detekci koncept driftu. Klíčová zjištění zahrnují:
- Lineární regrese má nízký výkon v meziteplotních scénářích (např. 6°C → 16°C).
- Support Vector Regression vykazuje robustní výkon napříč scénáři.

Podrobné výsledky jsou vypsány v notebooku, včetně přesnosti, R², MAE, MSE, RMSE, SMAPE a výsledků křížové validace.

## Kontakt

Pro dotazy nebo zpětnou vazbu kontaktujte Tereza Lusková na 253298@vutbr.cz .
