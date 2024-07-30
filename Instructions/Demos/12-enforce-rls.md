---
demo:
  title: "Erzwingen der Sicherheit auf Zeilenebene in Power\_BI"
  module: Deploy and manage Power BI service items
---

# Erzwingen der Sicherheit auf Zeilenebene in Power BI

## Hinzufügen einer Sicherheitstabelle zum Modell

1. Öffnen Sie in Power BI Desktop das Fenster „Power Query-Editor“.

1. Fügen Sie eine neue Abfrage basierend auf der `D:\Demo\Data\**ManagerCategory**.xlsx`-Datei hinzu.

1. Verwenden Sie die **ManagerCategory**-Tabelle in der Datei.

1. Entfernen Sie die Spalte **Manager**.

1. Verwenden Sie das Semikolon als Trennzeichen, um die Spalte **Category** in Zeilen aufzuteilen (erweiterte Optionen).

1. Ersetzen Sie in der Spalte **Email** den Wert **<ty-johnston@tailspintoys.com>** durch das Empfängerkonto (aus der Datei „MySettings.txt“).

1. Weisen Sie darauf hin, dass dieser Benutzer drei Produktkategorien anzeigen kann: **Collective Pitch, Trainer und Warbird**.

1. Schließen Sie die Abfragen, und wenden Sie sie an.

1. Erstellen Sie in der Modellansicht eine Beziehung zwischen den Tabellen **ManagerCategory** und „Product“, und verknüpfen Sie dabei die **Category**-Spalte.

1. Legen Sie die Kreuzfilterrichtung auf „Single“ (**ManagerCategory** filtert „Product“) fest.

1. Blenden Sie die Tabelle **ManagerCategory** aus.

## Hinzufügen einer Rolle

1. Öffnen Sie in der Berichtsansicht „Rollen verwalten“, und erstellen Sie dann eine Rolle namens **Manager**.

1. Filtern Sie in der Rolle die Adressspalte „Email“ der Tabelle **ManagerCategory** wie folgt:

  ```dax
   [Email] = USERPRINCIPALNAME()
   ```

1. **Speichern** Sie sie.

## Überprüfen der Rolle

1. Öffnen Sie Anzeigen als, und konfigurieren Sie die folgenden Einstellungen:

    - Anderer Benutzer: Überprüfen Sie das Empfängerkonto, und geben Sie es dann ein.

    - Managerrolle: Überprüfen

1. Weisen Sie darauf hin, dass das Filtervisual nur drei Produktkategorien anzeigt.

1. Beenden Sie die Anzeige des Berichts mithilfe der Optionen vom Typ „Anzeigen als“.

1. Speichern Sie die Power BI Desktop-Datei.

1. Veröffentlichen Sie die Power BI Desktop-Datei im Arbeitsbereich, und überschreiben Sie dabei das semantische Modell und den Bericht im Dienst.

1. Schließen Sie Power BI Desktop.

## Konfigurieren der Sicherheit des semantischen Modells

1. Öffnen Sie im Power BI-Dienst für den*die Kursleiter*in im Navigationsbereich die Sicherheitsseite für das semantische Modell **Verkaufsanalyse**.

1. Geben Sie im Abschnitt **Mitglieder** das Empfängerkonto (für Ty Johnston) ein.

1. Hinzufügen und Speichern.

## Testen der Sicherheit auf Zeilenebene in der App

1. Aktualisieren Sie im Power BI-Dienst für den Empfänger das Dashboard (noch aus der vorherigen Demo geöffnet).

1. Überprüfen Sie auf der Dashboardkachel **Profit Margin** (Rendite), ob nur drei Produktkategorien angezeigt werden.
