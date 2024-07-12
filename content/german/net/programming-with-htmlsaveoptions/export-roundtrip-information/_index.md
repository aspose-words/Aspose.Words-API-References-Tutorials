---
title: Informationen zum Exportieren von Roundtrips
linktitle: Informationen zum Exportieren von Roundtrips
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Exportieren von Roundtrip-Informationen beim Speichern eines Dokuments als HTML mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-htmlsaveoptions/export-roundtrip-information/
---

In diesem Tutorial führen wir Sie durch den C#-Quellcode zum Exportieren von Roundtrip-Informationen aus einem Dokument mit Aspose.Words für .NET. Mit dieser Funktion können Sie Roundtrip-Informationen in die exportierte HTML-Datei aufnehmen, wodurch sich Änderungen am Originaldokument leichter abrufen lassen.

## Schritt 1: Projekt-Setup

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten IDE. Stellen Sie sicher, dass in Ihrem Projekt auf die Bibliothek Aspose.Words für .NET verwiesen wird.

## Schritt 2: Dokument einlegen

In diesem Schritt laden wir das zu exportierende Dokument. Verwenden Sie den folgenden Code, um das Dokument aus einem angegebenen Verzeichnis zu laden:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Dieser Code erstellt eine Instanz von`Document` durch Laden des Dokuments aus dem angegebenen Verzeichnis.

## Schritt 3: Konfigurieren der HTML-Sicherungsoptionen

Nun konfigurieren wir die HTML-Speicheroptionen, um die Roundtrip-Informationen des Dokuments zu exportieren. Verwenden Sie den folgenden Code:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };
```

 Dieser Code erstellt eine Instanz von`HtmlSaveOptions`und setzt den`ExportRoundtripInformation` Möglichkeit,`true` um Roundtrip-Informationen beim Export einzuschließen.

## Schritt 4: Konvertieren und Speichern des Dokuments im HTML-Format

Zum Schluss konvertieren wir das Dokument in HTML, indem wir die zuvor konfigurierten HTML-Speicheroptionen verwenden. Verwenden Sie den folgenden Code:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
```

Dieser Code konvertiert das Dokument einschließlich der Roundtrip-Informationen in HTML und speichert die exportierte HTML-Datei im angegebenen Verzeichnis.

### Beispielquellcode für den Export von Roundtrip-Informationen mit Aspose.Words für .NET


```csharp

	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);

```

 Achten Sie darauf, den korrekten Pfad zum Dokumentenverzeichnis im`dataDir` Variable.