---
title: Präfix für CSS-Klassennamen hinzufügen
linktitle: Präfix für CSS-Klassennamen hinzufügen
second_title: Aspose.Words für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Hinzufügen eines CSS-Klassennamenpräfixes beim Konvertieren eines Dokuments in HTML mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-htmlsaveoptions/add-css-class-name-prefix/
---

In diesem Tutorial führen wir Sie durch den C#-Quellcode, um mit Aspose.Words für .NET ein CSS-Klassennamenpräfix hinzuzufügen. Mit dieser Funktion können Sie beim Konvertieren eines Dokuments in HTML den generierten CSS-Klassennamen ein benutzerdefiniertes Präfix hinzufügen.

## Schritt 1: Projekteinrichtung

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten IDE. Stellen Sie sicher, dass in Ihrem Projekt auf die Aspose.Words for .NET-Bibliothek verwiesen wird.

## Schritt 2: Laden des Dokuments

In diesem Schritt laden wir das Word-Dokument, das wir in HTML konvertieren möchten. Verwenden Sie den folgenden Code, um das Dokument zu laden:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem tatsächlichen Pfad des Verzeichnisses, in dem sich Ihr Dokument befindet.

## Schritt 3: HTML-Speicheroptionen festlegen

Legen wir nun die HTML-Speicheroptionen fest, einschließlich des CSS-Stylesheet-Typs und des CSS-Klassennamenpräfixes. Verwenden Sie den folgenden Code:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
     CssStyleSheetType = CssStyleSheetType.External,
     CssClassNamePrefix = "pfx_"
};
```

 Dieser Code erstellt eine Instanz von`HtmlSaveOptions` und Sets`CssStyleSheetType` Zu`CssStyleSheetType.External` um ein externes CSS-Stylesheet zu generieren und`CssClassNamePrefix` Zu`"pfx_"`voranstellen`"pfx_"` um CSS-Klassen zu benennen.

## Schritt 4: Konvertieren und Speichern des Dokuments in HTML

Abschließend konvertieren wir das Dokument mithilfe der zuvor definierten HTML-Speicheroptionen in HTML. Verwenden Sie den folgenden Code:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
```

Dieser Code konvertiert das Dokument in HTML und speichert es in einer Datei mit dem hinzugefügten CSS-Klassennamenpräfix.

### Beispielquellcode für das Hinzufügen eines CSS-Klassennamenpräfixes mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External, CssClassNamePrefix = "pfx_"
	};
	
	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);

```

 Stellen Sie sicher, dass Sie den richtigen Dokumentpfad angeben`dataDir` Variable.

Sie haben jetzt erfahren, wie Sie beim Konvertieren eines Dokuments in HTML mit Aspose.Words für .NET ein CSS-Klassennamenpräfix hinzufügen. Wenn Sie der Schritt-für-Schritt-Anleitung in diesem Tutorial folgen, können Sie die CSS-Klassennamen in Ihren konvertierten HTML-Dokumenten anpassen.