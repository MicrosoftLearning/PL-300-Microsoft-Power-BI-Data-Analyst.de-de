---
lab:
  title: Verwenden von DAX-Zeitintelligenzfunktionen in Power BI
  module: Use DAX time intelligence functions in Power BI
---

# Verwenden von DAX-Zeitintelligenzfunktionen in Power BI

## Labszenario

In dieser Übung erstellen Sie Measures mit DAX-Ausdrücken, die Zeitintelligenz umfassen.

In diesem Lab lernen Sie Folgendes:

 - Verwenden von verschiedenen Zeitintelligenzfunktionen, um den Filterkontext zu bearbeiten, der sich auf Datumsangaben bezieht

**Dieses Lab sollte ungefähr 15 Minuten in Anspruch nehmen.**

## Erste Schritte

Um diese Übung abzuschließen, müssen Sie zuerst einen Webbrowser öffnen und die folgende URL eingeben, um die ZIP-Datei herunterzuladen:

`https://github.com/MicrosoftLearning/PL-300-Microsoft-Power-BI-Data-Analyst/raw/Main/Allfiles/Labs/06-use-dax-time-intelligence/06-time-intelligence.zip`

Extrahieren Sie die Datei in den Ordner **C:\Benutzer\Student\Downloads\06-time-intelligence**.

Öffnen Sie die Datei **06-Starter-Sales Analysis.pbix** .

> _**Hinweis**: Sie können die Anmeldung abbrechen, indem Sie **Abbrechen** auswählen. Schließen Sie alle anderen Informationsfenster. Wählen Sie **Später übernehmen** aus, wenn Sie aufgefordert werden, die Änderungen anzuwenden._

## Erstellen eines YTD-Measures

In dieser Aufgabe erstellen Sie mithilfe von Zeitintelligenzfunktionen ein YTD-Measure (seit Jahresbeginn).

1. Beachten Sie in der Berichtsansicht von Power BI Desktop auf **Seite 2** das Matrixvisual, in dem verschiedene Measures mit Jahren und Monaten in den Zeilen gruppiert dargestellt sind.

2. Fügen Sie der Tabelle `Sales` ein Measure hinzu, das auf dem folgenden Ausdruck basiert und ohne Dezimalstellen formatiert ist:

    ```dax
    Sales YTD =
    TOTALYTD(
        SUM(Sales[Sales]),
        'Date'[Date],
        "6-30"
    )
    ```

    > _Die Funktion `TOTALYTD` wertet einen Ausdruck aus, in diesem Fall die Summe der Spalte `Sales` für eine bestimmte Datumsspalte. Die Datumsspalte muss zu einer Datumstabelle gehören, die als solche gekennzeichnet ist._
    >
    > _Die Funktion kann auch ein drittes optionales Argument verwenden, das das letzte Datum eines Jahres darstellt. Das Fehlen dieses Datums bedeutet, dass der 31. Dezember das letzte Datum des Jahres ist. Bei Adventure Works ist der Juni der letzte Monat des Geschäftsjahres, weshalb „6–30“ verwendet wird._

3. Fügen Sie das Feld `Sales` und das Measure `Sales YTD` dem Matrixvisual hinzu.

4. Beachten Sie die Akkumulation der Umsatzwerte innerhalb des Jahres.

    ![Abbildung 1](Linked_image_Files/06-use-dax-time-intelligence-functions_image21.png)

> _Die Funktion `TOTALYTD` nimmt Filteränderungen vor, insbesondere Zeitfilteränderungen. Um beispielsweise den YTD-Umsatz für September 2017 (den dritten Monat des Geschäftsjahres) zu berechnen, werden alle Filter für die Tabelle `Date` entfernt und durch einen neuen Datumsfilter ersetzt, der mit dem Jahresanfang (1. Juli 2017) beginnt und sich bis zum letzten Datum des kontextbezogenen Datumsbereichs (30. September 2017) erstreckt._
>
> _In DAX sind viele [Zeitintelligenzfunktionen](/dax/time-intelligence-functions-dax/?azure-portal=true) verfügbar, um gängige Zeitfilteränderungen zu unterstützen._

## Erstellen eines YoY-Measures des Umsatzwachstums

In dieser Aufgabe erstellen Sie ein YoY-Wachstumsmeasure mithilfe einer Variablen.

> Mit Variablen können Sie die Formel vereinfachen, und sie sind effizienter, wenn die Logik mehrmals innerhalb einer Formel verwendet wird. Variablen werden mit einem eindeutigen Namen deklariert. Der Measureausdruck muss nach dem Schlüsselwort `RETURN` ausgegeben werden. Im Gegensatz zu einigen anderen Programmiersprachenvariablen können DAX-Variablen nur innerhalb der einzelnen Formel verwendet werden.

1. Fügen Sie der Tabelle `Sales` ein weiteres Measure basierend auf dem folgenden Ausdruck hinzu:

    ```dax
    Sales YoY Growth =
    VAR SalesPriorYear =
        CALCULATE(
            SUM(Sales[Sales]),
            PARALLELPERIOD(
                'Date'[Date],
                -12,
                MONTH
            )
        )
    RETURN
        SalesPriorYear
    ```

    > _Der Variablen `SalesPriorYear` wird ein Ausdruck zugewiesen, der die Summe der Spalte `Sales` in einem geänderten Kontext berechnet. In diesem Kontext wird die Funktion `PARALLELPERIOD`verwendet, um 12 Monate von jedem Datum im Filterkontext zurück zu verschieben._

1. Fügen Sie das Measure `Sales YoY Growth` dem Matrixvisual hinzu.

1. Beachten Sie, dass das neue Measure für die ersten 12 Monate `BLANK` zurückgibt (vor dem Geschäftsjahr 2017 wurden keine Umsätze verzeichnet).

1. Beachten Sie, dass der Wert des Measures `Sales YoY Growth` für _Juli 2018_ der Verkaufswert für _Juli 2017_ ist.

    ![Abbildung 2](Linked_image_Files/06-use-dax-time-intelligence-functions_image22.png)

    > _Nachdem nun der „schwierige Teil“ der Formel getestet wurde, können Sie das Measure mit der endgültigen Formel überschreiben, mit der das Wachstumsergebnis berechnet wird._

1. Um das Measure zu vervollständigen, überschreiben Sie das Measure `Sales YoY Growth` mit dieser Formel und formatieren es als Prozentsatz mit zwei Dezimalstellen:

    ```dax
    Sales YoY Growth =
    VAR SalesPriorYear =
        CALCULATE(
            SUM(Sales[Sales]),
            PARALLELPERIOD(
                'Date'[Date],
                -12,
                MONTH
            )
        )
    RETURN
        DIVIDE(
            (SUM(Sales[Sales]) - SalesPriorYear),
            SalesPriorYear
        )
    ```

1. Beachten Sie, dass in der Formel in der `RETURN`-Klausel zweimal auf die Variable verwiesen wird.

1. Vergewissern Sie sich, dass für _Juli 2018_ das YoY-Wachstum 392,83 % beträgt.

    ![Abbildung 3](Linked_image_Files/06-use-dax-time-intelligence-functions_image23.png)

    > _Das YoY-Wachstumsmeasure identifiziert einen Umsatzanstieg von nahezu 400 % (oder 4x) gegenüber dem gleichen Zeitraum des Vorjahres._

1. Legen Sie in der Ansicht „Modell“ die beiden neuen Measures in einen Anzeigeordner mit dem Namen _Zeitintelligenz_ ab.

    ![Bild 4](Linked_image_Files/06-use-dax-time-intelligence-functions_image24.png)

1. Speichern Sie die Power BI Desktop-Datei.

## Lab abgeschlossen
