---
title: Ressourcen exportieren
linktitle: Ressourcen exportieren
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Exportieren von Dokumentressourcen beim Speichern als HTML mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-htmlsaveoptions/export-resources/
---

In diesem Tutorial führen wir Sie durch den C#-Quellcode zum Exportieren von Dokumentressourcen mit Aspose.Words für .NET. Mit dieser Funktion können Sie Ressourcen wie Schriftarten als externe Dateien exportieren, wenn Sie ein Dokument im HTML-Format speichern.

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

Nun konfigurieren wir die HTML-Speicheroptionen, um die Dokumentressourcen zu exportieren. Verwenden Sie den folgenden Code:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
CssStyleSheetType = CssStyleSheetType.External,
ExportFontResources=true,
ResourceFolder = ArtifactsDir + "Resources",
ResourceFolderAlias = "http://example.com/resources"
};
```

 Dieser Code erstellt eine Instanz von`HtmlSaveOptions` und legt die folgenden Optionen fest:

- `CssStyleSheetType` ist eingestellt auf`CssStyleSheetType.External`um das CSS-Stylesheet in eine externe Datei zu exportieren.
- `ExportFontResources` ist eingestellt auf`true` um Schriftressourcen zu exportieren.
- `ResourceFolder` Gibt das Zielverzeichnis an, in dem die Ressourcen gespeichert werden.
- `ResourceFolderAlias` Gibt den URL-Alias an, der für den Zugriff auf Ressourcen verwendet wird.

## Schritt 4: Konvertieren und Speichern des Dokuments im HTML-Format

Zum Schluss konvertieren wir das Dokument in HTML, indem wir die zuvor konfigurierten HTML-Speicheroptionen verwenden. Verwenden Sie den folgenden Code:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
```

Dieser Code konvertiert das Dokument in HTML und speichert die Ressourcen unter Verwendung des angegebenen URL-Alias im angegebenen Verzeichnis.

### Beispielquellcode für Exportressourcen mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External,
		ExportFontResources = true,
		ResourceFolder = ArtifactsDir + "Resources",
		ResourceFolderAlias = "http://example.com/resources"
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
  
```

 Achten Sie darauf, den korrekten Pfad zum Dokumentenverzeichnis im`dataDir` Variable.