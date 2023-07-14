---
title: Raum zwischen asiatischem und lateinischem Text
linktitle: Raum zwischen asiatischem und lateinischem Text
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET den Abstand zwischen asiatischem und lateinischem Text in Ihrem Dokument automatisch anpassen.
type: docs
weight: 10
url: /de/net/document-formatting/space-between-asian-and-latin-text/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie die Leerzeichenfunktion zwischen asiatischem und lateinischem Text mit Aspose.Words für .NET verwenden. Führen Sie die folgenden Schritte aus, um den Quellcode zu verstehen und die Änderungen anzuwenden.

## Schritt 1: Dokument erstellen und konfigurieren

Erstellen Sie zunächst ein neues Dokument und ein zugehöriges DocumentBuilder-Objekt. Hier ist wie:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Den Abstand zwischen asiatischem und lateinischem Text einrichten

Wir konfigurieren nun den Abstand zwischen asiatischem und lateinischem Text mithilfe der Eigenschaften des ParagraphFormat-Objekts. Hier ist wie:

```csharp
ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

builder.Writeln("Auto adjust space between Asian and Latin text");
builder.Writeln("Auto adjust space between Asian text and numbers");
```

## Schritt 3: Speichern des Dokuments

 Nachdem Sie das Texteingabeformularfeld eingefügt haben, speichern Sie das Dokument mithilfe von am gewünschten Ort`Save` Methode. Stellen Sie sicher, dass Sie den richtigen Dateipfad angeben:

```csharp
doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
```

### Beispielquellcode für Leerzeichen zwischen asiatischem und lateinischem Text mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für die Funktion „Leerzeichen zwischen asiatischem und lateinischem Text“ mit Aspose.Words für .NET:


```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	ParagraphFormat paragraphFormat = builder.ParagraphFormat;
	paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
	paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

	builder.Writeln("Automatically adjust space between Asian and Latin text");
	builder.Writeln("Automatically adjust space between Asian text and numbers");

	doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
        
```

Mit diesem Code können Sie mithilfe von Aspose.Words für .NET den Abstand zwischen asiatischem und lateinischem Text in Ihrem Dokument automatisch anpassen.



