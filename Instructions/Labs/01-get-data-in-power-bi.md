---
lab:
  title: Abrufen von Daten in Power BI
  module: Get data in Power BI
---

# Abrufen von Daten in Power BI

## Labszenario

In diesem Lab erfahren Sie mehr über die Anwendung Power BI Desktop, wie Sie eine Verbindung mit Daten herstellen und wie Sie Datenvorschautechniken verwenden, um die Eigenschaften und die Qualität der Quelldaten zu verstehen.

In diesem Lab lernen Sie Folgendes:

- Öffnen Sie Power BI Desktop.
- Verbindungsherstellung mit verschiedenen Datenquellen
- Vorschau der Quelldaten mit Power Query
- Verwenden von Datenprofilerstellungsfeatures in Power Query

**Dieses Lab sollte ungefähr 30 Minuten in Anspruch nehmen.**

## Erste Schritte mit Power BI Desktop

Um diese Übung abzuschließen, öffnen Sie zuerst einen Webbrowser, und geben Sie die folgende URL ein, um den ZIP-Ordner herunterzuladen:

`https://github.com/MicrosoftLearning/PL-300-Microsoft-Power-BI-Data-Analyst/raw/Main/Allfiles/Labs/01-get-data-in-power-bi/01-get-data.zip`

Extrahieren Sie den Ordner in den Ordner **C:\Benutzer\Student\Downloads\01-get-data**.

Öffnen Sie die Datei **01-Starter-Sales Analysis.pbix**.

- Die Starterdatei wurde speziell für die Durchführung des Labs konfiguriert. Die folgenden Einstellungen auf Berichtsebene wurden in der Startdatei deaktiviert:

  - Datenladevorgang > Beim ersten Laden Beziehungen aus Datenquellen importieren
  - Datenladevorgang > Neue Beziehungen nach dem Laden der Daten automatisch erkennen

## Abrufen von Daten aus SQL Server

In dieser Aufgabe erfahren Sie, wie Sie eine Verbindung mit einer SQL Server-Datenbank herstellen und Tabellen importieren, mit denen Abfragen in Power Query erstellt werden.

1. Wählen Sie auf der Registerkarte **Start** des Menübands in der Gruppe **Daten** die Option **SQL Server** aus.

     ![Symbol „SQL Server Daten abrufen“](Linked_image_Files/01-get-data-in-power-bi_image11.png)

1. Geben Sie im Fenster **SQL Server-Datenbank** im Feld **Server** den Text **localhost** ein. Lassen Sie **Datenbank** leer, und wählen Sie dann **OK** aus.

    > ***Hinweis**: Im Rahmen dieses Labs stellen Sie mit **localhost** eine Verbindung mit der SQL Server-Datenbank her. Obwohl dies für das Labor in Ordnung ist, wird es nicht als bewährte Methode für reale Lösungen angesehen.*

1. Wenn Sie zur Eingabe von Anmeldeinformationen aufgefordert werden, wählen Sie **Windows > Aktuelle Anmeldeinformationen verwenden** und dann **Verbinden** aus.

1. Wählen Sie **OK** aus, wenn Sie eine Warnung erhalten, dass keine verschlüsselte Verbindung hergestellt werden kann.

1. Erweitern Sie im Bereich **Navigator** die Datenbank **AdventureWorksDW2020**.

    > ***Hinweis**: Die Datenbank **AdventureWorksDW2020** basiert auf der Beispieldatenbank **AdventureWorksDW2017**. Sie wurde für die Zwecke der Lernziele der Kurslabs angepasst.*

1. Wählen Sie die Tabelle **DimEmployee** aus, und betrachten Sie die Vorschau der Tabellendaten.

     ![AdventureWorksDW2020-Datenbank mit DimEmployee-Angabe](Linked_image_Files/01-get-data-in-power-bi_image18.png)

    > ***Hinweis**: Diesen Vorschaudaten können Sie die Spalten und eine Auswahl von Zeilen entnehmen.*

1. Wählen Sie die folgenden Tabellen aus, indem Sie neben ihren Namen **die Kontrollkästchen aktivieren**.

    - DimEmployee
    - DimEmployeeSalesTerritory
    - DimProduct
    - DimReseller
    - DimSalesTerritory
    - FactResellerSales

1. Führen Sie diese Aufgabe aus, indem Sie **Daten transformieren** auswählen, wodurch der Power Query-Editor geöffnet wird – lassen Sie ihn für die nächste Aufgabe geöffnet.

Sie haben nun eine Verbindung mit sechs Tabellen aus einer SQL Server-Datenbank hergestellt.

## Vorschau der Daten in Power Query-Editor

Diese Aufgabe führt den Power Query-Editor ein und ermöglicht es Ihnen, die Daten zu überprüfen und ein Profil zu erstellen. Auf diese Weise können Sie bestimmen, wie die Daten später bereinigt und transformiert werden. Außerdem überprüfen Sie sowohl Dimensionstabellen mit dem Präfix „Dim“ als auch Faktentabellen mit dem Präfix „Fakt“.

1. Sehen Sie sich im Fenster **Power Query-Editor** links den Bereich **Abfragen** an. Der Bereich **Abfragen** enthält je eine Abfrage für jede ausgewählte Tabelle.

     ![Liste der geladenen Abfragen](Linked_image_Files/01-get-data-in-power-bi_image20.png)

1. Wählen Sie die Abfrage **DimEmployee** aus.

    > *Die Tabelle **DimEmployee** in der SQL Server-Datenbank speichert eine Zeile für jeden Mitarbeiter. Eine Teilmenge der Zeilen aus dieser Tabelle stellt die Vertriebsmitarbeiter dar, die für das von Ihnen zu entwickelnde Modell relevant sind.*

1. Sehen Sie sich unten links in der Statusleiste die Tabellenstatistik an. Die Tabelle besteht aus 33 Spalten und 296 Zeilen.

     ![Anzahl von 33 Spalten, 296 Zeilen](Linked_image_Files/01-get-data-in-power-bi_image22.png)

1. Scrollen Sie im Bereich „Datenvorschau“ horizontal, um alle Spalten zu überprüfen. Beachten Sie, dass die letzten fünf Spalten Verknüpfungen mit **Tabellen** oder **Werten** enthalten.

    > *Diese fünf Spalten stellen Beziehungen zu anderen Tabellen in der Datenbank dar. Sie können zum Verknüpfen von Tabellen verwendet werden. Sie verknüpfen diese Tabellen später im Lab **Laden von transformierten Daten in Power BI Desktop**.*

1. Aktivieren Sie zum Überprüfen der Spaltenqualität auf der Registerkarte **Ansicht** des Menübands in der Gruppe **Datenvorschau** das Kontrollkästchen **Spaltenqualität**. Über die Funktion „Spaltenqualität“ können Sie den Prozentsatz von gültigen, fehlerhaften und leeren Spaltenwerten ganz einfach ermitteln.

     ![Auswahl der Spaltenqualität im Menüband](Linked_image_Files/01-get-data-in-power-bi_image23.png)

1. Beachten Sie, dass die Spalte **Position** 94 % leere Zeilen (NULL) enthält.

     ![Spaltenqualität mit 94 % leeren Zeilen](Linked_image_Files/01-get-data-in-power-bi_image24.png)

1. Aktivieren Sie zum Überprüfen der Spaltenverteilung auf der Registerkarte **Ansicht** des Menübands in der Gruppe **Datenvorschau** die Option **Spaltenverteilung**.

1. Sehen Sie sich wieder die Spalte **Position** an. Wie Sie sehen, enthält diese vier verschiedene Werte und einen eindeutigen Wert.

1. Überprüfen Sie die Spaltenverteilung für die Spalte **EmployeeKey**. Diese enthält 296 unterschiedliche („distinct“) Werte und 296 eindeutige („unique“) Werte.

     ![Spaltenverteilung mit 296 unterschiedlichen und 296 eindeutigen Werten](Linked_image_Files/01-get-data-in-power-bi_image26.png)

    > ***Hinweis**: Wenn die Anzahl von verschiedenen und eindeutigen Werten übereinstimmt, enthält die Spalte nur eindeutige Werte. Beim Modellieren ist wichtig, dass einige Modelltabellen eindeutige Spalten enthalten. Sie können diese eindeutigen Spalten zum Erstellen von 1:n-Beziehungen verwenden. Dies werden Sie im Lab **Modellieren von Daten in Power BI Desktop** ausführen.*

1. Wählen Sie im Bereich **Abfragen** die Abfrage für **DimProduct** aus.

    > *Die Tabelle **DimProduct** enthält je eine Zeile für jedes vom Unternehmen verkaufte Produkt.*

1. Wählen Sie im Bereich **Abfragen** die Abfrage für **DimReseller** aus.

    > *Die Tabelle **DimReseller** enthält eine Zeile pro Wiederverkäufer. Wiederverkäufer verkaufen oder verteilen die Adventure Works-Produkte oder fügen ihnen einen Mehrwert hinzu.*

1. Aktivieren Sie auf der Registerkarte **Ansicht** des Menübands in der Gruppe **Datenvorschau** die Option **Spaltenprofil**, um Spaltenwerte anzuzeigen.

1. Wählen Sie die Spaltenüberschrift **BusinessType** aus, und beachten Sie den neuen Bereich unter dem Datenvorschaubereich. Überprüfen Sie die Spaltenstatistiken und die Werteverteilung im Bereich „Datenvorschau“.

    > *Wie Sie sehen, liegt ein Datenqualitätsproblem vor: Es gibt zwei Bezeichnungen für „Warehouse“ (**Warehouse** und das falsch geschriebene **Ware House**).*

     ![Wertverteilung für die Spalte „BusinessType“](Linked_image_Files/01-get-data-in-power-bi_image31.png)

1. Zeigen Sie mit dem Mauszeiger auf den Balken für **Ware House**. Wie Sie sehen, gibt es fünf Zeilen mit diesem Wert.

1. Wählen Sie im Bereich **Abfragen** die Abfrage für **DimSalesTerritory** aus.  

    > *Die Tabelle **DimSalesTerritory** enthält eine Zeile pro Vertriebsregion, einschließlich **Corporate HQ** (Hauptsitz). Regionen werden einem Land und Länder werden Gruppen zugewiesen. Im Lab **Modelldaten in Power BI Desktop** erstellen Sie eine Hierarchie zur Unterstützung der Analyse auf Regions-, Länder- oder Gruppenebene.*

1. Wählen Sie im Bereich **Abfragen** die Abfrage für **FactResellerSales** aus.

    > *Die Tabelle **FactResellerSales** enthält je eine Zeile für jede Auftragsposition. Ein Verkaufsauftrag enthält eine oder mehrere solcher Positionen.*

1. Überprüfen Sie die Spaltenqualität für die Spalte **TotalProductCost**. Wie Sie sehen, sind 8 % der Zeilen leer.

    > *Fehlende Werte in der Spalte **TotalProductCost** stellen ein Datenqualitätsproblem dar.*

## Abrufen von Daten aus einer CSV-Datei

In dieser Aufgabe erstellen Sie eine neue Abfrage basierend auf CSV-Dateien.

1. Wählen Sie zum Hinzufügen einer neuen Abfrage im Fenster **Power Query-Editor** auf der Registerkarte **Start** des Menübands in der Gruppe **Neue Abfrage** den Pfeil nach unten bei **Neue Quelle** und dann **Text/CSV** aus.

1. Navigieren Sie zu dem zuvor extrahierten Ordner **Downloads > 01-get-data**, und wählen Sie die Datei **ResellerSalesTargets.csv** aus. Klicken Sie auf **Öffnen**.

1. Sehen Sie sich die Vorschaudaten im Fenster **ResellerSalesTargets.csv** an. Klicken Sie auf **OK**.

1. Beachten Sie, dass im Bereich **Abfragen** die Abfrage für **ResellerSalesTargets** hinzugefügt wurde.

    > *Die CSV-Datei **ResellerSalesTargets** enthält eine Zeile pro Vertriebsmitarbeiter und Jahr. In jeder Zeile werden 12 monatliche Umsatzziele (ausgedrückt in Tausend) aufgezeichnet. Das Geschäftsjahr für die Firma Adventure Works beginnt am 1. Juli.*

1. Beachten Sie auch, dass keine der Spalten leere Werte enthält.  Wenn ein monatliches Umsatzziel fehlt, enthält die Spalte stattdessen einen Bindestrich.

1. Überprüfen Sie die Symbole in den einzelnen Spaltenüberschriften links neben dem Spaltennamen. Die Symbole stehen für den Datentyp der jeweiligen Spalte. **123** steht für ganze Zahlen und **ABC** für Text.

     ![Spaltendatentyp](Linked_image_Files/01-get-data-in-power-bi_image38.png)

1. Wiederholen Sie die Schritte zum Erstellen einer Abfrage auf Grundlage der Datei **ColorFormats.csv**.

    > *Die CSV-Datei **ColorFormats** enthält eine Zeile pro Produktfarbe. Jede Zeile zeichnet die HEX-Codes auf, um Hintergrund- und Schriftfarben zu formatieren.*

Sie sollten jetzt über zwei neue Abfragen verfügen: **ResellerSalesTargets** und **ColorFormats**.

 ![Abfrageliste](Linked_image_Files/01-get-data-in-power-bi_image43.png)

## Lab abgeschlossen

Sie können Ihren Power BI-Bericht speichern, aber für dieses Lab ist dies nicht erforderlich. In der nächsten Übung arbeiten Sie mit einer vorgefertigten Startdatei.

1. Navigieren Sie zum Menü **Datei** in der oberen linken Ecke, und wählen Sie **Speichern unter** aus. 
1. Wählen Sie **Dieses Gerät durchsuchen** aus.
1. Wählen Sie den Ordner aus, in dem Sie die Datei speichern möchten, und geben Sie ihm einen aussagekräftigen Namen. 
1. Wählen Sie die Schaltfläche **Speichern** aus, um den Bericht als PBIX-Datei zu speichern. 
1. Wenn ein Dialogfeld angezeigt wird, in dem Sie aufgefordert werden, ausstehende Abfrageänderungen anzuwenden, wählen Sie **Übernehmen** aus.
1. Schließen Sie Power BI Desktop.