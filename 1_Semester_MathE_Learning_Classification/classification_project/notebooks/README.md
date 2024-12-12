# 📊 **MathE Dataset Verarbeitung**

Ein Python-Skript zur Verarbeitung und Analyse des "MathE"-Datensatzes, der Lernleistungen in mathematischen Hochschulkursen bewertet.

## 🚀 **Funktionen**

- **Datenbereinigung**: Entfernt doppelte Zeilen und konvertiert fehlerhafte Werte.
- **Bag-of-Words**: Wandelt Textdaten (`Subtopic`, `Keywords`) in numerische Repräsentationen um.
- **Label-Encoding**: Kodiert kategorische Spalten in numerische Werte.
- **Kombination von Daten**: Verbindet numerische und textbasierte Daten zu einem verarbeiteten Datensatz.

## 📂 **Ausgabe**

Das Skript speichert den verarbeiteten Datensatz als `processed_dataset.csv` zur weiteren Analyse.

## 🛠️ **Verwendung**

1. Stelle sicher, dass die Datei `MathE dataset.csv` im Verzeichnis liegt.
2. Führe das Skript aus:
   ```bash
    python PreprocessingData_MathE_Classification_Frédéric Kurbel.ipynb
   ```
3. Der verarbeitete Datensatz wird im aktuellen Verzeichnis gespeichert.

## 📜 Lizenz

Dieses Projekt steht unter der MIT-Lizenz.
