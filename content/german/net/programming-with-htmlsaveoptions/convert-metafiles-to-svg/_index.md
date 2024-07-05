---
title: Metadateien in SVG konvertieren
linktitle: Metadateien in SVG konvertieren
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Konvertieren von Metadateien in das SVG-Format beim Konvertieren eines Dokuments in HTML mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-htmlsaveoptions/convert-metafiles-to-svg/
---

In diesem Tutorial führen wir Sie durch den C#-Quellcode, um Metadateien mit Aspose.Words für .NET in das SVG-Format zu konvertieren. Mit dieser Funktion können Sie Metadateien in das SVG-Format konvertieren, wenn Sie ein Dokument in HTML konvertieren.

## Schritt 1: Projekt-Setup

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten IDE. Stellen Sie sicher, dass in Ihrem Projekt auf die Bibliothek Aspose.Words für .NET verwiesen wird.

## Schritt 2: Einfügen eines SVG-Bildes in das Dokument

In diesem Schritt fügen wir ein SVG-Bild in das zu konvertierende Dokument ein. Verwenden Sie den folgenden Code, um ein SVG-Bild mithilfe eines HTML-Tags einzufügen:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an SVG image: ");
builder.InsertHtml(
	@"<svg height='210' width='500'>
	<polygon points='100,10 40,198 190,78 10,78 160,198' 
		style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
</svg> ");
```

 Dieser Code erstellt eine Instanz von`Document` Und`DocumentBuilder` um das Dokument zu erstellen. Es fügt ein`<svg>` Tag mit einem`<polygon>` Element mit Attributen zum Definieren der Form und des Stils des SVG-Bildes.

## Schritt 3: HTML-Speicheroptionen festlegen

Nun legen wir die HTML-Speicheroptionen fest und geben an, dass Metadateien in das SVG-Format konvertiert werden sollen. Verwenden Sie den folgenden Code:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };
```

 Dieser Code erstellt eine Instanz von`HtmlSaveOptions` und Sets`MetafileFormat` Zu`HtmlMetafileFormat.Svg` um anzugeben, dass Metadateien bei der Konvertierung in HTML in das SVG-Format konvertiert werden sollen.

## Schritt 4: Konvertieren und Speichern des Dokuments im HTML-Format

Zum Schluss konvertieren wir das Dokument in HTML, indem wir die zuvor definierten HTML-Speicheroptionen verwenden. Verwenden Sie den folgenden Code:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
```

Dieser Code konvertiert das Dokument in HTML und speichert es in einer Datei, wobei die Metadateien in SVG konvertiert werden.

### Beispielquellcode zum Konvertieren von Metadateien in SVG mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Write("Here is an SVG image: ");
	builder.InsertHtml(
		@"<svg height='210' width='500'>
		<polygon points='100,10 40,198 190,78 10,78 160,198' 
			style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
	</svg> ");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
	
```
