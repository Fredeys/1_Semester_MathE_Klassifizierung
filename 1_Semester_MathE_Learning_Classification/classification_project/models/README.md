# Klassifikationspipeline: Optimierung und Vergleich von Modellen

## Überblick
Dieses Projekt untersucht die Optimierung von Klassifikationsmodellen mit verschiedenen Algorithmen: 
- **Random Forest**
- **Logistische Regression**
- **XGBoost**
- **LightGBM**

Das Ziel ist es, die beste Modellleistung durch verschiedene Techniken wie Hyperparameter-Optimierung, Datenresampling, Feature-Engineering und Dimensionalitätsreduktion zu erzielen. Die verwendeten Modelle werden umfassend evaluiert, um die Auswirkungen der Optimierungen zu bewerten.

---

## Methodik
### 1. Datenvorbereitung
- **Datensatz**: `processed_dataset.csv` mit 225 Features und der Zielvariable `Type of Answer`.
- **Datenaufteilung**: 80% Trainings- und 20% Testdaten.
- **Herausforderung**: Klassenungleichgewicht, welches durch Datenresampling und gewichtete Klassen adressiert wird.

---

### 2. Modelle und Optimierungstechniken

#### **Random Forest**
- **Optimierungsschritte**:
  - Hyperparameter-Tuning mittels `GridSearchCV`.
  - Gewichtung der Klassen mit `class_weight='balanced'`.
  - Resampling durch SMOTE (Synthetic Minority Over-sampling Technique).
  - Reduktion der Features basierend auf Wichtigkeiten.
- **Ergebnisse**:
  - Beste Genauigkeit: ~64%.
  - SMOTE verbesserte Recall und F1-Score.
  - Reduzierte Features führten zu stabileren Ergebnissen.

#### **Logistische Regression**
- **Optimierungsschritte**:
  - Resampling mit SMOTE zur Ausbalancierung der Klassen.
  - Klassen-Gewichtung durch `class_weight='balanced'`.
  - Feature-Skalierung (Standardisierung auf Mittelwert = 0, Standardabweichung = 1).
- **Ergebnisse**:
  - Beste Genauigkeit: ~57%.
  - Verbesserungen bei Recall für unterrepräsentierte Klassen.
  - SMOTE führte zu leichten Einbußen bei der Genauigkeit.

#### **XGBoost**
- **Optimierungsschritte**:
  - Hyperparameter-Tuning mittels `GridSearchCV`, `RandomizedSearchCV` und `Optuna`.
  - Feature-Auswahl basierend auf Feature-Importances.
  - Resampling mit SMOTE.
  - Dimensionalitätsreduktion mit PCA (Principal Component Analysis).
- **Ergebnisse**:
  - Baseline-Modell: Genauigkeit 65%.
  - Mit Optimierung (Optuna): Beste Genauigkeit 65%.
  - PCA-Modell: Genauigkeit 61%.

#### **LightGBM**
- **Optimierungsschritte**:
  - **Baseline-Modell**:
    - Training mit Standardparametern: Genauigkeit 64%.
  - **Hyperparameter-Tuning**:
    - Optimierte Parameter:
      - `learning_rate=0.1`, `min_child_samples=50`, `n_estimators=200`, `num_leaves=50`.
    - Genauigkeit: 64%.
  - **Feature-Auswahl**:
    - Reduktion auf die wichtigsten 45 Features basierend auf Feature-Importances (Schwellenwert: 8).
    - Training mit reduzierten Features: Genauigkeit 65%.
  - **Cross-Validation**:
    - 5-fache Kreuzvalidierung:
      - Genauigkeiten: [59.8%, 58.0%, 61.8%, 53.7%, 53.2%].
      - Durchschnittliche Genauigkeit: 57%.

- **Ergebnisse**:
  - Baseline-Modell: Genauigkeit 64%.
  - Beste Optimierung mit reduzierten Features: Genauigkeit 65%.
  - Stabilität durch Feature-Reduktion und Hyperparameter-Tuning verbessert.

---

## Ergebnisse und Erkenntnisse

### **Vergleich der Modelle**
| Modell                 | Baseline-Genauigkeit | Beste Optimierung   | Techniken, die die Leistung verbessert haben |
|------------------------|----------------------|---------------------|---------------------------------------------|
| **Random Forest**      | 64%                 | 64%                 | SMOTE, Feature-Reduktion, Klassen-Gewichtung|
| **Logistische Regression** | 57%            | 57%                 | SMOTE, Klassen-Gewichtung, Feature-Skalierung|
| **XGBoost**            | 65%                 | 65%                 | Optuna, Feature-Reduktion, SMOTE            |
| **LightGBM**           | 64%                 | 65%                 | SMOTE, Klassen-Gewichtung, Feature-Reduktion|

### **Schlüsselerkenntnisse**
- **Feature-Engineering**:
  - Feature-Reduktion und -Skalierung verbesserten die Modellstabilität erheblich.
- **Datenresampling (SMOTE)**:
  - Half, die Balance zwischen den Klassen zu verbessern, jedoch teilweise auf Kosten der Genauigkeit.
- **Hyperparameter-Tuning**:
  - Besonders effektiv bei XGBoost und LightGBM (Optuna und GridSearch ermöglichten präzise Feinabstimmung).

---

## Nutzung
### **Voraussetzungen**
- Python 3.7+ und folgende Bibliotheken:
  ```bash
  pip install pandas scikit-learn imbalanced-learn xgboost lightgbm optuna
  ```
