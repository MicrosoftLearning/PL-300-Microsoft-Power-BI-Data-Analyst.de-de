---
lab:
  title: Entwerfen eines Berichts in Power BI Desktop, Teil 1
  module: Module 7 - Create Reports
ms.openlocfilehash: 9aa794d25d2eb2ec611315a7ec6ac472e9a3a141
ms.sourcegitcommit: 3520e7d016e94549d408464207c1b91cd47867c2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2022
ms.locfileid: "139839528"
---
# <a name="design-a-report-in-power-bi-desktop-part-1"></a>**Entwerfen eines Berichts in Power BI Desktop, Teil 1**

**Die geschätzte Dauer dieses Labs beträgt 45 Minuten.**

In diesem Lab erstellen Sie einen dreiseitigen Bericht. Danach veröffentlichen Sie ihn in Power BI, um ihn anschließend zu öffnen und mit ihm zu interagieren.

In diesem Lab lernen Sie Folgendes:

- Entwerfen eines Berichts

- Konfigurieren von Feldern und Formatierungseigenschaften für Visuals

### <a name="lab-story"></a>**Labszenario**

Dieses Lab ist eines von vielen in einer Reihe von Labs, die als fortlaufendes Szenario von der Datenvorbereitung bis zur Veröffentlichung als Berichte und Dashboards entworfen wurde. Sie können die Labs in beliebiger Reihenfolge abschließen. Wenn Sie jedoch beabsichtigen, mehrere Labs durchzuarbeiten, sollten Sie die ersten zehn Labs in der folgenden Reihenfolge absolvieren:

1. Vorbereiten von Daten in Power BI Desktop

2. Laden von Daten in Power BI Desktop

3. Modellieren von Daten in Power BI Desktop

5. Erstellen von DAX-Berechnungen in Power BI Desktop, Teil 1

6. Erstellen von DAX-Berechnungen in Power BI Desktop, Teil 2

7. **Entwerfen eines Berichts in Power BI Desktop, Teil 1**

8. Entwerfen eines Berichts in Power BI Desktop, Teil 2

9. Erstellen eines Power BI-Dashboards

10. Analysieren von Daten in Power BI Desktop

11. Erzwingen von Sicherheit auf Zeilenebene

## <a name="exercise-1-create-a-report"></a>**Übung 1: Erstellen eines Berichts**

In dieser Übung erstellen Sie einen dreiseitigen Bericht mit dem Namen **Sales Report** (Verkaufsbericht).

### <a name="task-1-get-started--sign-in"></a>**Aufgabe 1: Erste Schritte – Anmelden**

In dieser Aufgabe richten Sie die Umgebung für das Lab ein, indem Sie sich bei Power BI anmelden.

*Wichtig: Wenn Sie sich bereits bei Power BI angemeldet haben, fahren Sie mit der nächsten Aufgabe fort.*

1. Klicken Sie zum Öffnen von Microsoft Edge auf der Taskleiste auf die Programmverknüpfung für Microsoft Edge.

    ![Bild 65](Linked_image_Files/07-design-report-in-power-bi-desktop_image1.png)

1. Navigieren Sie im Browserfenster von Microsoft Edge zu **https://powerbi.com**.

    *Tipp: Sie können auch auf der Favoritenleiste von Microsoft Edge die Option für den Power BI-Dienst verwenden.*

1. Klicken Sie auf **Anmelden** (in der rechten oberen Ecke).

    ![Bild 63](Linked_image_Files/07-design-report-in-power-bi-desktop_image2.png)

1. Geben Sie die für Sie bereitgestellten Kontodetails ein (siehe **Ressourcen**).

1. Wenn Sie aufgefordert werden, das Kennwort zu aktualisieren, geben Sie das bereitgestellte Kennwort erneut ein, und geben Sie dann das neue Kennwort zweimal zur Bestätigung ein.

    *Wichtig: Denken Sie daran, sich das neue Kennwort zu notieren.*

1. Schließen Sie den Anmeldevorgang ab.

1. Wenn Sie von Microsoft Edge gefragt werden, ob Sie angemeldet bleiben möchten, klicken Sie auf **Ja**.

1. Lassen Sie das Browserfenster von Microsoft Edge geöffnet.

### <a name="task-2-get-started--enable-map-and-filled-map-visuals"></a>**Aufgabe 2: Erste Schritte – Aktivieren von Karten- und Flächenkartogrammvisuals**

In dieser Aufgabe aktivieren Sie Karten- und Flächenkartogrammvisuals in der Umgebung für das Lab, indem Sie die Integrationseinstellungen im Verwaltungsportal von Power BI aktualisieren. 


1. Um das Verwaltungsportal von Power BI zu öffnen, klicken Sie rechts oben im Browser auf das Symbol **Einstellungen**.

    ![Bild 101](Linked_image_Files/07-design-report-in-power-bi-desktop_image101.png)

1. Wählen Sie **Verwaltungsportal** aus.

    ![Bild 102](Linked_image_Files/07-design-report-in-power-bi-desktop_image102.png)

1. Scrollen Sie auf der Seite nach unten zu den Integrationseinstellungen. Klicken Sie auf den Pfeil, um die Option für Karten- und Flächenkartogrammvisuals zu erweitern.

    ![Bild 103](Linked_image_Files/07-design-report-in-power-bi-desktop_image103.png)

1. Legen Sie die Option für Karten- und Flächenkartogrammvisuals auf **Aktiviert** fest.

1. Klicken Sie auf **Übernehmen**, um die Änderungen anzuwenden. 

    ![Bild 104](Linked_image_Files/07-design-report-in-power-bi-desktop_image104.png)

1. Rechts oben im Browser wird eine Meldung mit dem Hinweis angezeigt, dass die Änderungen an den Mandanteneinstellungen innerhalb der nächsten 15 Minuten angewandt werden. 


    ![Bild 105](Linked_image_Files/07-design-report-in-power-bi-desktop_image105.png)



1. Lassen Sie das Browserfenster von Microsoft Edge geöffnet.

### <a name="task-3-get-started--open-report"></a>**Aufgabe 3: Erste Schritte – Öffnen des Berichts**

In dieser Aufgabe richten Sie die Umgebung für das Lab ein, indem Sie den Starterbericht öffnen.

*Wichtig: Wenn Sie nach einem vorherigen Lab fortfahren (und dieses Lab erfolgreich abgeschlossen haben), überspringen Sie diese Aufgabe und fahren mit der nächsten fort.*

1. Klicken Sie zum Öffnen von Power BI Desktop auf der Taskleiste auf die Verknüpfung „Microsoft Power BI Desktop“.

    ![Bild 48](Linked_image_Files/07-design-report-in-power-bi-desktop_image3.png)

2. Um das Fenster „Erste Schritte“ zu schließen, klicken Sie links oben im Fenster auf das **X**.

    ![Bild 47](Linked_image_Files/07-design-report-in-power-bi-desktop_image4.png)

3. Klicken Sie rechts oben auf **Anmelden**, um sich beim Power BI-Dienst anzumelden.

    ![Bild 66](Linked_image_Files/07-design-report-in-power-bi-desktop_image5.png)

4. Schließen Sie den Anmeldevorgang mit demselben Konto ab, das Sie für die Anmeldung beim Power BI-Dienst verwendet haben.

5. Um die Startdatei für Power BI Desktop zu öffnen, klicken Sie auf die Registerkarte **Datei** des Menübands, um die Backstage-Ansicht zu öffnen.

6. Wählen Sie **Bericht öffnen** aus.

    ![Bild 31](Linked_image_Files/07-design-report-in-power-bi-desktop_image6.png)

7. Klicken Sie auf **Berichte durchsuchen**.

    ![Bild 30](Linked_image_Files/07-design-report-in-power-bi-desktop_image7.png)

8. Navigieren Sie im Fenster **Öffnen** zum Ordner **D:\PL300\Labs\07-design-report-in-power-bi-desktop\Starter**.

9. Wählen Sie die Datei **Sales Analysis** aus.

10. Klicken Sie auf **Öffnen**.

    ![Bild 16](Linked_image_Files/07-design-report-in-power-bi-desktop_image8.png)

11. Schließen Sie alle Informationsfenster, die möglicherweise geöffnet werden.

12. Um eine Kopie der Datei zu erstellen, klicken Sie auf die Registerkarte **Datei** des Menübands, um die Backstage-Ansicht zu öffnen.

13. Wählen Sie **Speichern unter** aus.

    ![Bild 8](Linked_image_Files/07-design-report-in-power-bi-desktop_image9.png)

14. Wenn Sie aufgefordert werden, die Abfragen anzuwenden, klicken Sie auf **Anwenden**.

    ![Bild 5](Linked_image_Files/07-design-report-in-power-bi-desktop_image10.png)

15. Navigieren Sie im Fenster **Speichern unter** zum Ordner **D:\PL300\MySolution**.

16. Klicken Sie auf **Speichern**.

    ![Bild 4](Linked_image_Files/07-design-report-in-power-bi-desktop_image11.png)

### <a name="task-4-design-page-1"></a>**Aufgabe 4: Entwerfen der ersten Seite**

In dieser Aufgabe wird die erste Berichtsseite entworfen. Nach der Fertigstellung des Entwurfs sieht die Seite wie folgt aus:

![Abbildung der ersten Seite, bestehend aus einem Logo, zwei Slicern und drei Visuals](Linked_image_Files/07-design-report-in-power-bi-desktop_image12.png)

1. Klicken Sie in Power BI Desktop zum Umbenennen der Seite links unten mit der rechten Maustaste auf **Seite 1**, und wählen Sie dann **Umbenennen** aus.

    ![Bild 36](Linked_image_Files/07-design-report-in-power-bi-desktop_image13.png)

    *Tipp: Sie können auch auf den Seitennamen doppelklicken, um die Seite umzubenennen.*

2. Benennen Sie die Seite in **Overview** (Übersicht) um, und drücken Sie die **EINGABETASTE**.

    ![Bild 37](Linked_image_Files/07-design-report-in-power-bi-desktop_image14.png)

3. Klicken Sie zum Hinzufügen eines Bilds auf der Registerkarte **Einfügen** des Menübands in der Gruppe **Elemente** auf **Bild**.

    ![Abbildung 1](Linked_image_Files/07-design-report-in-power-bi-desktop_image15.png)

4. Navigieren Sie im Fenster **Öffnen** zum Ordner **D:\PL300\Resources**.

5. Wählen Sie die Datei **AdventureWorksLogo.jpg** aus, und klicken Sie anschließend auf **Öffnen**.

    ![Bild 11](Linked_image_Files/07-design-report-in-power-bi-desktop_image16.png)

6. Ziehen Sie das Bild, um es in der linken oberen Ecke zu positionieren, und ziehen Sie auch die Führungslinienmarkierungen, um die Größe zu ändern.

    ![Bild 12](Linked_image_Files/07-design-report-in-power-bi-desktop_image17.png)

7. Heben Sie zum Hinzufügen eines Datenschnitts zunächst die Auswahl des Bilds auf, indem Sie auf einen leeren Bereich der Berichtsseite klicken.
8. Wählen Sie im Bereich **Felder** das Feld **Date \| Year** aus (nicht die Ebene **Year** der Hierarchie).
    
    *In den Labs wird eine verkürzte Notation verwendet, um auf ein Feld zu verweisen. Das sieht folgendermaßen aus: **Date \| Year**. In diesem Beispiel ist **Date** der Tabellenname und **Year** der Feldname.*

9. Wie Sie sehen, wurde der Berichtsseite eine Tabelle mit Jahreswerten hinzugefügt.

10. Wenn Sie das Visual von einer Tabelle in einen Datenschnitt konvertieren möchten, wählen Sie im Bereich **Visualisierungen** die Option **Datenschnitt** aus.

    ![Bild 49](Linked_image_Files/07-design-report-in-power-bi-desktop_image18.png)

11. Wenn Sie den Datenschnitt von einer Liste in ein Dropdownfeld konvertieren möchten, klicken Sie in der rechten oberen Ecke des Datenschnitts auf den Abwärtspfeil, und wählen Sie **Dropdown** aus.

    ![Bild 18](Linked_image_Files/07-design-report-in-power-bi-desktop_image19.png)

12. Ändern Sie Größe und Position des Slicers so, dass er sich unter dem Bild befindet und die gleiche Breite wie das Bild hat.

    ![Bild 19](Linked_image_Files/07-design-report-in-power-bi-desktop_image20.png)

13. Öffnen Sie die Dropdownliste im Slicer **Year**, wählen Sie **FY2020** aus, und klappen Sie die Dropdownliste dann zu.

    ![Bild 20](Linked_image_Files/07-design-report-in-power-bi-desktop_image21.png)

    *Die Berichtsseite wird nun nach dem Jahr **FY2020** gefiltert.*

14. Heben Sie die Auswahl des Datenschnitts auf, indem Sie auf einen leeren Bereich der Berichtsseite klicken.

15. Erstellen Sie einen zweiten Slicer auf der Grundlage des Felds **Region \| Region** (nicht auf der Grundlage der Hierarchieebene **Region**).

16. Behalten Sie das Listenformat des Slicers bei, und ändern Sie Größe und Position so, dass sich der Slicer unter dem Slicer **Year** befindet.

    ![Bild 21](Linked_image_Files/07-design-report-in-power-bi-desktop_image22.png)

17. Öffnen Sie zum Formatieren des Datenschnitts unter dem Bereich **Visualisierungen** den Bereich **Format**.

    ![Bild 50](Linked_image_Files/07-design-report-in-power-bi-desktop_image23.png)

18. Erweitern Sie dann die Gruppe **Selection Controls** (Auswahlsteuerelemente).

    ![Bild 23](Linked_image_Files/07-design-report-in-power-bi-desktop_image24.png)

19. Legen Sie **Option „Alles auswählen“ anzeigen** auf **Ein** fest.

    ![Bild 24](Linked_image_Files/07-design-report-in-power-bi-desktop_image25.png)

20. Wie Sie sehen, ist das erste Element im Datenschnitt **Region** jetzt **Alles auswählen**.

    *Wenn diese Option ausgewählt ist, werden entweder alle Elemente ausgewählt, oder die Auswahl aller Elemente wird aufgehoben. Dadurch können Berichtsbenutzer*innen einfacher die passenden Filter festlegen.*

21. Heben Sie die Auswahl des Datenschnitts auf, indem Sie auf einen leeren Bereich der Berichtsseite klicken.

22. Klicken Sie im Bereich **Visualisierungen** auf den Visualtyp **Linien- und gestapeltes Säulendiagramm**, um der Seite ein Diagramm hinzuzufügen.

    ![Bild 51](Linked_image_Files/07-design-report-in-power-bi-desktop_image26.png)

23. Ändern Sie Größe und Position des Visuals so, dass es sich rechts neben dem Logo befindet und über die Breite der Berichtsseite erstreckt.

    ![Abbildung 26](Linked_image_Files/07-design-report-in-power-bi-desktop_image27.png)

24. Ziehen Sie die folgenden Felder per Drag & Drop in das Visual:

    - Date \| Month

    - Sales \| Sales

25. Im Feldbereich des Visuals (nicht im Bereich **Felder**; der Feldbereich des Visuals befindet sich unter dem Bereich **Visualisierungen**) sehen Sie, dass die Felder den Bereichen **Gemeinsame Achse** und **Spaltenwerte** zugewiesen sind.

    ![Bild 27](Linked_image_Files/07-design-report-in-power-bi-desktop_image28.png)

    *Wenn Sie Felder in ein Visual ziehen, werden sie den Standardbereichen hinzugefügt. Sie können Felder wie im nächsten Schritt auch direkt in die Bereiche ziehen, um eine höhere Genauigkeit zu erzielen.*

26. Ziehen Sie im Bereich **Felder** das Feld **Sales \| Profit Margin** in den Bereich **Zeilenwerte**.

    ![Bild 28](Linked_image_Files/07-design-report-in-power-bi-desktop_image29.png)

27. Beachten Sie, dass das Visual nur 11 Monate umfasst.

    *Für den letzten Monat des Jahres (Juni 2020) liegen noch keine Verkäufe vor. Monate OHNE Verkaufszahlen werden vom Visual standardmäßig entfernt. Im nächsten Schritt wird das Visual so konfiguriert, dass alle Monate angezeigt werden.*

28. Klicken Sie im Feldbereich des Visuals im Bereich **Gemeinsame Achse** für das Feld **Month** auf den Pfeil nach unten, und wählen Sie **Elemente ohne Daten anzeigen** aus.

    ![Bild 52](Linked_image_Files/07-design-report-in-power-bi-desktop_image30.png)

29. Wie Sie sehen, wird der Monat **2020 June** (Juni 2020) nun angezeigt.

30. Heben Sie die Auswahl des Diagramms auf, indem Sie auf einen leeren Bereich der Berichtsseite klicken.

31. Klicken Sie im Bereich **Visualisierungen** auf den Visualtyp **Karte**, um der Seite ein Diagramm hinzuzufügen.

    ![Bild 53](Linked_image_Files/07-design-report-in-power-bi-desktop_image31.png)

32. Ändern Sie Größe und Position des Visuals so, dass es sich unter dem Säulen-/Liniendiagramm befindet und die halbe Breite des darüber liegenden Diagramms einnimmt.

    ![Bild 33](Linked_image_Files/07-design-report-in-power-bi-desktop_image32.png)

33. Fügen Sie den Visualbereichen die folgenden Felder hinzu:

    - Standort: **Region \| Country**

    - Legende: **Product \| Category**

    - Größe: **Sales \| Sales**

34. Heben Sie die Auswahl des Diagramms auf, indem Sie auf einen leeren Bereich der Berichtsseite klicken.

35. Klicken Sie im Bereich **Visualisierungen** auf den Visualtyp **Gestapeltes Balkendiagramm**, um der Seite ein Diagramm hinzuzufügen.

    ![Bild 54](Linked_image_Files/07-design-report-in-power-bi-desktop_image33.png)

36. Ändern Sie Größe und Position des Visuals so, dass es die restliche Berichtsseite ausfüllt.

    ![Bild 35](Linked_image_Files/07-design-report-in-power-bi-desktop_image34.png)

37. Fügen Sie den Visualbereichen die folgenden Felder hinzu:

    - Achse: **Product \| Category**

    - Wert: **Sales \| Quantity**

38. Öffnen Sie zum Formatieren des Visuals den Bereich **Format**.

    ![Bild 3](Linked_image_Files/07-design-report-in-power-bi-desktop_image35.png)

39. Erweitern Sie die Gruppe **Datenfarben**, und legen Sie die Eigenschaft **Standardfarbe** auf eine geeignete Farbe fest (als Kontrast zum Säulen-/Liniendiagramm).

40. Legen Sie die Eigenschaft **Datenbeschriftungen** auf **Ein** fest.

    ![Abbildung 2](Linked_image_Files/07-design-report-in-power-bi-desktop_image36.png)

41. Speichern Sie die Power BI Desktop-Datei.

    *Damit ist der Entwurf der ersten Seite fertig.*

### <a name="task-5-design-page-2"></a>**Aufgabe 5: Entwerfen der zweiten Seite**

In dieser Aufgabe wird die zweite Berichtsseite entworfen. Nach der Fertigstellung des Entwurfs sieht die Seite wie folgt aus:

![Abbildung der zweiten Seite, bestehend aus einem Slicer und einer Matrix](Linked_image_Files/07-design-report-in-power-bi-desktop_image37.png)

*Wichtig: Da in den Labs bereits ausführliche Anweisungen bereitgestellt wurden, enthalten die folgenden Schritte zum Lab kurzgefasste Anweisungen. Wenn Sie die ausführlichen Anweisungen benötigen, können Sie zu den anderen Aufgaben in diesem Lab zurückkehren.*

1. Klicken Sie zum Erstellen einer neuen Seite links unten auf das Plussymbol.

    ![Bild 42](Linked_image_Files/07-design-report-in-power-bi-desktop_image38.png)

2. Benennen Sie die Seite in **Profit** (Gewinn) um.

    ![Bild 43](Linked_image_Files/07-design-report-in-power-bi-desktop_image39.png)

  
‎ 

3. Fügen Sie einen auf dem Feld **Region \| Region** basierenden Slicer hinzu.

4. Verwenden Sie den Bereich **Format**, um die Option „Alles auswählen“ zu aktivieren (in der Gruppe **Selection Controls** (Auswahlsteuerelemente)).

5. Ändern Sie die Größe und Position des Slicers so, dass er sich auf der linken Seite der Berichtsseite befindet und etwa die Hälfte der Seitenhöhe einnimmt.

    ![Bild 44](Linked_image_Files/07-design-report-in-power-bi-desktop_image40.png)

6. Fügen Sie ein Matrixvisual hinzu, und ändern Sie seine Größe und Position so, dass es den restlichen Bereich der Berichtsseite einnimmt.

    ![Bild 45](Linked_image_Files/07-design-report-in-power-bi-desktop_image41.png)

7. Fügen Sie dem Matrixbereich **Zeilen** die Hierarchie **Date \| Fiscal** hinzu.

    ![Bild 46](Linked_image_Files/07-design-report-in-power-bi-desktop_image42.png)

8. Fügen Sie dem Bereich **Werte** die folgenden fünf Felder der Tabelle **Sales** hinzu:

    - „Orders“ (Bestellungen) (aus dem Ordner **Counts** (Anzahl))

    - „Sales“ (Umsatz)

    - „Cost“ (Kosten)

    - „Profit“ (Gewinn)

    - Profit Margin

    ![Bild 55](Linked_image_Files/07-design-report-in-power-bi-desktop_image43.png)

9. Beachten Sie im Bereich **Filter** (auf der linken Seite des Bereichs **Visualisierungen**) den Bereich **Filter für diese Seite**. (Hierzu müssen Sie möglicherweise nach unten scrollen.)

    ![Bild 57](Linked_image_Files/07-design-report-in-power-bi-desktop_image44.png)

10. Ziehen Sie das Feld **Product \| Category** aus dem Bereich **Felder** in den Bereich **Filter für diese Seite**.

11. Klicken Sie rechts oben auf der Filterkarte auf den Pfeil, um die Karte zuzuklappen.

    ![Bild 58](Linked_image_Files/07-design-report-in-power-bi-desktop_image45.png)

    *Mit Feldern, die dem Bereich **Filter** hinzugefügt werden, kann das gleiche Ergebnis erzielt werden wie mit einem Slicer. Ein Unterschied besteht darin, dass sie keinen Platz auf der Berichtsseite beanspruchen. Ein weiterer Unterschied besteht darin, dass sie für erweiterte Filteranforderungen konfiguriert werden können.*

12. Fügen Sie dem Bereich **Filter für diese Seite** die folgenden Felder der Tabelle **Product** hinzu, und reduzieren Sie sie jeweils (direkt unterhalb der Karte **Kategorie**):

    - „Subcategory“ (Unterkategorie)

    - „Product“ (Produkt)

    - „Color“ (Farbe)

    ![Bild 60](Linked_image_Files/07-design-report-in-power-bi-desktop_image46.png)

13. Speichern Sie die Power BI Desktop-Datei.

    *Damit ist der Entwurf der zweiten Seite fertig.*

### <a name="task-6-design-page-3"></a>**Aufgabe 6: Entwerfen der dritten Seite**

In dieser Aufgabe wird die dritte und letzte Berichtsseite entworfen. Nach der Fertigstellung des Entwurfs sieht die Seite wie folgt aus:

![Abbildung der dritten Seite, bestehend aus einem Slicer und drei Visuals](Linked_image_Files/07-design-report-in-power-bi-desktop_image47.png)

1. Erstellen Sie eine neue Seite, und benennen Sie sie in **My Performance** (Meine Leistung) um.

1. Um die Leistung von Filtern für die Sicherheit auf Zeilenebene zu simulieren, ziehen Sie das Feld **Salesperson (Performance) \| Salesperson** in die Filter auf Seitenebene im Filterbereich.
    
    ![Abbildung des Felds „Salesperson“ im Filterbereich](Linked_image_Files/07-design-report-in-power-bi-desktop_image999.png) 

1. Wählen Sie **Michael Blythe** aus. Die Daten auf der Berichtsseite **My Performance** (Meine Leistung) werden jetzt gefiltert, um nur Daten für Michael Blythe anzuzeigen.

1. Fügen Sie einen auf dem Feld **Date \| Year** basierenden Dropdown-Slicer hinzu, und ändern Sie Größe und Position so, dass er sich in der linken oberen Ecke der Seite befindet.

    ![Bild 70](Linked_image_Files/07-design-report-in-power-bi-desktop_image49.png)

1. Legen Sie im Slicer die Seite so fest, dass Sie nach **FY2019** gefiltert wird.

    ![Bild 71](Linked_image_Files/07-design-report-in-power-bi-desktop_image50.png)

1. Fügen Sie ein Visual vom Typ **Mehrzeilige Zuordnung** hinzu, und ändern Sie Größe und Position so, dass es sich rechts von der Schaltfläche befindet und die restliche Breite der Seite einnimmt.

    ![Bild 56](Linked_image_Files/07-design-report-in-power-bi-desktop_image51.png)

    ![Bild 74](Linked_image_Files/07-design-report-in-power-bi-desktop_image52.png)

1. Fügen Sie dem Visual die folgenden vier Felder hinzu:

    - Sales \| Sales

    - Targets \| Target

    - Targets \| Variance

    - Targets \| Variance Margin

1. Formatieren Sie das Visual:

    - Erhöhen Sie in der Gruppe **Datenbeschriftungen** die Eigenschaft **Textgröße** auf **28 pt**.

    - Legen Sie in der Gruppe **Hintergrund** die Option **Farbe** auf ein helles Grau fest.

    ![Bild 79](Linked_image_Files/07-design-report-in-power-bi-desktop_image53.png)

1. Fügen Sie ein Visual vom Typ **Balkendiagramm (gruppiert)** hinzu, und ändern Sie Größe und Position so, dass es sich unter dem Visual „Mehrzeilige Zuordnung“ befindet und die restliche Höhe der Seite sowie die Hälfte der Breite des Visuals „Mehrzeilige Zuordnung“ einnimmt.

    ![Bild 59](Linked_image_Files/07-design-report-in-power-bi-desktop_image54.png)

    ![Bild 78](Linked_image_Files/07-design-report-in-power-bi-desktop_image55.png)

1. Fügen Sie den Visualbereichen die folgenden Felder hinzu:

    - Achse: **Date \| Month**

    - Wert: **Sales \| Sales** und **Targets \| Target**

    ![Bild 80](Linked_image_Files/07-design-report-in-power-bi-desktop_image56.png)

1. Drücken Sie **STRG+C**, um das Visual zu kopieren, und drücken Sie anschließend **STRG+V**.

1. Positionieren Sie das neue Visual rechts neben dem ursprünglichen Visual.

    ![Bild 82](Linked_image_Files/07-design-report-in-power-bi-desktop_image57.png)

1. Wählen Sie zum Ändern des Visualisierungstyps im Bereich **Visualisierungen** die Option **Säulendiagramm (gruppiert)** aus.

    ![Bild 61](Linked_image_Files/07-design-report-in-power-bi-desktop_image58.png)

    *Nun werden die gleichen Daten mit zwei verschiedenen Visualisierungstypen dargestellt. Das ist keine gute Verwendung des Seitenlayouts, aber Sie werden dies im Lab **Entwerfen eines Berichts in Power BI Desktop, Teil 2** verbessern, indem Sie die Visuals überlagern. Wenn Sie der Seite Schaltflächen hinzufügen, können die Berichtsbenutzer*innen bestimmen, welches der beiden Visuals sichtbar ist.*

    *Damit ist der Entwurf der dritten und letzten Seite fertig.*

### <a name="task-7-publish-the-report"></a>**Aufgabe 7: Veröffentlichen des Berichts**

In dieser Aufgabe wird der Bericht veröffentlicht.

1. Wählen Sie die Seite **Übersicht** aus.

2. Speichern Sie die Power BI Desktop-Datei.

3. Klicken Sie auf der Registerkarte **Start** des Menübands innerhalb der Gruppe **Freigeben** auf **Veröffentlichen**.

    ![Bild 67](Linked_image_Files/07-design-report-in-power-bi-desktop_image59.png)

4. Beachten Sie, dass im Fenster **In Power BI veröffentlichen** die Option **Mein Arbeitsbereich** ausgewählt ist.

5. Klicken Sie auf **Auswählen**, um den Bericht zu veröffentlichen.

    ![Bild 75](Linked_image_Files/07-design-report-in-power-bi-desktop_image60.png)

6. Klicken Sie nach erfolgreicher Veröffentlichung auf **Verstanden**.

    ![Bild 76](Linked_image_Files/07-design-report-in-power-bi-desktop_image61.png)

7. Lassen Sie Power BI Desktop geöffnet.

    *In der nächsten Übung untersuchen Sie den Bericht im Power BI-Dienst.*

## <a name="exercise-2-explore-the-report"></a>**Übung 2: Erkunden des Berichts**

In dieser Übung untersuchen Sie den Bericht, der in Power BI veröffentlicht wurde.

### <a name="task-1-explore-the-report"></a>**Aufgabe 1: Untersuchen des Berichts**

In dieser Aufgabe untersuchen Sie den Bericht, der in Power BI veröffentlicht wurde.

1. Erweitern Sie im Browserfenster von Microsoft Edge im Power BI-Dienst im Bereich **Navigation** (auf der linken Seite, möglicherweise ist der Bereich zugeklappt) die Option **Mein Arbeitsbereich**.

    ![Bild 93](Linked_image_Files/07-design-report-in-power-bi-desktop_image62.png)

2. Überprüfen Sie die Inhalte des Arbeitsbereichs, und beachten Sie dabei den Bericht **Sales Analysis** und das Dataset.

    *Wenn Sie die Power BI Desktop-Datei veröffentlicht haben, wurde das Datenmodell als Dataset veröffentlicht.*

    *Sollte es nicht angezeigt werden, drücken Sie **F5**, um den Browser zu aktualisieren, und erweitern Sie den Arbeitsbereich noch einmal.*

    ![Bild 94](Linked_image_Files/07-design-report-in-power-bi-desktop_image63.png)

3. Klicken Sie auf den Bericht **Sales Analysis**, um den Bericht zu öffnen.

4. Wählen Sie links im Bereich **Seiten** die Seite **Overview** aus. 

5. Wählen Sie im Datenschnitt **Regions** (Regionen) mehrere Regionen aus, und halten Sie dabei **STRG** gedrückt.

6. Wählen Sie im Säulen-/Liniendiagramm eine beliebige Monatsspalte aus, um eine Kreuzfilterung der Seite durchzuführen.

7. Wählen Sie einen zusätzlichen Monat aus, und halten Sie dabei **STRG** gedrückt.

    *Bei der Kreuzfilterung werden standardmäßig alle anderen Visuals auf der Seite gefiltert.*

8. Wie Sie sehen, wird das Balkendiagramm gefiltert und hervorgehoben. Der fett formatierte Teil der Balken stellt dabei die gefilterten Monate dar.

9. Zeigen Sie mit dem Cursor auf das Visual mit dem Balkendiagramm und anschließend rechts oben auf das Filtersymbol.

    ![Bild 95](Linked_image_Files/07-design-report-in-power-bi-desktop_image64.png)

    *Über das Filtersymbol können Sie nachvollziehen, welche Filter auf das Visual angewendet wurden (einschließlich Datenschnitte und Kreuzfilterungen von anderen Visuals).*

10. Zeigen Sie mit dem Mauszeiger auf einen Balken, und sehen Sie sich die QuickInfo an.

11. Klicken Sie zum Rückgängigmachen der Kreuzfilterung im Säulen-/Liniendiagramm auf einen leeren Bereich des Visuals.

12. Zeigen Sie mit dem Cursor auf das Kartenvisual, und klicken Sie anschließend rechts oben auf das Symbol für den **Fokusmodus**.

    ![Bild 96](Linked_image_Files/07-design-report-in-power-bi-desktop_image65.png)

    *Im Fokusmodus wird das Visual auf die volle Seitengröße vergrößert.*

13. Zeigen Sie mit dem Cursor auf verschiedene Segmente der Balkendiagramme, um QuickInfos anzuzeigen.

14. Klicken Sie links oben auf **Zurück zum Bericht**, um zur Berichtsseite zurückzukehren.

    ![Bild 86](Linked_image_Files/07-design-report-in-power-bi-desktop_image66.png)

15. Zeigen Sie mit dem Cursor erneut auf das Kartenvisual, und klicken Sie dann rechts oben auf die Auslassungspunkte (...). Sehen Sie sich die Menüoptionen an.

    ![Bild 97](Linked_image_Files/07-design-report-in-power-bi-desktop_image67.png)

16. Testen Sie die einzelnen Optionen mit Ausnahme von **In Teams chatten**.

17. Wählen Sie links im Bereich **Seiten** die Seite **Profit** (Gewinn) aus.

    ![Bild 84](Linked_image_Files/07-design-report-in-power-bi-desktop_image68.png)

18. Beachten Sie, dass der Slicer **Region** über eine andere Auswahl als der Slicer **Region** auf der Seite **Übersicht** verfügt.

    *Die Slicer werden nicht synchronisiert. Sie ändern den Berichtsentwurf im Lab **Entwerfen eines Berichts in Power BI Desktop, Teil 2**, um sicherzustellen, dass eine Synchronisierung zwischen den Seiten erfolgt.*

19. Erweitern Sie im Bereich **Filter** (rechts) eine Filterkarte, und wenden Sie einige Filter an.

    *Im Bereich **Filter** können Sie mehr Filter definieren als in Form von Slicern auf eine Seite passen.*

20. Verwenden Sie im Matrixvisual die Plusschaltfläche (+), um die Hierarchie **Geschäftskalender** zu erweitern.

21. Wählen Sie die Seite **My Performance** (Meine Leistung) aus.

    ![Bild 89](Linked_image_Files/07-design-report-in-power-bi-desktop_image69.png)

22. Klicken Sie rechts oben auf der Menüleiste auf **Ansicht**, und wählen Sie dann **Vollbild** aus.

    ![Bild 98](Linked_image_Files/07-design-report-in-power-bi-desktop_image70.png)

23. Interagieren Sie mit der Seite, indem Sie den Datenschnitt ändern und eine Kreuzfilterung der Seite durchführen.

24. Beachten Sie links unten auf dem Fenster die Befehle zum Ändern der Seite, zum Navigieren zwischen Seiten sowie zum Beenden des Vollbildmodus.

25. Klicken Sie auf das linke Symbol, um den Vollbildmodus zu beenden.

    ![Bild 91](Linked_image_Files/07-design-report-in-power-bi-desktop_image71.png)

### <a name="task-2-finish-up"></a>**Aufgabe 2: Abschluss**

Mit dieser Aufgabe schließen Sie das Lab ab.

1. Klicken Sie auf dem Banner auf der Fensterwebseite auf **Mein Arbeitsbereich**, um zurück zu Ihrem Arbeitsbereich zu navigieren.

    ![Bild 99](Linked_image_Files/07-design-report-in-power-bi-desktop_image72.png)

2. Lassen Sie das Browserfenster von Microsoft Edge geöffnet.

    *Sie erweitern den Berichtsentwurf um erweiterte Features im Lab **Entwerfen eines Berichts in Power BI Desktop, Teil 2**.*
