---
title: Ändern Sie asiatische Absatzabstände und Einzüge im Word-Dokument
linktitle: Ändern Sie asiatische Absatzabstände und Einzüge im Word-Dokument
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET asiatische Absatzabstände und Einzüge in Word-Dokumenten ändern.
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
format.CharacterUnitFirstLineIndent = 20; //Aktualisieren Sie ParagraphFormat.FirstLineIndent
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
	format.CharacterUnitLeftIndent = 10;       // ParagraphFormat.LeftIndent wird aktualisiert.
	format.CharacterUnitRightIndent = 10;      // ParagraphFormat.RightIndent wird aktualisiert.
	format.CharacterUnitFirstLineIndent = 20;  // ParagraphFormat.FirstLineIndent wird aktualisiert.
	format.LineUnitBefore = 5;                 // ParagraphFormat.SpaceBefore wird aktualisiert
	format.LineUnitAfter = 10;                 // ParagraphFormat.SpaceAfter wird aktualisiert

	doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");

```

Mit diesem Code können Sie die Abstände und Einzüge eines asiatischen Absatzes mit Aspose.Words für .NET ändern.

## Abschluss

 In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET den Abstand und die Einzüge eines asiatischen Absatzes ändert. Durch Ändern der relevanten Eigenschaften des`ParagraphFormat`können wir das Layout und die Darstellung asiatischer Absätze in einem Word-Dokument steuern. Diese Funktion ist nützlich, um die Formatierung von Text mit asiatischen Zeichen anzupassen und die gewünschte visuelle Präsentation in Dokumenten mit gemischtsprachigen Inhalten zu erreichen.

### FAQs

#### F: Was bewirkt die Funktion „Asiatische Absatzabstände und Einzüge ändern“ in Aspose.Words für .NET?

A: Mit der Funktion „Asiatische Absatzabstände und Einzüge ändern“ in Aspose.Words für .NET können Sie die Abstands- und Einrückungseigenschaften eines asiatischen Absatzes in einem Word-Dokument ändern. Sie können die Werte für den linken und rechten Einzug, den Einzug der ersten Zeile sowie den Abstand davor und den Abstand danach anpassen, um das Layout und das Erscheinungsbild des Absatzes zu steuern.

#### F: Wie ändere ich die Abstände und Einzüge eines asiatischen Absatzes mit Aspose.Words für .NET?

 A: Um den Abstand und die Einzüge eines asiatischen Absatzes zu ändern, müssen Sie auf zugreifen`ParagraphFormat`des Zielabsatzes und ändern Sie seine relevanten Eigenschaften. Im bereitgestellten Beispielcode greifen wir auf den ersten Absatz des Dokuments zu und legen den fest`CharacterUnitLeftIndent`, `CharacterUnitRightIndent`, `CharacterUnitFirstLineIndent`, `LineUnitBefore` , Und`LineUnitAfter` Eigenschaften, um die Abstände und Einzüge anzupassen.

#### F: Kann ich diese Änderungen auf andere Absätze im Dokument anwenden?

 A: Ja, Sie können diese Änderungen auf andere Absätze im Dokument anwenden, indem Sie auf die entsprechenden Absätze zugreifen`ParagraphFormat` Objekte. Der Beispielcode zielt auf den ersten Absatz des Dokuments ab, Sie können jedoch auch andere Absätze ändern, indem Sie den Index im anpassen`Paragraphs` Sammlung oder Verwendung anderer Kriterien zur Auswahl der gewünschten Absätze.