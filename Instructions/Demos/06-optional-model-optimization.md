---
demo:
  title: "(Optional) Optimieren eines Modells für bessere Ergebnisse in Power\_BI"
  module: Optimize model performance in Power BI
---

# (Optional) Optimieren der Modellleistung

## Überprüfen eines DirectQuery-Modellentwurfs

> **Hinweis**: In dieser Demo wird eine andere Power BI Desktop-Datei verwendet.

1. Öffnen Sie die Datei „D:\Allfiles\Demo\Resources\AW Sales Analysis.pbix“.

1. Wenn Sie zum Herstellen einer Verbindung mit der Datenquelle aufgefordert werden, klicken Sie auf Verbinden.

1. Weisen Sie darauf hin, dass das Datenmodell in der unteren rechten Ecke DirectQuery-Tabellen umfasst.

1. Speichern Sie die Power BI Desktop-Datei im Ordner „D:\Allfiles\Demo\MySolution“.

1. Stellen Sie in der Modellansicht den Modellentwurf vor, der zwei verknüpfte Tabellen enthält.

1. Interagieren Sie in der Berichtsansicht mit dem Bericht, indem Sie im Slicer Fiscal Year verschiedene Elemente auswählen.

1. Führen Sie einen Drillthrough für eine beliebige Monatsspalte aus, um Auftragsdetails anzuzeigen.

1. Kehren Sie zur Seite Sales Summary (Verkaufszusammenfassung) zurück.

## Überprüfen der Abfrageleistung

1. Zeigen Sie auf der Registerkarte Ansicht des Menübands den Bereich Leistungsanalyse an.

1. Aktualisieren Sie die visuellen Elemente, und erweitern Sie dann das visuelle Element „Datenschnitt“ und „Umsatz nach Monat“.

1. Weisen Sie darauf hin, dass sie den DirectQuery-Modus verwendet haben (Daten wurden von der Datenquelle angefordert).

## Konfigurieren von Speichertabellen vom Typ „Dual“

1. Wählen Sie in der Modellansicht die Tabelle Date aus, und legen Sie dann den Speichermodus auf Dual fest.

1. Wenn die Daten importiert wurden, wechseln Sie zur Berichtsansicht, und aktualisieren Sie dann im Bereich Leistungsanalyse die Visuals.

1. Weisen Sie darauf hin, dass die Tabelle Date nun vom Modellcache abgefragt wird.

## Erstellen von Aggregationen

1. Öffnen Sie das Power Query-Editor-Fenster, und duplizieren Sie im Bereich Abfragen die Abfrage Reseller Sales.

1. Benennen Sie die neue Abfrage in Reseller Sales Agg um.

1. Wenden Sie wie folgt eine Gruppe nach Transformation an:

    - Gruppieren Sie nach OrderDate.

    - Neue Spalte: Sales. Dies ist die Summe der Spalte SalesAmount.

1. Schließen Sie die Abfragen, und wenden Sie sie an.

1. Legen Sie in der Modellansicht den Speichermodus für die Tabelle Reseller Sales Agg auf Importieren fest.

1. Erstellen Sie eine Beziehung zwischen der Spalte Date der Tabelle Date und der Spalte OrderDate der Tabelle Reseller Sales Agg. Stellen Sie sicher, dass für die Spalte eine 1:n-Beziehung festgelegt wird und die Tabelle Date dabei für die 1 steht.

1. Verwalten Sie Aggregationen für die Tabelle Reseller Sales Agg:

    - OrderDate: Gruppieren Sie nach der Spalte OrderDate der Tabelle Reseller Sales.

    - Sales: Bilden Sie die Summe für die Spalte SalesAmount der Tabelle Reseller Sales.

1. Weisen Sie darauf hin, dass die Aggregationstabelle nun ausgeblendet ist.

1. Wechseln Sie zur Berichtsansicht, und aktualisieren Sie dann im Bereich Leistungsanalyse die Visuals.

1. Weisen Sie darauf hin, dass die Tabelle Sales by Month nun vom Modellcache abgefragt wird.

1. Führen Sie einen Drillthrough für einen beliebigen Monat aus, und weisen Sie darauf hin, dass die Details in der Tabelle per DirectQuery von der Datenquelle abgefragt werden.

1. Speichern Sie die Power BI Desktop-Datei.

1. Schließen Sie Power BI Desktop.

> **Hinweis**: Sie werden diese Power BI Desktop-Lösung nicht erneut verwenden.
