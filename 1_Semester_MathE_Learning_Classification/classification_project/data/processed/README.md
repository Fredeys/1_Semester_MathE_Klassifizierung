# 📊 **Verarbeiteter MathE-Datensatz**

Ein optimierter und bereinigter Datensatz zur Analyse mathematischer Lernleistungen in der Hochschulbildung.

## 🗂️ **Datenübersicht**

- **Datenquellen**: Ursprünglicher Datensatz aus dem [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/1031/dataset+for+assessing+mathematics+learning+in+higher+education).
- **Spaltenanzahl**: **226** Spalten
  - Die ursprünglichen 8 Spalten wurden erweitert durch die **Bag-of-Words-Transformation** der Textfelder `Subtopic` und `Keywords`.
  - Jede einzigartige Kombination von Wörtern in diesen Feldern wurde in eine eigene Spalte umgewandelt.
- **Merkmale**:
  - **Ursprüngliche Spalten**:
    - `Student ID`: Eindeutige Kennung der Studierenden.
    - `Student Country`: Herkunftsland der Studierenden (numerisch kodiert).
    - `Question ID`: Eindeutige Fragekennung.
    - `Type of Answer`: Korrekt/Inkorrekt (numerisch kodiert).
    - `Question Level`: Schwierigkeitsgrad der Frage (numerisch kodiert).
    - `Topic`: Mathematisches Thema (numerisch kodiert).
    - `Subtopic`: Unterthema (in Bag-of-Words umgewandelt).
    - `Keywords`: Schlüsselwörter (in Bag-of-Words umgewandelt).
  - **Erweiterte Spalten**:
    - Jede einzigartige Kombination von Schlüsselwörtern und Unterthemen als binäre Indikatoren (z. B. `algebraic expressions`, `integration by parts`).

## 🚀 **Besonderheiten**

- **Fehlende Werte**: Keine fehlenden Werte im Datensatz.
- **Duplikate**: 2.083 doppelte Zeilen wurden entfernt.
- **Bag-of-Words**: Textfelder (`Subtopic`, `Keywords`) wurden in numerische Merkmale umgewandelt, was die Spaltenanzahl erheblich erhöht hat.
- **Label-Encoding**: Kategorische Merkmale (`Student Country`, `Question Level`, `Topic`) wurden numerisch kodiert.

## 📂 **Verwendung**

1. **Datei-Name**: `processed_dataset.csv`
2. **Spaltenanzahl**: 226 Spalten, geeignet für maschinelles Lernen und datengetriebene Analysen.
3. **Format**: CSV-Datei, bereit für Algorithmen wie Klassifikations- und Clustering-Modelle.

## 📜 **Lizenz**

Die Nutzung des Datensatzes erfolgt gemäß den Richtlinien des ursprünglichen [UCI-Datensatzes](https://archive.ics.uci.edu).
