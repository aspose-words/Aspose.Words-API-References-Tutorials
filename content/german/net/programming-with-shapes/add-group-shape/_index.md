---
title: Gruppenform hinzufügen
linktitle: Gruppenform hinzufügen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET einem Word-Dokument eine Gruppenform mit mehreren Formen hinzufügen.
type: docs
weight: 10
url: /de/net/programming-with-shapes/add-group-shape/
---

In diesem Tutorial wird erklärt, wie Sie mit Aspose.Words für .NET einem Word-Dokument eine Gruppenform mit mehreren Formen hinzufügen. Mit Gruppenformen können Sie mehrere Formen als eine Einheit kombinieren und bearbeiten.

## Voraussetzungen
Um diesem Tutorial folgen zu können, benötigen Sie Folgendes:

- Aspose.Words für .NET-Bibliothek installiert.
- Grundkenntnisse in C# und Textverarbeitung mit Word-Dokumenten.

## Schritt 1: Einrichten des Dokumentverzeichnisses
 Beginnen Sie mit der Einrichtung des Pfades zu Ihrem Dokumentverzeichnis. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"`durch den tatsächlichen Pfad zum Verzeichnis, in dem Sie das Dokument speichern möchten.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Neues Dokument und GroupShape erstellen
 Erstellen Sie eine neue Instanz des`Document` Klasse und`GroupShape` Objekt, um mit dem Dokument zu arbeiten.

```csharp
Document doc = new Document();
doc.EnsureMinimum();
GroupShape groupShape = new GroupShape(doc);
```

## Schritt 3: Erstellen und Hinzufügen von Formen zur Gruppenform
 Erstellen Sie individuelle Formen wie`accentBorderShape`Und`actionButtonShape` Verwendung der`Shape` Klasse. Passen Sie ihre Eigenschaften nach Wunsch an. Fügen Sie diese Formen an die`groupShape` Objekt.

```csharp
Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1) { Width = 100, Height = 100 };
groupShape.AppendChild(accentBorderShape);

Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
{
    Left = 100,
    Width = 100,
    Height = 200
};
groupShape.AppendChild(actionButtonShape);
```

## Schritt 4: Dimensionen für die Gruppenform festlegen
Legen Sie die Breite, Höhe und Koordinatengröße für das`groupShape`.

```csharp
groupShape.Width = 200;
groupShape.Height = 200;
groupShape.CoordSize = new Size(200, 200);
```

## Schritt 5: Fügen Sie die Gruppenform in das Dokument ein
 Ein ... kreieren`DocumentBuilder` Objekt und fügen Sie das`groupShape` in das Dokument mit dem`InsertNode` Methode.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(groupShape);
```

## Schritt 6: Speichern Sie das Dokument
 Speichern Sie das Dokument im angegebenen Verzeichnis mit dem`Save` Methode. Geben Sie den gewünschten Dateinamen mit der entsprechenden Dateierweiterung an. In diesem Beispiel speichern wir das Dokument als „WorkingWithShapes.AddGroupShape.docx“.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

### Beispielquellcode für „Add Group Shape“ mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	doc.EnsureMinimum();
	GroupShape groupShape = new GroupShape(doc);
	Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1) { Width = 100, Height = 100 };
	groupShape.AppendChild(accentBorderShape);
	Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
	{
		Left = 100, Width = 100, Height = 200
	};
	groupShape.AppendChild(actionButtonShape);
	groupShape.Width = 200;
	groupShape.Height = 200;
	groupShape.CoordSize = new Size(200, 200);
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertNode(groupShape);
	doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

Das ist es! Sie haben erfolgreich eine Gruppenform mit mehreren Formen zu Ihrem Word-Dokument hinzugefügt, indem Sie Aspose.W verwenden.