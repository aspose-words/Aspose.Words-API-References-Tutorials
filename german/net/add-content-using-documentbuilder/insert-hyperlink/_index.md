---
title: Hyperlink einfügen
linktitle: Hyperlink einfügen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.Words für .NET Hyperlinks in Word-Dokumente einfügen.
type: docs
weight: 10
url: /de/net/add-content-using-documentbuilder/insert-hyperlink/
---

In diesem umfassenden Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET Hyperlinks in ein Word-Dokument einfügen. Wir führen Sie durch den Prozess und stellen Ihnen die notwendigen C#-Code-Snippets zur Verfügung. Am Ende dieses Leitfadens werden Sie in der Lage sein, anklickbare Hyperlinks zu Ihren Dokumenten hinzuzufügen.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Aspose.Words für .NET-Bibliothek auf Ihrem System installiert.

## Schritt 1: Erstellen Sie ein neues Dokument und einen neuen DocumentBuilder
Erstellen Sie zunächst ein neues Dokument mit der Document-Klasse und initialisieren Sie ein DocumentBuilder-Objekt:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Fügen Sie einen Hyperlink ein
Als nächstes verwenden Sie die Write-Methode der DocumentBuilder-Klasse, um Text hinzuzufügen und den Hyperlink zu formatieren, indem Sie die Eigenschaften Farbe und Unterstreichung festlegen:

```csharp
builder.Write("Please make sure to visit ");
builder.Font.Color = Color.Blue;
builder.Font.Underline = Underline.Single;

builder.InsertHyperlink("Aspose Website", "http://www.aspose.com", false);

builder.Font.ClearFormatting();
builder.Write(" for more information.");
```

## Schritt 3: Speichern Sie das Dokument
Speichern Sie das Dokument nach dem Einfügen des Hyperlinks mit der Save-Methode der Document-Klasse in einer Datei:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHyperlink.docx");
```

## Beispielquellcode für das Einfügen eines Hyperlinks mit Aspose.Words für .NET
Hier ist der vollständige Quellcode zum Einfügen eines Hyperlinks mit Aspose.Words für .NET:

Hyperlinks sind eine leistungsstarke Möglichkeit, die Interaktivität und den Nutzen Ihrer Word-Dokumente zu verbessern. Sie können verwendet werden, um auf externe Ressourcen zu verweisen, zusätzliche Informationen bereitzustellen oder Navigationselemente innerhalb des Dokuments zu erstellen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Please make sure to visit ");
builder.Font.Color = Color.Blue;
builder.Font.Underline = Underline.Single;

builder.InsertHyperlink("Aspose Website", "http://www.aspose.com", false);

builder.Font.ClearFormatting();
builder.Write(" for more information.");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHyperlink.docx");
```

Denken Sie daran, den Code entsprechend Ihren spezifischen Anforderungen anzupassen, einschließlich des Hyperlinktexts und der URL. Erweitern Sie es nach Bedarf mit zusätzlicher Formatierung oder Funktionalität.

## Abschluss
Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Words für .NET Hyperlinks in ein Word-Dokument einfügen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie jetzt anklickbare Hyperlinks zu Ihren Dokumenten hinzufügen und Leser auf externe Websites oder bestimmte URLs leiten.

