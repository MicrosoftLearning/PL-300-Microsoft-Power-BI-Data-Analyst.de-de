---
demo:
  course: 'PL-300, DP-605'
  title: 'Bereinigen, Transformieren und Laden von Daten in Power BI'
  module: 'Clean, transform, and load data in Power BI'
---

# Bereinigen, Transformieren und Laden von Daten in Power BI

## Anwenden von Abfragetransformationen

1. Wenden Sie zunächst Transformationen auf die Abfrage Product an.

1. Entfernen Sie die Spalten RetailPrice, Photo und Sales.

1. Ändern Sie den Datentyp der Spalte Channels in Ganze Zahl.

1. Benennen Sie die folgenden Spalten um:

    - ProductSKU in SKU

    - ProductName in Product

    - ProductCategory in Category

    - ItemGroup in Item Group

    - KitType in Kit Type

1. Wenden Sie im Anschluss Transformationen auf die Abfrage Sales an.

1. Entfernen Sie alle Spalten mit Ausnahme der folgenden:

    - OrderDate

    - ProductID

    - Quantity (Menge)

    - UnitPrice (Stückpreis)

1. Ändern Sie den Datentyp der Spalte UnitPrice in Feste Dezimalzahl.

1. Benennen Sie die Spalte UnitPrice in Unit Price um.

1. Wählen Sie die Spalten Quantity und Unit Price aus, und fügen Sie dann basierend auf ihrer Multiplikation eine neue Spalte hinzu.

1. Benennen Sie die neue Spalte in Sales um.

## Integrieren von Abfragen

1. Erstellen Sie mithilfe des Excel-Connectors eine neue Abfrage, und stellen Sie dabei eine Verbindung mit der Datei „D:\Allfiles\Demo\Data\ProductCost.xlsx“ her.

1. Entfernen Sie die Spalte Product.

1. Ändern Sie den Datentyp der Spalte ProductCost in Feste Dezimalzahl.

1. Wählen Sie die Abfrage Product aus, und führen Sie sie anschließend mit der Abfrage ProductCost zusammen. Verknüpfen Sie dabei die SKU-Spalten.

1. Legen Sie im Fenster „Datenschutzebenen“ die Datenschutzebene für D:\ auf „Organisation“ fest.

1. Erweitern Sie die Spalte ProductCost, um die Spalte ProductCost (aus der Abfrage ProductCost) hinzuzufügen.

1. Benennen Sie die neue Spalte in Cost um.

## Deaktivieren und Laden von Abfragen in das Datenmodell

1. Deaktivieren Sie im Bereich Abfragen die Abfrage ProductCost.

1. Klicken Sie auf der Registerkarte „Start“ des Menübands auf das Symbol „Close & Apply“ (Schließen und übernehmen).

1. Weisen Sie in Power BI Desktop auf die zwei Tabellen im Bereich „Daten“ hin.

1. Speichern Sie die Power BI Desktop-Datei.

1. Lassen Sie die Power BI Desktop-Datei für die nächste Demo geöffnet.
