---
lab:
  title: Erstellen visueller Berechnungen in Power BI Desktop
  module: Create Visual Calculations in Power BI Desktop
---

# Erstellen visueller Berechnungen in Power BI Desktop

## **Labszenario**

In dieser Übung werden Sie visuelle Berechnungen mithilfe von Data Analysis Expressions (DAX) erstellen. 

In diesem Lab lernen Sie Folgendes:

- Erstellen und Bearbeiten visueller Berechnungen
- Verwenden Sie die Funktionen PREVIOUS(), RUNNINGSUM() und MOVINGAVERAGE(), um Vergleichsmetriken zwischen den einzelnen Geschäftsjahren zu erstellen.
- Verwenden Sie den optionalen Parameter Axis bei der Erstellung von Vergleichsmetriken.
- Verwenden Sie den optionalen Parameter Reset, um die kumulativen Berechnungen in einer mehrstufigen Achse anzupassen.

**Dieses Lab sollte ungefähr 45 Minuten in Anspruch nehmen.**

## Erste Schritte

Um diese Übung abzuschließen, öffnen Sie zuerst einen Webbrowser, und geben Sie die folgende URL ein, um den ZIP-Ordner herunterzuladen:

`https://github.com/MicrosoftLearning/PL-300-Microsoft-Power-BI-Data-Analyst/raw/Main/Allfiles/Labs/05b-create-visual-calculations-in-power-bi-desktop/05b-visual-calculations.zip`

Entpacken Sie den Ordner in den Ordner **C:\Users\Student\Downloads\05b-visual-calculations**.

Öffnen Sie die Datei **05b-Starter-Verkaufsanalyse.pbix**.

> ***Hinweis**: Sie können die Anmeldung abbrechen, indem Sie **Abbrechen** wählen. Schließen Sie alle anderen Informationsfenster. Wählen Sie **Später anwenden**, wenn Sie aufgefordert werden, die Änderungen anzuwenden.*

Gehen Sie in Power BI Desktop zu **Datei > Optionen und Einstellungen > Optionen > Vorschaufunktionen**. Wählen Sie **Visuelle Berechnungen** und dann **OK**. Visuelle Berechnungen sind aktiviert, nachdem Power BI Desktop neu gestartet wurde.

## Erstellen eines Balkendiagramms

In dieser Aufgabe erstellen Sie ein Balkendiagramm, das den Umsatz, die Gesamtproduktkosten und den Gewinn nach Geschäftsjahr darstellt, mit Vergleichsmetriken als QuickInfos.

1. Wählen Sie im Bereich **Visualisierungen** den visuellen Typ des gruppierten Balkendiagramms aus.

   ![Abbildung 01](Linked_image_Files/05b-create-visual-calculations-in-power-bi-desktop_image01.png)

1. Ziehen Sie im Bereich **Daten** innerhalb der Tabelle **Datum** das Feld **Jahr** in den Bereich **Y-Achse**.

1. Ziehen Sie die Felder **Umsätze** und **Kosten** aus der Tabelle **Umsätze** in den Bereich **X-Achse**.

> Beachten Sie, dass beim Hinzufügen von Umsatz und Kosten zum Bildmaterial die Summe der einzelnen Felder automatisch berechnet wurde.

1. Sortieren Sie das resultierende Balkendiagramm nach **Jahr** aufsteigend, indem Sie mithilfe des Drei-Punkte-Menüs **Jahr** und anschließend **Aufsteigend sortieren** auswählen:

   ![Abbildung 02](Linked_image_Files/05b-create-visual-calculations-in-power-bi-desktop_image02.png)

> Sie haben nun ein Balkendiagramm, das die Summe der Umsätze und die Summe der Kosten nach Jahren chronologisch sortiert anzeigt.

### Hinzufügen von Berechnungen

1. Wenn das Balkendiagramm ausgewählt ist, wählen Sie **Neue visuelle Berechnung** im Menüband:

   ![Abbildung 03](Linked_image_Files/05b-create-visual-calculations-in-power-bi-desktop_image03.png)

1. Das Bearbeitungsfenster für visuelle Berechnungen wird geöffnet. Geben Sie in der Formelzeile oberhalb der visuellen Matrix den folgenden Ausdruck ein, und drücken Sie EINGABETASTE, um die Berechnung zu bestätigen:

   ```DAX
   Profit = [Sum of Sales] – [Sum of Cost]
   ```

1. Bestätigen Sie, dass Sie nun eine Gewinnspalte in der visuellen Matrix am unteren Rand des Bildschirms sehen:

   ![Abbildung 04](Linked_image_Files/05b-create-visual-calculations-in-power-bi-desktop_image04.png)

1. Erweitern Sie das Menü unter **Neue visuelle Berechnung** und wählen Sie **Im Vergleich zum vorherigen** aus den Vorlagenoptionen:

> **Im Vergleich zum vorherigen** vergleicht einen Wert mit einem vorhergehenden Wert, so dass wir den Gewinn im Vergleich zum vorherigen Wert für das Jahr sehen.

   ![Abbildung 05](Linked_image_Files/05b-create-visual-calculations-in-power-bi-desktop_image05.png)

1. Ersetzen Sie in der Formelzeile den Platzhalter `[Field]` zweimal durch `[Profit]` und bestätigen Sie die Berechnung.

1. Wählen Sie **Laufende Summe** aus dem Menü Vorlagen und ersetzen Sie den Platzhalter `[Field]` durch `[Profit]` und bestätigen Sie die Berechnung.

> **Laufende Summe** berechnet die Summe der Werte, indem der aktuelle Wert zu den vorangegangenen Werten addiert wird, so dass wir die Summe des aktuellen und des vorherigen Jahres sehen.

1. Wählen Sie **Gleitender Durchschnitt** aus dem Vorlagenmenü und ersetzen Sie den Platzhalter `[Field]` durch `[Profit]` und den Platzhalter `WindowSize` durch 2. Sie sollten jetzt Folgendes eingerichtet haben:

> **Der gleitende Durchschnitt** berechnet den Durchschnitt einer festgelegten Menge von Werten in einem bestimmten Fenster, indem er die Summe der Werte durch die Größe des Fensters teilt. Indem wir die Fenstergröße auf 2 festlegen, berechnen wir den Durchschnitt von zwei aufeinanderfolgenden Werten. In diesem Beispiel handelt es sich bei den Werten um Jahresgewinne. Der gleitende Durchschnitt für das GJ2019 ist also der Durchschnitt der Gewinne für das GJ2018 und das GJ2019.

   ![Abbildung 06](Linked_image_Files/05b-create-visual-calculations-in-power-bi-desktop_image06.png)

1. Wählen Sie unter dem Bereich **X-Achse** das Symbol für die Sichtbarkeit der folgenden Felder, um sie aus der Darstellung auszublenden:

   - Sum of Sales
   - Sum of Cost
   - „Profit“ (Gewinn)

   ![Abbildung 07](Linked_image_Files/05b-create-visual-calculations-in-power-bi-desktop_image07.png)

> Beachten Sie, dass die von Ihnen ausgeblendeten Felder und Berechnungen jetzt nicht mehr auf dem Bildschirm angezeigt werden.

1. Ziehen Sie im Bereich **Visualisierungen** **Laufende Summe** und **Gleitender Durchschnitt** in den Bereich **QuickInfos**.  

1. Bestätigen Sie, dass das Visuelle nun die Ziele erfüllt. Beenden Sie den Bearbeitungsbildschirm für visuelle Berechnungen für Ihren Bericht:

   ![Abbildung 08](Linked_image_Files/05b-create-visual-calculations-in-power-bi-desktop_image08.png)

> Sie haben nun ein Balkendiagramm mit den folgenden Werten: Summe der Verkäufe, Summe der Kosten, Gewinn und Gewinn *im Vergleich zum vorherigen* mit QuickInfos für Gewinn *Laufende Summe* und Gewinn *Gleitender Durchschnitt*.

## Erstellen eines Matrixvisuals

In dieser Aufgabe erstellen Sie eine visuelle Matrix, die den Umsatz pro Kategorie für jedes der folgenden Jahre mit dem ersten finanziellen Geschäftsjahr vergleicht.

1. Erstellen Sie in der Ansicht **Bericht** eine neue Berichtsseite.

1. Auf **Seite 2**, fügen Sie eine visuelle Matrix hinzu.

1. Fügen Sie den Visualbereichen die folgenden Felder hinzu:

     - Zeilen: **Produkt \| Kategorie**
     - Spalten: **Datum \| Jahr**
     - Werte: **Umsatz \| Umsatz**

 > *In den Labs wird eine verkürzte Notation verwendet, um auf ein Feld zu verweisen. Das sieht folgendermaßen aus: **Date \| Year**. In diesem Beispiel ist **Date** der Tabellenname und **Year** der Feldname.*

### Hinzufügen von Berechnungen

1. Wenn die Matrix ausgewählt ist, wählen Sie **Neue visuelle Berechnung** im Menüband.

1. Geben Sie im Bearbeitungsfenster für visuelle Berechnungen die folgende Berechnung ein und speichern Sie sie:

   ```DAX
    Versus first = [Sales] - FIRST([Sales])
   ```

> Beachten Sie, wie die Matrix den Unterschied zwischen den Verkaufsbeträgen der einzelnen Kategorien und denen der ersten Kategorie zeigt.

1. Wählen Sie das Feld **Im Vergleich zum ersten** im Bereich **Werte** und aktualisieren Sie Ihre Berechnung, indem Sie den Wert ROWS für den Parameter Axis zu FIRST hinzufügen:

   ```DAX
    Versus first = [Sales] - FIRST([Sales], ROWS)
   ```

> Beachten Sie, dass sich nichts ändert, da ROWS der Standardwert für den Parameter Axis ist.

1. Ersetzen Sie ZEILEN durch SPALTEN und beachten Sie, dass die Berechnung nun den Umsatzbetrag pro Kategorie mit dem ersten Geschäftsjahr vergleicht:

   ![Abbildung 11](Linked_image_Files/05b-create-visual-calculations-in-power-bi-desktop_image11.png)

> Beachten Sie, dass die Spalte **Im Vergleich zum ersten** für den **Gesamtumsatz** anstelle der Differenz zum ersten Geschäftsjahr Null ergibt. **Gesamtumsatz** befindet sich auf einer anderen hierarchischen Stufe als die Jahressummen und gilt daher als erste Spalte auf dieser Stufe.

1. Beenden Sie den Bearbeitungsbildschirm für visuelle Berechnungen für Ihren Bericht.

## Erstellen eines visuellen Liniendiagramms

In dieser Aufgabe werden Sie ein Liniendiagramm erstellen, das die laufende Summe der Verkäufe zeigt. Dieser Betrag wird zu Beginn eines jeden Geschäftsjahres neu festgesetzt.

1. Erstellen Sie in der Ansicht **Bericht** eine neue Berichtsseite.

1. Fügen Sie auf **Seite 3** ein visuelles Liniendiagramm hinzu.

1. Fügen Sie den Visualbereichen die folgenden Felder hinzu:

     - X-Achse: **Datum \| Jahr** und **Datum \| Quartal**
     - y-Achse: **Sales \| Sales**

### Hinzufügen der laufenden Summe

1. Erweitern Sie bei ausgewähltem Liniendiagramm das Menü unter **Neue visuelle Berechnung** und wählen Sie **Laufende Summe** aus den Vorlagenoptionen aus.

1. Ersetzen Sie den Platzhalter `[Field]` durch `[Sum of Sales]` und bestätigen Sie die Änderung. Die Ansicht sollte wie folgt aussehen:

   ![Abbildung 09](Linked_image_Files/05b-create-visual-calculations-in-power-bi-desktop_image09.png)

### Aktualisieren der laufenden Summe zum Neustart in jedem neuen Geschäftsjahr

1. Wählen Sie, während Sie sich noch im Bearbeitungsfenster für visuelle Berechnungen befinden, das Feld **Laufende Summe** unter **y-Achse** aus und aktualisieren Sie den Ausdruck für diese Berechnung, indem Sie den Rücksetzparameter HIGHESTPARENT hinzufügen und die Änderungen bestätigen:

   ```DAX
    Running sum = RUNNINGSUM([Sum of Sales], HIGHESTPARENT)
   ```

Überprüfen Sie, ob die laufende Summe tatsächlich für jedes neue Geschäftsjahr neu beginnt:

   ![Abbildung 10](Linked_image_Files/05b-create-visual-calculations-in-power-bi-desktop_image10.png)

## Lab abgeschlossen
