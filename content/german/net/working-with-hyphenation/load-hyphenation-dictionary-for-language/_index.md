---
title: Silbentrennungswörterbuch für Sprache laden
linktitle: Silbentrennungswörterbuch für Sprache laden
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie in Aspose.Words für .NET ein Silbentrennungswörterbuch für eine bestimmte Sprache laden.
type: docs
weight: 10
url: /de/net/working-with-hyphenation/load-hyphenation-dictionary-for-language/
---

In diesem Schritt-für-Schritt-Tutorial zeigen wir Ihnen, wie Sie ein Silbentrennungswörterbuch für eine bestimmte Sprache in Aspose.Words für .NET laden. Wir erklären den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn in Ihre eigenen Projekte implementieren.

 Stellen Sie zunächst sicher, dass Aspose.Words für .NET in Ihrer Entwicklungsumgebung installiert und konfiguriert ist. Wenn Sie dies noch nicht getan haben, laden Sie die Bibliothek herunter und installieren Sie sie von[[Originaltext von Aspose.Releases]https://releases.aspose.com/words/net/.

## Schritt 1: Dokument einlegen

Laden Sie zunächst Ihr Dokument aus dem angegebenen Verzeichnis:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## Schritt 2: Silbentrennungswörterbuch laden

Als nächstes öffnen wir einen Stream zur Silbentrennungswörterbuchdatei und speichern diese für die gewünschte Sprache. In diesem Beispiel laden wir ein Wörterbuch für Schweizerdeutsch (de-CH):

```csharp
Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);
```

Stellen Sie sicher, dass Sie die entsprechende Wörterbuchdatei in Ihrem Datenverzeichnis haben.

## Schritt 3: Speichern Sie das geänderte Dokument

Speichern Sie abschließend das geänderte Dokument:

```csharp
doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

So! Sie haben erfolgreich ein Silbentrennungswörterbuch für eine bestimmte Sprache in Aspose.Words für .NET geladen.

### Beispielquellcode zum Laden eines Silbentrennungswörterbuchs für eine Sprache mit Aspose.Words für .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);

doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

Sie können diesen Code gerne in Ihren eigenen Projekten verwenden und ihn Ihren spezifischen Anforderungen entsprechend ändern.

### Häufig gestellte Fragen

#### F: Wie lade ich in Aspose.Words ein Silbentrennungswörterbuch für eine bestimmte Sprache?

 A: Um ein Silbentrennungswörterbuch für eine bestimmte Sprache in Aspose.Words zu laden, können Sie den`Hyphenation` Klasse und die`LoadDictionary()` Methode. Erstellen Sie eine Instanz der`Hyphenation` Klasse und rufen Sie die`LoadDictionary()` Methode, die den Pfad zur Silbentrennungswörterbuchdatei für die gewünschte Sprache angibt. Dadurch wird das Silbentrennungswörterbuch in Aspose.Words geladen.

#### F: Wo finde ich Wörterbuchdateien zur Silbentrennung für verschiedene Sprachen?

A: Sie können Silbentrennungswörterbuchdateien für verschiedene Sprachen auf verschiedenen Online-Ressourcen finden. Diese Dateien liegen normalerweise im XML- oder TEX-Format vor. Open-Source-Silbentrennungswörterbücher für verschiedene Sprachen finden Sie auf Websites, die sich mit Linguistikprojekten oder Quellcode-Repositorien befassen.

#### F: Wie kann ich das geladene Silbenwörterbuch auf ein Dokument in Aspose.Words anwenden?

A: Um das geladene Silbentrennungswörterbuch auf ein Dokument in Aspose.Words anzuwenden, müssen Sie über die Wörter im Dokument iterieren und die`Hyphenate()` Methode der`Hyphenation` Klasse, um die Silbentrennung der Wörter zu erhalten. Sie können die silbentrennten Wörter dann nach Bedarf formatieren, beispielsweise durch Einfügen von Bindestrichen zwischen den Silben.

#### F: Welche Sprachen werden für die Silbentrennung in Aspose.Words unterstützt?

A: Aspose.Words unterstützt Silbentrennung für mehrere Sprachen, darunter Englisch, Französisch, Spanisch, Deutsch, Italienisch, Niederländisch, Russisch, Portugiesisch, Schwedisch, Norwegisch, Dänisch, Finnisch, Polnisch, Tschechisch und viele mehr. Die vollständige Liste der unterstützten Sprachen für die Silbentrennung finden Sie in der Aspose.Words-Dokumentation.