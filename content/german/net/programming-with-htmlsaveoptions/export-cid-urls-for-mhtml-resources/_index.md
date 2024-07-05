---
title: CID-URLs für MHTML-Ressourcen exportieren
linktitle: CID-URLs für MHTML-Ressourcen exportieren
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Exportieren von CID-URLs von MHTML-Ressourcen beim Speichern eines Dokuments mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-htmlsaveoptions/export-cid-urls-for-mhtml-resources/
---

In diesem Tutorial führen wir Sie durch den C#-Quellcode zum Exportieren von CID-URLs für MHTML-Ressourcen mit Aspose.Words für .NET. Mit dieser Funktion können Sie CID-URLs von MHTML-Ressourcen exportieren, wenn Sie ein Dokument im MHTML-Format speichern.

## Schritt 1: Projekt-Setup

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten IDE. Stellen Sie sicher, dass in Ihrem Projekt auf die Bibliothek Aspose.Words für .NET verwiesen wird.

## Schritt 2: Dokument einlegen

In diesem Schritt laden wir das zu exportierende Dokument. Verwenden Sie den folgenden Code, um das Dokument aus einem angegebenen Verzeichnis zu laden:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Content-ID.docx");
```

 Dieser Code erstellt eine Instanz von`Document` durch Laden des Dokuments aus dem angegebenen Verzeichnis.

## Schritt 3: Konfigurieren der HTML-Sicherungsoptionen

Nun konfigurieren wir HTML-Speicheroptionen, um CID-URLs von MHTML-Ressourcen zu exportieren. Verwenden Sie den folgenden Code:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
{
PrettyFormat = true,
ExportCidUrlsForMhtmlResources = true
};
```

 Dieser Code erstellt eine Instanz von`HtmlSaveOptions` mit dem Speicherformat MHTML. Es ermöglicht auch den Export von CID-URLs von MHTML-Ressourcen durch die Einstellung`ExportCidUrlsForMhtmlResources` Zu`true`.

## Schritt 4: Konvertieren und Speichern des Dokuments im MHTML-Format

Zum Schluss konvertieren wir das Dokument in MHTML, indem wir die zuvor konfigurierten HTML-Speicheroptionen verwenden. Verwenden Sie den folgenden Code:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);
```

Dieser Code konvertiert das Dokument in MHTML und speichert es in einer Datei mit den CID-URLs der exportierten MHTML-Ressourcen.

### Beispielquellcode zum Exportieren von Cid-URLs für Mhtml-Ressourcen mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Content-ID.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
	{
		PrettyFormat = true, ExportCidUrlsForMhtmlResources = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);

```

 Achten Sie darauf, den korrekten Pfad zum Dokumentenverzeichnis im`dataDir` Variable.

Sie haben jetzt gelernt, wie Sie CID-URLs von MHTML-Ressourcen exportieren, wenn Sie ein Dokument im MHTML-Format mit Aspose.Words für .NET speichern. Indem Sie der Schritt-für-Schritt-Anleitung in diesem Tutorial folgen, können Sie CID-URLs in Ihren exportierten MHTML-Dokumenten problemlos verwalten.

