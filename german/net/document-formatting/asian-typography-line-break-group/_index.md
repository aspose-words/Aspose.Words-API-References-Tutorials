---
title: Asiatische Typografie-Zeilenumbruchgruppe
linktitle: Asiatische Typografie-Zeilenumbruchgruppe
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie die Zeilenumbruchgruppe „Asiatische Typografie“ mit Aspose.Words für .NET verwenden.
type: docs
weight: 10
url: /de/net/document-formatting/asian-typography-line-break-group/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie die Zeilenumbruchgruppenfunktion für asiatische Typografie mit Aspose.Words für .NET verwenden. Führen Sie die folgenden Schritte aus, um den Quellcode zu verstehen und Formatierungsänderungen anzuwenden.

## Schritt 1: Laden des Dokuments

Geben Sie zunächst das Verzeichnis für Ihre Dokumente an und laden Sie das Dokument mit der asiatischen Typografie in ein Document-Objekt. Hier ist wie:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## Schritt 2: Einrichtung asiatischer Typografie

Wir konfigurieren nun die asiatischen Typografieeinstellungen für den ersten Absatz des Dokuments. Hier ist wie:

```csharp
ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
format. FarEastLineBreakControl = false;
format. WordWrap = true;
format. HangingPunctuation = false;
```

## Schritt 3: Speichern des Dokuments

 Nachdem Sie das Texteingabeformularfeld eingefügt haben, speichern Sie das Dokument mithilfe von am gewünschten Ort`Save` Methode. Stellen Sie sicher, dass Sie den richtigen Dateipfad angeben:

```csharp
doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
```

### Beispielquellcode für die Asian Typography Line Break Group mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für die Funktion „Asian Typography Line Break Group“ mit Aspose.Words für .NET:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
	format.FarEastLineBreakControl = false;
	format.WordWrap = true;
	format.HangingPunctuation = false;

	doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
	
```
Mit diesem Code können Sie die Zeilenumbruchgruppe „Asiatische Typografie“ mit Aspose.Words für .NET anwenden.

