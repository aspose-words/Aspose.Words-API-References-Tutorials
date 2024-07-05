---
title: Umrissrahmen anwenden
linktitle: Umrissrahmen anwenden
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Anwenden eines Gliederungsrahmens auf eine Tabelle mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-table-styles-and-formatting/apply-outline-border/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess, mit Aspose.Words für .NET einen Umrissrahmen auf eine Tabelle anzuwenden. Wir erklären den mitgelieferten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials haben Sie ein klares Verständnis dafür, wie Sie Tabellenrahmen in Ihren Word-Dokumenten mit Aspose.Words für .NET bearbeiten können.

## Schritt 1: Dokumentverzeichnis festlegen
Zunächst müssen Sie den Pfad zu Ihrem Dokumentenverzeichnis festlegen. Hier ist Ihr Word-Dokument gespeichert. Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Dokument hochladen
 Als nächstes müssen Sie das Word-Dokument in eine Instanz des`Document` Klasse.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Schritt 3: Auf die Tabelle zugreifen
 Um einen Umrissrahmen anzuwenden, müssen wir auf die Tabelle im Dokument zugreifen.`Table` Klasse stellt eine Tabelle in Aspose.Words dar.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## Schritt 4: Richten Sie die Tabelle an der Seitenmitte aus
 Nun können wir die Tabelle mittig auf der Seite ausrichten, indem wir`Alignment` Eigenschaft der Tabelle.

```csharp
table. Alignment = Table Alignment. Center;
```

## Schritt 5: Vorhandene Tabellenränder löschen
Um mit einem neuen Umrissrahmen zu beginnen, müssen wir zunächst alle vorhandenen Rahmen aus der Tabelle löschen. Dies kann mit dem`ClearBorders()` Methode.

```csharp
table. ClearBorders();
```

## Schritt 6: Definieren Sie einen grünen Rahmen um die Tabelle
 Wir können nun einen grünen Rahmen um die Tabelle setzen mit dem`SetBorder()` Methode für jede Seite der Tabelle. In diesem Beispiel verwenden wir einen Rahmen vom Typ „Einzeln“ mit einer Dicke von 1,5 Punkten und einer grünen Farbe.

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
Abschließend speichern wir das geänderte Dokument in einer Datei. Sie können einen geeigneten Namen und Speicherort für das Ausgabedokument wählen.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

Herzlichen Glückwunsch! Sie haben jetzt mit Aspose.Words für .NET einen Umrissrahmen auf eine Tabelle angewendet.

### Beispielquellcode für „Umrissrahmen anwenden“ mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Richten Sie die Tabelle an der Seitenmitte aus.
	table.Alignment = TableAlignment.Center;
	//Löschen Sie alle vorhandenen Ränder aus der Tabelle.
	table.ClearBorders();
	// Legen Sie einen grünen Rand um die Tabelle fest, jedoch nicht innerhalb.
	table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
	// Füllen Sie die Zellen mit einer hellgrünen Volltonfarbe.
	table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET einen Umrissrahmen auf eine Tabelle anwendet. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie diese Funktionalität problemlos in Ihre C#-Projekte integrieren. Die Bearbeitung der Tabellenformatierung ist ein wesentlicher Aspekt der Dokumentverarbeitung, und Aspose.Words bietet hierfür eine leistungsstarke und flexible API. Mit diesem Wissen können Sie die visuelle Darstellung Ihrer Word-Dokumente verbessern und bestimmte Anforderungen erfüllen.