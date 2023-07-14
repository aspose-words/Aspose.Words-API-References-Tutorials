---
title: Absatzstil anwenden
linktitle: Absatzstil anwenden
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET einen Absatzstil anwenden.
type: docs
weight: 10
url: /de/net/document-formatting/apply-paragraph-style/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET einen Absatzstil anwenden. Führen Sie die folgenden Schritte aus, um den Quellcode zu verstehen und den Absatzstil anzuwenden.

## Schritt 1: Dokument erstellen und konfigurieren

Erstellen Sie zunächst ein neues Dokument und ein zugehöriges DocumentBuilder-Objekt. Hier ist wie:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Konfigurieren des Absatzstils

Wir konfigurieren nun den Absatzstil mithilfe der integrierten Stilkennung. Hier ist wie:

```csharp
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Title;
```

## Schritt 3: Inhalte hinzufügen

Wir werden dem Absatz Inhalte hinzufügen. Hier ist wie:

```csharp
builder.Write("Hello");
doc.Save(dataDir + "DocumentFormatting.ApplyParagraphStyle.docx");
```

### Beispielquellcode für „Absatzstil anwenden“ mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für die Funktion „Absatzstil anwenden“ mit Aspose.Words für .NET:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Title;
	builder.Write("Hello");
	
	doc.Save(dataDir + "DocumentFormatting.ApplyParagraphStyle.docx");
	
```

Mit diesem Code können Sie mit Aspose.Words für .NET einen Absatzstil anwenden.

