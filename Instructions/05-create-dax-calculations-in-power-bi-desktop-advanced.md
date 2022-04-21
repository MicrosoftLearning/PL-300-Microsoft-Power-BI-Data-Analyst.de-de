---
lab:
  title: Erstellen von DAX-Berechnungen in Power BI Desktop, Teil 2
  module: Module 5 - Create Model Calculations using DAX in Power BI
ms.openlocfilehash: 80cfdfcfcb2072277760670c549cebaaca434cb9
ms.sourcegitcommit: 3520e7d016e94549d408464207c1b91cd47867c2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2022
ms.locfileid: "139839306"
---
# <a name="create-dax-calculations-in-power-bi-desktop-part-2"></a>**Erstellen von DAX-Berechnungen in Power BI Desktop, Teil 2**

**Die geschätzte Dauer dieses Labs beträgt 45 Minuten.**

In diesem Lab erstellen Sie Measures mit DAX-Ausdrücken, die eine Änderung des Filterkontexts vorsehen.

In diesem Lab lernen Sie Folgendes:

- Ändern von Filtern mit der Funktion CALCULATE()

- Verwenden von Zeitintelligenzfunktionen

### <a name="lab-story"></a>**Labszenario**

Dieses Lab ist eines von vielen in einer Reihe von Labs, die als fortlaufendes Szenario von der Datenvorbereitung bis zur Veröffentlichung als Berichte und Dashboards entworfen wurde. Sie können die Labs in beliebiger Reihenfolge abschließen. Wenn Sie jedoch beabsichtigen, mehrere Labs durchzuarbeiten, sollten Sie die ersten zehn Labs in der folgenden Reihenfolge absolvieren:

1. Vorbereiten von Daten in Power BI Desktop

2. Laden von Daten in Power BI Desktop

3. Modellieren von Daten in Power BI Desktop

5. Erstellen von DAX-Berechnungen in Power BI Desktop, Teil 1

6. **Erstellen von DAX-Berechnungen in Power BI Desktop, Teil 2**

7. Entwerfen eines Berichts in Power BI Desktop, Teil 1

8. Entwerfen eines Berichts in Power BI Desktop, Teil 2

9. Erstellen eines Power BI-Dashboards

10. Analysieren von Daten in Power BI Desktop

11. Erzwingen von Sicherheit auf Zeilenebene

## <a name="exercise-1-work-with-filter-context"></a>**Übung 1: Arbeiten mit Filterkontext**

In dieser Übung erstellen Sie Measures mit DAX-Ausdrücken, die eine Änderung des Filterkontexts vorsehen.

### <a name="task-1-get-started"></a>**Aufgabe 1: Erste Schritte**

In dieser Aufgabe richten Sie die Umgebung für das Lab ein.

*Wichtig: Wenn Sie nach einem vorherigen Lab fortfahren (und dieses Lab erfolgreich abgeschlossen haben), überspringen Sie diese Aufgabe und fahren mit der nächsten fort.*

1. Klicken Sie zum Öffnen von Power BI Desktop auf der Taskleiste auf die Verknüpfung „Microsoft Power BI Desktop“.

    ![Bild 12](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image1.png)

1. Um das Fenster „Erste Schritte“ zu schließen, klicken Sie links oben im Fenster auf das **X**.

    ![Bild 11](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image2.png)

1. Um die Startdatei für Power BI Desktop zu öffnen, klicken Sie auf die Registerkarte **Datei** des Menübands, um die Backstage-Ansicht zu öffnen.

1. Wählen Sie **Bericht öffnen** aus.

    ![Bild 10](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image3.png)

1. Klicken Sie auf **Berichte durchsuchen**.

    ![Bild 9](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image4.png)

1. Navigieren Sie im Fenster **Öffnen** zum Ordner **D:\PL300\Labs\06-create-dax-calculations-in-power-bi-desktop-advanced\Starter**.

1. Wählen Sie die Datei **Sales Analysis** aus.

1. Klicken Sie auf **Öffnen**.

    ![Bild 8](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image5.png)

1. Schließen Sie alle Informationsfenster, die möglicherweise geöffnet werden.

1. Um eine Kopie der Datei zu erstellen, klicken Sie auf die Registerkarte **Datei** des Menübands, um die Backstage-Ansicht zu öffnen.

1. Wählen Sie **Speichern unter** aus.

    ![Bild 7](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image6.png)

1. Wenn Sie aufgefordert werden, die Abfragen anzuwenden, klicken Sie auf **Anwenden**.

    ![Bild 6](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image7.png)

1. Navigieren Sie im Fenster **Speichern unter** zum Ordner **D:\PL300\MySolution**.

1. Klicken Sie auf **Speichern**.

    ![Abbildung 2](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image8.png)

### <a name="task-2-create-a-matrix-visual"></a>**Aufgabe 2: Erstellen eines Matrixvisuals**

In dieser Aufgabe erstellen Sie ein Matrixvisual, um das Testen Ihrer neuen Measures zu unterstützen.

1. Erstellen Sie im Power BI Desktop in der Ansicht „Bericht“ eine neue Berichtsseite.

    ![Abbildung 1](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image9.png)

2. Fügen Sie auf **Seite 3** ein Matrixvisual hinzu.

    ![Bild 13](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image10.png)

3. Ändern Sie die Größe des Matrixvisuals so, dass es die gesamte Seite einnimmt.

4. Um die Felder des Matrixvisuals zu konfigurieren, ziehen Sie die Hierarchie **Region \| Regions** aus dem Bereich **Felder** in das Visual.

    *In den Labs wird eine verkürzte Notation verwendet, um auf ein Feld oder eine Hierarchie zu verweisen. Das sieht folgendermaßen aus: **Region \| Regions**. In diesem Beispiel ist **Region** der Tabellenname und **Regions** der Hierarchiename.*

5. Fügen Sie auch das Feld **Sales \| Sales** hinzu.

6. Um die gesamte Hierarchie aufzuklappen, klicken Sie rechts oben im Matrixvisual zweimal auf das gabelförmige Doppelpfeilsymbol.

    ![Bild 47](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image11.png)

    *Zur Erinnerung: Die Hierarchie **Regions** hat die Ebenen **Group**, **Country** und **Region**.*

7. Um das Visual zu formatieren, wählen Sie unter dem Bereich **Visualisierungen** den Bereich **Format** aus.

    ![Bild 14](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image12.png)

8. Geben Sie in das Feld **Suchen** den Begriff **Abgestuft** ein.

    ![Bild 15](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image13.png)

9. Legen Sie die Eigenschaft **Abgestuftes Layout** auf **Aus** fest.

    ![Bild 49](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image14.png)

10. Vergewissern Sie sich, dass das Matrixvisual jetzt vier Spaltenüberschriften hat.

    ![Bild 50](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image15.png)

    *Bei Adventure Works sind die Vertriebsregionen in Gruppen, Ländern und Regionen organisiert. Alle Länder mit Ausnahme der USA haben nur eine Region, die nach dem Land benannt ist. Da die USA ein derart großes Vertriebsgebiet sind, sind sie in fünf Vertriebsregionen unterteilt.*

    *In dieser Übung erstellen Sie mehrere Measures, und testen sie dann, indem Sie sie zum Matrixvisual hinzufügen.*

### <a name="task-3-manipulate-filter-context"></a>**Aufgabe 3: Ändern des Filterkontexts**

In dieser Aufgabe erstellen Sie mehrere Measures mit DAX-Ausdrücken, die den Filterkontext mithilfe der CALCULATE()-Funktion ändern.

1. Fügen Sie der Tabelle **Sales** ein Measure basierend auf dem folgenden Ausdruck hinzu:

    *Der Einfachheit halber können Sie alle DAX-Definitionen in diesem Lab aus der Datei **D:\PL300\Labs\06-create-dax-calculations-in-power-bi-desktop-advanced\Assets\Snippets.txt** kopieren.*


    **DAX**


    ```
    Sales All Region =

    CALCULATE(SUM(Sales[Sales]), REMOVEFILTERS(Region))
    ```


    *Die CALCULATE()-Funktion ist eine leistungsstarke Funktion zum Ändern des Filterkontexts. Das erste Argument verwendet einen Ausdruck oder ein Measure (ein Measure ist lediglich ein benannter Ausdruck). Nachfolgende Argumente ermöglichen das Ändern des Filterkontexts.*

    *Mit der REMOVEFILTERS()-Funktion werden aktive Filter entfernt. Sie kann entweder keine Argumente oder eine Tabelle, eine Spalte oder mehrere Spalten als Argument verwenden.*

    *In dieser Formel wertet das Measure die Summe der Spalte **Sales** in einem geänderten Filterkontext aus, der alle auf die Tabelle **Region** angewandten Filter entfernt.*

2. Fügen Sie dem Matrixvisual das Measure **Sales All Region** hinzu.

    ![Bild 52](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image16.png)

3. Beachten Sie, dass das Measure **Sales All Region** die Summe der Umsätze aller Regionen für jede Region, jedes Land (Zwischensumme) und jede Gruppe (Zwischensumme) berechnet.

    *Das neue Measure muss erst noch ein nützliches Ergebnis liefern. Wenn der Umsatz für eine Gruppe, ein Land oder eine Region durch diesen Wert geteilt wird, ergibt sich ein nützliches Verhältnis, das als „Prozent des Gesamtergebnisses“ bezeichnet wird.*

4. Stellen Sie sicher, dass im Bereich **Felder** das Measure **Sales All Region** ausgewählt ist (wenn es ausgewählt ist, weist es einen dunkelgrauen Hintergrund auf). Ersetzen Sie anschließend auf der Bearbeitungsleiste den Namen des Measures und die Formel durch folgende Formel:

    *Tipp: Um die vorhandene Formel zu ersetzen, kopieren Sie zuerst den Ausschnitt. Klicken Sie dann auf die Bearbeitungsleiste, und drücken Sie **STRG+A**, um den gesamten Text auszuwählen. Drücken Sie dann **STRG+V**, um den Ausschnitt einzufügen und den markierten Text zu überschreiben. Drücken Sie anschließend die **EINGABETASTE**.*


    **DAX**


    ```
    Sales % All Region =  
    ‎DIVIDE(  
    ‎ SUM(Sales[Sales]),  
    ‎ CALCULATE(  
    ‎ SUM(Sales[Sales]),  
    ‎ REMOVEFILTERS(Region)  
    ‎ )  
    ‎)
    ```


    *Das Measure wurde so umbenannt, dass es die aktualisierte Formel genau wiedergibt. Die DIVIDE()-Funktion teilt das Measure **Sales** (nicht durch Filterkontext modifiziert) durch das Measure **Sales** in einem modifizierten Kontext, der alle auf die Tabelle **Region** angewandten Filter entfernt.*

5. Beachten Sie im Matrixvisual, dass das Measure umbenannt wurde und dass jetzt für jede Gruppe, jedes Land und jede Region andere Werte angezeigt werden.

6. Formatieren Sie das Measure **Sales % All Region** als Prozentsatz mit zwei Dezimalstellen.

7. Überprüfen Sie im Matrixvisual die Werte des Measures **Sales % All Region**.

    ![Bild 53](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image17.png)

8. Fügen Sie der Tabelle **Sales** ein weiteres Measure basierend auf dem folgenden Ausdruck hinzu, und formatieren Sie es als Prozentsatz:


    **DAX**

    ```
    Sales % Country =  
    ‎DIVIDE(  
    ‎ SUM(Sales[Sales]),  
    ‎ CALCULATE(  
    ‎ SUM(Sales[Sales]),  
    ‎ REMOVEFILTERS(Region[Region])  
    ‎ )  
    ‎)
    ```


9. Beachten Sie, dass sich die Formel des Measures **Sales % Country** geringfügig von der Formel des Measures **Sales % All Region** unterscheidet.

    *Der Unterschied besteht darin, dass der Nenner den Filterkontext durch Entfernen von Filtern für die Spalte **Region** in der Tabelle **Region** und nicht für alle Spalten in der Tabelle **Region** ändert. Das bedeutet, dass alle Filter, die auf die Gruppen- oder Länderspalten angewendet wurden, erhalten bleiben. Dadurch wird ein Ergebnis erzielt, das den Umsatz als Prozentsatz des Lands darstellt.*

10. Fügen Sie das Measure **Sales % Country** zum Matrixvisual hinzu.

11. Beachten Sie, dass nur die Regionen der USA einen Wert aufweisen, der nicht 100 % beträgt.

    ![Bild 54](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image18.png)

    *Denken Sie daran, dass nur die USA mehrere Regionen haben. Alle anderen Länder haben eine einzige Region, was bei allen das Ergebnis von 100 % erklärt.*

12. Um die Lesbarkeit dieses Measures im Visual zu verbessern, überschreiben Sie das Measure **Sales % Country** durch diese verbesserte Formel.


    **DAX**


    ```
    Sales % Country =  
    ‎IF(  
    ‎ ISINSCOPE(Region[Region]),  
    ‎ DIVIDE(  
    ‎ SUM(Sales[Sales]),  
    ‎ CALCULATE(  
    ‎ SUM(Sales[Sales]),  
    ‎ REMOVEFILTERS(Region[Region])  
    ‎ )  
    ‎ )  
    ‎)
    ```


    *Die in die IF()-Funktion eingebettete ISINSCOPE()-Funktion dient zum Testen, ob die Spalte „Region“ die Ebene in einer Ebenenhierarchie ist. Falls TRUE, wird die DIVIDE()-Funktion ausgewertet. Das Fehlen eines FALSE-Teils bedeutet, dass BLANK zurückgegeben wird, wenn die Spalte „Region“ nicht im Geltungsbereich liegt.*

13. Beachten Sie, dass das Measure **Sales % Country** jetzt nur dann einen Wert zurückgibt, wenn eine Region im Geltungsbereich liegt.

    ![Bild 55](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image19.png)

14. Fügen Sie der Tabelle **Sales** ein weiteres Measure basierend auf dem folgenden Ausdruck hinzu, und formatieren Sie es als Prozentsatz:


    **DAX**


    ```
    Sales % Group =  
    ‎DIVIDE(  
    ‎ SUM(Sales[Sales]),  
    ‎ CALCULATE(  
    ‎ SUM(Sales[Sales]),  
    ‎ REMOVEFILTERS(  
    ‎ Region[Region],  
    ‎ Region[Country]  
    ‎ )  
    ‎ )  
    ‎)
    ```


    *Um den Umsatz als Prozentsatz der Gruppe zu erreichen, können zwei Filter angewendet werden, um die Filter für zwei Spalten effektiv zu entfernen.*

15. Fügen Sie das Measure **Sales % Group** zum Matrixvisual hinzu.

16. Um die Lesbarkeit dieses Measures im Visual zu verbessern, überschreiben Sie das Measure **Sales % Group** durch diese verbesserte Formel.


    **DAX**


    ```
    Sales % Group =  
    ‎IF(  
    ‎ ISINSCOPE(Region[Region])  
    ‎ || ISINSCOPE(Region[Country]),  
    ‎ DIVIDE(  
    ‎ SUM(Sales[Sales]),  
    ‎ CALCULATE(  
    ‎ SUM(Sales[Sales]),  
    ‎ REMOVEFILTERS(  
    ‎ Region[Region],  
    ‎ Region[Country]  
    ‎ )  
    ‎ )  
    ‎ )  
    ‎)
    ```


17. Beachten Sie, dass das Measure **Sales % Group** jetzt nur dann einen Wert zurückgibt, wenn eine Region oder ein Land im Geltungsbereich liegt.

18. Legen Sie in der Ansicht „Modell“ die drei neuen Measures in einem Anzeigeordner mit dem Namen **Ratios** ab.

    ![Bild 56](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image20.png)

19. Speichern Sie die Power BI Desktop-Datei.

    *Die der Tabelle **Sales** hinzugefügten Measures haben den Filterkontext so geändert, dass eine hierarchische Navigation ermöglicht wird. Beachten Sie, dass das Muster zur Berechnung einer Zwischensumme das Entfernen einiger Spalten aus dem Filterkontext erfordert. Um eine Gesamtsumme zu erhalten, müssen alle Spalten entfernt werden.*

## <a name="exercise-2-work-with-time-intelligence"></a>**Übung 2: Arbeiten mit Zeitintelligenz**

In dieser Übung erstellen Sie ein Measure für den Umsatz seit Jahresbeginn (Year-to-Date, YTD) und eines für das Umsatzwachstum von Jahr zu Jahr (Year-over-Year, YoY).

### <a name="task-1-create-a-ytd-measure"></a>**Aufgabe 1: Erstellen eines YTD-Measures**

In dieser Aufgabe erstellen Sie ein YTD-Measure für den Umsatz.

1. Beachten Sie in der Berichtsansicht auf **Seite 2** das Matrixvisual, in dem verschiedene Measures mit Jahren und Monaten in den Zeilen gruppiert dargestellt sind.

2. Fügen Sie der Tabelle **Sales** ein Measure hinzu, das auf dem folgenden Ausdruck basiert und ohne Dezimalstellen formatiert ist:


    **DAX**


    ```
    Sales YTD =  
    ‎TOTALYTD(SUM(Sales[Sales]), 'Date'[Date], "6-30")
    ```


    *Die TOTALYTD()-Funktion wertet einen Ausdruck aus – in diesem Fall die Summe der Spalte **Sales** für eine bestimmte Datumsspalte. Die Datumsspalte muss zu einer Datumstabelle gehören, die als Datumstabelle gekennzeichnet ist, wie im Lab **Erstellen von DAX-Berechnungen in Power BI Desktop, Teil 1**.*

    *Die Funktion kann auch ein drittes optionales Argument verwenden, das das letzte Datum eines Jahres darstellt. Das Fehlen dieses Datums bedeutet, dass der 31. Dezember das letzte Datum des Jahres ist. Bei Adventure Works ist der Juni der letzte Monat des Geschäftsjahres, weshalb „6-30“ verwendet wird.*

3. Fügen Sie das Feld **Sales** und das Measure **Sales YTD** zum Matrixvisual hinzu.

4. Beachten Sie die Akkumulation der Umsatzwerte innerhalb des Jahres.

    ![Bild 59](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image21.png)

    *Die TOTALYTD()-Funktion nimmt Filteränderungen vor, insbesondere Zeitfilteränderungen. Um beispielsweise den YTD-Umsatz für September 2017 (den dritten Monat des Geschäftsjahres) zu berechnen, werden alle Filter für die Tabelle **Date** entfernt und durch einen neuen Datumsfilter ersetzt, der mit dem Jahresanfang (1. Juli 2017) beginnt und sich bis zum letzten Datum des kontextbezogenen Datumsbereichs (30. September 2017) erstreckt.*

    *Beachten Sie, dass in DAX viele Zeitintelligenzfunktionen verfügbar sind, um gängige Zeitfilteränderungen zu unterstützen.*

### <a name="task-2-create-a-yoy-growth-measure"></a>**Aufgabe 2: Erstellen eines YoY-Measures des Umsatzwachstums**

In dieser Aufgabe erstellen Sie ein YoY-Measure des Umsatzwachstums.

1. Fügen Sie der Tabelle **Sales** ein weiteres Measure basierend auf dem folgenden Ausdruck hinzu:


    **DAX**


    ```
    Sales YoY Growth =  
    ‎VAR SalesPriorYear =  
    ‎ CALCULATE(  
    ‎ SUM(Sales[Sales]),  
    ‎ PARALLELPERIOD(  
    ‎ 'Date'[Date],  
    ‎ -12,  
    ‎ MONTH  
    ‎ )  
    ‎ )  
    ‎RETURN  
    ‎ SalesPriorYear
    ```


    *Das Formelmeasure **Sales YoY Growth** deklariert eine Variable. Variablen können nützlich sein, um die Formellogik zu vereinfachen, und effizienter, wenn ein Ausdruck mehrfach innerhalb der Formel ausgewertet werden muss (was bei der Logik des YoY-Wachstums der Fall ist). Variablen werden mit einem eindeutigen Namen deklariert. Der Measureausdruck muss nach dem Schlüsselwort **RETURN** ausgegeben werden.*

    *Der Variable **SalesPriorYear** ist ein Ausdruck zugewiesen, der die Summe der Spalte **Sales** in einem modifizierten Kontext berechnet. Dabei wird die PARALLELPERIOD()-Funktion verwendet, um bei jedem Datum im Filterkontext eine Verschiebung zurück um 12 Monate vorzunehmen.*

2. Fügen Sie das Measure **Sales YoY Growth** zum Matrixvisual hinzu.

3. Beachten Sie, dass das neue Measure für die ersten 12 Monate BLANK zurückgibt (vor dem Geschäftsjahr 2017 wurden keine Umsätze verzeichnet).

4. Beachten Sie, dass der Wert des Measures **Sales YoY Growth** für **Juli 2018** der Wert von **Sales** für **Juli 2017** ist.

    ![Bild 61](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image22.png)

    *Nachdem nun der „schwierige Teil“ der Formel getestet wurde, können Sie das Measure mit der endgültigen Formel überschreiben, die das Wachstumsergebnis berechnet.*

5. Um das Measure zu vervollständigen, überschreiben Sie das Measure **Sales YoY Growth** mit dieser Formel und formatieren es als Prozentsatz mit zwei Dezimalstellen:


    **DAX**


    ```
    Sales YoY Growth =  
    ‎VAR SalesPriorYear =  
    ‎ CALCULATE(  
    ‎ SUM(Sales[Sales]),  
    ‎ PARALLELPERIOD(  
    ‎ 'Date'[Date],  
    ‎ -12,  
    ‎ MONTH  
    ‎ )  
    ‎ )  
    ‎RETURN  
    ‎ DIVIDE(  
    ‎ (SUM(Sales[Sales]) - SalesPriorYear),  
    ‎ SalesPriorYear  
    ‎ )
    ```


6. Beachten Sie, dass in der Formel in der **RETURN**-Klausel zweimal auf die Variable verwiesen wird.

7. Vergewissern Sie sich, dass für **Juli 2018** das YoY-Wachstum **392,83 %** beträgt.

    ![Bild 62](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image23.png)

    *Dies bedeutet, dass der Umsatz im Juli 2018 (2.411.559 US-Dollar) einer fast 400 %igen (fast vierfachen) Verbesserung gegenüber dem Umsatz des Vorjahres (489.328 US-Dollar) gleichkommt.*

8. Legen Sie in der Ansicht „Modell“ die beiden neuen Measures in einen Anzeigeordner mit dem Namen **Time Intelligence** ab.

    ![Bild 63](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image24.png)

### <a name="task-3-finish-up"></a>**Aufgabe 3: Abschluss**

Mit dieser Aufgabe schließen Sie das Lab ab.

1. Klicken Sie links unten mit der rechten Maustaste auf die Registerkarte **Seite 2**, und klicken Sie dann auf **Seite löschen**, um die Lösung zu bereinigen, sodass sie für die Berichtsentwicklung bereit ist.

    ![Bild 17](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image25.png)

2. Wenn Sie aufgefordert werden, die Seite zu löschen, klicken Sie auf **Löschen**.

    ![Bild 18](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image26.png)

3. Löschen Sie ebenfalls **Seite 3**.

4. Wählen Sie zum Löschen der Seite auf der verbleibenden Seite das Tabellenvisual aus, und drücken Sie die Taste **ENTF**.

5. Speichern Sie die Power BI Desktop-Datei.

6. Wenn Sie beabsichtigen, das nächste Lab zu starten, lassen Sie Power BI Desktop geöffnet.

    *Sie erstellen einen Bericht auf der Grundlage des Datenmodells im Lab **Entwerfen eines Berichts in Power BI Desktop, Teil 1**.*
