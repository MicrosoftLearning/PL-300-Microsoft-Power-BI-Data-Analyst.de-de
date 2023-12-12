---
demo:
  title: "Erstellen von Measures in Power\_BI mithilfe von DAX"
  module: Create measures using DAX in Power BI
---
# Erstellen von Measures in Power BI mithilfe von DAX

> **Tipp**: Alle Berechnungen können aus der Datei „D:\PL300\Demo\Resources\Snippets-Demo-05.txt“ kopiert werden.

## Erstellen einer berechneten Tabelle

1. Erstellen Sie mithilfe des folgenden Ausdrucks eine berechnete Tabelle:

```dax
Date = CALENDARAUTO()
```

1. Wechseln Sie zur Datenansicht, und sehen sie sich die Tabelle an, die eine einzelne Datumsspalte umfasst.

Erstellen von berechneten Spalten

1. Fügen Sie der Tabelle Date eine berechnete Spalte hinzu:

```dax
Year = "CY" & YEAR('Date'[Date])
```

1. Fügen Sie der Tabelle Date eine weitere berechnete Spalte hinzu:

```dax
Month = FORMAT('Date'[Date], "YYYY-MM")
```

1. Erstellen Sie in der Modellansicht eine Beziehung, indem Sie die Spalte Date der Tabelle Date auf die Spalte OrderDate der Tabelle Sales ziehen.

1. Blenden Sie die Spalte OrderDate der Tabelle Sales aus.

1. Erstellen Sie in der Tabelle Date die Hierarchie Calendar mit den Ebenen Year und Month.

1. Markieren Sie in der Berichtsansicht die Tabelle Date über die Spalte Date als Datumstabelle.

1. Entfernen Sie im Matrixvisual die Hierarchie Products, und ersetzen Sie sie durch die Hierarchie Calendar.

1. Fügen Sie der Tabelle Sales eine berechnete Spalte hinzu:

```dax
Cost = 'Sales'[Quantity] * RELATED('Product'[Cost])
```

1. Legen Sie das Format der Spalte Cost auf zwei Dezimalstellen fest.

## Erstellen eines Quickmeasures

1. Fügen Sie der Tabelle Sales ein Quickmeasure hinzu. Ziehen Sie dabei die Spalte Cost von der Spalte Profit ab.

1. Benennen Sie das Measure in Profit um.

1. Erklären Sie, dass das Measure keine Daten im Modell speichert.

Erstellen eines regulären Measures.

1. Fügen Sie der Tabelle Sales ein Measure hinzu:

```dax
Profit Margin = DIVIDE([Profit], SUM('Sales'[Sales]))
```

1. Formatieren Sie die Spalte Profit Margin als Prozentsatz.

1. Fügen Sie der Tabelle Sales ein weiteres Measure hinzu:

```dax
Sales YTD = TOTALYTD(SUM('Sales'[Sales]), 'Date'[Date])
```

1. Legen Sie das Format der Spalte Sales YTD auf zwei Dezimalstellen fest.

## Überprüfen der Berechnungen mit dem Matrixvisual

1. Fügen Sie dem Matrixvisual die Felder Cost, Profit, Profit Margin und Sales YTD hinzu.

1. Speichern Sie die Power BI Desktop-Datei.

1. Lassen Sie die Power BI Desktop-Datei für eine spätere Demo geöffnet.
