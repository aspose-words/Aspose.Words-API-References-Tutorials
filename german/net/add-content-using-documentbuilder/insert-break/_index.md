---
title: Pause einfügen
linktitle: Pause einfügen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Seitenumbrüche in Word-Dokumente einfügen. Schritt für Schritt Anleitung.
type: docs
weight: 10
url: /de/net/add-content-using-documentbuilder/insert-break/
---

In diesem umfassenden Beispiel erfahren Sie, wie Sie mithilfe der InsertBreak-Methode in Aspose.Words für .NET Seitenumbrüche in ein Word-Dokument einfügen. Wir führen Sie durch den Prozess und stellen Ihnen die notwendigen C#-Code-Snippets zur Verfügung. Am Ende dieses Handbuchs werden Sie in der Lage sein, Seitenumbrüche in Ihrem Dokument zu steuern.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Aspose.Words für .NET-Bibliothek auf Ihrem System installiert.

## Schritt 1: Erstellen Sie ein neues Dokument und einen neuen DocumentBuilder
Erstellen Sie zunächst ein neues Dokument mit der Document-Klasse und initialisieren Sie ein DocumentBuilder-Objekt:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Inhalt und Seitenumbrüche einfügen
Als nächstes verwenden Sie die Writeln-Methode der DocumentBuilder-Klasse, um dem Dokument Inhalte hinzuzufügen. Um einen Seitenumbruch einzufügen, verwenden Sie die Methode InsertBreak mit dem Parameter BreakType.PageBreak:

```csharp
builder.Writeln("This is page 1.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 2.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 3.");
```

## Schritt 3: Speichern Sie das Dokument
Nachdem Sie den Inhalt und die Seitenumbrüche eingefügt haben, speichern Sie das Dokument mit der Save-Methode der Document-Klasse in einer Datei:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertBreak.docx");
```

### Beispielquellcode für Insert Break mit Aspose.Words für .NET
Hier ist der vollständige Quellcode zum Einfügen von Seitenumbrüchen mit Aspose.Words für .NET:

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("This is page 1.");
	builder.InsertBreak(BreakType.PageBreak);

	builder.Writeln("This is page 2.");
	builder.InsertBreak(BreakType.PageBreak);

	builder.Writeln("This is page 3.");

	doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertBreak.docx");
			
```

Denken Sie daran, den Code an Ihre spezifischen Anforderungen anzupassen und ihn bei Bedarf um zusätzliche Funktionen zu erweitern.


## Abschluss
Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Words für .NET Seitenumbrüche in ein Word-Dokument einfügen. Wenn Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie nun die Paginierung und das Layout Ihres Dokuments steuern, indem Sie an den gewünschten Positionen Seitenumbrüche einfügen.
