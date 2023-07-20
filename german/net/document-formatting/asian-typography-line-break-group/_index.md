---
title: Asiatische Typografie-Zeilenumbruchgruppe im Word-Dokument
linktitle: Asiatische Typografie-Zeilenumbruchgruppe im Word-Dokument
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die Zeilenumbruchgruppe „Asiatische Typografie“ in einem Word-Dokument verwenden.
type: docs
weight: 10
url: /de/net/document-formatting/asian-typography-line-break-group/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie die Zeilenumbruchgruppe „Asiatische Typografie“ in der Word-Dokumentfunktion mit Aspose.Words für .NET verwenden. Führen Sie die folgenden Schritte aus, um den Quellcode zu verstehen und Formatierungsänderungen anzuwenden.

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

## Abschluss

 In diesem Tutorial haben wir die Funktion „Asian Typography Line Break Group“ in Aspose.Words für .NET untersucht. Durch die Konfiguration des`FarEastLineBreakControl`, `WordWrap` , Und`HangingPunctuation` Eigenschaften der`ParagraphFormat`konnten wir das Zeilenumbruchverhalten für asiatische Typografie in einem Word-Dokument steuern. Diese Funktion ist nützlich, um asiatische Zeichen zu verarbeiten und korrekte Zeilenumbrüche und Zeilenumbrüche in Dokumenten mit gemischtsprachigen Inhalten sicherzustellen.

### FAQs

#### F: Was ist die Funktion „Zeilenumbruchgruppe für asiatische Typografie“ in Aspose.Words für .NET?

A: Mit der Funktion „Zeilenumbruchgruppe für asiatische Typografie“ in Aspose.Words für .NET können Sie das Zeilenumbruchverhalten für asiatische Typografie in einem Word-Dokument steuern. Insbesondere wirkt es sich darauf aus, wie Zeilen unterbrochen und umbrochen werden, wenn in Absätzen asiatische Zeichen verwendet werden.

#### F: Wie aktiviere ich die „Zeilenumbruchgruppe für asiatische Typografie“ in Aspose.Words für .NET?

 A: Um die „Zeilenumbruchgruppe für asiatische Typografie“ zu aktivieren, müssen Sie die konfigurieren`FarEastLineBreakControl`, `WordWrap` , Und`HangingPunctuation` Eigenschaften der`ParagraphFormat` für den/die relevanten Absatz(e) in Ihrem Dokument. Einstellung`FarEastLineBreakControl` Zu`false` stellt sicher, dass asiatische Zeichen bezüglich Zeilenumbruch ähnlich behandelt werden wie lateinische Zeichen.`WordWrap` einstellen`true` ermöglicht den Zeilenumbruch für asiatische Typografie und`HangingPunctuation` einstellen`false` Verhindert, dass Satzzeichen in asiatischen Texten hängen bleiben.

#### F: Kann ich die „Asian Typography Line Break Group“ auf bestimmte Absätze in einem Dokument anwenden?

A: Ja, Sie können die Einstellungen „Asiatische Typografie-Zeilenumbruchgruppe“ auf bestimmte Absätze in einem Word-Dokument anwenden. Im Beispielcode werden die Einstellungen auf den ersten Absatz des Dokuments angewendet. Sie können den Code so anpassen, dass er bei Bedarf auf andere Absätze abzielt, indem Sie über darauf zugreifen`Paragraphs` Sammlung der relevanten Abschnitte im Dokument.