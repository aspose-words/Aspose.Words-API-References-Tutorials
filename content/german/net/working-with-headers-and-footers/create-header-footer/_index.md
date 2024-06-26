---
title: Erstellen Sie eine Kopf- und Fußzeile
linktitle: Erstellen Sie eine Kopf- und Fußzeile
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Kopf- und Fußzeilen in Word-Dokumenten hinzufügen und anpassen. Diese Schritt-für-Schritt-Anleitung sorgt für eine professionelle Dokumentformatierung.
type: docs
weight: 10
url: /de/net/working-with-headers-and-footers/create-header-footer/
---

Das Hinzufügen von Kopf- und Fußzeilen zu Ihren Dokumenten kann deren Professionalität und Lesbarkeit verbessern. Mit Aspose.Words für .NET können Sie ganz einfach Kopf- und Fußzeilen für Ihre Word-Dokumente erstellen und anpassen. In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess und stellen sicher, dass Sie diese Funktionen nahtlos implementieren können.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

-  Aspose.Words für .NET: Von herunterladen und installieren[Download-Link](https://releases.aspose.com/words/net/).
- Entwicklungsumgebung: Wie Visual Studio, um Ihren Code zu schreiben und auszuführen.
- Grundkenntnisse in C#: Verständnis von C# und .NET Framework.
- Beispieldokument: Ein Beispieldokument zum Anwenden der Kopf- und Fußzeilen oder zum Erstellen eines neuen Dokuments, wie im Tutorial gezeigt.

## Namespaces importieren

Zunächst müssen Sie die erforderlichen Namespaces importieren, um auf die Klassen und Methoden von Aspose.Words zuzugreifen.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
using System;
```

## Schritt 1: Definieren Sie das Dokumentenverzeichnis

Definieren Sie das Verzeichnis, in dem Ihr Dokument gespeichert wird. Dies hilft bei der effektiven Verwaltung des Pfades.

```csharp
// Der Pfad zum Dokumentenverzeichnis
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

## Schritt 2: Erstellen Sie ein neues Dokument

 Erstellen Sie ein neues Dokument und a`DocumentBuilder` um das Hinzufügen von Inhalten zu erleichtern.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 3: Konfigurieren Sie die Seiteneinrichtung

Richten Sie die Seiteneinstellungen ein, einschließlich der Frage, ob die erste Seite eine andere Kopf-/Fußzeile haben soll.

```csharp
Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;

pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;
```

## Schritt 4: Fügen Sie der ersten Seite eine Kopfzeile hinzu

Gehen Sie zum Kopfzeilenbereich der ersten Seite und konfigurieren Sie den Kopfzeilentext.

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words Header/Footer Creation Primer - Title Page.");
```

## Schritt 5: Fügen Sie einen primären Header hinzu

Gehen Sie zum primären Kopfzeilenbereich und fügen Sie ein Bild und einen Text ein.

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);

// Fügen Sie ein Bild in die Kopfzeile ein
builder.InsertImage(dataDir + "Graphics Interchange Format.gif", 
    RelativeHorizontalPosition.Page, 10, RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Aspose.Words Header/Footer Creation Primer.");
```

## Schritt 6: Fügen Sie eine primäre Fußzeile hinzu

Gehen Sie zum primären Fußzeilenbereich und erstellen Sie eine Tabelle, um den Inhalt der Fußzeile zu formatieren.

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

builder.StartTable();
builder.CellFormat.ClearFormatting();
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

// Seitennummerierung hinzufügen
builder.Write("Page ");
builder.InsertField("PAGE", "");
builder.Write(" of ");
builder.InsertField("NUMPAGES", "");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Left;
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

builder.Write("(C) 2001 Aspose Pty Ltd. All rights reserved.");
builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.EndRow();
builder.EndTable();
```

## Schritt 7: Fügen Sie Inhalte und Seitenumbrüche hinzu

Gehen Sie zum Ende des Dokuments, fügen Sie einen Seitenumbruch hinzu und erstellen Sie einen neuen Abschnitt mit anderen Seiteneinstellungen.

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder.CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
pageSetup.DifferentFirstPageHeaderFooter = false;

currentSection.HeadersFooters.LinkToPrevious(false);
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];
Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

## Schritt 8: Kopieren Sie Kopf- und Fußzeilen aus dem vorherigen Abschnitt

Wenn Sie Kopf- und Fußzeilen aus einem vorherigen Abschnitt wiederverwenden möchten, kopieren Sie sie und nehmen Sie die erforderlichen Änderungen vor.

```csharp
private static void CopyHeadersFootersFromPreviousSection(Section section)
{
    Section previousSection = (Section)section.PreviousSibling;
    if (previousSection == null) return;

    section.HeadersFooters.Clear();

    foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    {
        section.HeadersFooters.Add(headerFooter.Clone(true));
    }
}
```

## Abschluss

Wenn Sie diese Schritte befolgen, können Sie mit Aspose.Words für .NET effektiv Kopf- und Fußzeilen in Ihren Word-Dokumenten hinzufügen und anpassen. Dies verbessert das Erscheinungsbild und die Professionalität Ihres Dokuments und macht es lesbarer und ansprechender.

## FAQs

### F1: Was ist Aspose.Words für .NET?

Aspose.Words für .NET ist eine Bibliothek, die es Entwicklern ermöglicht, Word-Dokumente programmgesteuert in .NET-Anwendungen zu erstellen, zu bearbeiten und zu konvertieren.

### F2: Kann ich der Kopf- oder Fußzeile Bilder hinzufügen?

 Ja, Sie können ganz einfach Bilder zur Kopf- oder Fußzeile hinzufügen`DocumentBuilder.InsertImage` Methode.

### F3: Wie stelle ich unterschiedliche Kopf- und Fußzeilen für die erste Seite ein?

 Mit können Sie für die erste Seite unterschiedliche Kopf- und Fußzeilen festlegen`DifferentFirstPageHeaderFooter` Eigentum der`PageSetup` Klasse.

### F4: Wo finde ich weitere Dokumentation zu Aspose.Words?

 Eine umfassende Dokumentation finden Sie hier[Aspose.Words API-Dokumentationsseite](https://reference.aspose.com/words/net/).

### F5: Gibt es Unterstützung für Aspose.Words?

 Ja, Aspose bietet Support über ihre[Hilfeforum](https://forum.aspose.com/c/words/8).
