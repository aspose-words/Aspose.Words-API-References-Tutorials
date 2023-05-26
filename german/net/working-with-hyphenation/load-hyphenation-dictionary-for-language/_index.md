---
title: Silbentrennungswörterbuch für Sprache laden
linktitle: Silbentrennungswörterbuch für Sprache laden
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie in Aspose.Words für .NET ein Silbentrennungswörterbuch für eine bestimmte Sprache laden.
type: docs
weight: 10
url: /de/net/working-with-hyphenation/load-hyphenation-dictionary-for-language/
---

In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie ein Silbentrennungswörterbuch für eine bestimmte Sprache in Aspose.Words für .NET laden. Wir erklären Ihnen den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn in Ihren eigenen Projekten implementieren.

Stellen Sie zunächst sicher, dass Aspose.Words für .NET in Ihrer Entwicklungsumgebung installiert und konfiguriert ist. Wenn Sie es noch nicht getan haben, laden Sie die Bibliothek von der offiziellen Website herunter und installieren Sie sie.

## Schritt 1: Laden des Dokuments

Laden Sie zunächst Ihr Dokument aus dem angegebenen Verzeichnis:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## Schritt 2: Laden des Silbentrennungswörterbuchs

Öffnen Sie als Nächstes einen Stream zur Silbentrennungswörterbuchdatei und speichern Sie ihn für die gewünschte Sprache. In diesem Beispiel laden wir ein Wörterbuch für Schweizerdeutsch (de-CH):

```csharp
Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);
```

Stellen Sie sicher, dass sich in Ihrem Datenverzeichnis die entsprechende Wörterbuchdatei befindet.

## Schritt 3: Speichern Sie das geänderte Dokument

Speichern Sie abschließend das geänderte Dokument:

```csharp
doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

So ! Sie haben erfolgreich ein Silbentrennungswörterbuch für eine bestimmte Sprache in Aspose.Words für .NET geladen.

### Beispielquellcode für das Laden eines Silbentrennungswörterbuchs für eine Sprache mit Aspose.Words für .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);

doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

Sie können diesen Code gerne in Ihren eigenen Projekten verwenden und an Ihre spezifischen Bedürfnisse anpassen.