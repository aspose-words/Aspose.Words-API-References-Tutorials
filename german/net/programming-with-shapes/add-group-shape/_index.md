---
title: Gruppenform hinzufügen
linktitle: Gruppenform hinzufügen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine Gruppenform mit mehreren Formen zu einem Word-Dokument hinzufügen.
type: docs
weight: 10
url: /de/net/programming-with-shapes/add-group-shape/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET eine Gruppenform mit mehreren Formen zu einem Word-Dokument hinzufügen. Mit Gruppenformen können Sie mehrere Formen als eine Einheit kombinieren und bearbeiten.

## Voraussetzungen
Um diesem Tutorial folgen zu können, benötigen Sie Folgendes:

- Aspose.Words für .NET-Bibliothek installiert.
- Grundkenntnisse in C# und der Arbeit mit Word-Dokumenten.

## Schritt 1: Richten Sie das Dokumentenverzeichnis ein
 Beginnen Sie mit der Einrichtung des Pfads zu Ihrem Dokumentenverzeichnis. Ersetzen`"YOUR DOCUMENT DIRECTORY"`mit dem tatsächlichen Pfad zu dem Verzeichnis, in dem Sie das Dokument speichern möchten.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Erstellen Sie ein neues Dokument und eine GroupShape
 Erstellen Sie eine neue Instanz von`Document` Klasse und`GroupShape` Objekt, um mit dem Dokument zu arbeiten.

```csharp
Document doc = new Document();
doc.EnsureMinimum();
GroupShape groupShape = new GroupShape(doc);
```

## Schritt 3: Erstellen Sie Formen und fügen Sie sie zur GroupShape hinzu
 Erstellen Sie individuelle Formen wie z`accentBorderShape` Und`actionButtonShape` Verwendung der`Shape` Klasse. Passen Sie ihre Eigenschaften nach Ihren Wünschen an. Hängen Sie diese Formen an die an`groupShape` Objekt.

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

## Schritt 4: Legen Sie die Abmessungen für die GroupShape fest
 Legen Sie die Breite, Höhe und Koordinatengröße für fest`groupShape`.

```csharp
groupShape.Width = 200;
groupShape.Height = 200;
groupShape.CoordSize = new Size(200, 200);
```

## Schritt 5: Fügen Sie die GroupShape in das Dokument ein
 Ein ... kreieren`DocumentBuilder` Objekt und fügen Sie das ein`groupShape` in das Dokument einfügen`InsertNode` Methode.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(groupShape);
```

## Schritt 6: Speichern Sie das Dokument
 Speichern Sie das Dokument mit im angegebenen Verzeichnis`Save`Methode. Geben Sie den gewünschten Dateinamen mit der entsprechenden Dateierweiterung an. In diesem Beispiel speichern wir das Dokument als „WorkingWithShapes.AddGroupShape.docx“.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

### Beispielquellcode für „Gruppenform hinzufügen“ mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
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

Das ist es! Sie haben mit Aspose.W erfolgreich eine Gruppenform mit mehreren Formen zu Ihrem Word-Dokument hinzugefügt