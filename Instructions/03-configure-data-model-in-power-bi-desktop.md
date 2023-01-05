---
lab:
  title: Entwerfen eines Datenmodells in Power BI
  module: 4 - Design a Data Model in Power BI
---


# <a name="design-a-data-model-in-power-bi"></a>Entwerfen eines Datenmodells in Power BI

**Die geschätzte Dauer dieses Labs beträgt 45 Minuten.**

In diesem Lab beginnen Sie mit der Entwicklung des Datenmodells. Dies umfasst das Erstellen von Beziehungen zwischen Tabellen und das anschließende Konfigurieren von Tabellen- und Spalteneigenschaften, um die Benutzerfreundlichkeit und Nutzbarkeit des Datenmodells zu verbessern. Außerdem erstellen Sie Hierarchien und Quickmeasures.

In diesem Lab lernen Sie Folgendes:

- Erstellen von Modellbeziehungen

- Konfigurieren von Tabellen- und Spalteneigenschaften

- Erstellen von Hierarchien


### <a name="lab-story"></a>**Labszenario**

Dieses Lab ist eines von vielen in einer Reihe von Labs, die als fortlaufendes Szenario von der Datenvorbereitung bis zur Veröffentlichung als Berichte und Dashboards entworfen wurde. Sie können die Labs in beliebiger Reihenfolge abschließen. Wenn Sie jedoch beabsichtigen, mehrere Labs durchzuarbeiten, sollten Sie sie in der folgenden Reihenfolge absolvieren:

1. Vorbereiten von Daten in Power BI Desktop

2. Laden von Daten in Power BI Desktop

3. **Entwerfen eines Datenmodells in Power BI**

4. Erstellen von DAX-Berechnungen in Power BI Desktop, Teil 1

5. Erstellen von DAX-Berechnungen in Power BI Desktop, Teil 2

6. Entwerfen eines Berichts in Power BI Desktop, Teil 1

7. Entwerfen eines Berichts in Power BI Desktop, Teil 2

8. Analysieren von Daten mit KI-Visuals

9. Erstellen eines Power BI-Dashboards

10. Erzwingen von Sicherheit auf Zeilenebene

## <a name="exercise-1-create-model-relationships"></a>**Übung 1: Erstellen von Modellbeziehungen**

In dieser Übung erstellen Sie Modellbeziehungen.

### <a name="task-1-get-started"></a>**Aufgabe 1: Erste Schritte**

In dieser Aufgabe richten Sie die Umgebung für das Lab ein.

*Wichtig: Wenn Sie nach einem vorherigen Lab fortfahren (und dieses Lab erfolgreich abgeschlossen haben), überspringen Sie diese Aufgabe und fahren mit der nächsten fort.*

1. Klicken Sie zum Öffnen von Power BI Desktop auf der Taskleiste auf die Verknüpfung „Microsoft Power BI Desktop“.

    ![Bild 12](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image1.png)

1. Um das Fenster „Erste Schritte“ zu schließen, klicken Sie links oben im Fenster auf das **X**.

    ![Bild 11](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image2.png)

1. Um die Startdatei für Power BI Desktop zu öffnen, klicken Sie auf die Registerkarte **Datei** des Menübands, um die Backstage-Ansicht zu öffnen.

1. Wählen Sie **Bericht öffnen** aus.

    ![Bild 10](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image3.png)

1. Klicken Sie auf **Berichte durchsuchen**.

    ![Bild 8](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image4.png)

1. Navigieren Sie im Fenster **Öffnen** zum Ordner **D:\PL300\Labs\03-configure-data-model-in-power-bi-desktop\Starter**.

1. Wählen Sie die Datei **Sales Analysis** aus.

1. Klicken Sie auf **Öffnen**.

    ![Bild 7](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image5.png)

1. Schließen Sie alle Informationsfenster, die möglicherweise geöffnet werden.

1. Um eine Kopie der Datei zu erstellen, klicken Sie auf die Registerkarte **Datei** des Menübands, um die Backstage-Ansicht zu öffnen.

1. Wählen Sie **Speichern unter** aus.

    ![Bild 5](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image6.png)

1. Wenn Sie aufgefordert werden, die Abfragen anzuwenden, klicken Sie auf **Anwenden**.

    ![Bild 15](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image7.png)

1. Navigieren Sie im Fenster **Speichern unter** zum Ordner **D:\PL300\MySolution**.

1. Klicken Sie auf **Speichern**.

    ![Bild 3](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image8.png)

### <a name="task-2-create-model-relationships"></a>**Aufgabe 2: Erstellen von Modellbeziehungen**

In dieser Aufgabe erstellen Sie Modellbeziehungen.

1. Klicken Sie links in Power BI Desktop auf das Symbol für die **Modellansicht**.

    ![Abbildung 1](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image9.png)

2. Wenn Ihnen nicht alle sieben Tabellen angezeigt werden, scrollen Sie nach rechts, und ordnen Sie die Tabellen aneinander an, damit Sie alle gleichzeitig sehen können.

    *Tipp: Sie können auch das Zoomsteuerelement unten im Fenster verwenden.*

    *In der Modellansicht können Sie jede Tabelle und alle Beziehungen (Connectors zwischen Tabellen) anzeigen. Zurzeit gibt es keine Beziehungen, da Sie im Lab **Vorbereiten von Daten in Power BI Desktop** die Optionen für die Datenladebeziehung deaktiviert haben.*

3. Klicken Sie links auf das Symbol für die **Berichtsansicht**, um zur Berichtsansicht zurückzukehren.

    ![Bild 327](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image10.png)

4. Klicken Sie im Bereich **Felder** mit der rechten Maustaste auf einen leeren Bereich, und wählen Sie dann **Alle erweitern** aus.

    ![Bild 328](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image11.png)

5. Aktivieren Sie zum Erstellen eines Tabellenvisuals im Bereich **Felder** innerhalb der Tabelle **Product** das Feld **Category**.

    ![Bild 329](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image12.png)

    *In den Labs wird eine verkürzte Notation verwendet, um auf ein Feld zu verweisen. Das sieht folgendermaßen aus: **Product \| Category**. In diesem Beispiel ist **Product** der Tabellenname und **Category** der Feldname.*

6. Aktivieren Sie im Bereich **Felder** das Feld **Sales \| Sales**, um der Tabelle eine Spalte hinzuzufügen.

7. Beachten Sie, dass das Tabellenvisual vier Produktkategorien aufführt und dass der Umsatzwert für alle Kategorien sowie für den Gesamtwert gleich ist.

    ![Bild 330](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image13.png)

    *Das Problem besteht darin, dass die Tabelle auf Feldern aus anderen Tabellen basiert. Es wird erwartet, dass jede Produktkategorie den Umsatz für die Kategorie anzeigt. Allerdings wird die Tabelle **Sales** nicht gefiltert, da zwischen diesen Tabellen keine Modellbeziehung besteht. Im Folgenden fügen Sie eine Beziehung hinzu, um Filter zwischen den Tabellen weiterzugeben.*

8. Klicken Sie auf der Menübandregisterkarte **Modellierung** innerhalb der Gruppe **Beziehungen** auf **Beziehungen verwalten**.

    ![Bild 331](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image14.png)

9. Beachten Sie, dass im Fenster **Beziehungen verwalten** keine Beziehungen definiert sind.

10. Klicken Sie auf **Neu**, um eine Beziehung zu erstellen.

    ![Bild 332](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image15.png)

11. Wählen Sie im Fenster **Beziehung erstellen** in der ersten Dropdownliste die Tabelle **Product** aus.

    ![Bild 333](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image16.png)

12. Wählen Sie in der zweiten Dropdownliste (unter dem Tabellenraster **Product**) die Tabelle **Sales** aus.

    ![Bild 334](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image17.png)

13. Beachten Sie, dass die **ProductKey**-Spalten in beiden Tabellen ausgewählt wurden.

    *Diese Spalten wurden ausgewählt, da sie denselben Namen und Datentyp haben.*

14. Beachten Sie, dass in der Dropdownliste **Kardinalität** die Option **1:n** ausgewählt ist.

    *Die Kardinalität wurde automatisch ermittelt, da Power BI versteht, dass die Spalte **ProductKey** der Tabelle **Product** eindeutige Werte enthält. 1:n-Beziehungen sind die gängigste Kardinalität, und alle Beziehungen, die Sie in diesem Lab erstellen, weisen diesen Typ auf.*

15. Beachten Sie, dass in der Dropdownliste **Kreuzfilterrichtung** die Option **Einfach** ausgewählt ist.

    *Die Filterrichtung „Einfach“ bedeutet, dass die Filter von der Seite „1“ zur Seite „n“ weitergegeben werden. In diesem Fall werden die Filter, die auf die Tabelle **Product** angewandt wurden, an die Tabelle **Sales** weitergegeben, aber nicht in die andere Richtung.*

16. Beachten Sie, dass das Kontrollkästchen **Diese Beziehung aktivieren** aktiviert ist.

    *Aktive Beziehungen geben Filter weiter. Eine Beziehung kann als inaktiv gekennzeichnet werden, damit die Filter nicht weitergegeben werden. Inaktive Beziehungen können vorhanden sein, wenn mehrere Beziehungspfade zwischen Tabellen vorliegen. In diesem Fall können Modellberechnungen spezielle Funktionen nutzen, um sie zu aktivieren.*

17. Klicken Sie auf **OK**.

    ![Bild 335](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image18.png)

18. Überprüfen Sie, ob die neue Beziehung im Fenster **Beziehungen verwalten** aufgelistet wird, und klicken Sie dann auf **Schließen**.

    ![Bild 336](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image19.png)

19. Beachten Sie, dass das Tabellenvisual im Bericht aktualisiert wurde und verschiedene Werte für alle Produktkategorien angezeigt werden.

    ![Bild 337](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image20.png)

    *Die Filter, die auf die Tabelle **Product** angewandt werden, werden nun an die Tabelle **Sales** weitergegeben.*

20. Wechseln Sie zur Modellansicht, und beachten Sie, dass jetzt ein Connector zwischen den beiden Tabellen vorhanden ist (es spielt keine Rolle, ob die Tabellen nebeneinander positioniert sind).

    ![Bild 338](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image21.png)

21. Sie können die Kardinalität im Diagramm interpretieren, die mit den Indikatoren **1** und ***** dargestellt wird.

    *Die Filterrichtung wird durch eine Pfeilspitze dargestellt. Eine durchgängige Linie stellt eine aktive Beziehung dar, während eine gestrichelte Linie eine inaktive Beziehung darstellt.*

22. Zeigen Sie mit dem Cursor auf die Beziehung, um die zugehörigen Spalten hervorzuheben.

    *Es gibt eine einfachere Methode zum Erstellen einer Beziehung. Im Modelldiagramm können Sie Spalten per Drag & Drop gruppieren, um eine neue Beziehung zu erstellen.*

23. Zum Erstellen einer neuen Beziehung auf andere Weise über die Tabelle **Reseller** ziehen Sie die Spalte **ResellerKey** auf die Spalte **ResellerKey** der Tabelle **Sales**.

    ![Bild 339](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image22.png)

    *Tipp: Manchmal ist es nicht möglich, eine Spalte zu bewegen. Tritt eine solche Situation auf, wählen Sie zunächst eine andere Spalte und dann wieder die Spalte aus, die Sie bewegen möchten, und versuchen Sie es noch mal. Vergewissern Sie sich, dass die neue Beziehung im Diagramm hinzugefügt wurde.*

24. Erstellen Sie die folgenden zwei Modellbeziehungen mit der neuen Vorgehensweise:

    - **Region \| SalesTerritoryKey** mit **Sales \| SalesTerritoryKey**

    - **Salesperson \| EmployeeKey** mit **Sales \| EmployeeKey**

25. Ordnen Sie die Tabellen im Diagramm so an, dass die Tabelle **Sales** in der Mitte des Diagramms positioniert ist und die zugehörigen Tabellen darüber angeordnet sind. Platzieren Sie die getrennten Tabellen an der Seite.

    ![Bild 340](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image23.png)


26. Speichern Sie die Power BI Desktop-Datei.

## <a name="exercise-2-configure-tables"></a>**Übung 2: Konfigurieren von Tabellen**

In dieser Übung konfigurieren Sie die einzelnen Tabellen, indem Sie Hierarchien erstellen und Spalten ausblenden, formatieren und kategorisieren.

### <a name="task-1-configure-the-product-table"></a>**Aufgabe 1: Konfigurieren der Tabelle „Product“**

In dieser Aufgabe konfigurieren Sie die Tabelle **Product**.

1. Erweitern Sie in der Modellansicht im Bereich **Felder** bei Bedarf die Tabelle **Product**, um alle Felder anzuzeigen.

2. Klicken Sie zum Erstellen einer Hierarchie im Bereich **Felder** mit der rechten Maustaste auf die Spalte **Category**, und klicken Sie dann auf **Hierarchie erstellen**.

    ![Bild 341](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image24.png)

3. Ersetzen Sie im Bereich **Eigenschaften** (links neben dem Bereich **Felder**) im Feld **Name** den Text durch **Products**.

    ![Bild 344](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image25.png)

4. Scrollen Sie zum Hinzufügen einer zweiten Hierarchieebene im Bereich **Eigenschaften** in der Dropdownliste **Hierarchie** nach unten, und wählen Sie **Subcategory** aus (Sie müssen eventuell im Bereich nach unten scrollen).

5. Klicken Sie zum Hinzufügen einer dritten Hierarchieebene in der Dropdownliste **Hierarchie** auf **Product**.

6. Klicken Sie zum Abschließen der Hierarchieerstellung auf **Ebenenänderungen anwenden**.

    ![Bild 343](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image26.png)

    *Tipp: Vergessen Sie nicht, auf **Ebenenänderungen anwenden** zu klicken. Es ist ein häufiger Fehler, diesen Schritt zu übersehen.*

7. Sehen Sie sich im Bereich **Felder** die Hierarchie **Products** an.

    ![Bild 347](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image27.png)

8. Damit die Hierarchieebenen angezeigt werden, erweitern Sie die Hierarchie **Products**.

    ![Bild 346](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image28.png)

9. Wenn Sie die Spalten in einem Anzeigeordner organisieren möchten, klicken Sie im Bereich **Felder** zunächst auf die Spalte **Background Color Format**.

10. Wählen Sie die Spalte **Font Color Format** aus, während Sie **STRG** gedrückt halten.

11. Geben Sie im Bereich **Eigenschaften** im Feld **Anzeigeordner** **Formatting** ein.

    ![Bild 348](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image29.png)

12. Beachten Sie, dass sich die beiden Spalten im Bereich **Felder** nun in einem Ordner befinden.

    ![Bild 349](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image30.png)

    *Anzeigeordner bieten eine sehr gute Möglichkeit, Tabellen zu bereinigen, insbesondere diejenigen, die viele Felder enthalten.*

### <a name="task-2-configure-the-region-table"></a>**Aufgabe 2: Konfigurieren der Tabelle „Region“**

In dieser Aufgabe konfigurieren Sie die Tabelle **Region**.

1. Erstellen Sie in der Tabelle **Region** eine Hierarchie namens **Regions** mit den folgenden drei Ebenen:

    - Group

    - Country

    - Region

    ![Bild 350](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image31.png)

2. Wählen Sie die Spalte **Country** aus (nicht die Hierarchieebene **Country**).

3. Erweitern Sie im Bereich **Eigenschaften** den Abschnitt **Erweitert** (unten im Bereich), und wählen Sie dann in der Dropdownliste **Datenkategorie** die Option **Land/Region** aus.

    ![Bild 352](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image32.png)

    *Eine Datenkategorisierung kann Hinweise für den Berichts-Designer geben. In diesem Fall gibt das Kategorisieren der Spalte als Land oder Region genauere Informationen beim Rendern einer Kartenvisualisierung durch Power BI.*

### <a name="task-3-configure-the-reseller-table"></a>**Aufgabe 3: Konfigurieren der Tabelle „Reseller“**

In dieser Aufgabe konfigurieren Sie die Tabelle **Reseller**.

1. Erstellen Sie in der Tabelle **Reseller** eine Hierarchie namens **Resellers** mit den folgenden beiden Ebenen:

    - Business Type

    - Reseller

    ![Bild 351](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image33.png)

2. Erstellen Sie eine zweite Hierarchie namens **Geography** mit den folgenden vier Ebenen:

    - Country-Region

    - State-Province

    - City

    - Reseller

    ![Bild 353](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image34.png)

3. Legen Sie die **Datenkategorie** für die Spalten **Country-Region**, **State-Province** und **City** (nicht die Hierarchieebene) auf **Land/Region**, **Bundesland/Kanton** und **Stadt** fest. 

### <a name="task-4-configure-the-sales-table"></a>**Aufgabe 4: Konfigurieren der Tabelle „Sales“**

In dieser Aufgabe konfigurieren Sie die Tabelle **Sales**.

1. Klicken Sie in der Tabelle **Sales** auf die Spalte **Cost**.

2. Geben Sie im Bereich **Eigenschaften** in das Feld **Beschreibung** Folgendes ein: **Basierend auf Standardkosten**

    ![Bild 358](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image35.png)

    *Beschreibungen können auf Tabellen, Spalten, Hierarchien oder Measures angewandt werden. Im Bereich **Felder** wird Beschreibungstext als QuickInfo angezeigt, wenn der Berichtersteller den Cursor über ein Feld bewegt.*

3. Klicken Sie auf die Spalte **Quantity**.

4. Verschieben Sie im Bereich **Eigenschaften** im Abschnitt **Formatierung** den Schieberegler für die Eigenschaft **Tausendertrennzeichen** auf **Ja**.

    ![Bild 357](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image36.png)

5. Klicken Sie auf die Spalte **Unit Price**.

6. Legen Sie die Eigenschaft **Dezimalstellen** im Bereich **Eigenschaften** im Abschnitt **Formatierung** auf **2** fest.

7. Klicken Sie in der Gruppe **Erweitert** (möglicherweise müssen Sie dazu nach unten scrollen) in der Dropdownliste **Zusammenfassen nach** auf **Durchschnitt**.

    ![Bild 354](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image37.png)

    *Standardmäßig werden numerische Spalten zusammengefasst, indem Werte summiert werden. Dieses Standardverhalten ist jedoch nicht für Spalten wie **Unit Price** geeignet, in denen eine Rate dargestellt wird. Das Festlegen der Standardzusammenfassung auf einen Durchschnitt erzeugt ein aussagekräftiges Ergebnis.*

### <a name="task-5-bulk-update-properties"></a>**Aufgabe 5: Massenaktualisieren von Eigenschaften**

Bei dieser Aufgabe aktualisieren Sie mehrere Spalten mit einer einzelnen Massenaktualisierung. Sie verwenden diesen Ansatz, um Spalten auszublenden und Spaltenwerte zu formatieren.

1. Wählen Sie im Bereich **Felder** die Spalte **Product \| ProductKey** aus.

2. Wählen Sie die folgenden 13 Spalten aus, die sich über mehrere Tabellen erstrecken, und halten Sie dabei **STRG** gedrückt:

    - Region \| SalesTerritoryKey

    - Reseller \| ResellerKey

    - Sales \| EmployeeKey
    
    - Sales \| ProductKey

    - Sales \| ResellerKey

    - Sales \| SalesOrderNumber

    - Sales \| SalesTerritoryKey

    - Salesperson \| EmployeeID

    - Salesperson \| EmployeeKey

    - Salesperson \| UPN

    - SalespersonRegion \| EmployeeKey

    - SalespersonRegion \| SalesTerritoryKey

    - Targets \| EmployeeID

3. Bewegen Sie im Bereich **Eigenschaften** den Schieberegler für die Eigenschaft **Ist verborgen** auf **Ja**.

    ![Bild 355](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image38.png)

    *Die Spalten wurden ausgeblendet, da sie entweder von Beziehungen oder in der Sicherheitskonfiguration oder Berechnungslogik auf Zeilenebene verwendet werden.*

    *Im Lab **Erstellen von DAX-Berechnungen in Power BI Desktop, Teil 1** verwenden Sie **SalesOrderNumber** in einer Berechnung.*

4. Nehmen Sie eine Mehrfachauswahl für die folgenden drei Spalten vor:

    - Product \| Standard Cost

    - Sales \| Cost

    - Sales \| Sales

5. Verschieben Sie im Bereich **Eigenschaften** im Abschnitt **Formatierung** den Schieberegler für die Eigenschaft **Dezimalstellen** auf **0** (null).

    ![Bild 356](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image39.png)

## <a name="exercise-3-review-the-model-interface"></a>**Übung 3: Überprüfen der Benutzeroberfläche des Modells**

In dieser Übung wechseln Sie zur Berichtsansicht und überprüfen die Benutzeroberfläche des Modells.

### <a name="task-1-review-the-model-interface"></a>**Aufgabe 1: Überprüfen der Benutzeroberfläche des Modells**

In dieser Aufgabe wechseln Sie zur Berichtsansicht und überprüfen die Benutzeroberfläche des Modells.

1. Wechseln Sie zur Ansicht „Bericht“.

2. Sehen Sie sich im Bereich **Felder** Folgendes an:

    - Spalten, Hierarchien und die zugehörigen Ebenen sind Felder, die zum Konfigurieren von Berichtsvisuals verwendet werden können.

    - Nur Felder, die für die Berichterstellung relevant sind, werden angezeigt.

    - Die Tabelle **SalespersonRegion** wird nicht angezeigt, da alle zugehörigen Felder ausgeblendet sind.

    - Felder mit räumlichen Daten in den Tabellen **Region** und **Reseller** werden mit einem entsprechenden Symbol hervorgehoben.

    - Felder mit dem Sigmasymbol (Ʃ) werden standardmäßig zusammengefasst.

    - Wenn der Cursor über das Feld **Sales \| Cost** bewegt wird, wird eine QuickInfo angezeigt.

3. Erweitern Sie das Feld **Sales \| OrderDate**. Daraufhin wird eine Datumshierarchie angezeigt.

    ![Bild 359](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image40.png)

    *Das Feld **Targets \| TargetMonth** bietet eine ähnliche Hierarchie. Diese Hierarchien wurden nicht von Ihnen erstellt. Sie wurden automatisch erstellt. Es gibt jedoch ein Problem. Das Finanzjahr von Adventure Works beginnt am 1. Juli jedes Jahres. Diese automatisch erstellten Datumshierarchien beginnen jedoch am 1. Januar jedes Jahres.*

    *Im Folgenden deaktivieren Sie dieses automatische Verhalten. Im Lab **Erstellen von DAX-Berechnungen in Power BI Desktop, Teil 1** erstellen Sie mit DAX eine Datumstabelle und konfigurieren sie so, dass sie dem Adventure Works-Kalender entspricht.*

4. Klicken Sie zum Deaktivieren der automatischen Datums-/Uhrzeitfunktion im Menüband auf die Registerkarte **Datei**, um die Backstage-Ansicht zu öffnen.

5. Klicken Sie links auf **Optionen und Einstellungen**, und wählen Sie dann **Optionen** aus.

    ![Bild 360](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image41.png)

6. Klicken Sie links im Fenster **Optionen** in der Gruppe **Aktuelle Datei** auf **Daten laden**.

    ![Bild 361](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image42.png)

7. Deaktivieren Sie im Abschnitt **Zeitintelligenz** die Option **Autom. Datum/Uhrzeit**.

    ![Bild 362](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image43.png)

8. Klicken Sie auf **OK**.

    ![Bild 9](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image44.png)

9. Beachten Sie, dass die Datumshierarchien im Bereich **Felder** nicht mehr verfügbar sind.

    ![Bild 363](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image45.png)


## <a name="exercise-4-create-quick-measures"></a>**Übung 4: Erstellen von Quickmeasures**

In dieser Übung erstellen Sie zwei Quickmeasures.

### <a name="task-1-create-quick-measures"></a>**Aufgabe 1: Erstellen von Quickmeasures**

In dieser Aufgabe erstellen Sie zwei Quickmeasures zur Berechnung des Gewinns und der Gewinnspanne.

1. Klicken Sie im Bereich **Felder** mit der rechten Maustaste auf die Tabelle **Sales**, und wählen Sie dann die Option **Neues Quickmeasure** aus.

    ![Bild 366](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image46.png)

2. Wählen Sie im Fenster **Quickmeasures** in der Dropdownliste **Berechnung** innerhalb der Gruppe **Mathematische Operationen** die Option **Subtraktion** aus.

    ![Bild 367](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image47.png)

3. Erweitern Sie im Bereich **Felder** des Fensters **Quickmeasures** die Tabelle **Sales**.

4. Ziehen Sie das Feld **Sales** in das Feld **Basiswert**.

5. Ziehen Sie das Feld **Cost** in das Feld **Wert, der subtrahiert werden soll**.

    ![Bild 368](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image48.png)

6. Klicken Sie auf **OK**.

    ![Bild 369](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image49.png)

    *Quickmeasures erstellen die Berechnungsformel für Sie. Sie können diese schnell für einfache und häufige Berechnungen erstellen. Im Lab **Erstellen von DAX-Berechnungen in Power BI Desktop, Teil 1** erstellen Sie Measures ohne dieses Tool.*

7. Beachten Sie das neue Measure im Bereich **Felder** in der Tabelle **Sales**.

    ![Bild 370](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image50.png)

    *Measures werden mit dem Rechnersymbol versehen.*

8. Zum Umbenennen des Measures klicken Sie mit der rechten Maustaste auf dieses und wählen dann **Umbenennen** aus.

    ![Bild 371](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image51.png)

    *Tipp: Zum Umbenennen eines Feldes können Sie auf dieses doppelklicken oder es auswählen und **F2** drücken.*

9. Benennen Sie das Measure in **Profit** um, und drücken Sie dann die **EINGABETASTE**.

10. Fügen Sie in der Tabelle **Sales** ein zweites Quickmeasure basierend auf den folgenden Anforderungen hinzu:

    - Verwenden Sie die mathematische Operation **Division**.

    - Legen Sie als **Numerator** das Feld **Sales \| Profit** fest.

    - Legen Sie als **Denominator** das Feld **Sales \| Sales** fest.

    - Benennen Sie das Measure in **Profit Margin** um.

    ![Bild 372](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image52.png)

    ![Bild 373](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image53.png)

11. Stellen Sie sicher, dass das Measure **Profit Margin** ausgewählt ist, und legen Sie dann im Kontextmenüband **Messtools** das Format **Prozent** mit zwei Dezimalstellen fest.

    ![Bild 374](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image54.png)

12. Wählen Sie das erste Tabellenvisual auf der Berichtsseite aus, um die zwei Measures zu testen.

13. Markieren Sie die zwei Measures im Bereich **Felder**.

    ![Bild 375](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image55.png)

14. Klicken Sie auf die Führungslinie, und ziehen Sie diese, um das Tabellenvisual zu erweitern.

    ![Bild 376](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image56.png)

15. Stellen Sie sicher, dass die Measures sinnvolle Ergebnisse erzeugen, die ordnungsgemäß formatiert sind.

    ![Bild 378](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image57.png)

### <a name="task-2-create-a-many-to-many-relationship"></a>**Aufgabe 2: Erstellen einer m:n-Beziehung**

In dieser Aufgabe erstellen Sie eine m:n-Beziehung zwischen den Tabellen **Salesperson** und **Sales**.

1. Aktivieren Sie in Power BI Desktop in der Berichtsansicht im Bereich **Felder** die folgenden zwei Felder, um ein Tabellenvisual zu erstellen:

    - Salesperson \| Salesperson

    - Sales \| Sales

    *In den Labs wird eine verkürzte Notation verwendet, um auf ein Feld zu verweisen. Das sieht folgendermaßen aus: **Salesperson \| Salesperson**. In diesem Beispiel ist **Salesperson** der Tabellenname und **Salesperson** der Feldname.*

    ![Abbildung 1](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image9.png)

    *Die Tabelle zeigt die Umsätze der einzelnen Vertriebsmitarbeiter an. Allerdings besteht eine weitere Beziehung zwischen den Vertriebsmitarbeiter*innen und den Umsätzen. Einige Vertriebsmitarbeiter gehören zu einer oder mehreren Vertriebsregionen. Darüber hinaus können den Vertriebsregionen mehrere Vertriebsmitarbeiter zugewiesen sein.*

    *Aus der Leistungsverwaltungsperspektive müssen die Umsätze von Vertriebsmitarbeiter*innen (anhand den ihnen zugewiesenen Regionen) analysiert und mit Verkaufszielen verglichen werden. In der nächsten Übung erstellen Sie Beziehungen, um diese Analyse zu unterstützen.*

2. Beachten Sie, dass Michael Blythe einen Umsatz von fast 9 Millionen Dollar erzielt hat.

3. Wechseln Sie zur Ansicht „Modell“.

    ![Bild 10](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image10.png)

4. Ziehen Sie die Tabelle **SalespersonRegion** zwischen die Tabellen **Region** und **Salesperson**.

5. Erstellen Sie die folgenden zwei Modellbeziehungen per Drag & Drop:

    - **Salesperson \| EmployeeKey** mit **SalespersonRegion \| EmployeeKey**

    - **Region \| SalesTerritoryKey** mit **SalespersonRegion \| SalesTerritoryKey**

    *Die Tabelle **SalespersonRegion** kann als Bridgingtabelle betrachtet werden.*

6. Wechseln Sie zur Berichtsansicht. Sie sollten sehen, dass das Visual nicht aktualisiert und somit die Ergebnisse für Michael Blythe nicht geändert wurden.

7. Wechseln Sie zurück zur Modellansicht, und führen Sie dann die Anweisungen für den Beziehungsfilter (Pfeilspitzen) von der Tabelle **Salesperson**.

    *Beachten Sie, dass die Tabelle **Salesperson** die Tabelle **Sales** filtert. Außerdem filtert sie die Tabelle **SalespersonRegion**, gibt aber keine Filter an die Tabelle **Region** weiter (der Pfeil zeigt in die falsche Richtung).*

    ![Bild 380](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image11.png)

8. Doppelklicken Sie auf die Beziehung, um die Beziehung zwischen den Tabellen **Region** und **SalespersonRegion** zu bearbeiten.

9. Wählen Sie im Fenster **Beziehung bearbeiten** in der Dropdownliste **Kreuzfilterrichtung** die Option **Beide** aus.

10. Aktivieren Sie das Kontrollkästchen **Sicherheitsfilter in beide Richtungen anwenden**.

    ![Bild 381](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image12.png)

11. Klicken Sie auf **OK**.

    ![Bild 335](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image13.png)

12. Beachten Sie, dass die Beziehung über Pfeile in beide Richtungen verfügt.

    ![Bild 382](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image14.png)

13. Wechseln Sie zur Berichtsansicht, und beachten Sie, dass die Umsätze sich noch immer nicht geändert haben.

    *Das Problem besteht nun darin, dass es zwei mögliche Pfade für die Filterweiterleitung zwischen den Tabellen **Salesperson** und **Sales** gibt. Diese Mehrdeutigkeit wird anhand einer Bewertung nach „der geringsten Anzahl an Tabellen“ intern aufgelöst. Sie sollten keine Modelle mit einer solchen Mehrdeutigkeit erstellen. Das Problem wird später in diesem Lab und im Laufe des Labs **Erstellen von DAX-Berechnungen in Power BI Desktop, Teil 1** aufgegriffen.*

14. Wechseln Sie zur Ansicht „Modell“.

15. Bearbeiten (doppelklicken) Sie die Beziehung zwischen den Tabellen **Salesperson** und **Sales**, um die Filterweiterleitung über die Bridgingtabelle zu erzwingen.

16. Deaktivieren Sie im Fenster **Beziehung bearbeiten** das Kontrollkästchen **Diese Beziehung aktivieren**.

    ![Bild 383](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image15.png)

17. Klicken Sie auf **OK**.

    ![Bild 5696](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image16.png)

    *Die Filterweitergabe erfolgt nun über den einzigen aktiven Pfad.*

18. Beachten Sie, dass die inaktive Beziehung im Diagramm mit einer gestrichelten Linie dargestellt wird.

    ![Bild 5697](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image17.png)

19. Wechseln Sie zur Berichtsansicht, dort sollten Sie nun sehen, dass der Umsatz von Michael Blythe nun nahezu 22 Millionen Dollar beträgt.

    ![Bild 5698](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image18.png)

20. Beachten Sie, dass die Umsätze aller Vertriebsmitarbeiter*innen die Tabellensumme überschreiten würden, wenn sie summiert werden.

    *Dies kann bei m:n-Beziehungen häufig beobachtet werden, da die regionalen Verkaufsergebnisse mehrmals gezählt werden. Sehen Sie sich den zweiten Vertriebsmitarbeiter, Brian Welcker, in der Liste an. Sein Umsatz entspricht dem Gesamtumsatz. Dabei handelt es sich um das richtige Ergebnis, da er der Vertriebsleiter ist und sein Umsatz sich aus den Umsätzen aller Regionen ergibt.*

    *Zwar funktionieren die m:n-Beziehungen nun, jedoch ist es nicht möglich, den Umsatz von Vertriebsmitarbeiter*innen zu analysieren (da die Beziehung inaktiv ist). Sie können die Beziehung reaktivieren, wenn Sie eine berechnete Tabelle einführen, die die Analyse von Umsätzen in den Vertriebsregionen ermöglicht, die den Vertriebsmitarbeiter*innen (für die Leistungsanalyse) im Lab **Erstellen von DAX-Berechnungen in Power BI Desktop, Teil 1** zugewiesen wurden.*

21. Wechseln Sie zur Modellierungsansicht, und wählen Sie im Diagramm die Tabelle **Salesperson** aus.

22. Ersetzen Sie im Bereich **Eigenschaften** den Text im Feld **Name** durch **Salesperson (Performance)**.

    *Die umbenannte Tabelle spiegelt nun ihren Zweck wider: Sie wird dazu verwendet, die Leistung von Vertriebsmitarbeiter*innen anhand ihrer Umsätze in den ihnen zugewiesenen Vertriebsregionen zu dokumentieren und zu analysieren.*

### <a name="task-3-relate-the-targets-table"></a>**Aufgabe 3: Zuordnen der Targets-Tabelle**

Im Rahmen dieser Aufgabe erstellen Sie eine Beziehung zur Tabelle **Targets**.

1. Erstellen Sie eine Beziehung zwischen den Spalten **Salesperson (Performance) \| EmployeeID** und **Targets \| EmployeeID**.

2. Fügen Sie in der Berichtsansicht das Feld **Targets \| Target** zum Tabellenvisual hinzu.

3. Ändern Sie die Größe des Tabellenvisuals, sodass alle Spalten angezeigt werden.

    ![Bild 5699](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image19.png)

    *Zwar können Sie nun Verkäufe und Ziele visualisieren, allerdings sollten Sie aus zwei Gründen vorsichtig vorgehen. Erstens gibt es keinen Filter für einen Zeitraum, weshalb Ziele auch zukünftige Zielwerte einschließen. Zweitens sind Ziele nicht additiv, weshalb die Summe nicht angezeigt werden sollte. Diese können entweder durch das Formatieren des Visuals deaktiviert oder mithilfe von Berechnungslogik entfernt werden. Sie verfolgen den zweiten Ansatz, indem Sie im Lab **Erstellen von DAX-Berechnungen in Power BI Desktop, Teil 2** ein Zielmeasure erstellen, das einen leeren Wert zurückgibt, wenn nach mehreren Vertriebsmitarbeiter*innen gefiltert wird.*

### <a name="task-4-finish-up"></a>**Aufgabe 4: Abschluss**

Mit dieser Aufgabe schließen Sie das Lab ab.

1. Speichern Sie die Power BI Desktop-Datei.

2. Wenn Sie aufgefordert werden, die Abfragen anzuwenden, wählen Sie **Später übernehmen** aus.

3. Wenn Sie beabsichtigen, das nächste Lab zu starten, lassen Sie Power BI Desktop geöffnet.
