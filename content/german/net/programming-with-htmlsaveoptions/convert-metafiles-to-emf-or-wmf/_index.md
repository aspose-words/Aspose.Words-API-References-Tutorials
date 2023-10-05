---
title: Konvertieren Sie Metadateien in EMF oder WMF
linktitle: Konvertieren Sie Metadateien in EMF oder WMF
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Konvertieren von Metadateien in EMF- oder WMF-Formate beim Konvertieren eines Dokuments in HTML mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-htmlsaveoptions/convert-metafiles-to-emf-or-wmf/
---

In diesem Tutorial führen wir Sie durch den C#-Quellcode zum Konvertieren von Metadateien in das EMF- oder WMF-Format mit Aspose.Words für .NET. Mit dieser Funktion können Sie Bilder im Metadateiformat in kompatiblere Formate wie EMF oder WMF konvertieren, wenn Sie ein Dokument in HTML konvertieren.

## Schritt 1: Projekteinrichtung

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten IDE. Stellen Sie sicher, dass in Ihrem Projekt auf die Aspose.Words for .NET-Bibliothek verwiesen wird.

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

 Dieser Code erstellt eine Instanz von`Document` Und`DocumentBuilder` um das Dokument zu erstellen. Es fügt ein`<img>` Tag mit einem Base64-codierten Bild in das Dokument einfügen.

## Schritt 3: HTML-Speicheroptionen festlegen

Jetzt legen wir die HTML-Speicheroptionen fest, einschließlich des für Bilder zu verwendenden Metadateiformats. Verwenden Sie den folgenden Code:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };
```

 Dieser Code erstellt eine Instanz von`HtmlSaveOptions` und Sets`MetafileFormat` Zu`HtmlMetafileFormat.EmfOrWmf` um anzugeben, dass Metadateien bei der Konvertierung in HTML in das EMF- oder WMF-Format konvertiert werden sollen.

## Schritt 4: Konvertieren und Speichern des Dokuments in HTML

Abschließend konvertieren wir das Dokument mithilfe der zuvor definierten HTML-Speicheroptionen in HTML. Verwenden Sie den folgenden Code:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);
```

Dieser Code konvertiert das Dokument in HTML und speichert es in einer Datei mit den konvertierten Metadateien im EMF- oder WMF-Format, abhängig von den festgelegten Speicheroptionen.

### Beispielquellcode für die Konvertierung von Metadateien in EMF oder WMF mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
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

 Stellen Sie sicher, dass Sie den richtigen Pfad zum Dokumentenverzeichnis im angeben`dataDir` Variable.

Sie haben jetzt gelernt, wie Sie Metadateien in EMF- oder WMF-Formate konvertieren, wenn Sie ein Dokument mit Aspose.Words für .NET in HTML konvertieren. Wenn Sie der Schritt-für-Schritt-Anleitung in diesem Tutorial folgen, können Sie Metadateien in Ihren konvertierten HTML-Dokumenten problemlos verwalten.