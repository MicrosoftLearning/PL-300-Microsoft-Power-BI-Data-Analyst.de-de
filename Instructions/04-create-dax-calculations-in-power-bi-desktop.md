---
lab:
  title: Erstellen von DAX-Berechnungen in Power BI Desktop, Teil 1
  module: Module 5 - Create Model Calculations using DAX in Power BI
ms.openlocfilehash: 3bbdf3dfb4b302a9b3c28005976ff34764c1c542
ms.sourcegitcommit: d88b7941fe3805f0bc2979ea864c5483ec289c75
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2022
ms.locfileid: "146071708"
---
# <a name="create-dax-calculations-in-power-bi-desktop-part-1"></a>**Erstellen von DAX-Berechnungen in Power BI Desktop, Teil 1**

**Die geschätzte Dauer dieses Labs beträgt 45 Minuten.**

In diesem Lab erstellen Sie mithilfe von Data Analysis Expressions (DAX) berechnete Tabellen, berechnete Spalten und einfache Measures.

In diesem Lab lernen Sie Folgendes:

- Erstellen berechneter Tabellen

- Erstellen berechneter Spalten

- Erstellen von Measures

### <a name="lab-story"></a>**Labszenario**

Dieses Lab ist eines von vielen in einer Reihe von Labs, die als fortlaufendes Szenario von der Datenvorbereitung bis zur Veröffentlichung als Berichte und Dashboards entworfen wurde. Sie können die Labs in beliebiger Reihenfolge abschließen. Wenn Sie jedoch beabsichtigen, mehrere Labs durchzuarbeiten, sollten Sie die ersten zehn Labs in der folgenden Reihenfolge absolvieren:

1. Vorbereiten von Daten in Power BI Desktop

2. Laden von Daten in Power BI Desktop

3. Modellieren von Daten in Power BI Desktop

5. **Erstellen von DAX-Berechnungen in Power BI Desktop, Teil 1**

6. Erstellen von DAX-Berechnungen in Power BI Desktop, Teil 2

7. Entwerfen eines Berichts in Power BI Desktop, Teil 1

8. Entwerfen eines Berichts in Power BI Desktop, Teil 2

9. Erstellen eines Power BI-Dashboards

10. Analysieren von Daten in Power BI Desktop

11. Erzwingen von Sicherheit auf Zeilenebene

## <a name="exercise-1-create-calculated-tables"></a>**Übung 1: Erstellen berechneter Tabellen**

In dieser Übung erstellen Sie zwei berechnete Tabellen. Die erste ist die Tabelle **Salesperson**, um eine direkte Beziehung zwischen ihr und der Tabelle **Sales** zu ermöglichen. Die zweite ist die Tabelle **Date**.

### <a name="task-1-get-started"></a>**Aufgabe 1: Erste Schritte**

In dieser Aufgabe richten Sie die Umgebung für das Lab ein.

*Wichtig: Wenn Sie nach einem vorherigen Lab fortfahren (und dieses Lab erfolgreich abgeschlossen haben), überspringen Sie diese Aufgabe und fahren mit der nächsten fort.*

1. Klicken Sie zum Öffnen von Power BI Desktop auf der Taskleiste auf die Verknüpfung „Microsoft Power BI Desktop“.

    ![Bild 50](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image1.png)

1. Um das Fenster „Erste Schritte“ zu schließen, klicken Sie links oben im Fenster auf das **X**.

    ![Bild 49](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image2.png)

1. Um die Startdatei für Power BI Desktop zu öffnen, klicken Sie auf die Registerkarte **Datei** des Menübands, um die Backstage-Ansicht zu öffnen.

1. Wählen Sie **Bericht öffnen** aus.

    ![Bild 48](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image3.png)

1. Klicken Sie auf **Berichte durchsuchen**.

    ![Bild 47](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image4.png)

1. Navigieren Sie im Fenster **Öffnen** zum Ordner **D:\PL300\Labs\04-create-dax-calculations-in-power-bi-desktop\Starter**.

1. Wählen Sie die Datei **Sales Analysis** aus.

1. Klicken Sie auf **Öffnen**.

    ![Bild 35](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image5.png)

1. Schließen Sie alle Informationsfenster, die möglicherweise geöffnet werden.

1. Um eine Kopie der Datei zu erstellen, klicken Sie auf die Registerkarte **Datei** des Menübands, um die Backstage-Ansicht zu öffnen.

1. Wählen Sie **Speichern unter** aus.

    ![Bild 34](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image6.png)

1. Wenn Sie aufgefordert werden, die Abfragen anzuwenden, klicken Sie auf **Anwenden**.

    ![Abbildung 25](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image7.png)

1. Navigieren Sie im Fenster **Speichern unter** zum Ordner **D:\PL300\MySolution**.

1. Klicken Sie auf **Speichern**.

    ![Bild 13](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image8.png)

### <a name="task-2-create-the-salesperson-table"></a>**Aufgabe 2: Erstellen der Tabelle „Salesperson“**

In dieser Aufgabe erstellen Sie die Tabelle **Salesperson** (direkte Beziehung zu **Sales**).

1. Klicken Sie in Power BI Desktop in der Berichtsansicht auf dem Menüband **Modellierung** in der Gruppe **Berechnungen** auf **Neue Tabelle**.

    ![Abbildung 1](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image9.png)

2. Geben Sie in die Bearbeitungsleiste (die beim Erstellen oder Bearbeiten von Berechnungen direkt unterhalb des Menübands geöffnet wird) **SalesPerson =** ein. Drücken Sie **UMSCHALT+EINGABE**, geben Sie **'SalesPerson (Performance)'** ein, und drücken Sie dann die **EINGABETASTE**.

    ![Bild 4](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image10.png)

    *Der Einfachheit halber können Sie alle DAX-Definitionen in diesem Lab aus den Codebeispielen in der Datei **D:\PL300\Labs\04-create-dax-calculations-in-power-bi-desktop\Assets\Snippets.txt** kopieren.*

    *Eine berechnete Tabelle wird erstellt, indem zuerst der Tabellenname eingegeben wird, gefolgt vom Gleichheitssymbol (=), gefolgt von einer DAX-Formel, die eine Tabelle zurückgibt. Beachten Sie, dass der Tabellenname nicht bereits im Datenmodell vorhanden sein darf.*

    *Die Bearbeitungsleiste unterstützt das Eingeben einer gültigen DAX-Formel. Sie bietet Features wie AutoVervollständigen, IntelliSense und Farbcodierung, mit denen Sie die Formel schnell und fehlerfrei eingeben können.*

    *Diese Tabellendefinition erstellt eine Kopie der Tabelle **Salesperson (Performance)** . Es werden nur die Daten kopiert. Eigenschaften wie Sichtbarkeit, Formatierung usw. werden jedoch nicht kopiert.*

    *Tipp: Es wird empfohlen, „Leerraum“ (d. h. Wagenrückläufe und Tabulatoren) einzugeben, um Formeln in einem intuitiven und einfach lesbaren Format zu gestalten, insbesondere bei langen und komplexen Formeln. Um einen Wagenrücklauf einzugeben, drücken Sie **UMSCHALT+EINGABETASTE**. Leerraum ist optional.*

3. Beachten Sie im Bereich **Felder**, dass das Tabellensymbol einen Blauton hat (zur Kennzeichnung einer berechneten Tabelle).

    ![Bild 10](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image11.png)

    *Berechnete Tabellen werden mithilfe einer DAX-Formel definiert, die eine Tabelle zurückgibt. Es ist wichtig zu verstehen, dass berechnete Tabellen das Datenmodell vergrößern, da sie Werte materialisieren und speichern. Sie werden immer dann neu berechnet, wenn die Formelabhängigkeiten aktualisiert werden, wie es in diesem Datenmodell der Fall sein wird, wenn neue (zukünftige) Datumswerte in Tabellen geladen werden.*

    *Im Gegensatz zu Power Query-Tabellen können berechnete Tabellen nicht zum Laden von Daten aus externen Datenquellen genutzt werden. Sie können Daten nur auf Grundlage dessen transformieren, was bereits in das Datenmodell geladen wurde.*

4. Wechseln Sie zur Ansicht „Modell“.

5. Beachten Sie, dass die Tabelle **Salesperson** verfügbar ist (wenn Sie in der Ansicht nicht zu sehen ist, scrollen Sie horizontal, um sie einzublenden).

6. Erstellen Sie eine Beziehung zwischen der Spalte **Salesperson \| EmployeeKey** und der Spalte **Sales \| EmployeeKey**.

7. Klicken Sie mit der rechten Maustaste auf die inaktive Beziehung zwischen den Tabellen **Salesperson (Performance)** und **Sales**, und wählen Sie **Löschen** aus.

    ![Abbildung 2](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image12.png)

8. Klicken Sie bei Aufforderung auf **OK**, um den Löschvorgang zu bestätigen.

    ![Bild 3](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image13.png)

9. Wählen Sie in der Tabelle **Salesperson** die folgenden Spalten zusammen aus, und blenden Sie sie dann aus (legen Sie die Eigenschaft **Ausgeblendet** auf **Ja** fest):

    - EmployeeID

    - EmployeeKey

    - UPN

10. Wählen Sie im Modelldiagramm die Tabelle **Salesperson** aus.

11. Geben Sie im Bereich **Eigenschaften** in das Feld **Beschreibung** Folgendes ein: **Salesperson related to Sales**

    *Denken Sie daran, dass die Beschreibungen als QuickInfo im Bereich **Felder** angezeigt werden, wenn Benutzer*innen den Cursor über eine Tabelle oder ein Feld bewegen.*

12. Legen Sie für die Tabelle **Salesperson (Performance)** die Beschreibung wie folgt fest: **Salesperson related to region(s)**

    *Das Datenmodell bietet zwei Alternativen bei der Analyse von Vertriebsmitarbeiter*innen. Die Tabelle **Salesperson** ermöglicht die Analyse der von einem Vertriebsmitarbeiter erzielten Umsätze, während die Tabelle **Salesperson (Performance)** die Analyse der Umsätze ermöglicht, die in den dem Vertriebsmitarbeiter zugewiesenen Vertriebsregionen erzielt wurden.*

### <a name="task-3-create-the-date-table"></a>**Aufgabe 3: Erstellen der Tabelle „Date“**

In dieser Aufgabe erstellen Sie die Tabelle **Date**.

1. Wechseln Sie zur Ansicht „Daten“.

    ![Bild 29](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image14.png)

2. Klicken Sie auf der Registerkarte **Start** des Menübands in der Gruppe **Berechnungen** auf **Neue Tabelle**.

    ![Bild 5](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image15.png)

3. Geben Sie auf der Formelleiste Folgendes ein:


    **DAX**


    ```
    Date =  
    CALENDARAUTO(6)
    ```


    ![Bild 6](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image16.png)

    
    *Die CALENDARAUTO()-Funktion gibt eine Tabelle mit einer einzigen Spalte mit Datumswerten zurück. Es werden automatisch alle Datumsspalten des Datenmodells durchsucht, um die im Datenmodell gespeicherten frühesten und spätesten Datumswerte zu ermitteln. Anschließend wird für jedes Datum innerhalb dieses Bereichs eine Zeile angelegt, wobei der Bereich in beide Richtungen erweitert wird, um sicherzustellen, dass Daten für vollständige Jahre gespeichert werden.*

    *Diese Funktion kann ein einzelnes optionales Argument verwenden, das die Zahl des letzten Monats eines Jahres ist. Falls weggelassen, ist der Wert 12, was bedeutet, dass Dezember der letzte Monat des Jahres ist. In diesem Fall wird „6“ eingegeben, was bedeutet, dass Juni der letzte Monat des Geschäftsjahres ist.*

4. Beachten Sie die Spalte mit Datumswerten.

    ![Bild 7](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image17.png)

    *Die gezeigten Datumsangaben sind mit US-amerikanischen Regionseinstellungen formatiert (d. h. MM/TT/JJJJ).*

5. Links unten auf der Statusleiste sehen Sie die Tabellenstatistik, die bestätigt, dass 1.826 Datenzeilen generiert wurden, was den Daten fünf vollständiger Jahre entspricht.

    ![Bild 9](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image18.png)

### <a name="task-4-create-calculated-columns"></a>**Aufgabe 4:** **Erstellen berechneter Spalten**

In dieser Aufgabe fügen Sie zusätzliche Spalten hinzu, um das Filtern und Gruppieren nach verschiedenen Zeiträumen zu ermöglichen. Sie erstellen auch eine berechnete Spalte, um die Sortierreihenfolge anderer Spalten zu steuern.

*Der Einfachheit halber können Sie alle DAX-Definitionen in diesem Lab aus den Codebeispielen in der Datei **D:\PL300\Labs\04-create-dax-calculations-in-power-bi-desktop\Assets\Snippets.txt** kopieren.*

1. Klicken Sie auf dem kontextbezogenen Menüband **Tabellentools** in der Gruppe **Berechnungen** auf **Neue Spalte**.

    ![Bild 11](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image19.png)

2. Geben Sie auf der Formelleiste Folgendes ein (oder kopieren Sie die Eingaben aus der Datei mit den Codeausschnitten), und drücken Sie dann die **EINGABETASTE**:


    **DAX**


    ```
    Year =
    "FY" & YEAR('Date'[Date]) + IF(MONTH('Date'[Date]) > 6, 1)
    ```


    *Eine berechnete Spalte wird erstellt, indem zuerst der Spaltenname eingegeben wird, gefolgt vom Gleichheitssymbol (=), gefolgt von einer DAX-Formel, die ein Ergebnis mit einem Wert zurückgibt. Der Spaltenname darf nicht bereits in der Tabelle vorhanden sein.*

    *Die Formel nutzt den Jahreswert des Datums, addiert jedoch 1 zum Jahreswert, wenn der Monat später als Juni ist. Auf diese Weise werden Geschäftsjahre bei Adventure Works berechnet.*

3. Vergewissern Sie sich, dass die neue Spalte hinzugefügt wurde.

    ![Bild 12](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image20.png)

4. Erstellen Sie mithilfe der Definitionen in der Codeausschnittsdatei die folgenden beiden berechneten Spalten für die Tabelle **Date**:

    - Quarter

    - Month

    ![Bild 14](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image21.png)

5. Um die Berechnungen zu überprüfen, wechseln Sie zur Ansicht „Bericht“.

6. Klicken Sie links unten auf das Plussymbol, um eine neue Berichtsseite zu erstellen.

    ![Bild 15](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image22.png)

7. Um der neuen Berichtsseite ein Matrixvisual hinzuzufügen, wählen Sie im Bereich **Visualisierungen** den Visualtyp der Matrix aus.

    *Tipp: Sie können den Cursor über jedes Symbol bewegen, um eine QuickInfo mit einer Beschreibung des Visualtyps anzuzeigen.*

    ![Bild 51](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image23.png)

8. Ziehen Sie im Bereich **Felder** aus der Tabelle **Date** das Feld **Year** in den Bereich **Zeilen**.

    ![Bild 17](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image24.png)

9. Ziehen Sie das Feld **Month** in den Bereich **Zeilen** direkt unter dem Feld **Year**.

    ![Bild 18](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image25.png)

10. Klicken Sie rechts oben im Matrixvisual (oder unten, je nach Position des Visuals) auf den gabelförmigen Doppelpfeil (damit werden alle Jahre um eine Ebene nach unten erweitert).

    ![Bild 19](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image26.png)

11. Beachten Sie, dass die Jahre zu Monaten aufgeklappt und dass die Monate nicht chronologisch, sondern alphabetisch sortiert sind.

    ![Bild 20](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image27.png)

    *Standardmäßig werden Textwerte alphabetisch, Zahlen vom kleinsten bis zum größten Wert und Datumsangaben vom frühesten bis zum spätesten Wert sortiert.*

12. Um die Sortierreihenfolge des Felds **Month** anzupassen, wechseln Sie zur Ansicht „Daten“.

13. Fügen Sie die Spalte **MonthKey** zur Tabelle **Date** hinzu.


    **DAX**


    ```
    MonthKey =
    (YEAR('Date'[Date]) * 100) + MONTH('Date'[Date])
    ```


    *Diese Formel berechnet für jede Kombination aus Jahr/Monat einen numerischen Wert.*

14. Vergewissern Sie sich in der Ansicht „Daten“, dass die neue Spalte numerische Werte enthält (z. B. 201707 für Juli 2017 usw.).

    ![Bild 21](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image28.png)

15. Wechseln Sie zurück zur Berichtsansicht.

16. Stellen Sie sicher, dass im Bereich **Felder** das Feld **Month** ausgewählt ist (falls ausgewählt, hat es einen dunkelgrauen Hintergrund).

17. Klicken Sie auf dem kontextbezogenen Menüband **Spaltentools** innerhalb der Gruppe **Sortieren** auf **Nach Spalte sortieren**, und wählen Sie dann **MonthKey** aus.

    ![Bild 22](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image29.png)

18. Beachten Sie im Matrixvisual, dass die Monate jetzt chronologisch sortiert sind.

    ![Bild 23](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image30.png)

### <a name="task-5-complete-the-date-table"></a>**Aufgabe 5:** **Vervollständigen der Tabelle „Date“**

In dieser Aufgabe vervollständigen Sie den Entwurf der Tabelle **Date**, indem Sie eine Spalte ausblenden und eine Hierarchie erstellen. Sie erstellen dann Beziehungen zu den Tabellen **Sales** und **Targets**.

1. Wechseln Sie zur Ansicht „Modell“.

2. Blenden Sie in der Tabelle **Date** die Spalte **MonthKey** aus (legen Sie **Ausgeblendet** auf **Ja** fest).

3. Wählen Sie im rechten Bereich **Felder** die Tabelle **Date** aus, klicken Sie mit der rechten Maustaste auf die Spalte **Year**, und wählen Sie **Hierarchie erstellen** aus. 

4. Benennen Sie die neu erstellte Hierarchie mit **Fiscal**, indem Sie mit der rechten Maustaste darauf klicken und **Umbenennen** auswählen. 
5. Fügen Sie der Hierarchie „Fiscal“ die folgenden beiden verbleibenden Felder hinzu, indem Sie sie im Bereich „Felder“ auswählen, mit der rechten Maustaste darauf klicken und **Zu Hierarchie hinzufügen** -> **Fiscal** auswählen.
    
    - Quarter

    - Month

    ![Bild 24](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image31.png)

6. Erstellen Sie die beiden folgenden Modellbeziehungen:

    - **Date \| Date** mit **Sales \| OrderDate**

    - **Date \| Date** mit **Targets \| TargetMonth**

7. Blenden Sie die folgenden beiden Spalten aus:

    - Sales \| OrderDate

    - Targets \| TargetMonth

### <a name="task-6-mark-the-date-table"></a>**Aufgabe 6: Markieren der Tabelle „Date“**

In dieser Aufgabe markieren Sie die Tabelle **Date** als Datumstabelle.

1. Wechseln Sie zur Ansicht „Bericht“.

2. Wählen Sie im Bereich **Felder** die Tabelle **Date** und nicht das Feld **Date** aus.

3. Klicken Sie auf dem kontextbezogenen Menüband **Tabellentools** innerhalb der Gruppe **Kalender** auf **Als Datumstabelle markieren**, und wählen Sie dann **Als Datumstabelle markieren** aus.

    ![Bild 8](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image32.png)

4. Wählen Sie im Fenster **Als Datumstabelle markieren** in der Dropdownliste **Datumsspalte** den Eintrag **Date** aus.

    ![Bild 37](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image33.png)

5. Klicken Sie auf **OK**.

    ![Abbildung 26](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image34.png)

6. Speichern Sie die Power BI Desktop-Datei.

    *Power BI Desktop versteht nun, dass diese Tabelle das Datum (die Uhrzeit) definiert. Dies ist wichtig, wenn Sie sich auf Berechnungen der Zeitintelligenz stützen. Im Lab **Erstellen von DAX-Berechnungen in Power BI Desktop, Teil 2** arbeiten Sie mit Zeitintelligenzberechnungen.*

    *Beachten Sie, dass dieser Entwurfsansatz für eine Datumstabelle geeignet ist, wenn in Ihrer Datenquelle keine Datumstabelle vorhanden ist. Wenn Sie ein Data Warehouse verwenden, wäre es angebracht, Datumsdaten aus dessen Datendimensionstabelle zu laden, anstatt die Datumslogik in Ihrem Datenmodell neu zu definieren.*

## <a name="exercise-2-create-measures"></a>**Übung 2: Erstellen von Measures**

In dieser Übung erstellen und formatieren Sie mehrere Measures.

### <a name="task-1-create-simple-measures"></a>**Aufgabe 1: Erstellen einfacher Measures**

In dieser Aufgabe erstellen Sie einfache Measures. Einfache Measures aggregieren Werte in einer einzelnen Spalte oder zählen die Zeilen einer Tabelle.

1. Ziehen Sie in der Berichtsansicht auf **Seite 2** im Bereich **Felder** das Feld **Sales \| Unit Price** in das Matrixvisual.

    *In den Labs wird eine verkürzte Notation verwendet, um auf ein Feld zu verweisen. Das sieht folgendermaßen aus: **Sales \| Unit Price**. In diesem Beispiel ist **Sales** der Tabellenname und **Unit Price** der Feldname.*

    ![Bild 27](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image35.png)

    *Im Lab **Modellieren von Daten in Power BI Desktop** haben Sie die Spalte **Unit Price** so festgelegt, dass sie nach **Durchschnitt** zusammengefasst wird. Das Ergebnis, das im Matrixvisual angezeigt wird, ist der durchschnittliche monatliche Einzelpreis (Summe der Einzelpreise dividiert durch die Anzahl der Einzelpreise).*

2. Beachten Sie, dass im Bereich der Visualfelder (unterhalb des Bereichs **Visualisierungen**) im Bereich **Werte** der **Unit Price** aufgeführt ist.

    ![Bild 28](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image36.png)

3. Klicken Sie auf den nach unten zeigenden Pfeil für **Unit Price**, und sehen Sie sich die verfügbaren Menüoptionen an.

    ![Bild 30](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image37.png)

    *Sichtbare numerische Spalten ermöglichen Berichtsautor*innen, zur Zeit der Berichtsgestaltung zu entscheiden, wie eine Spalte summiert wird (oder nicht). Dies kann zu einer ungeeigneten Berichterstellung führen. Einige Datenmodellierer*innen überlassen Dinge jedoch nicht gerne dem Zufall und entscheiden sich dafür, diese Spalten auszublenden und stattdessen eine durch Measures definierte Aggregationslogik verfügbar zu machen. Dies ist der Ansatz, den Sie nun in diesem Lab verfolgen.*

4. Um ein Measure zu erstellen, klicken Sie im Bereich **Felder** mit der rechten Maustaste auf die Tabelle **Sales**, und wählen Sie dann **Neues Measure** aus.

    ![Bild 31](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image38.png)

5. Fügen Sie in der Bearbeitungsleiste die folgende Measuredefinition hinzu:


    **DAX**


    ```
    Avg Price =  
    ‎AVERAGE(Sales[Unit Price])
    ```


6. Fügen Sie das Measure **Avg Price** dem Matrixvisual hinzu.

7. Beachten Sie, dass dadurch das gleiche Ergebnis wie in der Spalte **Unit Price** erzielt wird (jedoch mit anderer Formatierung).

8. Öffnen Sie im Well **Werte** das Kontextmenü für das Feld **Avg Price**, und beachten Sie, dass es nicht möglich ist, die Aggregationsmethode zu ändern.

    ![Bild 32](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image39.png)

    *Es ist nicht möglich, das Aggregationsverhalten eines Measure zu ändern.*

9. Erstellen Sie mithilfe der Definitionen in der Codeausschnittsdatei die folgenden fünf Measures für die Tabelle **Sales**:

    - Median Price

    - Min Price

    - Max Price

    - Orders

    - Order Lines

    *Die im Measure **Orders** verwendete DISTINCTCOUNT()-Funktion zählt Aufträge nur einmal (Duplikate werden ignoriert). Die im Measure **Order Lines** verwendete COUNTROWS()-Funktion wird auf eine Tabelle angewandt.*

    *In diesem Fall wird die Anzahl der Aufträge durch Zählen der eindeutigen Werte in der Spalte **SalesOrderNumber** berechnet, während die Anzahl der Auftragszeilen einfach die Anzahl der Tabellenzeilen ist (jede Zeile ist eine Auftragsposition).*

10. Wechseln Sie zur Ansicht „Modell“, und wählen Sie in einer Mehrfachauswahl die vier Measures für Preise aus: **Avg Price**, **Max Price**, **Median Price** und **Min Price**.

11. Konfigurieren Sie für die Mehrfachauswahl von Measures die folgenden Anforderungen:

    - Legen Sie das Format auf zwei Dezimalstellen fest.

    - Weisen Sie sie einem Anzeigeordner namens **Pricing** zu.

    ![Bild 33](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image40.png)

12. Blenden Sie die Spalte **Unit Price** aus.

    *Die Spalte **Unit Price** ist jetzt für Berichtsautor*innen nicht mehr verfügbar. Sie müssen die Preismeasuresverwenden, die Sie dem Modell hinzugefügt haben. Dieser Entwurfsansatz stellt sicher, dass Berichtsautor*innen die Preise nicht unsachgemäß aggregieren, z. B. durch Addition.*

13. Wählen Sie in einer Mehrfachauswahl die Measures **Order Lines** und **Orders** aus, und konfigurieren Sie dann die folgenden Anforderungen:

    - Legen Sie das Format so fest, dass Tausendertrennzeichen verwendet werden.

    - Weisen Sie sie einem Anzeigeordner namens **Counts** zu.

    ![Bild 36](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image41.png)

14. Klicken Sie in der Berichtsansicht im Bereich **Werte** des Matrixvisuals für das Feld **Unit Price** auf das **X**, um es zu entfernen.

    ![Bild 38](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image42.png)

15. Vergrößern Sie das Matrixvisual so, dass es die Seitenbreite und -höhe ausfüllt.

16. Fügen Sie dem Matrixvisual die folgenden fünf Measures hinzu:

    - Median Price

    - Min Price

    - Max Price

    - Orders

    - Order Lines

17. Vergewissern Sie sich, dass die Ergebnisse sinnvoll aussehen und ordnungsgemäß formatiert sind.

    ![Bild 39](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image43.png)

### <a name="task-2-create-additional-measures"></a>**Aufgabe 2: Erstellen zusätzlicher Measures**

In dieser Aufgabe erstellen Sie zusätzliche Measures, die komplexere Formeln verwenden.

1. Wählen Sie in der Ansicht „Bericht“ **Seite 1** aus.

    ![Bild 40](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image44.png)

2. Überprüfen Sie das Tabellenvisual, und beachten Sie dabei die Summe für die Spalte **Target**.

    ![Bild 41](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image45.png)

    

3. Wählen Sie das Tabellenvisual aus, und entfernen Sie dann im Bereich **Visualisierungen** das Feld **Ziel**.

    ![Bild 42](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image46.png)

4. Benennen Sie die Spalte **Targets \| Target** in **Targets \| TargetAmount** um.

    *Tipp: Es gibt mehrere Möglichkeiten, die Spalte in der Ansicht „Bericht“ umzubenennen: Im Bereich **Felder** können Sie mit der rechten Maustaste auf die Spalte klicken und dann **Umbenennen** auswählen. Alternativ können Sie auf die Spalte doppelklicken oder **F2** drücken.*

    *Sie sind im Begriff, ein Measure namens **Target** zu erstellen. In einer Tabelle ist es nicht möglich, dass eine Spalte und ein Measure denselben Namen haben.*

5. Erstellen Sie das folgende Measure für die Tabelle **Targets**:


    **DAX**


    ```
    Target =

    IF(

    HASONEVALUE('Salesperson (Performance)'[Salesperson]),

    SUM(Targets[TargetAmount])

    )
    ```


    *Die Funktion „HASONEVALUE()“ prüft, ob ein einzelner Wert in der Spalte **Salesperson** gefiltert wird. Falls TRUE, gibt der Ausdruck die Summe der Zielbeträge (für genau diesen Vertriebsmitarbeiter) zurück. Bei „false“ wird „BLANK“ zurückgegeben.*

6. Formatieren Sie das Measure **Target** ohne Dezimalstellen.

    *Tipp: Sie können das kontextbezogene Menüband **Measuretools** verwenden.*

7. Blenden Sie die Spalte **TargetAmount** aus.

    *Tipp: Im Bereich **Felder** können Sie mit der rechten Maustaste auf die Spalte klicken und dann **Ausblenden** auswählen.*

8. Fügen Sie das Measure **Target** dem Tabellenvisual hinzu.

9. Beachten Sie, dass die Gesamtsumme der Spalte **Target** jetzt BLANK ist.

    ![Bild 43](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image47.png)

10. Erstellen Sie mithilfe der Definitionen in der Codeausschnittsdatei die folgenden zwei Measures für die Tabelle **Targets**:

    - Variance

    - Variance Margin

11. Formatieren Sie das Measure **Variance** ohne Dezimalstellen.

12. Formatieren Sie das Measure **Variance Margin** als Prozentsatz mit zwei Dezimalstellen.

13. Fügen Sie die Measures **Variance** und **Variance Margin** zum Tabellenvisual hinzu.

14. Ändern Sie die Größe des Tabellenvisuals, sodass alle Spalten und Zeilen angezeigt werden.

    ![Bild 44](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image48.png)

    *Auch wenn es den Anschein hat, dass nicht alle Vertriebsmitarbeiter*innen die Zielvorgaben erfüllen, denken Sie daran, dass das Tabellenvisual noch nicht nach einem bestimmten Zeitraum gefiltert wurde. Sie erstellen Umsatzleistungsberichte, die nach einem von Benutzer*innen ausgewählten Zeitraum im Lab **Entwerfen eines Berichts in Power BI Desktop, Teil 1** filtern.*

15. Klappen Sie rechts oben im Bereich **Felder** den Bereich zu, und klappen Sie ihn dann auf.

    ![Bild 45](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image49.png)

    *Durch das Zuklappen und erneute Öffnen des Bereichs wird der Inhalt zurückgesetzt.*

16. Beachten Sie, dass die Tabelle **Targets** jetzt oben in der Liste steht.

    ![Bild 46](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image50.png)

    *Tabellen, die nur sichtbare Measures enthalten, werden automatisch am Anfang der Liste angezeigt.*

### <a name="task-3-finish-up"></a>**Aufgabe 3: Abschluss**

Mit dieser Aufgabe schließen Sie das Lab ab.

1. Speichern Sie die Power BI Desktop-Datei.

2. Wenn Sie beabsichtigen, das nächste Lab zu starten, lassen Sie Power BI Desktop geöffnet.

    *Im Lab **Erstellen von DAX-Berechnungen in Power BI Desktop, Teil 2** erweitern Sie das Datenmodell um weitere DAX-Berechnungen.*
