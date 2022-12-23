---
lab:
  title: "Erstellen eines Power\_BI-Dashboards"
  module: 11 - Create Dashboards
---


# <a name="create-a-power-bi-dashboard"></a>**Erstellen eines Power BI-Dashboards**

**Die geschätzte Dauer dieses Labs beträgt 45 Minuten.**

In diesem Lab erstellen Sie das Dashboard **Sales Monitoring** (Umsatzüberwachung).

In diesem Lab lernen Sie Folgendes:

- Anheften von Visuals an ein Dashboard

- Verwenden von Q&A zum Erstellen von Dashboardkacheln

### <a name="lab-story"></a>**Labszenario**

Dieses Lab ist eines von vielen in einer Reihe von Labs, die als fortlaufendes Szenario von der Datenvorbereitung bis zur Veröffentlichung als Berichte und Dashboards entworfen wurde. Sie können die Labs in beliebiger Reihenfolge abschließen. Wenn Sie jedoch beabsichtigen, mehrere Labs durchzuarbeiten, sollten Sie sie in der folgenden Reihenfolge absolvieren:

1. Vorbereiten von Daten in Power BI Desktop

2. Laden von Daten in Power BI Desktop

3. Modellieren von Daten in Power BI Desktop

4. Erstellen von DAX-Berechnungen in Power BI Desktop, Teil 1

5. Erstellen von DAX-Berechnungen in Power BI Desktop, Teil 2

6. Entwerfen eines Berichts in Power BI Desktop, Teil 1

7. Entwerfen eines Berichts in Power BI Desktop, Teil 2

8. Analysieren von Daten mit KI-Visuals

9. **Erstellen eines Power BI-Dashboards**

10. Erzwingen von Sicherheit auf Zeilenebene

## <a name="exercise-1-create-a-dashboard"></a>**Übung 1: Erstellen eines Dashboards**

In dieser Übung erstellen Sie das Dashboard **Sales Monitoring** (Umsatzüberwachung). Das fertige Dashboard sieht wie folgt aus:

![Abbildung des fertigen Dashboards mit drei Kacheln](Linked_image_Files/09-create-power-bi-dashboard_image1.png)

### <a name="task-1-get-started--sign-in"></a>**Aufgabe 1: Erste Schritte – Anmelden**

In dieser Aufgabe richten Sie die Umgebung für das Lab ein, indem Sie sich bei Power BI anmelden.

*Wichtig: Wenn Sie sich in einem vorherigen Lab bereits bei Power BI angemeldet haben, fahren Sie mit der nächsten Aufgabe fort.*

1. Klicken Sie zum Öffnen von Microsoft Edge auf der Taskleiste auf die Programmverknüpfung für Microsoft Edge.

    ![Bild 42](Linked_image_Files/09-create-power-bi-dashboard_image2.png)

2. Navigieren Sie im Browserfenster von Microsoft Edge zu **https://powerbi.microsoft.com**.

    *Tipp: Sie können auch auf der Favoritenleiste von Microsoft Edge die Option für den Power BI-Dienst verwenden.*

3. Klicken Sie auf **Anmelden** (in der rechten oberen Ecke).

    ![Bild 41](Linked_image_Files/09-create-power-bi-dashboard_image3.png)

4. Geben Sie die Kontodaten ein, die Sie erhalten haben.

5. Wenn Sie aufgefordert werden, das Kennwort zu aktualisieren, geben Sie das bereitgestellte Kennwort erneut ein, und geben Sie dann das neue Kennwort zweimal zur Bestätigung ein.

    *Wichtig: Denken Sie daran, sich das neue Kennwort zu notieren.*

6. Schließen Sie den Anmeldevorgang ab.

7. Wenn Sie von Microsoft Edge gefragt werden, ob Sie angemeldet bleiben möchten, klicken Sie auf **Ja**.

8. Erweitern Sie im Browserfenster von Microsoft Edge im Power BI-Dienst im **Navigationsbereich** die Option **Mein Arbeitsbereich**.

    ![Bild 40](Linked_image_Files/09-create-power-bi-dashboard_image4.png)

9. Lassen Sie das Browserfenster von Microsoft Edge geöffnet.

### <a name="task-2-get-started--open-report"></a>**Aufgabe 2: Erste Schritte – Öffnen des Berichts**

In dieser Aufgabe richten Sie die Umgebung für das Lab ein, indem Sie den Starterbericht öffnen.

*Wichtig: Wenn Sie nach einem vorherigen Lab fortfahren (und dieses Lab erfolgreich abgeschlossen haben), überspringen Sie diese Aufgabe und fahren mit der nächsten fort.*

1. Klicken Sie zum Öffnen von Power BI Desktop auf der Taskleiste auf die Verknüpfung „Microsoft Power BI Desktop“.

    ![Bild 39](Linked_image_Files/09-create-power-bi-dashboard_image5.png)

2. Um das Fenster „Erste Schritte“ zu schließen, klicken Sie links oben im Fenster auf das **X**.

    ![Bild 38](Linked_image_Files/09-create-power-bi-dashboard_image6.png)

3. Wenn Power BI Desktop nicht beim Power BI-Dienst angemeldet ist, klicken Sie rechts oben auf **Anmelden**.

    ![Bild 37](Linked_image_Files/09-create-power-bi-dashboard_image7.png)

4. Schließen Sie den Anmeldevorgang mit demselben Konto ab, das Sie für die Anmeldung beim Power BI-Dienst verwendet haben.

5. Um die Startdatei für Power BI Desktop zu öffnen, klicken Sie auf die Registerkarte **Datei** des Menübands, um die Backstage-Ansicht zu öffnen.

6. Wählen Sie **Bericht öffnen** aus.

    ![Bild 36](Linked_image_Files/09-create-power-bi-dashboard_image8.png)

7. Klicken Sie auf **Berichte durchsuchen**.

    ![Bild 34](Linked_image_Files/09-create-power-bi-dashboard_image9.png)

8. Navigieren Sie im Fenster **Öffnen** zum Ordner **D:\PL300\Labs\09-create-power-bi-dashboard\Starter**.

9. Wählen Sie die Datei **Sales Analysis** aus.

10. Klicken Sie auf **Öffnen**.

    ![Bild 32](Linked_image_Files/09-create-power-bi-dashboard_image10.png)

11. Schließen Sie alle Informationsfenster, die möglicherweise geöffnet werden.

12. Um eine Kopie der Datei zu erstellen, klicken Sie auf die Registerkarte **Datei** des Menübands, um die Backstage-Ansicht zu öffnen.

13. Wählen Sie **Speichern unter** aus.

    ![Bild 29](Linked_image_Files/09-create-power-bi-dashboard_image11.png)

14. Wenn Sie aufgefordert werden, die Abfragen anzuwenden, klicken Sie auf **Anwenden**.

    ![Bild 10](Linked_image_Files/09-create-power-bi-dashboard_image12.png)

15. Navigieren Sie im Fenster **Speichern unter** zum Ordner **D:\PL300\MySolution**.

16. Klicken Sie auf **Speichern**.

    ![Bild 9](Linked_image_Files/09-create-power-bi-dashboard_image13.png)

### <a name="task-3-get-started--publish-the-report"></a>**Aufgabe 3: Erste Schritte – Veröffentlichen des Berichts**

In dieser Aufgabe richten Sie die Umgebung für das Lab ein, indem Sie ein Dataset erstellen.

*Wichtig: Wenn Sie den Bericht bereits im Lab **Entwerfen eines Berichts in Power BI Desktop, Teil 2** veröffentlicht haben, fahren Sie mit der nächsten Aufgabe fort.*

1. Klicken Sie im Browserfenster von Microsoft Edge im Power BI-Dienst im **Navigationsbereich** unten auf **Daten abrufen**.

    ![Bild 8](Linked_image_Files/09-create-power-bi-dashboard_image14.png)

2. Klicken Sie auf der Kachel **Dateien** auf **Abrufen**.

    ![Abbildung 2](Linked_image_Files/09-create-power-bi-dashboard_image15.png)

3. Klicken Sie auf die Kachel **Lokale Datei**.

    ![Bild 5](Linked_image_Files/09-create-power-bi-dashboard_image16.png)

4. Navigieren Sie im Fenster **Öffnen** zum Ordner **D:\PL300\Labs\08-create-power-bi-dashboard\Solution**.

5. Wählen Sie die Datei **SalesAnalysis.pbix** aus, und klicken Sie dann auf **Öffnen**.

6. Wenn Sie zum Ersetzen des Datasets aufgefordert werden, klicken Sie auf **Ersetzen**.

### <a name="task-4-create-a-dashboard"></a>**Aufgabe 4: Erstellen des Dashboards**

In dieser Aufgabe erstellen Sie das Dashboard **Sales Monitoring** (Umsatzüberwachung). Sie heften ein Visual aus dem Bericht an, fügen eine Kachel auf der Grundlage eines Bilddaten-URIs hinzu, und verwenden Q&A, um eine Kachel zu erstellen.

1. Öffnen Sie im Browserfenster von Microsoft Edge im Power BI-Dienst den Bericht **Sales Analysis**.

2. Legen Sie auf der Seite **Übersicht** den Slicer **Year** auf **FY2020** fest.

    ![Bild 4](Linked_image_Files/09-create-power-bi-dashboard_image17.png)

3. Legen Sie den Slicer **Region** auf **Alle auswählen** fest.

    *Beim Anheften von Visuals an ein Dashboard verwenden diese den aktuellen Filterkontext. Nach dem Anheften kann der Filterkontext nicht geändert werden. Bei zeitbasierten Filtern empfiehlt es sich, einen relativen Slicer mit Datum (oder Q&A mit einer relativen zeitbasierten Frage) zu verwenden.*

4. Zeigen Sie mit dem Mauszeiger auf das Visual **Sales and Profit Margin by Month** (Spalte/Zeile), um ein Dashboard zu erstellen und ein Visual anzuheften.

5. Klicken Sie in der unteren rechten Ecke auf die Reißzwecke.

    ![Bild 43](Linked_image_Files/09-create-power-bi-dashboard_image18.png)

6. Geben Sie im Fenster **An Dashboard anheften** im Feld **Dashboardname** den Namen **Sales Monitoring** ein.

    ![Bild 3](Linked_image_Files/09-create-power-bi-dashboard_image19.png)

7. Klicken Sie auf **Anheften**.

    ![Abbildung 1](Linked_image_Files/09-create-power-bi-dashboard_image20.png)

8. Öffnen Sie den **Navigationsbereich**, klicken Sie auf **Mein Arbeitsbereich**, und öffnen Sie dann das Dashboard **Sales Monitoring**.

    ![Bild 44](Linked_image_Files/09-create-power-bi-dashboard_image21.png)

9. Beachten Sie, dass das Dashboard über eine einzelne Kachel verfügt.

    ![Bild 45](Linked_image_Files/09-create-power-bi-dashboard_image22.png)

10. Zum Hinzufügen einer Kachel, die auf einer Frage basiert, klicken Sie oben links im Dashboard auf **Stellen Sie eine Frage zu Ihren Daten**.

    ![Bild 7](Linked_image_Files/09-create-power-bi-dashboard_image23.png)

    *Mithilfe der Q&A-Funktion können Sie eine Frage stellen, und Power BI antwortet mit einem Visual.*

11. Klicken Sie auf eine der vorgeschlagenen Fragen, die unterhalb des Q&A-Felds in blauen Feldern angegeben sind.

12. Prüfen Sie die Antwort.

13. Entfernen Sie den gesamten Text aus dem Q&A-Feld.

14. Geben Sie im Q&A-Feld den folgenden Text ein: **Sales YTD**

    ![Bild 11](Linked_image_Files/09-create-power-bi-dashboard_image24.png)

15. Die Antwort lautet **(Leer)**.

    ![Bild 14](Linked_image_Files/09-create-power-bi-dashboard_image25.png)

    *Möglicherweise erinnern Sie sich, dass Sie das Measure **Sales YTD** im Lab **Erstellen von DAX-Berechnungen in Power BI Desktop, Teil 2** hinzugefügt haben. Dieses Measure ist ein Zeitintelligenzausdruck und erfordert daher einen Filter für die Tabelle **Date**, damit ein Ergebnis generiert wird.*

16. Erweitern Sie die Frage um **in year FY2020** (im Jahr 2020).

    ![Bild 12](Linked_image_Files/09-create-power-bi-dashboard_image26.png)

17. Die Antwort lautet nun **$33M**.

    ![Bild 13](Linked_image_Files/09-create-power-bi-dashboard_image27.png)

18. Zum Anheften der Antwort an das Dashboard klicken Sie in der oberen rechten Ecke auf **Visualisierung anheften**.

    ![Bild 15](Linked_image_Files/09-create-power-bi-dashboard_image28.png)

19. Wenn Sie aufgefordert werden, die Kachel an das Dashboard anzuheften, klicken Sie auf **Anheften**.

    ![Bild 17](Linked_image_Files/09-create-power-bi-dashboard_image29.png)

20. Um zum Dashboard zurückzukehren, klicken Sie links oben auf **Q&amp;A beenden**.

    ![Bild 16](Linked_image_Files/09-create-power-bi-dashboard_image30.png)

21. Klicken Sie auf der Menüleiste auf **Bearbeiten**, und wählen Sie dann **Kachel hinzufügen** aus, um das Firmenlogo hinzuzufügen.

    ![Bild 46](Linked_image_Files/09-create-power-bi-dashboard_image31.png)

    *Mithilfe dieses Verfahrens zum Hinzufügen einer Dashboardkachel können Sie das Dashboard mit Medien überarbeiten, einschließlich Webinhalte, Bilder, Textfelder mit umfangreicher Formatierung und Videos (mit YouTube- oder Vimeo-Links).*

22. Wählen Sie im Bereich **Kachel hinzufügen** rechts die Kachel **Bild** aus.

    ![Bild 47](Linked_image_Files/09-create-power-bi-dashboard_image32.png)

23. Klicken Sie auf **Weiter**.

    ![Bild 48](Linked_image_Files/09-create-power-bi-dashboard_image33.png)

24. Geben Sie im Bereich **Bildkachel hinzufügen** im Feld **URL** die vollständige URL aus der Datei **D:\PL300\Resources\AdventureWorksLogo_DataURL.txt** ein.

    *Sie können ein Bild mithilfe der zugehörigen URL einbetten oder eine Daten-URL verwenden, die Inhalte inline einbettet.*

25. Klicken Sie unten im Bereich auf **Übernehmen**.

    ![Bild 49](Linked_image_Files/09-create-power-bi-dashboard_image34.png)

26. Um die Größe der Logokachel zu ändern, ziehen Sie die untere rechte Ecke. Ändern Sie die Größe der Kachel so, dass Sie eine Einheit breit und zwei Einheiten hoch ist.

    *Kachelgrößen sind auf eine rechteckige Form beschränkt. Es ist nur möglich, die Größe auf ein Vielfaches der rechteckigen Form zu ändern.*

27. Ordnen Sie die Kacheln so, dass das Logo ganz oben links angezeigt wird. Daneben ordnen Sie die Kachel **Sales YTD** und rechts die Kachel **Sales, Profit Margin** an.

    ![Bild 52](Linked_image_Files/09-create-power-bi-dashboard_image35.png)

### <a name="task-5-edit-tile-details"></a>**Aufgabe 5: Bearbeiten von Kacheldetails**

In dieser Aufgabe bearbeiten Sie die Details von zwei Kacheln.

1. Zeigen Sie mit dem Mauszeiger auf die Kachel **Sales YTD** (Umsatz seit Jahresbeginn), klicken Sie dann oben rechts auf der Kachel auf die Auslassungszeichen, und wählen Sie anschließend **Details bearbeiten** aus.

    ![Bild 50](Linked_image_Files/09-create-power-bi-dashboard_image36.png)

2. Geben Sie im Bereich **Kacheldetails** (rechts) im Feld **Untertitel** den Text **FY2020** ein.

    ![Bild 19](Linked_image_Files/09-create-power-bi-dashboard_image37.png)

3. Klicken Sie auf **Übernehmen**.

    ![Bild 20](Linked_image_Files/09-create-power-bi-dashboard_image38.png)

4. Nun wird auf der Kachel **Sales YTD** ein Untertitel angezeigt.

    ![Bild 21](Linked_image_Files/09-create-power-bi-dashboard_image39.png)

5. Bearbeiten Sie die Kacheldetails für die Kachel **Sales, Profit Margin** (Umsatz, Gewinnspanne).

6. Aktivieren Sie im Bereich **Kacheldetails** im Abschnitt **Funktionalität** die Option **Zeitpunkt der letzten Aktualisierung anzeigen**.

    ![Bild 22](Linked_image_Files/09-create-power-bi-dashboard_image40.png)

7. Klicken Sie auf **Übernehmen**.

    ![Bild 23](Linked_image_Files/09-create-power-bi-dashboard_image41.png)

8. Die Kachel gibt jetzt den Zeitpunkt der letzten Aktualisierung an (bei der Aktualisierung des Datenmodells in Power BI Desktop).



    *In der nächsten Übung aktualisieren Sie das Dataset. Dies sollte normalerweise mithilfe einer geplanten Aktualisierung erfolgen. Power BI könnte dann über ein Gateway eine Verbindung mit der SQL Server-Datenbank herstellen. Aufgrund von Einschränkungen im Setup für diesen Kurs ist jedoch kein Gateway vorhanden. Daher öffnen Sie Power BI Desktop, führen eine manuelle Datenaktualisierung durch und laden die Datei dann in Ihren Arbeitsbereich hoch.*

## <a name="exercise-2-refresh-the-dataset"></a>**Übung 2: Aktualisieren des Datasets**

In dieser Übung laden Sie zuerst Bestelldaten für Juni 2020 in die Datenbank **AdventureWorksDW2020**. Anschließend öffnen Sie die Power BI Desktop-Datei, führen eine Datenaktualisierung aus und laden die Datei dann in Ihren Arbeitsbereich hoch.

### <a name="task-1-update-the-lab-database"></a>**Aufgabe 1: Aktualisieren der Labdatenbank**

In dieser Aufgabe führen Sie ein PowerShell-Skript aus, um Daten in der Datenbank **AdventureWorksDW2020** zu aktualisieren.

1. Klicken Sie im Datei-Explorer im Ordner **D:\PL300\Setup** mit der rechten Maustaste auf die Datei **UpdateDatabase-2-AddSales.ps1**, und wählen Sie dann **Mit PowerShell ausführen** aus.

    ![Bild 28](Linked_image_Files/09-create-power-bi-dashboard_image46.png)

2. Wenn Sie aufgefordert werden, die Ausführungsrichtlinie zu ändern, drücken Sie auf die Taste **A**.

3. Wenn Sie aufgefordert werden, zum Schließen eine beliebige Taste zu drücken, drücken Sie erneut die **EINGABETASTE**.

    *Die Datenbank **AdventureWorksDW2020** enthält nun Bestellungen vom Juni 2020.*

### <a name="task-2-refresh-the-power-bi-desktop-file"></a>**Aufgabe 2: Aktualisieren der Power BI Desktop-Datei**

In dieser Aufgabe öffnen Sie die Power BI Desktop-Datei **Sales Analysis**, führen eine Datenaktualisierung durch und laden die Datei anschließend in den Arbeitsbereich **Sales Analysis** hoch.

1. Klicken Sie in der Power BI Desktop-Datei im Bereich **Felder** mit der rechten Maustaste auf die Tabelle **Sales**, und wählen Sie dann **Daten aktualisieren** aus.

    ![Bild 55](Linked_image_Files/09-create-power-bi-dashboard_image47.png)

2. Wenn die Aktualisierung abgeschlossen ist, speichern Sie die Power BI Desktop-Datei.

3. Klicken Sie auf der Registerkarte **Start** des Menübands innerhalb der Gruppe **Freigeben** auf **Veröffentlichen** und dann auf **Auswählen**, um die Datei in Ihrem Arbeitsbereich zu veröffentlichen.

    ![Bild 59](Linked_image_Files/09-create-power-bi-dashboard_image48.png)

4. Wenn Sie zum Ersetzen des Datasets aufgefordert werden, klicken Sie auf **Ersetzen**.

    ![Bild 31](Linked_image_Files/09-create-power-bi-dashboard_image49.png)

    *Das Dataset im Power BI-Dienst enthält jetzt Umsatzdaten vom Juni 2020.*

5. Schließen Sie Power BI Desktop.

## <a name="exercise-3-review-the-dashboard"></a>**Übung 3: Überprüfen des Dashboards**

In dieser Übung überprüfen Sie das Dashboard, um aktualisierte Umsatzdaten anzuzeigen.

### <a name="task-1-review-the-dashboard"></a>**Aufgabe 1: Überprüfen des Dashboards**

Bei dieser Aufgabe überprüfen Sie das Dashboard, um aktualisierte Umsatzdaten anzuzeigen.

1. Überprüfen Sie im Fenster des Microsoft Edge-Browsers im Power BI-Dienst das Dashboard für **Sales Monitoring**.

2. Auf der Kachel **Sales, Profit Margin** (Umsatz, Gewinnspanne) können Sie im Untertitel sehen, dass die Daten **JETZT** aktualisiert wurden.

3. Beachten Sie auch, dass nun eine Diagrammsäule für **2020 Jun** vorhanden ist.

    *Wenn die Daten für Juni 2020 nicht angezeigt werden, müssen Sie möglicherweise **F5** drücken, um den Browser zu aktualisieren.*

    ![Bild 33](Linked_image_Files/09-create-power-bi-dashboard_image50.png)

    

4. Klicken Sie auf **Schließen**, um den Bereich zu schließen.
