# Klassifikation: Methoden und Ergebnisse

## 📄 Projektübersicht
Dieses Projekt untersucht die Klassifikation von mathematischen Antworttypen mithilfe moderner maschineller Lernmodelle. Ziel ist es, die Leistung verschiedener Klassifikatoren wie **Random Forest**, **Logistische Regression**, **XGBoost** und **LightGBM** zu vergleichen und durch Techniken wie **Feature-Auswahl**, **Datenbalancierung (SMOTE)** und **Hyperparameter-Tuning** zu optimieren.  

Der Workflow umfasst:
- Datenvorbereitung
- Erstellung und Optimierung von Klassifikationsmodellen
- Analyse der Ergebnisse und Modellvergleich

---

## 📁 Dateistruktur
Die wichtigsten Dateien und deren Speicherorte sind wie folgt organisiert:

### **Daten**
- **Raw Data**: `data/raw/MathE dataset.csv`  
  Enthält den ursprünglichen Datensatz.
- **Verarbeitete Daten**: `data/processed/processed_dataset.csv`  
  Aufbereiteter Datensatz für maschinelle Lernmodelle.

### **Modelle**
- **LightGBM-Modell**: `models/LightGBM_MathE_Classification_Frédéric Kurbel.ipynb`  
- **Logistische Regression**: `models/LogisticRegression_MathE_Classification_Frédéric Kurbel.ipynb`  
- **Random Forest**: `models/RandomForestClassifier_MathE_Classification_Frédéric Kurbel.ipynb`  
- **XGBoost-Modell**: `models/XGBClassifier_MathE_Classification_Frédéric Kurbel.ipynb`  

### **Notebooks**
- **Datenvorverarbeitung**: `notebooks/PreprocessingData_MathE_Classification_Frédéric Kurbel.ipynb`  
  Notebook zur Datenbereinigung und -vorbereitung.

### **Berichte**
- **PDF-Bericht**: `reports/1_Semester_Classification_Project.pdf`  
  Wissenschaftliche Dokumentation des Projekts.  
- **LaTeX-Dokument**: `reports/1_Semester_Documentation_Classification.tex`  
  LaTeX-Datei für die wissenschaftliche Dokumentation.  
- **Quellenverzeichnis**: `reports/bibliography.bib`  
  Alle verwendeten Quellen im BibTeX-Format.

### **Weitere Dateien**
- **README.md**: Dieses Dokument.

---

## 🚀 Projektschritte
Das Projekt gliedert sich in folgende Hauptschritte:

1. **Datenvorbereitung**
   - Laden des Datensatzes und Bereinigung fehlender Werte.
   - Identifikation und Analyse doppelter Zeilen (2.083 doppelte Einträge).
   - Transformation von Textdaten (Bag-of-Words) und numerische Kodierung der kategorialen Merkmale.

2. **Feature-Auswahl**
   - Analyse der Feature-Wichtigkeit mit Techniken wie `Feature Importance`.
   - Reduktion irrelevanter Merkmale, um Modellstabilität und Effizienz zu verbessern.

3. **Modellerstellung und Optimierung**
   - **Random Forest**: Optimierung der Modellleistung durch `GridSearchCV`.
   - **Logistische Regression**: Skalierung der Features und Anwendung von SMOTE zur Datenbalancierung.
   - **XGBoost**: Randomized Search und SMOTE zur Optimierung und Balancierung der Klassenverteilung.
   - **LightGBM**: Feature-Reduktion und Hyperparameter-Tuning zur Steigerung der Genauigkeit.

4. **Ergebnisse und Modellvergleich**
   - Die besten Ergebnisse wurden mit **XGBoost** erzielt (Genauigkeit: 65.7%), gefolgt von **LightGBM** (Genauigkeit: 65.0%).
   - Techniken wie Datenbalancierung und Hyperparameter-Tuning verbesserten die Performance erheblich.

---

## ✍️ Autoren
Dieses Projekt wurde erstellt von:

- **Frédéric C. Kurbel**  
  Studiengang: Computational and Data Science  
  Kontakt: [GitHub-Profil](https://github.com/Fredeys)

- **Abdul J. Safi**  
  Studiengang: Computational and Data Science  

## 📝 Lizenz
Dieses Projekt steht unter der **MIT-Lizenz**.  
Details zur Lizenz finden Sie in der Datei [LICENSE](LICENSE) im Repository.

---

## 🛠️ Voraussetzungen
Um das Projekt auszuführen, sind folgende Komponenten erforderlich:

### **Software**
- **Python 3.7+**

### **Bibliotheken**
Die benötigten Python-Bibliotheken können mit folgendem Befehl installiert werden:
```bash
pip install pandas numpy scikit-learn xgboost lightgbm imbalanced-learn matplotlib seaborn
```

