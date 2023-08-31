---
title: Layout in Zelle
linktitle: Layout in Zelle
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine Form innerhalb einer Tabellenzelle in einem Word-Dokument anordnen.
type: docs
weight: 10
url: /de/net/programming-with-shapes/layout-in-cell/
---

In diesem Tutorial wird erklärt, wie Sie mit Aspose.Words für .NET eine Form innerhalb einer Tabellenzelle in einem Word-Dokument anordnen. Durch Anpassen der Formeigenschaften und Verwendung der Layoutoptionen können Sie die Positionierung und das Erscheinungsbild der Form innerhalb der Zelle steuern.

## Voraussetzungen
Um diesem Tutorial folgen zu können, benötigen Sie Folgendes:

- Aspose.Words für .NET-Bibliothek installiert.
- Grundkenntnisse in C# und Textverarbeitung mit Word-Dokumenten.

## Schritt 1: Richten Sie das Dokumentenverzeichnis ein
 Beginnen Sie mit der Einrichtung des Pfads zu Ihrem Dokumentenverzeichnis. Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu dem Verzeichnis, in dem Sie das Dokument speichern möchten.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Erstellen Sie ein neues Dokument und einen neuen DocumentBuilder
 Erstellen Sie eine neue Instanz von`Document` Klasse und a`DocumentBuilder` Objekt, um mit dem Dokument zu arbeiten.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 3: Erstellen Sie die Tabelle
 Benutzen Sie die`StartTable`, `EndTable`, `InsertCell` , Und`Write` Methoden der`DocumentBuilder` Objekt zum Erstellen einer Tabelle. Stellen Sie die gewünschte Zeilenhöhe und Höhenregel mit ein`RowFormat` Eigenschaften.

```csharp
builder.StartTable();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
for (int i = 0; i < 31; i++)
{
    if (i != 0 && i % 7 == 0) builder.EndRow();
    builder.InsertCell();
    builder.Write("Cell contents");
}
builder.EndTable();
```

## Schritt 4: Erstellen und formatieren Sie die Form
 Ein ... kreieren`Shape` Objekt und konfigurieren Sie seine Eigenschaften, um das Wasserzeichen zu definieren. Legen Sie mithilfe von fest, welche Form innerhalb einer Zelle angeordnet werden soll`IsLayoutInCell` Eigentum.

```csharp
Shape watermark = new Shape(doc, ShapeType.TextPlainText)
{
    RelativeHorizontalPosition = RelativeHorizontalPosition.Page,
    RelativeVerticalPosition = RelativeVerticalPosition.Page,
    IsLayoutInCell = true,
    Width = 300,
    Height = 70,
    HorizontalAlignment = HorizontalAlignment.Center,
    VerticalAlignment = VerticalAlignment.Center,
    Rotation = -40
};
```

## Schritt 5: Passen Sie die Form an
 Passen Sie das Erscheinungsbild und den Text der Wasserzeichenform an, indem Sie Eigenschaften wie festlegen`FillColor`, `StrokeColor`, `TextPath`, `Name`, `WrapType`, usw.

```csharp
watermark.FillColor = Color.Gray;
watermark.StrokeColor = Color.Gray;
watermark.TextPath.Text = "watermarkText";
watermark.TextPath.FontFamily = "Arial";
watermark.Name = $"WaterMark_{Guid.NewGuid()}";
watermark.WrapType = WrapType.None;
```

## Schritt 6: Fügen Sie die Form in das Dokument ein
Fügen Sie die Wasserzeichenform mit in das Dokument ein`InsertNode` Methode der`DocumentBuilder` Objekt. Positionieren Sie die Form mit dem`MoveTo` Methode, um es nach der letzten Ausführung im Dokument zu platzieren.

```csharp
Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
builder.MoveTo(run);
builder.InsertNode(watermark);
```

## Schritt 7: Speichern Sie das Dokument
 Speichern Sie das Dokument mit im angegebenen Verzeichnis`Save` Methode. Geben Sie den gewünschten Dateinamen mit der entsprechenden Dateierweiterung an. In diesem Beispiel speichern wir das Dokument als „WorkingWithShapes.LayoutInCell.docx“.

```csharp
doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
doc

.Save(dataDir + "WorkingWithShapes.LayoutInCell.docx");
```

### Beispielquellcode für Layout In Cell mit Aspose.Words für .NET 

```csharp
	//Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.StartTable();
	builder.RowFormat.Height = 100;
	builder.RowFormat.HeightRule = HeightRule.Exactly;
	for (int i = 0; i < 31; i++)
	{
		if (i != 0 && i % 7 == 0) builder.EndRow();
		builder.InsertCell();
		builder.Write("Cell contents");
	}
	builder.EndTable();
	Shape watermark = new Shape(doc, ShapeType.TextPlainText)
	{
		RelativeHorizontalPosition = RelativeHorizontalPosition.Page,
		RelativeVerticalPosition = RelativeVerticalPosition.Page,
		IsLayoutInCell = true, // Zeigen Sie die Form außerhalb der Tabellenzelle an, wenn sie in einer Zelle platziert wird.
		Width = 300,
		Height = 70,
		HorizontalAlignment = HorizontalAlignment.Center,
		VerticalAlignment = VerticalAlignment.Center,
		Rotation = -40
	};
	watermark.FillColor = Color.Gray;
	watermark.StrokeColor = Color.Gray;
	watermark.TextPath.Text = "watermarkText";
	watermark.TextPath.FontFamily = "Arial";
	watermark.Name = $"WaterMark_{Guid.NewGuid()}";
	watermark.WrapType = WrapType.None;
	Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
	builder.MoveTo(run);
	builder.InsertNode(watermark);
	doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
	doc.Save(dataDir + "WorkingWithShapes.LayoutInCell.docx");
```

Das ist es! Sie haben mit Aspose.Words für .NET erfolgreich eine Form in einer Tabellenzelle in einem Word-Dokument angelegt.