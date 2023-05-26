---
title: Legen Sie die Markierung für die Schriftbetonung fest
linktitle: Legen Sie die Markierung für die Schriftbetonung fest
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET den Schriftbetonungsstil in einem Word-Dokument festlegen.
type: docs
weight: 10
url: /de/net/working-with-fonts/set-font-emphasis-mark/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET den Schriftbetonungsstil in einem Word-Dokument festlegen. Mit der Schrifthervorhebung werden bestimmte Wörter oder Phrasen im Text hervorgehoben.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über die folgenden Artikel verfügen:
- Grundkenntnisse der Programmiersprache C#
- Die in Ihrem Projekt installierte Aspose.Words-Bibliothek für .NET

## Schritt 1: Definieren Sie das Dokumentenverzeichnis
Legen Sie zunächst den Verzeichnispfad auf den Speicherort Ihres Word-Dokuments fest. Ersetzen`"YOUR DOCUMENT DIRECTORY"` im Code mit dem entsprechenden Pfad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Erstellen Sie das Dokument und passen Sie es an
 Erstellen Sie eine Instanz von`Document` Klasse und eine zugehörige`DocumentBuilder` um den Dokumentinhalt zu erstellen. Benutzen Sie die`Font.EmphasisMark`Eigenschaft, auf die der Schrifthervorhebungsstil festgelegt werden soll`EmphasisMark.UnderSolidCircle` . Dann nutzen Sie die`Write` Und`Writeln` Methoden der`DocumentBuilder` um Text mit der angegebenen Schriftarthervorhebung hinzuzufügen.

```csharp
Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasized text");
builder. Writen();
builder.Font.ClearFormatting();
builder.Write("Simple text");
```

## Schritt 3: Speichern Sie das Dokument
 Speichern Sie das Dokument mit`Save` Methode der`Document` mit dem entsprechenden Pfad und Dateinamen.

```csharp
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

### Beispielquellcode für Set Font Emphasis Mark mit Aspose.Words für .NET 

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasis text");
builder.Writeln();
builder.Font.ClearFormatting();
builder.Write("Simple text");
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

## Abschluss
In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Words für .NET den Schriftbetonungsstil in einem Word-Dokument festlegen. Experimentieren Sie mit verschiedenen Hervorhebungsstilen und nutzen Sie diese Funktion, um Wörter oder Phrasen in Ihren Dokumenten hervorzuheben.
