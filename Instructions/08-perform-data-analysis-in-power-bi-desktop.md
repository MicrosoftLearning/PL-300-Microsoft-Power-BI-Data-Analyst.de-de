---
lab:
  title: "Analysieren von Daten in Power\_BI"
  module: 8 - Perform Data Analysis in Power BI
---


# **Analysieren von Daten in Power BI**

**Die geschätzte Dauer dieses Labs beträgt 45 Minuten.**

In diesem Lab erstellen Sie den Bericht **Sales Exploration**.

In diesem Lab lernen Sie Folgendes:

- Erstellen von animierten Punktdiagrammen
- Verwenden eines Visuals zum Vorhersagen von Werten

### **Labszenario**

Dieses Lab ist eines von vielen in einer Reihe von Labs, die als fortlaufendes Szenario von der Datenvorbereitung bis zur Veröffentlichung als Berichte und Dashboards entworfen wurde. Sie können die Labs in beliebiger Reihenfolge abschließen. Wenn Sie jedoch beabsichtigen, mehrere Labs durchzuarbeiten, sollten Sie sie in der folgenden Reihenfolge absolvieren:

1. Vorbereiten von Daten in Power BI Desktop
1. Laden von Daten in Power BI Desktop
1. Modellieren von Daten in Power BI Desktop
1. Erstellen von DAX-Berechnungen in Power BI Desktop
1. Erstellen erweiterter DAX-Berechnungen in Power BI Desktop
1. Entwerfen eines Berichts in Power BI Desktop
1. Verbessern eines Berichts in Power BI Desktop
1. **Analysieren von Daten in Power BI**
1. Erstellen eines Power BI-Dashboards
1. Erzwingen von Sicherheit auf Zeilenebene

## **Übung 1: Erstellen des Berichts**

In dieser Übung erstellen Sie den Bericht **Umsatzuntersuchung**.

### **Aufgabe 1: Erste Schritte – Anmelden**

In dieser Aufgabe richten Sie die Umgebung für das Lab ein, indem Sie sich bei Power BI anmelden.

*Hinweis: Wenn Sie sich bereits bei Power BI angemeldet haben, fahren Sie mit der nächsten Aufgabe fort.*

1. Klicken Sie zum Öffnen von Microsoft Edge auf der Taskleiste auf die Programmverknüpfung für Microsoft Edge.

     ![Bild 12](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image1.png)

1. Navigieren Sie im Browserfenster von Microsoft Edge zu **https://app.powerbi.com**.

    *Tipp: Sie können auch auf der Favoritenleiste von Microsoft Edge die Option für den Power BI-Dienst verwenden.*

1. Schließen Sie den Anmeldevorgang mit den Anmeldeinformationen Ihrer Organisation (oder den angegebenen Anmeldeinformationen) ab. Wenn Sie von Microsoft Edge gefragt werden, ob Sie angemeldet bleiben möchten, klicken Sie auf **Ja**.

1. Erweitern Sie im Browserfenster von Microsoft Edge im Power BI-Dienst im **Navigationsbereich** die Option **Mein Arbeitsbereich**. Lassen Sie das Browserfenster von Microsoft Edge geöffnet.

     ![Bild 22](Linked_image_Files/07-my-workspace-new.png)

### **Aufgabe 2: Erste Schritte – Erstellen eines Datasets**

In dieser Aufgabe richten Sie die Umgebung für das Lab ein, indem Sie ein Dataset erstellen. *Wenn Sie das Dataset bereits veröffentlicht haben, fahren Sie mit der nächsten Aufgabe fort.*

1. Navigieren Sie im Browserfenster von Microsoft Edge im Power BI-Dienst zu **Mein Arbeitsbereich**.

1. Wählen Sie **Hochladen > Durchsuchen** aus.

1. Navigieren Sie zum Ordner **D:\PL300\Labs\08-perform-data-analysis-in-power-bi-desktop\Starter**.

1. Wählen Sie die Datei **SalesAnalysis.pbix** und dann **Öffnen** aus.

    *Wenn Sie zum Ersetzen des Datasets aufgefordert werden, wählen Sie **Ersetzen** aus.*

*Mit dieser Methode erstellen Sie einen Bericht und ein Dataset. In dieser Übung wird das Dataset nur zum Erstellen eines neuen Berichts verwendet. Dieser Prozess kann auch mit einem vorhandenen Dataset aus einem anderen Bericht durchgeführt werden, anstatt ein neues hochzuladen. Wenn Sie den Bericht nicht verwenden, empfiehlt es sich außerdem, die nicht benötigte Datei zu löschen.*

### **Aufgabe 3: Erstellen des Berichts**

In dieser Aufgabe erstellen Sie eine Liveverbindung mit dem Power BI-Dataset, das in der letzten Aufgabe erstellt wurde, und erstellen dann einen neuen Bericht zur **Umsatzuntersuchung**.

1. Öffnen Sie Power BI Desktop.

    ![Power BI Desktop-Symbol](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image1.png)

    *Wichtig: Wenn Power BI Desktop bereits (aus einem früheren Lab) geöffnet ist, schließen Sie diese Instanz.*

    *Tipp: Standardmäßig wird das Dialogfeld „Erste Schritte“ vor Power BI Desktop geöffnet. Sie können sich anmelden und dann das Popup schließen.*

1. Wählen Sie im Menüband „Start“ die Option **Daten abrufen > Power BI-Datasets** aus.

1. Wählen Sie im Fenster **Datenhub** das Dataset **Verkaufsanalyse** in **Mein Arbeitsbereich** aus, und klicken Sie dann auf **Verbinden**, oder doppelklicken Sie darauf, um das Dataset zu laden.

1. Navigieren Sie zu **Datei > Speichern** und speichern Sie den Dateinamen als **Umsatzuntersuchung** im Ordner **D:\PL300\MySolution**.

*Sie erstellen nun zwei Berichtsseiten, und auf jeder Seite arbeiten Sie mit einem anderen Visual, um Daten zu analysieren und zu erkunden.*

## **Übung 2: Erstellen eines Punktdiagramms**

In dieser Übung erstellen Sie ein Punktdiagramm, das animiert werden kann.

### **Aufgabe 1: Erstellen eines animierten Punktdiagramms**

In dieser Aufgabe erstellen Sie ein Punktdiagramm, das animiert werden kann.

1. Benennen Sie **Seite 1** in **Punktdiagramm** um.

1. Fügen Sie der Berichtsseite ein **Punktdiagrammvisual** hinzu und ändern anschließend seine Position und Größe, damit es die gesamte Seite ausfüllt.
    
    *Das Diagramm kann animiert werden, wenn dem Bereich **Wiedergabeachse** ein Feld hinzugefügt wird.*

     ![Bild 18](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image15.png)

     ![Bild 75](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image16.png)

1. Fügen Sie den Visualbereichen die folgenden Felder hinzu:
    
    *In den Labs wird eine verkürzte Notation verwendet, um auf ein Feld zu verweisen. Das sieht folgendermaßen aus: **Reseller** **\|** **Business Type**. In diesem Beispiel ist **Reseller** der Tabellenname und **Business Type** der Feldname.*

     - X-Achse: **Sales \| Sales**
     - Y-Achse: **Sales \| Profit Margin**
     - Legende: **Reseller \| Business Type**
     - Größe: **Sales \| Quantity**
     - Wiedergabeachse: **Date \| Quarter**

1. Fügen Sie im Bereich **Filter** das Feld **Product \| Category** im Bereich **Filter für diese Seite** hinzu.

1. Filtern Sie auf der Filterkarte nach **Bikes** (Fahrräder).

1. Wählen Sie links unten **Wiedergabe** aus, um das Diagramm zu animieren.

    ![Bild 41](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image19.png)

1. Sehen Sie sich den gesamten Animationszyklus vom ersten Quartal im Jahr 2018 (**FY2018 Q1**) bis zum viertel Quartal im Jahr 2020 (**FY2020 Q4**) an.
    
    *Das Punktdiagramm ermöglicht Ihnen, die Measurewerte gleichzeitig aufzuschlüsseln, also in diesem Fall die Bestellmenge (order quantity), den Nettoumsatz (sales revenue) und die Gewinnspanne (profit margin).*
    
    *Jede Blase stellt einen Handelspartner-Unternehmenstyp dar. Änderungen an der Blasengröße spiegeln eine größere oder kleinere Bestellmenge wider. Horizontale Bewegungen stellen eine Erhöhung/Abnahme des Nettoumsatzes dar, und vertikale Verschiebungen stellen eine Erhöhung/Abnahme der Rentabilität dar.*

1. Wenn die Animation angehalten wird, klicken Sie auf eine der Blasen, um die Nachverfolgung für einen Zeitraum anzuzeigen.

1. Bewegen Sie den Cursor auf eine beliebige Blase, um eine QuickInfo mit den Measurewerten für den Handelspartnertyp zu diesem Zeitpunkt anzuzeigen.

1. Filtern Sie im Bereich **Filter** nach **Clothing** (Kleidung), und beachten Sie, dass das Ergebnis ein anderes ist.

1. Speichern Sie die Power BI Desktop-Datei.

## **Übung 3: Erstellen einer Vorhersage**

In dieser Übung erstellen Sie eine Vorhersage, um den möglichen zukünftigen Umsatz zu ermitteln.

### **Aufgabe 1: Erstellen einer Vorhersage**

In dieser Aufgabe erstellen Sie eine Vorhersage, um den möglichen zukünftigen Umsatz zu ermitteln.

1. Fügen Sie eine neue Seite hinzu, und benennen Sie dann die Seite in **Vorhersage** um.

1. Fügen Sie der Berichtsseite ein **Liniendiagrammvisual** hinzu und ändern anschließend seine Position und Größe, damit es die gesamte Seite ausfüllt.

     ![Bild 19](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image21.png)

     ![Bild 74](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image22.png)

1. Fügen Sie den Visualbereichen die folgenden Felder hinzu:

     - x-Achse: **Date \| Date**
     - y-Achse: **Sales \| Sales**

1. Fügen Sie im Bereich **Filter** das Feld **Date \| Year** im Bereich **Filter für diese Seite** hinzu.

1. Filtern Sie auf der Filterkarte nach zwei Jahren: **FY2019** und **FY2020**.
    
    *Wenn Sie eine Vorhersage über eine Zeitachse treffen, benötigen Sie mindestens zwei Zyklen (Jahre) von Daten, um eine präzise und beständige Vorhersage zu erhalten.*

1. Fügen Sie ebenso das Feld **Product \| Category** im Bereich **Filter für diese Seite** hinzu, und filtern Sie nach **Bikes** (Fahrrädern).

1. Wählen Sie zum Hinzufügen einer Vorhersage unter dem Bereich **Visualisierung** den Bereich **Analyse** aus.

     ![Bild 20](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image26.png)

8. Erweitern Sie den Abschnitt **Vorhersage**.
    
    *Wenn der Abschnitt **Vorhersage** nicht verfügbar ist, wurde das visuelle Element wahrscheinlich nicht ordnungsgemäß konfiguriert. Die Vorhersage ist nur verfügbar, wenn zwei Bedingungen erfüllt sind: Die Achse verfügt über ein einzelnes Feld vom Typ „Date“ (Datum), und es gibt nur ein Wertfeld.*

1. Legen Sie die Option **Vorhersage** auf **Ein** fest.

1. Konfigurieren Sie die folgenden Vorhersageeigenschaften, und klicken Sie dann auf **Anwenden**:

    - Einheiten: **Monate**
    - Vorhersagezeitraum: **1 Monat**
    - Saisonalität: **365**
    - Konfidenzintervall: **80 %**

    ![Bild 52](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image29.png)

1. Beachten Sie, dass die Vorhersage im Linienvisual einen Monat über die Verlaufsdaten hinaus verlängert wurde.
    
    *Der graue Bereich stellt die Konfidenz dar. Je breiter die Konfidenz, desto weniger beständig und präzise ist wahrscheinlich auch die Vorhersage.*
    
    *Wenn Sie die Länge des Zyklus kennen (in diesem Fall jährlich), sollten Sie die Saisonalitätspunkte eingeben. Manchmal ist sind diese wöchentlich (7) oder monatlich (30).*

1. Filtern Sie im Bereich **Filter** nun nach **Clothing** (Kleidung). Sie sehen, dass das Ergebnis sich verändert.

### **Aufgabe 2: Abschluss**

In dieser Aufgabe schließen Sie das Lab in Power BI Desktop ab.

1. Wählen Sie die Seite **Punktdiagramm** aus.

1. Speichern Sie die Power BI Desktop-Datei.

1. Klicken Sie auf der Registerkarte **Start** des Menübands innerhalb der Gruppe **Freigeben** auf **Veröffentlichen** und dann auf **Auswählen**, um die Datei unter **Mein Arbeitsbereich** zu veröffentlichen.

    ![Bild 23](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image46.png)

1.  Schließen Sie Power BI Desktop.
