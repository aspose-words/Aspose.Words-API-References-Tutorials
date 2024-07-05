---
title: Präfix für CSS-Klassennamen hinzufügen
linktitle: Präfix für CSS-Klassennamen hinzufügen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Hinzufügen eines CSS-Klassennamenpräfixes beim Konvertieren eines Dokuments in HTML mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-htmlsaveoptions/add-css-class-name-prefix/
---

In diesem Tutorial führen wir Sie durch den C#-Quellcode, um mit Aspose.Words für .NET ein CSS-Klassennamenpräfix hinzuzufügen. Mit dieser Funktion können Sie beim Konvertieren eines Dokuments in HTML ein benutzerdefiniertes Präfix zu generierten CSS-Klassennamen hinzufügen.

## Schritt 1: Projekt-Setup

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten IDE. Stellen Sie sicher, dass in Ihrem Projekt auf die Bibliothek Aspose.Words für .NET verwiesen wird.

## Schritt 2: Dokument einlegen

In diesem Schritt laden wir das Word-Dokument, das wir in HTML konvertieren möchten. Verwenden Sie den folgenden Code, um das Dokument zu laden:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Ersetzen`"YOUR DOCUMENTS DIRECTORY"` durch den tatsächlichen Pfad des Verzeichnisses, in dem sich Ihr Dokument befindet.

## Schritt 3: HTML-Speicheroptionen festlegen

Jetzt legen wir die HTML-Speicheroptionen fest, einschließlich CSS-Stylesheet-Typ und CSS-Klassennamenpräfix. Verwenden Sie den folgenden Code:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
     CssStyleSheetType = CssStyleSheetType.External,
     CssClassNamePrefix = "pfx_"
};
```

 Dieser Code erstellt eine Instanz von`HtmlSaveOptions` und Sets`CssStyleSheetType` Zu`CssStyleSheetType.External`ein externes CSS-Stylesheet zu generieren und`CssClassNamePrefix` Zu`"pfx_"` voranstellen`"pfx_"` zur Benennung der CSS-Klasse.

## Schritt 4: Konvertieren und Speichern des Dokuments im HTML-Format

Zum Schluss konvertieren wir das Dokument in HTML, indem wir die zuvor definierten HTML-Speicheroptionen verwenden. Verwenden Sie den folgenden Code:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
```

Dieser Code konvertiert das Dokument in HTML und speichert es in einer Datei mit dem hinzugefügten Präfix des CSS-Klassennamens.

### Beispielquellcode zum Hinzufügen eines CSS-Klassennamenpräfixes mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External, CssClassNamePrefix = "pfx_"
	};
	
	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);

```

 Achten Sie darauf, den korrekten Dokumentpfad im`dataDir` Variable.

Sie haben jetzt gelernt, wie Sie beim Konvertieren eines Dokuments in HTML mit Aspose.Words für .NET ein CSS-Klassennamenpräfix hinzufügen. Wenn Sie der Schritt-für-Schritt-Anleitung in diesem Tutorial folgen, können Sie die CSS-Klassennamen in Ihren konvertierten HTML-Dokumenten anpassen.