---
title: Wörter in verschiedenen Sprachen mit Bindestrich verbinden
linktitle: Wörter in verschiedenen Sprachen mit Bindestrich verbinden
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Wörter in verschiedenen Sprachen in Word-Dokumenten trennen.
type: docs
weight: 10
url: /de/net/working-with-hyphenation/hyphenate-words-of-languages/
---

In diesem Schritt-für-Schritt-Tutorial zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET Wörter in verschiedenen Sprachen in Word-Dokumenten trennen. Wir erklären den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn in Ihren eigenen Projekten implementieren.

Stellen Sie zunächst sicher, dass Aspose.Words für .NET in Ihrer Entwicklungsumgebung installiert und konfiguriert ist. Wenn Sie dies noch nicht getan haben, laden Sie die Bibliothek von der offiziellen Site herunter und installieren Sie sie.

## Schritt 1: Initialisieren des Dokumentobjekts

 Initialisieren Sie zunächst den`Document` Objekt, indem Sie den Pfad zu Ihrem Quelldokument angeben, das Text in verschiedenen Sprachen enthält:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## Schritt 2: Silbentrennungswörterbücher speichern

Als nächstes speichern Sie die Silbentrennungswörterbücher für die verschiedenen Sprachen, die Sie verarbeiten möchten. In diesem Beispiel registrieren wir Wörterbücher für amerikanisches Englisch und Schweizerdeutsch:

```csharp
Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");
```

Stellen Sie sicher, dass Sie die entsprechenden Wörterbuchdateien in Ihrem Datenverzeichnis haben.

## Schritt 3: Wörter durch Silbentrennung verarbeiten

Jetzt können Sie Silbentrennungsfunktionen verwenden, um Wörter in verschiedenen Sprachen zu verarbeiten. Sie können verschiedene Methoden verwenden,`Document` oder`DocumentBuilder` abhängig von Ihren spezifischen Anforderungen.

```csharp
// Beispiel: Verwenden der Hyphenate-Methode von DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Example of text to hyphenate");
builder.InsertHyphenation();
```

## Schritt 4: Speichern Sie das Dokument

Speichern Sie abschließend das geänderte Dokument:

```csharp
doc.Save(dataDir + "TreatmentByCesure.pdf");
```

So! Sie haben Wörter erfolgreich verarbeitet, indem Sie sie in verschiedenen Sprachen in einem Word-Dokument mit Aspose.Words für .NET getrennt haben.

### Beispielquellcode für die Worttrennung mit Aspose.Words für .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");

doc.Save(dataDir + "TreatmentByCesure.pdf");
```

Sie können diesen Code gerne in Ihren eigenen Projekten verwenden und ihn Ihren spezifischen Anforderungen entsprechend ändern.

### Häufig gestellte Fragen

#### F: Wie kann ich mit Aspose.Words ein Wort in einer bestimmten Sprache in Silben trennen?

 A: Um ein Wort in einer bestimmten Sprache mit Aspose.Words in Silben zu unterteilen, können Sie die`Hyphenation` Klasse und die`Hyphenate()` Methode. Erstellen Sie eine Instanz der`Hyphenation` Klasse mit Angabe der gewünschten Sprache, dann rufen Sie die`Hyphenate()` Methode, die das zu silbende Wort als Argument übergibt. Dadurch erhalten Sie die Silben des Wortes in der angegebenen Sprache.

#### F: Welche Sprachcodes sollte ich verwenden, um die Silbentrennungssprache in Aspose.Words anzugeben?

A: Um die Silbentrennungssprache in Aspose.Words anzugeben, müssen Sie die entsprechenden Sprachcodes verwenden. Sie können beispielsweise „en“ für Englisch, „fr“ für Französisch, „es“ für Spanisch, „de“ für Deutsch usw. verwenden. Eine vollständige Liste der unterstützten Sprachcodes finden Sie in der Aspose.Words-Dokumentation.

#### F: Funktioniert die Silbentrennung für alle Sprachen in Aspose.Words?

A: Die Silbentrennung in Aspose.Words hängt von sprachspezifischen Silbentrennungsregeln ab. Obwohl Aspose.Words eine Vielzahl von Sprachen unterstützt, werden einige Sprachen möglicherweise nicht unterstützt oder die Silbentrennung ist für sie nicht verfügbar. Lesen Sie in der Aspose.Words-Dokumentation nach, welche Sprachen für die Silbentrennung unterstützt werden.