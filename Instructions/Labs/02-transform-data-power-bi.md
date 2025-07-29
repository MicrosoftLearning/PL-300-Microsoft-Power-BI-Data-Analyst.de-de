---
lab:
  title: 'Bereinigen, Transformieren und Laden von Daten in Power BI'
  module: 'Clean, transform, and load data in Power BI'
---

# Bereinigen, Transformieren und Laden von Daten in Power BI

## Labszenario

In diesem Lab verwenden Sie Datenbereinigungs- und Transformationstechniken, um mit der Strukturierung Ihres Datenmodells zu beginnen. Anschließend werden Sie jede einzelne Abfrage als Tabelle in das semantische Modell laden.

In diesem Lab lernen Sie Folgendes:

- Anwenden verschiedener Datentransformationen
- Laden Sie Abfragen in das semantische Modell.

**Dieses Lab sollte ungefähr 45 Minuten in Anspruch nehmen.**

## Erste Schritte

Um diese Übung abzuschließen, öffnen Sie zuerst einen Webbrowser, und geben Sie die folgende URL ein, um den ZIP-Ordner herunterzuladen:

`https://github.com/MicrosoftLearning/PL-300-Microsoft-Power-BI-Data-Analyst/raw/Main/Allfiles/Labs/02-transform-data-power-bi/02-transform-data.zip`

Extrahieren Sie den Ordner in den Ordner **C:\Benutzer\Student\Downloads\02-transform-data**.

Öffnen Sie die Datei **02-Starter-Sales Analysis.pbix** .

> ***Hinweis**: Sie können die Anmeldung abbrechen, indem Sie **Abbrechen** wählen. Schließen Sie alle anderen Informationsfenster. Wählen Sie **Später anwenden**, wenn Sie aufgefordert werden, die Änderungen anzuwenden.*

## Konfigurieren der „Salesperson“-Abfrage

In dieser Aufgabe verwenden Sie den Power Query-Editor zum Konfigurieren der **Salesperson**-Abfrage.

> ***Wichtig:** Wenn Sie aufgefordert werden, Spalten umzubenennen, ist es wichtig, dass Sie genauso wie beschrieben vorgehen.*

1. Klicken Sie auf der Registerkarte **Start** des Menübands in der Gruppe **Abfragen** auf das Symbol **Daten transformieren**, um das Fenster **Power Query-Editor** zu öffnen.

    ![„Daten transformieren“ im Menüband „Start“](Linked_image_Files/02-transform-data-power-bi_image10.png)

1. Wählen Sie im Fenster **Power Query-Editor** im Bereich **Abfragen** die Abfrage **DimEmployee** aus.

    ![Abbildung 1](Linked_image_Files/02-transform-data-power-bi_image11.png)

    > **Hinweis:** Wenn Sie eine Warnmeldung erhalten, in der Sie aufgefordert werden, anzugeben, wie die Verbindung hergestellt werden soll, wählen Sie „**Anmeldeinformationen bearbeiten**“ aus, stellen Sie die Verbindung mit den aktuellen Anmeldeinformationen her und wählen Sie „**OK**“, um eine unverschlüsselte Verbindung zu verwenden.
 
1. Ersetzen Sie zum Umbenennen der Abfrage im Bereich **Abfrageeinstellungen** (rechts) den Text im Feld **Name** durch **Salesperson**, und drücken Sie die **EINGABETASTE**. Überprüfen Sie dann, ob der Name im Bereich**Abfragen** aktualisiert wurde.

    > *Der Name der Abfrage bestimmt den Namen der Modelltabelle. Es wird empfohlen, präzise und benutzerfreundliche Namen zu definieren.*

1. Klicken Sie auf der Registerkarte **Start** des Menübands in der Gruppe **Spalten verwalten** auf den Abwärtspfeil **Spalten auswählen**, und klicken Sie auf **Zur Spalte wechseln**.

    > *„Zur Spalte wechseln“ ist bei vielen Spalten ein nützliches Feature. Andernfalls können Sie horizontal nach Spalten scrollen.*

    ![Spalten verwalten > Spalten auswählen > Zur Spalte wechseln](Linked_image_Files/02-transform-data-power-bi_image13.png)

1. Klicken Sie im Fenster **Zur Spalte wechseln** auf die Sortierschaltfläche **AZ**, um die Liste nach Spaltennamen zu sortieren, und klicken Sie dann auf **Name** und auf **SalesPersonFlag**. Klicken Sie auf **OK**.

    ![Wechseln zu den Optionen für die Spaltensortierung](Linked_image_Files/02-transform-data-power-bi_image14.png)

1. Suchen Sie die Spalte **SalesPersonFlag** , filtern Sie dann die Spalte, um nur Verkaufspersonal (d. h. **TRUE**) auszuwählen, und klicken Sie auf **OK**.

1. Beachten Sie im Bereich **Abfrageeinstellungen** in der Liste **Angewendete Schritte**, dass der Schritt **Gefilterte Zeilen** hinzugefügt wurde.

    > *Jede Transformation, die Sie erstellen, führt zu einer weiteren Schrittlogik. Schritte können auch bearbeitet oder gelöscht werden. Es ist ebenso möglich, einen Schritt auszuwählen und eine Vorschau der Abfrageergebnisse in dieser Phase der Abfragetransformation anzuzeigen.*

    ![Angewendete Schritte](Linked_image_Files/02-transform-data-power-bi_image17.png)

1. Klicken Sie auf der Registerkarte **Start** des Menübands in der Gruppe **Spalten verwalten** auf das Symbol **Spalten auswählen**, um Spalten zu entfernen.

1. Deaktivieren Sie im Fenster **Spalten auswählen** das Element **(Alle Spalten auswählen)**, um alle Spalten zu deaktivieren.

1. Damit Spalten berücksichtigt werden, müssen Sie die Kontrollkästchen für folgenden sechs Spalten aktivieren:

    - EmployeeKey
    - EmployeeNationalIDAlternateKey
    - FirstName
    - LastName
    - Title
    - EmailAddress

1. Beachten Sie in der Liste **Angewendete Schritte**, dass ein weiterer Abfrageschritt hinzugefügt wurde.

    ![Schritt „Andere entfernte Spalten“](Linked_image_Files/02-transform-data-power-bi_image21.png)

1. Klicken Sie zuerst auf die Spaltenüberschrift **FirstName**, um eine einzelne Namensspalte zu erstellen. Klicken Sie auf die Spalte **LastName**, während Sie **STRG** gedrückt halten.

    ![Mehrfachauswahl zweier Spalten zum Erstellen einer einzelnen Spalte](Linked_image_Files/02-transform-data-power-bi_image22.png)

1. Klicken Sie mit der rechten Maustaste auf eine der markierten Spaltenüberschriften, und wählen Sie dann im Kontextmenü **Spalten zusammenführen** aus.

    > *Viele gängige Transformationen können angewandt werden, indem Sie mit der rechten Maustaste auf die Spaltenüberschrift klicken und die Transformation im Kontextmenü auswählen. Beachten Sie jedoch, dass im Menüband mehr Transformationen verfügbar sind.*

1. Wählen Sie im Fenster **Spalten zusammenführen** in der Dropdownliste **Trennlinie** die Option **Leertaste** aus.

1. Ersetzen Sie im Feld **Neuer Spaltenname** den Text durch **Salesperson**.

1. Um die Spalte **EmployeeNationalIDAlternateKey** umzubenennen, doppelklicken Sie auf die Spaltenüberschrift **EmployeeNationalIDAlternateKey**, ersetzen Sie den Text durch **EmployeeID**, und drücken Sie dann die **Eingabetaste**.

1. Führen Sie die vorherigen Schritte noch einmal aus, um die Spalte **EmailAddress** in **UPN** umzubenennen.

    > *Das Akronym „UPN“ steht für „User Principal Name“, zu Deutsch: „Benutzerprinzipalname“.*

**Überprüfen Sie links unten in der Statusleiste, ob die Abfrage 5 Spalten und 18 Zeilen enthält.**

## **Konfigurieren der „SalespersonRegion“-Abfrage**

In dieser Aufgabe konfigurieren Sie die **SalespersonRegion**-Abfrage.

1. Wählen Sie im Bereich **Abfragen** die Abfrage **DimEmployeeSalesTerritory** aus.

1. Benennen Sie die Abfrage im Bereich **Abfrageeinstellungen** in **SalespersonRegion** um.

1. Wählen Sie zuerst die Spaltenüberschrift **DimEmployee** aus, um die letzten zwei Spalten zu entfernen.

1. Halten Sie **STRG** gedrückt, und klicken Sie dann auf die Spaltenüberschrift **DimSalesTerritory**.

1. Klicken Sie mit der rechten Maustaste auf eine der markierten Spaltenüberschriften, und wählen Sie dann im Kontextmenü **Spalten entfernen** aus.

**Überprüfen Sie in der Statusleiste, ob die Abfrage 2 Spalten und 39 Zeilen enthält.**

## Konfigurieren der Product-Abfrage

In dieser Aufgabe konfigurieren Sie die Abfrage **Product**.

> ***Wichtig**: Da bereits ausführliche Anweisungen bereitgestellt wurden, enthalten die folgenden Schritte zum Lab kurzgefasste Anweisungen. Wenn Sie die ausführlichen Anweisungen benötigen, können Sie zu den Schritten der vorherigen Aufgaben zurückkehren.*

1. Wählen Sie die **DimProduct**-Abfrage aus, und benennen Sie die Abfrage in **Product** um.

1. Suchen Sie die Spalte **FinishedGoodsFlag**, und filtern Sie dann die Spalte, um Produkte abzurufen, bei denen es sich um fertiggestellte Waren handelt (d. h. sie weisen den Wert TRUE auf).

1. Entfernen Sie alle Spalten, **außer** den folgenden:

    - ProductKey
    - EnglishProductName
    - StandardCost
    - Color
    - DimProductSubcategory

1. Beachten Sie, dass die Spalte **DimProductSubcategory** eine verknüpfte Tabelle ist (sie enthält **Value**-Verknüpfungen).

1. Klicken Sie in der Spaltenüberschrift **DimProductSubcategory** rechts neben dem Spaltennamen auf die Schaltfläche „Erweitern“.

    ![Symbol zum Erweitern von Spalten](Linked_image_Files/02-transform-data-power-bi_image31.png)

1. Sehen Sie sich die vollständige Liste der Spalten an, und wählen Sie dann das Feld **Alle Spalten auswählen** aus, um die Auswahl aller Spalten aufzuheben.

1. Wählen Sie **EnglishProductSubcategoryName** und **DimProductCategory** aus, und deaktivieren Sie das Kontrollkästchen **Originalspaltennamen als Präfix verwenden**, bevor Sie **OK** auswählen.

    ![Spalte erweitern](Linked_image_Files/02-transform-data-power-bi_image23.png)

    > *Indem Sie diese zwei Spalten auswählen, wird eine Transformation für eine Verknüpfung mit der Tabelle **DimProductSubcategory** durchgeführt. Daraufhin werden diese Spalten eingefügt. Bei der Spalte **DimProductCategory** handelt es sich tatsächlich um eine andere verknüpfte Tabelle in der Datenquelle.*

    > *Abfragespaltennamen müssen immer eindeutig sein. Wenn das Kontrollkästchen aktiviert ist, wird der erweiterte Spaltenname allen Spalten als Präfix vorangestellt (in diesem Fall **DimProductSubcategory**). Da bekannt ist, dass die ausgewählten Spalten keinen Konflikt mit den Spalten in der Abfrage **Product** auslösen, ist diese Option deaktiviert.*

1. Beachten Sie, dass die Transformation dazu geführt hat, dass zwei Spalten hinzugefügt wurden und dass die Spalte **DimProductSubcategory** entfernt wurde.

1. Erweitern Sie die Spalte **DimProductCategory**, und führen Sie dann nur die Spalte **EnglishProductCategoryName** ein.

1. Benennen Sie die folgenden vier Spalten um:

    - **EnglishProductName** in **Product**
    - **StandardCost** in **Standard Cost** (fügen Sie ein Leerzeichen ein)
    - **EnglishProductSubcategoryName** in **Subcategory**
    - **EnglishProductCategoryName** in **Category**

**Überprüfen Sie in der Statusleiste, ob die Abfrage 6 Spalten und 397 Zeilen enthält.**

## Konfigurieren der Reseller-Abfrage

In dieser Aufgabe konfigurieren Sie die Abfrage **Reseller**.

1. Wählen Sie die Abfrage **DimReseller** aus, und benennen Sie sie in **Reseller** um.

1. Entfernen Sie alle Spalten, **außer** den folgenden:

    - ResellerKey
    - BusinessType
    - ResellerName
    - DimGeography

1. Erweitern Sie die Spalte **DimGeography** so, dass **nur** die folgenden drei Spalten enthalten sind:

    - City
    - StateProvinceName
    - EnglishCountryRegionName

1. Klicken Sie in der Spaltenüberschrift **BusinessType** auf den Pfeil nach unten, und überprüfen Sie dann die einzelnen Spaltenwerte. Beachten Sie die unterschiedliche Schreibweise von **Warehouse** und **Ware House**.

1. Klicken Sie mit der rechten Maustaste auf die Spaltenüberschrift **Business Type**, und wählen Sie dann **Werte ersetzen** aus.

1. Konfigurieren Sie im Fenster **Werte ersetzen** die folgenden Werte:

    - Geben Sie in das Feld **Zu suchender Wert** **Ware House** ein.
    - Geben Sie in das Feld **Ersetzen durch** **Warehouse** ein.

    ![Dialogfeld „Werte ersetzen“](Linked_image_Files/02-transform-data-power-bi_image40.png)

1. Benennen Sie die folgenden vier Spalten um:

    - **BusinessType** in **Business Type** (fügen Sie ein Leerzeichen ein)
    - **ResellerName** in **Reseller**
    - **StateProvinceName** in **State-Province**
    - **EnglishCountryRegionName** in **Country-Region**

**Überprüfen Sie in der Statusleiste, ob die Abfrage 6 Spalten und 701 Zeilen enthält.**

## Konfigurieren der Region-Abfrage

In dieser Aufgabe konfigurieren Sie die Abfrage **Region**.

1. Wählen Sie die Abfrage **DimSalesTerritory** aus, und benennen Sie die Abfrage in **Region** um.

1. Wenden Sie einen Filter auf die Spalte **SalesTerritoryAlternateKey** an, um den Wert 0 (null) zu entfernen.

    > *Dadurch wird eine Zeile entfernt.*

1. Entfernen Sie alle Spalten, **außer** den folgenden:

    - SalesTerritoryKey
    - SalesTerritoryRegion
    - SalesTerritoryCountry
    - SalesTerritoryGroup

1. Benennen Sie die folgenden drei Spalten um:

    - **SalesTerritoryRegion** in **Region**
    - **SalesTerritoryCountry** in **Country**
    - **SalesTerritoryGroup** in **Group**

**Überprüfen Sie in der Statusleiste, ob die Abfrage 4 Spalten und 10 Zeilen enthält.**

## Konfigurieren der Sales-Abfrage

In dieser Aufgabe konfigurieren Sie die Abfrage **Sales**.

1. Wählen Sie die Abfrage **FactResellerSales** aus, und benennen Sie sie in **Sales** um.

1. Entfernen Sie alle Spalten, **außer** den folgenden:

    - SalesOrderNumber
    - OrderDate
    - ProductKey
    - ResellerKey
    - EmployeeKey
    - SalesTerritoryKey
    - OrderQuantity
    - UnitPrice
    - TotalProductCost
    - SalesAmount
    - DimProduct

    > ***Hinweis**: Möglicherweise erinnern Sie sich, dass im Lab **Vorbereiten von Daten in Power BI Desktop** in den Zeilen **FactResellerSales** ein kleiner Prozentsatz an Werten von **TotalProductCost** fehlte. Die Spalte **DimProduct** wurde hinzugefügt, um die Spalten mit den Standardproduktkosten abzurufen und so die fehlenden Werte zu ergänzen.*

1. Erweitern Sie die Spalte **DimProduct**, deaktivieren Sie alle Spalten, und fügen Sie dann nur die Spalte **StandardCost** hinzu.

1. Klicken Sie zum Erstellen einer benutzerdefinierten Spalte auf der Registerkarte **Spalte hinzufügen** des Menübands in der Gruppe **Allgemein** auf **Benutzerdefinierte Spalte**.

    ![Bild 5.664](Linked_image_Files/02-transform-data-power-bi_image47.png)

1. Ersetzen Sie im Fenster **Benutzerdefinierte Spalte** im Feld **Neuer Spaltenname** den Text durch **Cost**.

1. Geben Sie im Feld **Benutzerdefinierte Spaltenformel** den folgenden Ausdruck ein (nach dem Gleichheitszeichen), und speichern Sie dann die neue Spalte:

   ` if [TotalProductCost] = null then [OrderQuantity] * [StandardCost] else [TotalProductCost] `

    > ***Hinweis**: Sie können den Ausdruck aus der Datei **Snippets.txt** im Ordner „02-transform-data“ kopieren.*

    > *Mit diesem Ausdruck wird getestet, ob der Wert für **TotalProductCost** fehlt. Wenn er fehlt, wird durch Multiplizieren der Werte für **OrderQuantity** und **StandardCost** ein Wert erzeugt. Andernfalls wird der vorhandene Wert für **TotalProductCost** verwendet.*

1. Entfernen Sie die beiden folgenden Spalten:

    - TotalProductCost
    - StandardCost

1. Benennen Sie die folgenden drei Spalten um:

    - **OrderQuantity** in **Quantity**
    - **UnitPrice** in **Unit Price** (Ergänzen eines Leerzeichens)
    - **SalesAmount** in **Sales**

1. Klicken Sie zum Ändern des Datentyps in der Spaltenüberschrift **Quantity** links neben dem Spaltennamen auf das Symbol **1.2**, und wählen Sie **Ganze Zahl** aus.

    > *Es ist wichtig, den richtigen Datentyp zu konfigurieren. Wenn die Spalte einen numerischen Wert enthält, ist es auch wichtig, den richtigen Typ auszuwählen, wenn Sie planen, mit dem Wert mathematische Berechnungen durchzuführen.*

    ![Bild 5.667](Linked_image_Files/02-transform-data-power-bi_image50.png)

1. Ändern Sie bei den folgenden drei Spalten den Datentyp in **Feste Dezimalzahl**.

    > *Der feste Dezimalzahl-Datentyp lässt 19 Ziffern zu und ermöglicht eine höhere Genauigkeit zu, um Rundungsfehler zu vermeiden. Es ist wichtig, den festen Dezimalzahlentyp für Finanzwerte oder Kurse (z. B. Wechselkurse) zu verwenden.*

    - Unit Price
    - Sales
    - Cost

**Überprüfen Sie in der Statusleiste, ob die Abfrage 10 Spalten und 999+ Zeilen enthält.** *Maximal 1000 Zeilen werden als Vorschaudaten für jede Abfrage geladen.*

## Konfigurieren der Abfrage „Targets“

In dieser Aufgabe konfigurieren Sie die Abfrage **Targets**.

1. Wählen Sie die Abfrage **ResellerSalesTargets** aus, und benennen Sie sie in **Targets** um.

    > **Hinweis:** Wenn Sie eine Warnmeldung erhalten, in der Sie aufgefordert werden, anzugeben, wie die Verbindung hergestellt werden soll, wählen Sie **Zugangsdaten bearbeiten** aus und verwenden Sie den anonymen Zugriff.

1. Wählen Sie zum Entpivotieren der 12 Monatsspalten (**M01**-**M12**) zunächst gleichzeitig die Überschriften der Spalten **Year** und **EmployeeID** aus.

1. Klicken Sie mit der rechten Maustaste auf eine der markierten Spaltenüberschriften und dann mit der linken Maustaste im Kontextmenü auf **Andere Spalten entpivotieren**.

1. Wie Sie sehen, werden jetzt die Spaltennamen in der Spalte **Attribut** und die Werte in der Spalte **Wert** angezeigt.

1. Wenden Sie einen Filter auf die Spalte **Wert** an, um die Bindestrichwerte (-) zu entfernen.

    > *Möglicherweise erinnern Sie sich, dass das Bindestrichzeichen in der CSV-Quelldatei verwendet wurde, um Null (0) darzustellen.*

1. Benennen Sie die beiden folgenden Spalten um:

    - **Attribute** in **MonthNumber** (ohne Leerzeichen)
    - **Wert** in **Target**

1. Klicken Sie zum Vorbereiten der Werte in der Spalte **MonthNumber** mit der rechten Maustaste auf die Spaltenüberschrift **MonthNumber** und dann mit der linken Maustaste auf **Werte ersetzen**.

    > *Nun wenden Sie Transformationen an, um eine Datumsspalte zu erstellen. Das Datum wird aus den Spalten **Year** und **MonthNumber** abgeleitet. Sie erstellen die Spalte mithilfe des Features **Spalte aus Beispielen**.*

1. Geben Sie im Fenster **Werte ersetzen** im Feld **Zu suchender Wert** den Wert **M** ein, und lassen Sie die Option **Ersetzen durch** leer.

1. Ändern Sie den Datentyp der Spalte **MonthNumber** in **Ganze Zahl**.

1. Klicken Sie auf der Registerkarte **Spalte hinzufügen** des Menübands in der Gruppe **Allgemein** auf das Symbol für **Spalte aus Beispielen**.

    ![Bild 5.675](Linked_image_Files/02-transform-data-power-bi_image59.png)

1. Beachten Sie, dass die erste Zeile für das Jahr **2017** und die Monatsnummer **7** ist.

1. Geben Sie in der Spalte **Column1** in der ersten Rasterzelle **7/1/2017**ein, und drücken Sie dann die **EINGABETASTE**.

    > ***Hinweis**: Der virtuelle Computer verwendet das Gebietsschema für die USA, sodass dieses Datum dem 1. Juli 2017 entspricht. Andere regionale Einstellungen erfordern möglicherweise eine **0** vor dem Datum.*

1. Wie Sie sehen, werden die Rasterzellen mit vorhergesagten Werten aktualisiert.

    > *Das Feature hat richtig vorhergesagt, dass Sie Werte aus den Spalten **Year** und **MonthNumber** kombinieren.*

1. Beachten Sie auch die über dem Abfrageraster angezeigte Formel.

    ![Bild 5.679](Linked_image_Files/02-transform-data-power-bi_image60.png)

1. Um die neue Spalte umzubenennen, doppelklicken Sie auf die Spaltenüberschrift **Merged**, und benennen Sie die Spalte in **TargetMonth** um.

1. Entfernen Sie die folgenden Spalten:

    - Year
    - MonthNumber

1. Ändern Sie bei den folgenden Spalten den Datentyp:

    - Bei **Target** in „Feste Dezimalzahl“
    - Bei **TargetMonth** in „Datum“

1. Gehen Sie wie folgt vor, um die Werte in der Spalte **Target** mit 1000 zu multiplizieren: Klicken Sie auf die Spaltenüberschrift **Target**, dann auf der Registerkarte **Transformieren** des Menübands in der Gruppe **Zahlenspalte** auf **Standard**, und wählen Sie **Multiplizieren** aus.

    > *Sicherlich erinnern Sie sich daran, dass die Zielwerte als Tausend gespeichert wurden.*

    ![Bild 5.682](Linked_image_Files/02-transform-data-power-bi_image63.png)

1. Geben Sie im Fenster **Multiplizieren** im Feld **Wert** den Wert **1000** an, und wählen Sie **OK** aus.

**Überprüfen Sie in der Statusleiste, ob die Abfrage 3 Spalten und 809 Zeilen enthält.**

## Konfigurieren der Abfrage „ColorFormats“

In dieser Aufgabe konfigurieren Sie die Abfrage **ColorFormats**.

1. Wählen Sie die Abfrage **ColorFormats** aus, und beachten Sie, dass die erste Zeile die Spaltennamen enthält.

1. Klicken Sie auf der Registerkarte **Start** des Menübands in der Gruppe **Transformieren** auf **Erste Zeile als Überschriften verwenden**.

    ![Bild 5.688](Linked_image_Files/02-transform-data-power-bi_image68.png)

**Überprüfen Sie in der Statusleiste, ob die Abfrage 3 Spalten und 10 Zeilen enthält.**

## Aktualisieren der Abfrage „Product“

In dieser Aufgabe aktualisieren Sie die Abfrage **Product**, indem Sie sie mit der Abfrage **ColorFormats** zusammenführen.

1. Wählen Sie die Abfrage **Product** aus.

1. Klicken Sie zum Zusammenführen mit der Abfrage **ColorFormats** auf der Registerkarte **Start** des Menübands in der Gruppe **Kombinieren** auf **Abfragen zusammenführen**.

    > *Das Zusammenführen von Abfragen ermöglicht das Integrieren von Daten, in diesem Fall aus verschiedenen Datenquellen (SQL Server und einer CSV-Datei).*

    ![Bild 5.654](Linked_image_Files/02-transform-data-power-bi_image71.png)

1. Klicken Sie im Fenster **Zusammenführen** im Abfrageraster für **Product** auf die Spaltenüberschrift **Color**.

    ![Bild 5.655](Linked_image_Files/02-transform-data-power-bi_image72.png)

1. Wählen Sie in der Dropdownliste unterhalb des Abfragerasters für **Product** die Abfrage **ColorFormats** aus.

    ![Bild 21](Linked_image_Files/02-transform-data-power-bi_image73.png)

1. Klicken Sie im Abfrageraster für **ColorFormats** auf die Spaltenüberschrift **Color**.

1. Wenn das Fenster **Datenschutzebenen** geöffnet wird, wählen Sie dort für jede der beiden Datenquellen in der entsprechenden Dropdownliste **Organisation** und dann **Speichern** aus.

    > *Datenschutzebenen können für Datenquellen konfiguriert werden, um festzulegen, ob Daten zwischen Quellen freigegeben werden können. Wenn Sie für alle Datenquellen **Organisation** festlegen, können diese bei Bedarf Daten freigeben. Private Datenquellen können nicht für andere Datenquellen freigegeben werden. Dies bedeutet nicht, dass private Daten überhaupt nicht freigegeben werden können, sondern lediglich, dass die Power Query-Engine keine Daten zwischen den Quellen freigeben kann.*

    ![Bild 5.691](Linked_image_Files/02-transform-data-power-bi_image74.png)

1. Verwenden Sie im Fenster **Zusammenführen** den Standardwert für die **Art des Joins**. Behalten Sie dabei die Auswahl von „Linker äußerer Join“ bei, und klicken Sie auf **OK**.

1. Erweitern Sie die Spalte **ColorFormats**, um die beiden folgenden Spalten hinzuzufügen:

    - Background Color Format
    - Font Color Format

**Sehen Sie sich die Statusleiste an, um sicherzustellen, dass die Abfrage jetzt 8 Spalten und 397 Zeilen enthält.**

## Aktualisieren der Abfrage „ColorFormats“

In dieser Aufgabe aktualisieren Sie **ColorFormats**, um das Laden für diese Abfrage zu deaktivieren.

1. Wählen Sie die Abfrage **ColorFormats** aus.

1. Klicken Sie im Bereich **Abfrageeinstellungen** auf den Link **Alle Eigenschaften**.

    ![Bild 322](Linked_image_Files/02-transform-data-power-bi_image80.png)

1. Deaktivieren Sie im Fenster **Abfrageeigenschaften** das Kontrollkästchen bei **Laden in Bericht aktivieren**.

    > *Wenn Sie den Ladevorgang deaktivieren, wird es nicht als Tabelle in das Datenmodell geladen. Dies geschieht, weil die Abfrage mit der **Product**-Abfrage zusammengeführt wurde, die zum Laden in das Datenmodell aktiviert ist.*

    ![Bild 323](Linked_image_Files/02-transform-data-power-bi_image81.png)

### Überprüfen des endgültigen Produkts

1. Stellen Sie in Power Query-Editor sicher, dass Sie über **8 Abfragen** verfügen, die wie folgt korrekt benannt sind:

    - Salesperson
    - SalespersonRegion
    - Product
    - Reseller
    - Region
    - Sales
    - Targets
    - ColorFormats (wird nicht ins Datenmodell geladen)

1. Wählen Sie **Schließen &amp; Übernehmen** aus, um die Daten in das Modell zu laden und das Fenster des Power Query-Editors zu schießen.

    ![Bild 326](Linked_image_Files/02-transform-data-power-bi_image83.png)

1. Sie können nun den Zeichenbereich in Power BI Desktop mit Filtern, Visualisierungen und Datenbereichen auf der rechten Seite sehen. Im Bereich „Daten“ sehen Sie die **7 Tabellen**, die in das Datenmodell geladen wurden.

    ![Abbildung 3](Linked_image_Files/02-transform-data-power-bi_image84.png)

## Lab abgeschlossen
