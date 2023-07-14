---
title: Verwenden Sie die Warnquelle
linktitle: Verwenden Sie die Warnquelle
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie Schritt-für-Schritt-Anleitung, wie Sie die Warnquelle mit Aspose.Words für .NET verwenden.
type: docs
weight: 10
url: /de/net/working-with-markdown/use-warning-source/
---

In diesem Beispiel zeigen wir Ihnen, wie Sie die Warnquelle mit Aspose.Words für .NET verwenden. Die Warnungsquelle gibt den Ursprung der Warnung an, wenn die Callback-Funktion verwendet wird.

## Schritt 1: Laden des Dokuments

 Wir laden ein vorhandenes Dokument, das Warnungen enthält, mithilfe von`Load` Methode der`Document` Klasse.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");
```

## Schritt 3: Verwenden der Warnquelle

 Wir verwenden die Warnquelle, indem wir die des Dokuments festlegen`WarningCallback` Eigentum an eine Sammlung von`WarningInfo` Objekte.

```csharp
WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;
```

## Schritt 4: Speichern des Dokuments

Abschließend können wir das Dokument im gewünschten Format speichern.

```csharp
doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");
foreach (WarningInfo warningInfo in warnings)
{
if (warningInfo.Source == WarningSource.Markdown)
	Console.WriteLine(warningInfo.Description);
}
```

### Beispielquellcode für die Verwendung von Warning Source mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");

WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;

doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");

foreach (WarningInfo warningInfo in warnings)
{
	if (warningInfo.Source == WarningSource.Markdown)
		Console.WriteLine(warningInfo.Description);
}
```

Herzlichen Glückwunsch! Sie haben jetzt gelernt, wie Sie die Warnquelle mit Aspose.Words für .NET verwenden.

### FAQs

#### F: Können wir das Erscheinungsbild des Tags „Warnung“ anpassen?

A: Die Formatierung des „Warning“-Tags hängt vom verwendeten Markdown-Renderer ab. In den meisten Fällen können Sie das Erscheinungsbild anpassen, indem Sie CSS als Ziel verwenden`blockquote` Tag in Ihrem Dokument.

#### F: Ist es möglich, dem Tag „Warnung“ Symbole hinzuzufügen?

 A: Ja, es ist möglich, mithilfe von HTML-Code in Ihrem Markdown-Dokument Symbole zum Tag „Warnung“ hinzuzufügen. Sie können eine einfügen`span` Tag mit der entsprechenden Klasse, um ein Symbol neben dem Warntext anzuzeigen.

#### F: Ist das Tag „Warnung“ mit allen Markdown-Readern kompatibel?

 A: Die Kompatibilität des „Warning“-Tags hängt vom verwendeten Markdown-Rendering ab. Die meisten Markdown-Leser werden das unterstützen`blockquote` Tag, um hervorgehobenen Text anzuzeigen, aber das genaue Erscheinungsbild kann variieren.