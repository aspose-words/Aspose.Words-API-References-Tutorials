---
title: Schriftarten als Base 64 exportieren
linktitle: Schriftarten als Base 64 exportieren
second_title: Aspose.Words für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Exportieren von Base-64-Schriftarten beim Speichern eines Dokuments mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-htmlsaveoptions/export-fonts-as-base-64/
---

In diesem Tutorial führen wir Sie durch den C#-Quellcode zum Exportieren von Base-64-Schriftarten mit Aspose.Words für .NET. Mit dieser Funktion können Sie Schriftarten als Base-64-Daten exportieren, wenn Sie ein Dokument im HTML-Format speichern.

## Schritt 1: Projekteinrichtung

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten IDE. Stellen Sie sicher, dass in Ihrem Projekt auf die Aspose.Words for .NET-Bibliothek verwiesen wird.

## Schritt 2: Laden des Dokuments

In diesem Schritt laden wir das zu exportierende Dokument. Verwenden Sie den folgenden Code, um das Dokument aus einem angegebenen Verzeichnis zu laden:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Dieser Code erstellt eine Instanz von`Document` durch Laden des Dokuments aus dem angegebenen Verzeichnis.

## Schritt 3: Konfigurieren der HTML-Backup-Optionen

Jetzt konfigurieren wir die HTML-Speicheroptionen für den Export von Base-64-Schriftarten. Verwenden Sie den folgenden Code:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };
```

 Dieser Code erstellt eine Instanz von`HtmlSaveOptions` und Sets`ExportFontsAsBase64` Zu`true` um anzugeben, dass Schriftarten beim Speichern als HTML als Base-64-Daten exportiert werden sollen.

## Schritt 4: Konvertieren und Speichern des Dokuments in HTML

Abschließend konvertieren wir das Dokument mithilfe der zuvor konfigurierten HTML-Speicheroptionen in HTML. Verwenden Sie den folgenden Code:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
```

Dieser Code konvertiert das Dokument in HTML und speichert es in einer Datei, wobei die Schriftarten als Base-64-Daten exportiert werden.

### Beispielquellcode für den Export von Schriftarten als Base 64 mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);

```

 Stellen Sie sicher, dass Sie den richtigen Pfad zum Dokumentenverzeichnis im angeben`dataDir` Variable.

Sie haben jetzt erfahren, wie Sie Base-64-Schriftarten exportieren, wenn Sie ein Dokument mit Aspose.Words für .NET als HTML speichern. Wenn Sie der Schritt-für-Schritt-Anleitung in diesem Tutorial folgen, können Sie Schriftarten ganz einfach sicher exportieren und in Ihre HTML-Dokumente einbetten.