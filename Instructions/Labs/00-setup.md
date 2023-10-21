---
lab:
  title: Einrichten einer eigenen Umgebung
  module: Set up your own environment
---

# Einrichten einer lokalen Labumgebung

Idealerweise sollten Sie diese Labs in einer gehosteten Labumgebung absolvieren. Wenn Sie sie auf Ihrem eigenen Computer durchführen möchten, können Sie dazu die folgende Software installieren.

- Alle Setup- und Ressourcendateien können [von GitHub heruntergeladen](https://github.com/MicrosoftLearning/PL-300-Microsoft-Power-BI-Data-Analyst/raw/Main/AllfilesDownload.zip) werden.
  - Extrahieren Sie den Ordner „AllFiles“ in D:/, und benennen Sie ihn in „PL300“ um.

***Möglicherweise werde unerwartete Dialogfelder angezeigt oder unerwartetes Verhalten tritt auf, wenn Sie Ihre eigene Umgebung verwenden. Aufgrund der Vielzahl möglicher lokaler Konfigurationen kann sich das Kursteam um Probleme, die in Ihrer eigenen Umgebung auftreten können, nicht kümmern.***

## Anweisungen zur Verwendung von Windows 11

> &#128221; Die folgenden Anweisungen beziehen sich auf einen Windows 11-Computer. Das Benutzererlebnis beim Herstellen einer Verbindung von unterschiedlichen Benutzeroberflächen kann sich unterscheiden.

### Power BI Desktop

1. Laden Sie die Anwendung aus dem Microsoft Store herunter, und installieren Sie sie. Wenn Sie keinen Zugriff auf den Microsoft Store haben, laden Sie sie aus dem [Internet](https://www.microsoft.com/download/details.aspx?id=58494) herunter. Power BI Desktop ist die primäre Anwendung für diese Labs.

    - Verwenden Sie die Standardoptionen im Installationsprogramm.

### M365-Entwicklerkonto

Für einige der Übungen müssen Sie sich mit einem Organisationskonto bei Power BI anmelden. Sie können Ihr eigenes verwenden, aber wenn Sie keinen Zugriff haben, können Sie ein kostenloses [M365 Developer-Konto](https://developer.microsoft.com/en-us/microsoft-365/dev-program) erstellen.

### SQL Server-Datenbank-Engine

1. Das Lab stellt eine Verbindung mit einer Localhost-Instanz auf SQL Server her. Die folgenden Anweisungen helfen Ihnen beim Installieren von SQL Server und Konfigurieren der Standardoptionen. Sie müssen nur das Datenbank-Engine-Feature installieren.

    - Laden Sie die kostenlose [Entwicklerkopie des Installationsmediums](https://www.microsoft.com/sql-server/sql-server-downloads?SilentAuth=1&f=255&MSPPError=-2147217396&rtc=1) herunter.
    - [Installieren von SQL Server über den Installations-Assistenten (Setup)](https://learn.microsoft.com/sql/database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup)

> &#128221; Sie können eine vorhandene SQL Server-Instanz verwenden, wenn Sie Zugriff haben, anstatt eine lokale Version zu installieren. Sie müssen jedoch die Verbindungszeichenfolge von „localhost“ in den Namen Ihrer Instanz ändern.

### Microsoft Edge

1. Installieren Sie die neueste Version von [Microsoft Edge](https://microsoft.com/edge), um online auf den Power BI-Dienst zuzugreifen.
