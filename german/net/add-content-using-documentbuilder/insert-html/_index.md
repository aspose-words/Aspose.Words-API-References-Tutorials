---
title: HTML einfügen
linktitle: HTML einfügen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET HTML-Inhalte in Word-Dokumente einfügen. Schritt für Schritt Anleitung.
type: docs
weight: 10
url: /de/net/add-content-using-documentbuilder/insert-html/
---

In diesem umfassenden Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET HTML-Inhalte in ein Word-Dokument einfügen. Wir führen Sie durch den Prozess und stellen Ihnen die notwendigen C#-Code-Snippets zur Verfügung. Am Ende dieser Anleitung werden Sie in der Lage sein, Ihren Word-Dokumenten HTML-Elemente, Formatierungen und Stile hinzuzufügen.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Aspose.Words für .NET-Bibliothek auf Ihrem System installiert.

## Schritt 1: Erstellen Sie ein neues Dokument und einen neuen DocumentBuilder
Erstellen Sie zunächst ein neues Dokument mit der Document-Klasse und initialisieren Sie ein DocumentBuilder-Objekt:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: HTML-Inhalt einfügen
Als nächstes verwenden Sie die InsertHtml-Methode der DocumentBuilder-Klasse, um HTML-Inhalte in das Dokument einzufügen. Sie können HTML-Tags, Attribute und Stile in die HTML-Zeichenfolge einfügen:

```csharp
builder.InsertHtml(
	"<P align='right'>Paragraph right</P>" +
	"<b>Implicit paragraph left</b>" +
	"<div align='center'>Div center</div>" +
	"<h1 align='left'>Heading 1 left.</h1>");
```

## Schritt 3: Speichern Sie das Dokument
Speichern Sie das Dokument nach dem Einfügen des HTML-Inhalts mit der Save-Methode der Document-Klasse in einer Datei:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHtml.docx");
```

## Beispielquellcode zum Einfügen von HTML mit Aspose.Words für .NET
Hier ist der vollständige Quellcode zum Einfügen von HTML-Inhalten in ein Word-Dokument mit Aspose.Words für .NET:
Diese Funktion ist besonders nützlich, wenn Sie über vorhandenen HTML-Inhalt verfügen, den Sie in Ihre Word-Dokumente einbinden und dabei die ursprüngliche Formatierung und das ursprüngliche Layout beibehalten möchten.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertHtml(
	"<P align='right'>Paragraph right</P>" +
	"<b>Implicit paragraph left</b>" +
	"<div align='center'>Div center</div>" +
	"<h1 align='left'>Heading 1 left.</h1>");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHtml.docx");
```

Denken Sie daran, den Code an Ihren spezifischen HTML-Inhalt und Ihre Anforderungen anzupassen. Stellen Sie sicher, dass Ihr HTML wohlgeformt und mit Aspose.Words für .NET kompatibel ist.

## Abschluss
Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Words für .NET HTML-Inhalte in ein Word-Dokument einfügen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie jetzt HTML-Elemente, Formatierungen und Stile in Ihre Word-Dokumente integrieren.


