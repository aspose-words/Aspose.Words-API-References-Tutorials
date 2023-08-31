---
title: Pause in Word-Dokument einfügen
linktitle: Pause in Word-Dokument einfügen
second_title: Aspose.Words-Dokumentverarbeitungs-API
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

### FAQs

#### F: Kann ich neben Seitenumbrüchen auch andere Arten von Umbrüchen einfügen?

A: Auf jeden Fall! Aspose.Words für .NET unterstützt verschiedene Arten von Umbrüchen, einschließlich Seitenumbrüchen, Spaltenumbrüchen und Abschnittsumbrüchen. Sie können die InsertBreak-Methode mit verschiedenen BreakType-Parametern verwenden, um den gewünschten Unterbrechungstyp einzufügen.

#### F: Kann ich in bestimmten Abschnitten des Dokuments Seitenumbrüche einfügen?

A: Ja, Sie können Seitenumbrüche an bestimmten Stellen im Dokument einfügen. Mithilfe des DocumentBuilder können Sie die Platzierung von Seitenumbrüchen basierend auf dem Inhalt und der Struktur Ihres Dokuments steuern.

#### F: Bleiben die Seitenumbrüche erhalten, wenn das Dokument in verschiedenen Dateiformaten gespeichert wird?

A: Ja, mit Aspose.Words für .NET eingefügte Seitenumbrüche bleiben erhalten, wenn das Dokument in anderen Dateiformaten wie DOCX, PDF oder RTF gespeichert wird. Dies gewährleistet eine konsistente Paginierung und ein einheitliches Layout über verschiedene Dateiformate hinweg.

#### F: Kann ich das Erscheinungsbild von Seitenumbrüchen anpassen?

A: Seitenumbrüche sind im Dokument selbst nicht sichtbar, Sie können jedoch die Formatierung und das Layout des Inhalts vor und nach den Seitenumbrüchen anpassen, um das Erscheinungsbild des Dokuments zu steuern.

#### F: Ist Aspose.Words für .NET sowohl für Desktop- als auch für Webanwendungen geeignet?

A: Ja, Aspose.Words für .NET ist eine vielseitige Bibliothek, die sowohl für Desktop- als auch für Webanwendungen geeignet ist. Unabhängig davon, ob Sie eine Windows-Anwendung oder ein webbasiertes System erstellen, können Sie die Bibliothek mühelos integrieren.