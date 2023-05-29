---
title: Wörter von Sprachen trennen
linktitle: Wörter von Sprachen trennen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Wörter in verschiedenen Sprachen in Word-Dokumenten trennen.
type: docs
weight: 10
url: /de/net/working-with-hyphenation/hyphenate-words-of-languages/
---

In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET Wörter in verschiedenen Sprachen in Word-Dokumenten trennen. Wir erklären Ihnen den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn in Ihren eigenen Projekten implementieren.

Stellen Sie zunächst sicher, dass Aspose.Words für .NET in Ihrer Entwicklungsumgebung installiert und konfiguriert ist. Wenn Sie es noch nicht getan haben, laden Sie die Bibliothek von der offiziellen Website herunter und installieren Sie sie.

## Schritt 1: Initialisieren des Dokumentobjekts

 Initialisieren Sie zunächst die`Document` -Objekt, indem Sie den Pfad zu Ihrem Quelldokument angeben, das Text in verschiedenen Sprachen enthält:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## Schritt 2: Silbentrennungswörterbücher speichern

Speichern Sie als Nächstes die Silbentrennungswörterbücher für die verschiedenen Sprachen, die Sie verarbeiten möchten. In diesem Beispiel registrieren wir Wörterbücher für amerikanisches Englisch und Schweizerdeutsch:

```csharp
Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");
```

Stellen Sie sicher, dass sich in Ihrem Datenverzeichnis die entsprechenden Wörterbuchdateien befinden.

## Schritt 3: Wörter durch Silbentrennung verarbeiten

 Jetzt können Sie Silbentrennungsfunktionen verwenden, um Wörter in verschiedenen Sprachen zu verarbeiten. Sie können verschiedene Methoden verwenden`Document` oder`DocumentBuilder`abhängig von Ihren spezifischen Bedürfnissen.

```csharp
// Beispiel: Verwendung der Hyphenate-Methode von DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Example of text to hyphenate");
builder.InsertHyphenation();
```

## Schritt 4: Speichern Sie das Dokument

Speichern Sie abschließend das geänderte Dokument:

```csharp
doc.Save(dataDir + "TreatmentByCesure.pdf");
```

So ! Sie haben Wörter erfolgreich verarbeitet, indem Sie sie in verschiedenen Sprachen in einem Word-Dokument mit Aspose.Words für .NET getrennt haben.

### Beispielquellcode für die Worttrennung mit Aspose.Words für .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");

doc.Save(dataDir + "TreatmentByCesure.pdf");
```

Sie können diesen Code gerne in Ihren eigenen Projekten verwenden und an Ihre spezifischen Bedürfnisse anpassen.
