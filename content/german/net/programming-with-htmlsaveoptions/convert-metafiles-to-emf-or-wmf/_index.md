---
title: Metadateien in EMF oder WMF konvertieren
linktitle: Metadateien in EMF oder WMF konvertieren
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Konvertieren von Metadateien in die Formate EMF oder WMF bei der Konvertierung eines Dokuments in HTML mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-htmlsaveoptions/convert-metafiles-to-emf-or-wmf/
---

In diesem Tutorial führen wir Sie durch den C#-Quellcode, um Metadateien mit Aspose.Words für .NET in das EMF- oder WMF-Format zu konvertieren. Mit dieser Funktion können Sie Bilder im Metadateiformat in kompatiblere Formate wie EMF oder WMF konvertieren, wenn Sie ein Dokument in HTML konvertieren.

## Schritt 1: Projekt-Setup

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten IDE. Stellen Sie sicher, dass in Ihrem Projekt auf die Bibliothek Aspose.Words für .NET verwiesen wird.

## Schritt 2: Einfügen eines Bildes in das Dokument

In diesem Schritt fügen wir ein Bild in das zu konvertierende Dokument ein. Verwenden Sie den folgenden Code, um mithilfe eines HTML-Tags ein Bild aus einer Datenquelle einzufügen:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an image as is: ");
builder.InsertHtml(
	@"<img src=""data:image/png;base64,
		iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
		C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
		AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
		REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
		ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
		vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");
```

 Dieser Code erstellt eine Instanz von`Document` Und`DocumentBuilder` um das Dokument zu erstellen. Es fügt ein`<img>` Tag mit einem Base64-codierten Bild in das Dokument.

## Schritt 3: HTML-Speicheroptionen festlegen

Nun legen wir die HTML-Speicheroptionen fest, einschließlich des für Bilder zu verwendenden Metadateiformats. Verwenden Sie den folgenden Code:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };
```

 Dieser Code erstellt eine Instanz von`HtmlSaveOptions` und Sets`MetafileFormat` Zu`HtmlMetafileFormat.EmfOrWmf` um anzugeben, dass Metadateien bei der Konvertierung in HTML in das EMF- oder WMF-Format konvertiert werden sollen.

## Schritt 4: Konvertieren und Speichern des Dokuments im HTML-Format

Zum Schluss konvertieren wir das Dokument in HTML, indem wir die zuvor definierten HTML-Speicheroptionen verwenden. Verwenden Sie den folgenden Code:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);
```

Dieser Code konvertiert das Dokument in HTML und speichert es in einer Datei mit den konvertierten Metadateien im EMF- oder WMF-Format, je nach den festgelegten Speicheroptionen.

### Beispielquellcode zum Konvertieren von Metadateien in EMF oder WMF mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Here is an image as is: ");
	builder.InsertHtml(
		@"<img src=""data:image/png;base64,
			iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
			C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
			AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
			REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
			ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
			vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);

```

 Achten Sie darauf, den korrekten Pfad zum Dokumentenverzeichnis im`dataDir` Variable.

Sie haben nun gelernt, wie Sie Metadateien in die Formate EMF oder WMF konvertieren, wenn Sie ein Dokument mit Aspose.Words für .NET in HTML konvertieren. Indem Sie der Schritt-für-Schritt-Anleitung in diesem Tutorial folgen, können Sie Metadateien in Ihren konvertierten HTML-Dokumenten problemlos verwalten.