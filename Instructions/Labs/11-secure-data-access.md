---
lab:
  title: Sicherer Datenzugriff in Power BI
  module: Secure data access in Power BI
---

# Sicherer Datenzugriff in Power BI

## Labszenario

In diesem Lab erzwingen Sie die Sicherheit auf Zeilenebene, um sicherzustellen, dass ein Vertriebsmitarbeiter nur die Vertriebsdaten für die ihm zugewiesenen Regionen analysieren kann.

In diesem Lab lernen Sie Folgendes:

- Erzwingen von Sicherheit auf Zeilenebene
- Wählen Sie zwischen dynamischen und statischen Methoden aus.

**Dieses Lab sollte ungefähr 20 Minuten in Anspruch nehmen.**

## Erste Schritte

Um diese Übung abzuschließen, öffnen Sie zuerst einen Webbrowser, und geben Sie die folgende URL ein, um den ZIP-Ordner herunterzuladen:

`https://github.com/MicrosoftLearning/PL-300-Microsoft-Power-BI-Data-Analyst/raw/Main/Allfiles/Labs/11-secure-data-access/11-secure-data.zip`

Extrahieren Sie den Ordner in den Ordner **C:\Benutzer\Student\Downloads\11-secure-data**.

Öffnen Sie die Datei **11-Starter-Sales Analysis.pbix**.

> ***Hinweis**: Sie können die Anmeldung abbrechen, indem Sie **Abbrechen** wählen. Schließen Sie alle anderen Informationsfenster. Wählen Sie **Später anwenden**, wenn Sie aufgefordert werden, die Änderungen anzuwenden.*

## Erzwingen von Sicherheit auf Zeilenebene

In dieser Aufgabe erzwingen Sie Sicherheit auf Zeilenebene, um sicherzustellen, dass Vertriebsmitarbeiter nur Umsätze in den zugewiesenen Regionen anzeigen können.

1. Wechseln Sie zur Tabellenansicht.

   ![Bild 5.701](Linked_image_Files/11-secure-data-access_image20.png)

1. Wählen Sie im Bereich **Daten** die Tabelle **Salesperson (Performance)** aus.

1. Wenn Sie die Daten überprüfen, werden Sie bemerken, dass Michael Blythe (EmployeeKey 281) den UPN-Wert **`michael-blythe@adventureworks.com`** hat.
    
    > *Sie werden sich erinnern, dass Michael Blythe drei Vertriebsregionen zugewiesen ist: „USA, Nordosten“, „USA, Mitte“ und „USA, Südosten“.*

1. Wählen Sie auf der Registerkarte des Menübands **Startseite** innerhalb der Gruppe **Sicherheit** die Option **Rollen verwalten**.

    ![Bild 5.700](Linked_image_Files/11-secure-data-access_image21.png)

1. Wählen Sie im Fenster **Sicherheitsrollen verwalten** im Abschnitt **Rollen** die Option **Neu**.

1. Ersetzen Sie im Feld den ausgewählten Text durch den Namen der Rolle: Geben Sie **Salespeople** ein, und drücken Sie dann die **EINGABETASTE**.

   ![Bild 5.703](Linked_image_Files/11-secure-data-access_image23.png)

1. Um einen Filter zuzuweisen, markieren Sie die Tabelle **Salesperson (Performance)** und wählen dann **Zum DAX-Editor wechseln** im Abschnitt **Daten filtern**.

   ![Bild 5.703](Linked_image_Files/11-secure-data-access_image24.png)

1. Geben Sie im DAX-Editorfeld den folgenden Ausdruck ein:

    ```DAX
    [UPN] = USERPRINCIPALNAME()
    ```

   ![Abbildung 11](Linked_image_Files/11-secure-data-access_image25.png)

    > *USERPRINCIPALNAME() ist eine DAX-Funktion (Data Analysis Expressions), die den Namen des authentifizierten Benutzers zurückgibt. Dies bedeutet, dass die Tabelle **Salesperson (Performance)** nach dem Benutzerprinzipalnamen (User Principal Name, UPN) des Benutzers gefiltert wird, der das Modell abfragt.*

1. Wählen Sie **Speichern** und **Schließen** aus.

1. Um die Sicherheitsrolle zu testen, wählen Sie auf der Registerkarte des Menübands **Startseite** in der Gruppe **Sicherheit** die Option **Anzeigen als**.

   ![Bild 5.708](Linked_image_Files/11-secure-data-access_image27.png)

1. Aktivieren Sie im Fenster **Als Rollen anzeigen** das Element **Anderer Benutzer**, und geben Sie dann in das entsprechende Feld Folgendes ein: **`michael-blythe@adventureworks.com`**

1. Aktivieren Sie die Rolle **Salespeople**, und klicken Sie auf **OK**.
    
    > *Diese Konfiguration führt dazu, dass die Rolle **Salespeople** verwendet und die Identität des Benutzers mit dem Namen „Michael Blythe“ angenommen wird.*

   ![Bild 5.709](Linked_image_Files/11-secure-data-access_image28.png)

1. Beachten Sie das gelbe Banner oberhalb der Berichtsseite, das den Testsicherheitskontext angibt.

   ![Bild 13](Linked_image_Files/11-secure-data-access_image30.png)

1. Beachten Sie, dass im Tabellenvisual nur der Vertriebsmitarbeiter **Michael Blythe** aufgeführt ist.

   ![Bild 5.713](Linked_image_Files/11-secure-data-access_image31.png)

1. Wählen Sie zum Beenden des Tests auf der rechten Seite des gelben Banners **Anzeige beenden** aus.

   ![Bild 5.712](Linked_image_Files/11-secure-data-access_image32.png)

1. Um die Rolle **Salespeople** zu löschen, wählen Sie auf der Registerkarte des Menübands **Startseite** in der Gruppe **Sicherheit** die Option **Rollen verwalten**.

   ![Abbildung 16](Linked_image_Files/11-secure-data-access_image33.png)

1. Wählen Sie im Fenster **Sicherheitsrollen verwalten** die Auslassungspunkte (...) bei der Rolle **Salespeople** und wählen Sie **Löschen**. Wenn Sie aufgefordert werden, den Löschvorgang zu bestätigen, wählen Sie **Ja, Löschen** aus.

   ![Abbildung 34](Linked_image_Files/11-secure-data-access_image34.png)

*Hinweis: Wenn die Power BI Desktop-Datei im Power BI-Dienst veröffentlicht wird, müssen Sie noch eine Aufgabe nach der Veröffentlichung durchführen, um der Rolle **Salespeople** Sicherheitsprinzipale zuzuordnen. Das erledigen Sie in diesem Lab nicht.*

## Lab abgeschlossen
