---
demo:
  title: Verwalten von Dateien und semantischen Modellen in Power BI
  module: Deploy and manage Power BI service items
---
# Verwalten von Dateien und semantischen Modellen in Power BI

## Einrichten des Gateways (persönlicher Modus)

1. Laden Sie im Power BI-Dienst die Seite mit den Einstellungen für das semantische Modell neu (F5).

1. Erweitern Sie den Abschnitt „Gatewayverbindung“, und weisen Sie darauf hin, dass kein Gateway installiert ist.

1. Wählen Sie in der Dropdownliste für den Download (oben rechts) die Option Datengateway aus.

1. Laden Sie auf der neuen Webseite das Gateway im persönlichen Modus herunter.

1. Öffnen Sie nach dem Herunterladen die heruntergeladene Datei.

1. Schließen Sie die Gatewayeinrichtung mit Ihrem Organisationskonto ab.

1. Kehren Sie nach der Einrichtung zur Seite mit den semantischen Modelleinstellungen zurück und laden Sie sie erneut.

1. Weisen Sie das persönliche Gateway zu, und bearbeiten Sie die Anmeldeinformationen für die beiden Datenquellen.

1. Legen Sie für beide Datenquellen die Authentifizierungsmethode auf **WindowsWithoutImpersonation** und die Datenschutzebene auf **Organisation** fest.

1. Erweitern Sie optional den Abschnitt **Geplante Aktualisierung**, und zeigen Sie, wie eine Zeitplanserie konfiguriert wird.

## Aktualisieren Sie das semantische Modell

1. Öffnen Sie vor dem Aktualisieren des semantischen Modells das Dashboard für die **Umsatzüberwachung**.

1. Bearbeiten Sie die Details für die Kachel „Sales, Profit Margin“ (Umsatz, Rendite), um den letzten Aktualisierungszeitpunkt anzuzeigen.

1. Klicken Sie mit der rechten Maustaste auf die `D:\Allfiles\Demo\Resources\UpdateDatabase-LoadAdditionalSales.ps1`-Datei, und führen Sie sie dann mit PowerShell aus. *Dieses Skript lädt die Verkaufsdaten vom Dezember 2020 in die Datenbank.*

1. Aktualisieren Sie im Power BI-Dienst für den*die Kursleiter*in im Navigationsbereich das semantische Modell **Verkaufsanalyse**.

1. Weisen Sie nach Abschluss der Aktualisierung darauf hin, dass die Dashboardkachel mit der Spalte für **Dezember 2020** angezeigt wird und dass die Aktualisierungszeit **JETZT** ist.
