---
title: Erstellen Sie eine Kopf- und Fußzeile
linktitle: Erstellen Sie eine Kopf- und Fußzeile
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Kopf- und Fußzeilen in Ihren Word-Dokumenten erstellen. Passen Sie Kopf- und Fußzeilen für jede Seite an.
type: docs
weight: 10
url: /de/net/working-with-headers-and-footers/create-header-footer/
---

Hier finden Sie eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes zum Erstellen von Kopf- und Fußzeilen mithilfe der Funktionalität von Aspose.Words für .NET. Stellen Sie sicher, dass Sie die Aspose.Words-Bibliothek in Ihr Projekt eingebunden haben, bevor Sie diesen Code verwenden.

## Schritt 1: Legen Sie den Pfad zum Dokumentverzeichnis fest

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Stellen Sie sicher, dass Sie den korrekten Pfad zu Ihrem Dokumentenverzeichnis angeben, in dem das bearbeitete Dokument gespeichert wird.

## Schritt 2: Erstellen Sie ein Dokument und einen Dokumentengenerator

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Hier erstellen wir eine Instanz von`Document` Klasse und eine Instanz davon`DocumentBuilder` Klasse, die es uns ermöglicht, das Dokument zu bearbeiten und Elemente hinzuzufügen.

## Schritt 3: Seitenparameter und erste Kopfzeile festlegen

```csharp
Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;

// Geben Sie an, ob sich die Kopf-/Fußzeilen der ersten Seite von den anderen Seiten unterscheiden sollen.
// Sie können zur Angabe auch die Eigenschaft PageSetup.OddAndEvenPagesHeaderFooter verwenden
// unterschiedliche Kopf-/Fußzeilen für ungerade und gerade Seiten.
pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;

builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words - Creating Headers/Footers - Title Page.");

pageSetup.HeaderDistance = 20;
builder. MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
```

Wir legen die Seitenparameter fest, einschließlich des Header-Abstands, und gehen dann zum Hauptheader (`HeaderPrimary`). Wir verwenden den Dokumentgenerator, um Text hinzuzufügen und die Kopfzeile zu formatieren.

## Schritt 4: Fügen Sie ein Bild und einen Text in die Hauptkopfzeile ein

```csharp
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
     RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words - Building headers/footers.");

builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

Wir verwenden den Dokumentgenerator, um ein Bild in der oberen linken Ecke der Hauptkopfzeile einzufügen, und fügen dann rechtsbündigen Text hinzu.

## Schritt 5: Fügen Sie eine Tabelle in die Hauptfußzeile ein

```csharp
builder.StartTable();

builder.CellFormat.ClearFormatting();

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

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

builder.MoveToDocumentEnd();
```

## Schritt 6: Fügen Sie eine neue Seite hinzu und legen Sie Kopf-/Fußzeilen fest

```csharp
builder. InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder. CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
// Dieser Abschnitt benötigt keine andere Kopf-/Fußzeile für die erste Seite, wir benötigen nur eine Titelseite im Dokument.
// und die Kopf-/Fußzeile für diese Seite wurde bereits im vorherigen Abschnitt definiert.
pageSetup.DifferentFirstPageHeaderFooter = false;

// In diesem Abschnitt werden standardmäßig die Kopf-/Fußzeilen des vorherigen Abschnitts angezeigt. Rufen Sie currentSection.HeadersFooters.LinkToPrevious(false) auf, um diesen Link zu unterbrechen.
// Die Seitenbreite ist für den neuen Abschnitt unterschiedlich, daher müssen wir für eine Fußzeilentabelle andere Zellenbreiten festlegen.
currentSection.HeadersFooters.LinkToPrevious(false);

//Wenn wir für diesen Abschnitt die bereits vorhandenen Kopf-/Fußzeilen verwenden möchten,
// aber mit ein paar kleinen Änderungen könnte es sinnvoll sein, die Kopf-/Fußzeilen zu kopieren
// aus dem vorherigen Abschnitt und wenden Sie die erforderlichen Änderungen an der gewünschten Stelle an.
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

// Speichern Sie das Dokument
doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

 Wir fügen einen Seitenumbruch und einen Abschnittsumbruch hinzu, um eine neue Seite zu erstellen, auf der die primären Kopf-/Fußzeilen sichtbar sind. Wir legen die Parameter für den neuen Abschnitt fest und verwenden dann die`CopyHeadersFootersFromPreviousSection` Methode zum Kopieren der Kopf-/Fußzeilen aus dem vorherigen Abschnitt. Abschließend stellen wir die entsprechenden Zellenbreiten für die Hauptfußtabelle ein und speichern das Dokument.

### Beispielquellcode zum Erstellen von Kopf- und Fußzeilen mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;
// Geben Sie an, ob sich die Kopf-/Fußzeilen der ersten Seite von denen anderer Seiten unterscheiden sollen.
// Sie können zur Angabe auch die Eigenschaft PageSetup.OddAndEvenPagesHeaderFooter verwenden
// unterschiedliche Kopf-/Fußzeilen für ungerade und gerade Seiten.
pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;

builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words Header/Footer Creation Primer - Title Page.");

pageSetup.HeaderDistance = 20;
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);

// Fügen Sie ein positioniertes Bild in die obere/linke Ecke der Kopfzeile ein.
// Der Abstand vom oberen/linken Rand der Seite ist auf 10 Punkte eingestellt.
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
	RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words Header/Footer Creation Primer.");

builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

//Wir verwenden eine Tabelle mit zwei Zellen, um einen Teil des Textes in die Zeile einzufügen (mit Seitennummerierung).
// Linksbündig und der andere Teil des Textes (mit Copyright) rechtsbündig.
builder.StartTable();

builder.CellFormat.ClearFormatting();

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

// Es verwendet die Felder PAGE und NUMPAGES, um die aktuelle Seitenzahl und viele Seiten automatisch zu berechnen.
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

builder.MoveToDocumentEnd();

// Machen Sie einen Seitenumbruch, um eine zweite Seite zu erstellen, auf der die primären Kopf-/Fußzeilen angezeigt werden.
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder.CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
// Dieser Abschnitt benötigt keine andere Kopf-/Fußzeile auf der ersten Seite. Wir benötigen nur eine Titelseite im Dokument.
// und die Kopf-/Fußzeile für diese Seite wurde bereits im vorherigen Abschnitt definiert.
pageSetup.DifferentFirstPageHeaderFooter = false;

// In diesem Abschnitt werden Kopf-/Fußzeilen aus dem vorherigen Abschnitt angezeigt
// Rufen Sie standardmäßig currentSection.HeadersFooters.LinkToPrevious(false) auf, um diese Seitenbreite abzubrechen
// ist für den neuen Abschnitt anders, und deshalb müssen wir für eine Fußzeilentabelle andere Zellenbreiten festlegen.
currentSection.HeadersFooters.LinkToPrevious(false);

// Wenn wir für diesen Abschnitt den bereits vorhandenen Kopf-/Fußzeilensatz verwenden möchten.
// Mit einigen geringfügigen Änderungen kann es jedoch sinnvoll sein, Kopf-/Fußzeilen zu kopieren
//aus dem vorherigen Abschnitt und wenden Sie die erforderlichen Änderungen an der gewünschten Stelle an.
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

### FAQs

#### F: Wie kann ich in Aspose.Words eine Kopfzeile zu meinem Dokument hinzufügen?

 A: Um Ihrem Dokument in Aspose.Words eine Kopfzeile hinzuzufügen, können Sie die verwenden`Document.FirstSection.HeadersFooters.Add(HeaderFooterType.HeaderPrimary)` Methode. Diese Methode fügt dem ersten Abschnitt Ihres Dokuments eine primäre Überschrift hinzu.

#### F: Wie kann ich in Aspose.Words eine Fußzeile zu meinem Dokument hinzufügen?

 A: Um Ihrem Dokument in Aspose.Words eine Fußzeile hinzuzufügen, können Sie die verwenden`Document.FirstSection.HeadersFooters.Add(HeaderFooterType.FooterPrimary)` Methode. Diese Methode fügt dem ersten Abschnitt Ihres Dokuments eine primäre Fußzeile hinzu.

#### F: Wie kann ich meiner Kopf- oder Fußzeile in Aspose.Words Text hinzufügen?

 A: Um Ihrer Kopf- oder Fußzeile in Aspose.Words Text hinzuzufügen, können Sie die verwenden`HeaderFooter.Paragraphs` -Eigenschaft, um die Absatzsammlung der Kopf- oder Fußzeile abzurufen, und fügen Sie dann mithilfe der einen Absatz mit Ihrem Text zu dieser Sammlung hinzu`ParagraphCollection.Add` Methode.

#### F: Kann ich den Inhalt von Kopf- oder Fußzeilen mit Bildern und Seitenzahlen in Aspose.Words anpassen?

A: Ja, Sie können den Inhalt von Kopf- und Fußzeilen mit Bildern und Seitenzahlen in Aspose.Words anpassen. Sie können Objekte wie verwenden`Shape` um Bilder und Objekte wie hinzuzufügen`Field` um Ihrer Kopf- oder Fußzeile Seitenzahlen hinzuzufügen.

#### F: Kann ich die Schriftart, Größe und Farbe des Textes in meiner Kopf- oder Fußzeile in Aspose.Words ändern?

 A: Ja, Sie können die Schriftart, Größe und Farbe des Textes in Ihrer Kopf- oder Fußzeile in Aspose.Words ändern. Sie können auf Textformatierungseigenschaften zugreifen, z`Font` um die Schriftart zu ändern,`Size` um die Größe anzupassen, und`Color` um die Textfarbe festzulegen.