---
title: Document Builder Lesezeichen einfügen
linktitle: Document Builder Lesezeichen einfügen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit DocumentBuilder in Aspose.Words für .NET Lesezeichen in Word-Dokumente einfügen. Schritt für Schritt Anleitung.
type: docs
weight: 10
url: /de/net/add-content-using-documentbuilder/document-builder-insert-bookmark/
---

In diesem umfassenden Beispiel erfahren Sie, wie Sie mithilfe der DocumentBuilder-Klasse in Aspose.Words für .NET Lesezeichen in ein Word-Dokument einfügen. Wir führen Sie durch den Prozess und stellen Ihnen die notwendigen C#-Code-Snippets zur Verfügung. Am Ende dieses Leitfadens werden Sie in der Lage sein, Lesezeichen in Ihren Dokumenten zu erstellen und zu verwalten.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Aspose.Words für .NET-Bibliothek auf Ihrem System installiert.

## Schritt 1: Erstellen Sie ein neues Dokument und einen neuen DocumentBuilder
Erstellen Sie zunächst ein neues Dokument mit der Document-Klasse und initialisieren Sie ein DocumentBuilder-Objekt:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Fügen Sie ein Lesezeichen ein
Als nächstes verwenden Sie die Methoden StartBookmark und EndBookmark der DocumentBuilder-Klasse, um ein Lesezeichen in das Dokument einzufügen. Geben Sie als Parameter einen eindeutigen Namen für das Lesezeichen an:

```csharp
builder.StartBookmark("FineBookmark");
builder.Writeln("This is just a fine bookmark.");
builder.EndBookmark("FineBookmark");
```

## Schritt 3: Speichern Sie das Dokument
Speichern Sie das Dokument nach dem Einfügen des Lesezeichens mit der Save-Methode der Document-Klasse in einer Datei:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.DocumentBuilderInsertBookmark.docx");
```

### Beispielquellcode für DocumentBuilder: Einfügen eines Lesezeichens mit Aspose.Words für .NET
Hier ist der vollständige Quellcode zum Einfügen eines Lesezeichens mithilfe der DocumentBuilder-Klasse in Aspose.Words für .NET:

```csharp
   
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartBookmark("FineBookmark");
	builder.Writeln("This is just a fine bookmark.");
	builder.EndBookmark("FineBookmark");

	doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.DocumentBuilderInsertBookmark.docx");
	 
```

## Abschluss
Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mithilfe der DocumentBuilder-Klasse in Aspose.Words für .NET Lesezeichen in ein Word-Dokument einfügen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie jetzt Lesezeichen in Ihren Dokumenten erstellen und verwalten.

Lesezeichen sind für verschiedene Szenarien nützlich, z. B. zum Navigieren durch große Dokumente, zum Verweisen auf bestimmte Abschnitte oder zum programmgesteuerten Bearbeiten von Inhalten in mit Lesezeichen versehenen Bereichen.

Denken Sie daran, den Code an Ihre spezifischen Anforderungen anzupassen und ihn bei Bedarf um zusätzliche Funktionen zu erweitern.

