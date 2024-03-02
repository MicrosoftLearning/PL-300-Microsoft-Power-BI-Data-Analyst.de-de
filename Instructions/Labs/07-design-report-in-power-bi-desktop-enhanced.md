---
lab:
  course: PL-300
  title: "Verbessern eines Berichts in Power\_BI Desktop"
  module: Create Reports in Power BI desktop
---


# Verbessern eines Berichts in Power BI Desktop

## **Labszenario**

In diesem Lab optimieren Sie die Verkaufsanalyse **Sales Analysis** mit erweiterten Entwurfsfunktionen.

In diesem Lab lernen Sie Folgendes:

- Synchronisieren von Slicers
- Erstellen einer Drillthroughseite
- Anwenden von bedingter Formatierung
- Erstellen und Verwenden von Lesezeichen

**Dieses Lab sollte ungefähr 45 Minuten in Anspruch nehmen.**

## **Erste Schritte: Anmelden**

In dieser Aufgabe richten Sie die Umgebung für das Lab ein, indem Sie sich bei Power BI anmelden.

*Hinweis: Wenn Sie sich bereits bei Power BI angemeldet haben, fahren Sie mit der nächsten Aufgabe fort.*

1. Klicken Sie zum Öffnen von Microsoft Edge auf der Taskleiste auf die Programmverknüpfung für Microsoft Edge.

     ![Bild 12](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image1.png)

1. Navigieren Sie im Browserfenster von Microsoft Edge zu **https://app.powerbi.com**.

    *Tipp: Sie können auch auf der Favoritenleiste von Microsoft Edge die Option für den Power BI-Dienst verwenden.*

1. Schließen Sie den Anmeldevorgang mit den Anmeldeinformationen Ihrer Organisation (oder den angegebenen Anmeldeinformationen) ab. Wenn Sie von Microsoft Edge gefragt werden, ob Sie angemeldet bleiben möchten, klicken Sie auf **Ja**.

1. Erweitern Sie im Browserfenster von Microsoft Edge im Power BI-Dienst im **Navigationsbereich** die Option **Mein Arbeitsbereich**. Lassen Sie das Browserfenster von Microsoft Edge geöffnet.

     ![Bild 22](Linked_image_Files/07-my-workspace-new.png)

## **Erste Schritte: Öffnen des Berichts**

In dieser Aufgabe richten Sie die Umgebung für das Lab ein, indem Sie den Starterbericht öffnen.

*Wichtig: Wenn Sie nach einem vorherigen Lab fortfahren (und dieses Lab erfolgreich abgeschlossen haben), überspringen Sie diese Aufgabe und fahren Sie mit der nächsten fort.*

1. Öffnen Sie Power BI Desktop.

    ![Power BI Desktop-Symbol](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image1.png)

    *Tipp: Standardmäßig wird das Dialogfeld „Erste Schritte“ vor Power BI Desktop geöffnet. Sie können sich anmelden und dann das Popup schließen.*

1. Um die Power BI Desktop-Startdatei zu öffnen, wählen Sie **Datei > Bericht öffnen > Berichte durchsuchen** aus.

1. Navigieren Sie im Fenster **Öffnen** zum Ordner **D:\Allfiles\Labs\07-design-report-in-power-bi-desktop-enhanced\Starter**, und öffnen Sie die Datei **Verkaufsanalyse**.

1. Schließen Sie alle Informationsfenster, die möglicherweise geöffnet werden.

1. Beachten Sie die Warnmeldung unterhalb des Menübands.

    *In dieser Meldung werden Sie darauf hingewiesen, dass die Abfragen nicht als Modelltabellen geladen wurden. Sie wenden die Abfragen später in diesem Lab an.*

    *Wählen Sie rechts auf der Warnmeldung das **X** aus, um die Warnmeldung zu schließen.*

1. Um eine Kopie der Datei zu erstellen, wechseln Sie zu **Datei > Speichern unter**, und speichern Sie sie im Ordner **D:\Allfiles\MySolution**.

1. Wenn Sie aufgefordert werden, Änderungen zu übernehmen, klicken Sie auf **Später übernehmen**.

## **Synchronisieren von Slicers**

In dieser Aufgabe synchronisieren Sie die Datenschnitte **Jahr** und **Region** und setzen die Entwicklung des Berichts fort, der im Lab **Entwerfen eines Berichts in Power BI Desktop** erstellt wurde.

1. Legen Sie In Power BI Desktop auf der Seite **Übersicht** den Slicer **Year** auf **FY2018** fest.

1. Wechseln Sie zur Seite **My Performance** (Meine Leistung). Sie sehen, dass der Slicer **Year** einen anderen Wert aufweist.

    *Wenn Datenschnitte nicht synchronisiert werden, kann dies zur fehlerhaften Darstellung von Daten und zu Frustration bei den Benutzern des Berichts führen. Synchronisieren Sie nun die Datenschnitte im Bericht.*

1. Kehren Sie zur Seite **Übersicht** zurück, und wählen Sie dann den Slicer **Year** aus.

1. Wählen Sie auf der Registerkarte **Ansicht** des Menübands in der Gruppe **Bereiche anzeigen** **Slicer synchronisieren** aus.

     ![Abbildung 1](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image13.png)

1. Aktivieren Sie im Bereich **Slicers synchronisieren** (links im Bereich **Visualisierungen**) in der zweiten Spalte (für die Synchronisierung) die Kontrollkästchen für die Seiten **Übersicht** und **My Performance** (Meine Leistung).

     ![Bild 93](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image14.png)

1. Wählen Sie auf der Seite **Übersicht** den Slicer **Region** aus.

1. Synchronisieren Sie den Slicer mit den Seiten **Übersicht** und **Gewinn**.

     ![Bild 94](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image15.png)

1. Testen Sie die Synchronisierungsslicer, indem Sie verschiedene Filteroptionen auswählen und dann überprüfen, ob mit den synchronisierten Slicern nach der gleichen Auswahl gefiltert wird.

1. Wählen Sie zum Schließen der Seite **Slicer synchronisieren** das **X**oben rechts im Bereich aus.

## **Konfigurieren eines Drillthroughs**

In dieser Übung erstellen Sie eine neue Seite und konfigurieren sie als Drillthroughseite. Nach der Fertigstellung des Entwurfs sieht die Seite wie folgt aus:

![Abbildung der neuen Seite, bestehend aus einem Kartenvisual und einem Tabellenvisual](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image17.png)

## **Erstellen einer Drillthroughseite**

Bei dieser Aufgabe erstellen Sie eine neue Seite und konfigurieren sie als Drillthroughseite.

1. Fügen Sie eine neue Berichtsseite mit dem Namen **Produktdetails** hinzu.

1. Klicken Sie mit der rechten Maustaste auf die Seitenregisterkarte **Produktdetails**, und wählen Sie dann die Option **Seite ausblenden** aus.

    *Berichtsbenutzer*innen können nicht direkt zur Drillthroughseite navigieren. Sie müssen über Visuals auf anderen Seiten darauf zugreifen. In der abschließenden Übung dieses Labs wird beschrieben, wie Sie den Drillthrough zur Seite durchführen.*

1. Fügen Sie unterhalb des Bereichs **Visualisierungen** im Abschnitt **Drillthrough** im Feld **Drillthroughfelder hier hinzufügen** das Feld **Product \| Category** hinzu.

    *In den Labs wird eine verkürzte Notation verwendet, um auf ein Feld zu verweisen. Das sieht folgendermaßen aus: **Product \| Category**. In diesem Beispiel ist **Product** der Tabellenname und **Category** der Feldname.*

     ![Bild 96](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image20.png)

1. Wählen Sie zum Testen der Drillthroughseite auf der Drillthrough-Filterkarte die Option **Fahrräder** aus.

     ![Bild 99](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image21.png)

1. Beachten Sie oben links auf der Berichtsseite die Pfeilschaltfläche.

    *Es wird automatisch eine Pfeilschaltfläche hinzugefügt, wenn dem Drillthroughbereich ein Feld hinzugefügt wird. Sie ermöglicht es Berichtsbenutzern, zurück zu der Seite zu wechseln, auf der sie den Drillthrough gestartet haben.*

1. Fügen Sie der Seite das Visual **Karte** hinzu. Ändern Sie dann die Größe und Position so, dass es rechts von der Schaltfläche angeordnet ist und die restliche Breite der Seite ausfüllt.

    ![Bild 13](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image23.png)

    ![Bild 101](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image24.png)

1. Ziehen Sie das Feld **Product \| Category** auf das Visual „Karte“.

1. Konfigurieren Sie die Formatoptionen für das Visual, und legen Sie die Eigenschaft **Kategoriebeschriftung** dann auf **Aus** fest.

     ![Bild 103](Linked_image_Files/07-design-report-in-power-bi-desktop_image36b.png)

1. Legen Sie die Eigenschaft **Effekte > Hintergrundfarbe** auf einen hellen Grauton fest, wie z. B. auf *Weiß, 20 % dunkler*.

     ![Bild 103](Linked_image_Files/07-design-report-in-power-bi-desktop_image36c.png)

1. Fügen Sie der Seite ein Visual vom Typ **Tabelle** hinzu. Ändern Sie dessen Größe und Position anschließend so, dass es unterhalb des Kartenvisuals angeordnet ist und den restlichen Platz der Seite einnimmt.

     ![Bild 14](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image26.png)

     ![Bild 105](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image27.png)

1. Fügen Sie dem Visual die folgenden Felder hinzu:

     - Product \| Subcategory
     - Product \| Color
     - Sales \| Quantity
     - Sales \| Sales
     - Sales \| Profit Margin

1. Konfigurieren Sie die Formatoptionen für das Visual, und legen Sie im Abschnitt **Werte** die Eigenschaft **Textgröße** auf **20 Pt** fest.

*Der Entwurf der Drillthroughseite ist nun fast abgeschlossen. In der nächsten Übung reichern Sie die Seite mit bedingter Formatierung an.*

## **Hinzufügen von bedingter Formatierung**

In dieser Übung erweitern Sie die Drillthroughseite, indem Sie eine bedingte Formatierung hinzufügen. Nach der Fertigstellung des Entwurfs sieht die Seite wie folgt aus:

![Abbildung einer aktualisierten Seite mit farbigen Werten und Symbolen](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image28.png)

## **Hinzufügen von bedingter Formatierung**

Bei dieser Aufgabe erweitern Sie die Drillthroughseite, indem Sie eine bedingte Formatierung hinzufügen.

1. Wählen Sie das Visual vom Typ „Tabelle“ aus. Klicken Sie im Bereich „Visualisierung“ beim Wert **Profit Margin** (Gewinnspanne) auf den Pfeil nach unten, und wählen Sie **Bedingte Formatierung \| Symbole** aus.

    ![Bild 107](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image29.png)

1. Wählen Sie im Fenster **Symbole – Profit Margin** in der Dropdownliste **Symbollayout** die Option **Rechts von den Daten** aus.

     ![Bild 108](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image30.png)

1. Wählen Sie links neben dem gelben Dreieck das **X** aus, um die mittlere Regel zu löschen.

     ![Bild 109](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image31.png)

1. Konfigurieren Sie die erste Regel (rotes Karo) wie folgt:

    - Entfernen Sie im zweiten Steuerelement den Wert.
    - Wählen Sie für das dritte Steuerelement **Zahl** aus.
    - Geben Sie im fünften Steuerelement **0** ein.
    - Wählen Sie für das sechste Steuerelement **Zahl** aus.

1. Konfigurieren Sie die zweite Regel (grüner Kreis) wie folgt und wählen Sie dann **OK** aus:

    *Die Regeln können wie folgt interpretiert werden: Anzeige eines roten Karos, wenn der Wert für die Rendite kleiner als „0“ ist, und Anzeige des grünen Kreises, wenn der Wert größer oder gleich null ist.*

     - Geben Sie im zweiten Steuerelement **0** ein.
     - Wählen Sie für das dritte Steuerelement **Zahl** aus.
     - Entfernen Sie im fünften Steuerelement den Wert.
     - Wählen Sie für das sechste Steuerelement **Zahl** aus.

     ![Bild 110](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image32.png)

1. Überprüfen Sie im visuellen Tabellenelement, ob die richtigen Symbole angezeigt werden.

     ![Bild 112](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image34.png)

1. Konfigurieren Sie die bedingte Formatierung der Hintergrundfarbe für das Feld **Farbe**.

1. Wählen Sie im Fenster **Hintergrundfarbe – Farbe** in der Dropdownliste **Formatstil** die Option **Feldwert** aus.

1. Wählen Sie in der Dropdownliste **Welches Feld sollten wir als Grundlage nehmen?** die Optionen **Produkt \| Formatierung \| Format der Hintergrundfarbe**  und anschließend **OK** aus.

     ![Bild 114](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image36.png)

1. Wiederholen Sie die obigen Schritte, um die bedingte Formatierung der Schriftfarbe für das Feld **Farbe** zu konfigurieren, indem Sie das Feld **Produkt \| Formatierung \| Font Color Format** (Format der Schriftfarbe) verwenden.

*Sie erinnern sich vielleicht daran, dass die Hintergrundfarben aus der Datei **ColorFormats.csv** im Lab **Vorbereiten von Daten in Power BI Desktop** stammen und dann mit der Abfrage **Product** auf der Registerkarte **Daten in Power BI Desktop laden** integriert wurden.*

## **Hinzufügen von Lesezeichen und Schaltflächen**

In dieser Übung erweitern Sie die Seite **My Performance** (Meine Leistung) durch Schaltflächen, damit Berichtsbenutzer den gewünschten Typ des visuellen Elements auswählen können. Nach der Fertigstellung des Entwurfs sieht die Seite wie folgt aus:

![Abbildung der aktualisierten dritten Seite mit zwei Schaltflächen und jetzt nur noch zwei Visuals](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image38.png)

## **Hinzufügen von Lesezeichen**

Bei dieser Aufgabe fügen Sie zwei Lesezeichen hinzu, und zwar jeweils eins für die Anzeige der visuellen Elemente für den monatlichen Umsatz bzw. das Umsatzziel.

1. Navigieren Sie zur Seite **My Performance** (Meine Leistung). Wählen Sie auf der Registerkarte **Ansicht** des Menübands in der Gruppe **Bereiche anzeigen** **Lesezeichen** aus.

     ![Bild 118](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image39.png)

1. Wählen Sie auf der Registerkarte **Ansicht** des Menübands in der Gruppe **Bereiche anzeigen** **Auswahl** aus.

1. Wählen Sie zum Ausblenden des Visuals im Bereich **Auswahl** neben einem der Elemente unter **Sales and Target by Month** (Umsatz und Ziel nach Monat) das Augensymbol aus.

     ![Bild 120](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image41.png)

1. Wählen Sie im Bereich **Lesezeichen** **Hinzufügen** aus.

    *Doppelklicken Sie auf das Lesezeichen, um es umzubenennen.*

     ![Bild 121](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image42.png)

1. Falls das Balkendiagramm angezeigt wird, sollten Sie das Lesezeichen in **Balkendiagramm EIN** umbenennen, und andernfalls in **Säulendiagramm EIN**.

1. Zeigen Sie zum Bearbeiten des Lesezeichens im Bereich **Lesezeichen** mit dem Cursor auf das Lesezeichen, klicken Sie auf die Auslassungspunkte, und wählen Sie dann **Daten** aus.
     
     *Das Deaktivieren der Option **Daten** bewirkt, dass das Lesezeichen den aktuellen Filterstatus nicht verwendet. Das ist wichtig, da andernfalls das Lesezeichen zu einer dauerhaften Sperre in dem Filter führen würde, der aktuell vom Slicer **Year** angewandt wird.*

     ![Bild 16](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image43.png)

1. Zum Aktualisieren des Lesezeichens klicken Sie erneut auf die Auslassungspunkte und wählen dann **Aktualisieren** aus.

     *In den folgenden Schritten erstellen und konfigurieren Sie ein zweites Lesezeichen, um das zweite Visual anzuzeigen.*

1. Schalten Sie im Bereich **Auswahl** die Sichtbarkeit der beiden Elemente unter **Sales and Target by Month** (Umsatz und Ziel nach Monat) um.

     *Anders ausgedrückt: Blenden Sie das angezeigte Visual aus und das ausgeblendete Visual ein.*

     ![Bild 122](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image45.png)

1. Erstellen Sie ein zweites Lesezeichen, und benennen Sie es entsprechend (entweder **Säulendiagramm EIN** oder **Balkendiagramm EIN)**.

     ![Bild 123](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image46.png)

1. Konfigurieren Sie das zweite Lesezeichen so, dass Filter ignoriert werden (Option **Daten** AUS), und aktualisieren Sie das Lesezeichen.

1. Zeigen Sie im Bereich **Auswahl** einfach das ausgeblendete Visual an, um beide Visuals einzublenden.

1. Ändern Sie die Größe und Position beider Visuals so, dass sie die Seite unterhalb des Visuals mit mehreren Karten ausfüllen und einander vollständig überlappen.

    *Wählen Sie das verdeckte visuelle Element im Bereich **Auswahl** aus.*

    ![Bild 124](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image47.png)

1. Wählen Sie im Bereich **Lesezeichen** die beiden Lesezeichen aus. Sie sehen, dass nur ein Visual sichtbar ist.

*In der nächsten Entwurfsphase werden der Seite zwei Schaltflächen hinzugefügt, damit Berichtsbenutzer die Lesezeichen auswählen können.*

## **Hinzufügen von Schaltflächen**

Bei dieser Aufgabe fügen Sie zwei Schaltflächen hinzu und weisen ihnen jeweils Lesezeichenaktionen zu.

1. Wählen Sie im Menüband **Einfügen** in der Gruppe **Elemente** **Schaltfläche** und dann die Option **Leer** aus.

     ![Bild 125](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image48.png)

1. Platzieren Sie die Schaltfläche direkt unterhalb des Slicers **Year**.

1. Wählen Sie die Schaltfläche aus und dann im Bereich **Schaltfläche formatieren** die Option **Schaltfläche**, erweitern Sie den Abschnitt **Formatvorlage** und setzen Sie die Eigenschaft **Text** auf **Ein**.

     ![Bild 126](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image49b.png)

1. Erweitern Sie den Abschnitt **Text**, und geben Sie dann in das Feld **Text** **Balkendiagramm** ein.

1. Erweitern Sie den Abschnitt **Füllen**, und legen Sie eine Komplementärfarbe als Füllfarbe fest.

1. Klicken Sie auf **Schaltfläche**, und setzen Sie die Eigenschaft **Aktion** auf **Ein**.

    ![Bild 127](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image50.png)

1. Erweitern Sie den Abschnitt **Aktion**, und wählen Sie dann in der Dropdownliste **Typ** die Option **Lesezeichen** aus.

1. Wählen Sie in der Dropdownliste **Lesezeichen** die Option **Balkendiagramm EIN** aus.

    ![Bild 128](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image51.png)

1. Erstellen Sie per Kopieren und Einfügen eine Kopie der Schaltfläche, und konfigurieren Sie die neue Schaltfläche dann wie folgt:

    *Tipp: Die Tastenkombination für das Kopieren und Einfügen ist **STRG+C** gefolgt von **STRG+V**.*

    - Legen Sie die Eigenschaft **Schaltflächentext** auf **Säulendiagramm** fest.
    - Wählen Sie im Abschnitt **Aktion** in der Dropdownliste **Lesezeichen** die Option **Säulendiagramm EIN** aus.

*Der Entwurf des Sales Analysis-Berichts ist nun fertig gestellt.*

## **Veröffentlichen des Berichts**

In dieser Aufgabe wird der Bericht veröffentlicht.

1. Wählen Sie die Seite **Übersicht** aus.

1. Wählen Sie im Slicer **Jahr** die Option **FY2020** (GJ2020) aus.

1. Wählen Sie im Slicer **Region** die Option **Alles auswählen** aus.

1. Speichern Sie die Power BI Desktop-Datei.

    *Die Datei muss vor dem Veröffentlichen im Power BI-Dienst immer gespeichert werden.*

1. Klicken Sie auf der Registerkarte **Start** des Menübands innerhalb der Gruppe **Freigeben** auf **Veröffentlichen**.

     ![Bild 21](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image52.png)

1. Beachten Sie, dass im Fenster **In Power BI veröffentlichen** die Option **Mein Arbeitsbereich** ausgewählt ist.

1. Wählen Sie **Auswählen** aus, um den Bericht zu veröffentlichen.
    1. Wenn Sie zum Ersetzen des semantischen Modells aufgefordert werden, wählen Sie **Ersetzen** aus.
    1. Wenn die Veröffentlichung erfolgreich war, klicken Sie auf **OK**.

1. Schließen Sie Power BI Desktop.

*In der nächsten Übung untersuchen Sie den Bericht im Power BI-Dienst.*

## **Erkunden des Berichts**

In dieser Aufgabe untersuchen Sie den Bericht im Power BI-Dienst.

1. Navigieren Sie in einem Microsoft Edge-Browserfenster zum Power BI-Dienst > **Mein Arbeitsbereich**, und wählen Sie den Bericht **Verkaufsanalyse** aus.

1. Um das Drillthroughfeature zu testen, navigieren Sie zur Seite **Übersicht** und zum visuellen Element **Menge nach Kategorie**. Klicken Sie dann mit der rechten Maustaste auf die Leiste **Kleidung**, und wählen Sie **Drillthrough \| Produktdetails** aus.

     ![Bild 130](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image55.png)

1. Beachten Sie, dass die Seite **Produktdetails** Informationen zu **Clothing** (Bekleidung) enthält.

1. Klicken Sie links oben auf die Pfeilschaltfläche, um zur Ausgangsseite zurückzukehren.

1. Wählen Sie die Seite **My Performance** (Meine Leistung) aus.

    *Wählen Sie die einzelnen Schaltflächen aus. Sie sehen, dass jeweils ein anderes Visual angezeigt wird.*

### **Abschluss**

Mit dieser Aufgabe schließen Sie das Lab ab.

Klicken Sie auf dem Banner auf der Fensterwebseite auf **Mein Arbeitsbereich**, um zurück zu Ihrem Arbeitsbereich zu navigieren.

![Bild 23](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image56.png)
