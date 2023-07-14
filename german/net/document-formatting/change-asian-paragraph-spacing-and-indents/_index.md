---
title: Ändern Sie asiatische Absatzabstände und Einzüge
linktitle: Ändern Sie asiatische Absatzabstände und Einzüge
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie asiatische Absatzabstände und Einzüge mit Aspose.Words für .NET ändern.
type: docs
weight: 10
url: /de/net/document-formatting/change-asian-paragraph-spacing-and-indents/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie die Abstände und Einzüge eines asiatischen Absatzes mit Aspose.Words für .NET ändern. Führen Sie die folgenden Schritte aus, um den Quellcode zu verstehen und die Änderungen anzuwenden.

## Schritt 1: Laden des Dokuments

Geben Sie zunächst das Verzeichnis für Ihre Dokumente an und laden Sie das Dokument mit der asiatischen Typografie in ein Document-Objekt. Hier ist wie:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## Schritt 2: Absatzabstände und Einzüge ändern

Wir werden nun die Abstände und Einzüge des ersten Absatzes des asiatischen Dokuments ändern. Hier ist wie:

```csharp
ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
format.CharacterUnitLeftIndent = 10; // Aktualisieren Sie ParagraphFormat.LeftIndent
format.CharacterUnitRightIndent = 10; // Aktualisieren Sie ParagraphFormat.RightIndent
format.CharacterUnitFirstLineIndent = 20; // Aktualisieren Sie ParagraphFormat.FirstLineIndent
format.LineUnitBefore = 5; // Aktualisieren Sie ParagraphFormat.SpaceBefore
format.LineUnitAfter = 10; // Aktualisieren Sie ParagraphFormat.SpaceAfter
```

## Schritt 3: Speichern des Dokuments

 Nachdem Sie das Texteingabeformularfeld eingefügt haben, speichern Sie das Dokument mithilfe von am gewünschten Ort`Save` Methode. Stellen Sie sicher, dass Sie den richtigen Dateipfad angeben:

```csharp
doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");
```

### Beispielquellcode für die Änderung asiatischer Absatzabstände und Einzüge mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für die Funktion „Asiatische Absatzabstände und Einzüge bearbeiten“ mit Aspose.Words für .NET:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
	format.CharacterUnitLeftIndent = 10;       // ParagraphFormat.LeftIndent wird aktualisiert
	format.CharacterUnitRightIndent = 10;      // ParagraphFormat.RightIndent wird aktualisiert
	format.CharacterUnitFirstLineIndent = 20;  //ParagraphFormat.FirstLineIndent wird aktualisiert
	format.LineUnitBefore = 5;                 // ParagraphFormat.SpaceBefore wird aktualisiert
	format.LineUnitAfter = 10;                 // ParagraphFormat.SpaceAfter wird aktualisiert

	doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");

```

Mit diesem Code können Sie die Abstände und Einzüge eines asiatischen Absatzes mit Aspose.Words für .NET ändern.

