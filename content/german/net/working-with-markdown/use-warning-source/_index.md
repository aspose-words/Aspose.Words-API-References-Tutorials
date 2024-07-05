---
title: Warnquelle verwenden
linktitle: Warnquelle verwenden
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie in der Schritt-für-Schritt-Anleitung, wie Sie die Warnquelle mit Aspose.Words für .NET verwenden.
type: docs
weight: 10
url: /de/net/working-with-markdown/use-warning-source/
---

In diesem Beispiel zeigen wir Ihnen, wie Sie die Warnungsquelle mit Aspose.Words für .NET verwenden. Die Warnungsquelle gibt den Ursprung der Warnung bei Verwendung der Rückruffunktion an.

## Schritt 1: Dokument einlegen

 Wir laden ein vorhandenes Dokument, das Warnungen enthält, mit dem`Load` Methode der`Document` Klasse.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");
```

## Schritt 3: Verwenden der Warnquelle

 Wir verwenden die Warnungsquelle, indem wir das Dokument`WarningCallback` Eigentum an einer Sammlung von`WarningInfo` Objekte.

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

### Beispielquellcode zur Verwendung der Warnquelle mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentverzeichnis.
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

### Häufig gestellte Fragen

#### F: Können wir das Erscheinungsbild des Tags „Warnung“ anpassen?

 A: Die Formatierung des Tags „Warning“ hängt vom verwendeten Markdown-Renderer ab. In den meisten Fällen können Sie das Aussehen anpassen, indem Sie CSS verwenden, um die`blockquote` Tag in Ihrem Dokument.

#### F: Ist es möglich, dem Tag „Warnung“ Symbole hinzuzufügen?

A: Ja, es ist möglich, dem Tag "Warning" Symbole hinzuzufügen, indem Sie HTML-Code in Ihrem Markdown-Dokument verwenden. Sie können ein`span` Tag mit der entsprechenden Klasse, um neben dem Warntext ein Symbol anzuzeigen.

#### F: Ist das Tag „Warnung“ mit allen Markdown-Readern kompatibel?

 A: Die Kompatibilität des Tags „Warning“ hängt von der verwendeten Markdown-Darstellung ab. Die meisten Markdown-Reader unterstützen das`blockquote` Tag, um hervorgehobenen Text anzuzeigen, aber das genaue Erscheinungsbild kann variieren.