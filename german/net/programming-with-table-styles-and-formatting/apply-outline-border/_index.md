---
title: Umrissrahmen anwenden
linktitle: Umrissrahmen anwenden
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Anwenden eines Umrissrahmens auf eine Tabelle mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-table-styles-and-formatting/apply-outline-border/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess zum Anwenden eines Umrissrahmens auf eine Tabelle mit Aspose.Words für .NET. Wir erklären Ihnen den gebündelten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials werden Sie ein klares Verständnis dafür haben, wie Sie Tabellenränder in Ihren Word-Dokumenten mit Aspose.Words für .NET bearbeiten.

## Schritt 1: Definieren Sie das Dokumentenverzeichnis
Zuerst müssen Sie den Pfad zu Ihrem Dokumentenverzeichnis festlegen. Hier wird Ihr Word-Dokument gespeichert. Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument hoch
 Als nächstes müssen Sie das Word-Dokument in eine Instanz von laden`Document` Klasse.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Schritt 3: Greifen Sie auf die Tabelle zu
 Um einen Umrissrahmen anzuwenden, müssen wir auf die Tabelle im Dokument zugreifen. Der`Table` Die Klasse stellt eine Tabelle in Aspose.Words dar.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## Schritt 4: Richten Sie die Tabelle in der Mitte der Seite aus
 Jetzt können wir die Tabelle mithilfe von an der Mitte der Seite ausrichten`Alignment` Eigenschaft der Tabelle.

```csharp
table. Alignment = Table Alignment. Center;
```

## Schritt 5: Vorhandene Tabellenränder löschen
Um mit einem neuen Umrissrahmen zu beginnen, müssen wir zunächst alle vorhandenen Rahmen aus der Tabelle löschen. Dies kann mit der erfolgen`ClearBorders()` Methode.

```csharp
table. ClearBorders();
```

## Schritt 6: Definieren Sie einen grünen Rand um die Tabelle
 Mit können wir nun einen grünen Rand um die Tabelle setzen`SetBorder()` Methode für jede Seite der Tabelle. In diesem Beispiel verwenden wir einen Rahmen vom Typ „Single“ mit einer Dicke von 1,5 Punkt und einer grünen Farbe.

```csharp
table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
```

## Schritt 7: Füllen Sie die Zellen mit einer Hintergrundfarbe
Um die visuelle Darstellung der Tabelle zu verbessern, können wir die Zellen mit einer Grundhintergrundfarbe füllen

Idee. In diesem Beispiel verwenden wir eine hellgrüne Farbe.

```csharp
table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
```

## Schritt 8: Speichern Sie das geänderte Dokument
Abschließend speichern wir das geänderte Dokument in einer Datei. Sie können einen geeigneten Namen und Speicherort für das Ausgabedokument auswählen.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

Herzlichen Glückwunsch! Sie haben jetzt mit Aspose.Words für .NET einen Umrissrahmen auf eine Tabelle angewendet.

### Beispielquellcode für „Umrissrahmen anwenden“ mit Aspose.Words für .NET 

```csharp
	//Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Richten Sie die Tabelle in der Mitte der Seite aus.
	table.Alignment = TableAlignment.Center;
	//Löschen Sie alle vorhandenen Ränder aus der Tabelle.
	table.ClearBorders();
	// Legen Sie einen grünen Rand um den Tisch, aber nicht nach innen.
	table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
	// Füllen Sie die Zellen mit einer hellgrünen Volltonfarbe.
	table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET einen Umrissrahmen auf eine Tabelle anwendet. Wenn Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie diese Funktionalität problemlos in Ihre C#-Projekte integrieren. Die Manipulation der Tabellenformatierung ist ein wesentlicher Aspekt der Dokumentverarbeitung, und Aspose.Words bietet eine leistungsstarke und flexible API, um dies zu erreichen. Mit diesem Wissen können Sie die visuelle Darstellung Ihrer Word-Dokumente verbessern und spezifische Anforderungen erfüllen.