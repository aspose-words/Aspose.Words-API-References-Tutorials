---
title: Vertikaler Anker
linktitle: Vertikaler Anker
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit der vertikalen Ankerfunktion in Aspose.Words für .NET eine Form vertikal in einem Dokument positionieren.
type: docs
weight: 10
url: /de/net/programming-with-shapes/vertical-anchor/
---

In diesem Tutorial wird erklärt, wie Sie die vertikale Ankerfunktion in Aspose.Words für .NET verwenden, um eine Form vertikal in einem Dokument zu positionieren. Indem Sie die vertikale Ankereigenschaft einer Form festlegen, können Sie ihre vertikale Ausrichtung relativ zum Text oder zur Seite steuern.

## Voraussetzungen
Um diesem Tutorial folgen zu können, benötigen Sie Folgendes:

- Aspose.Words für .NET-Bibliothek installiert.
- Grundkenntnisse in C# und Textverarbeitung mit Word-Dokumenten.

## Schritt 1: Einrichten des Dokumentverzeichnisses
 Beginnen Sie mit der Einrichtung des Pfades zu Ihrem Dokumentverzeichnis. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zum Verzeichnis, in dem Sie das Dokument speichern möchten.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Neues Dokument und DocumentBuilder erstellen
 Erstellen Sie eine neue Instanz des`Document` Klasse und eine`DocumentBuilder`Objekt, um mit dem Dokument zu arbeiten.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 3: Einfügen und Konfigurieren einer Form
 Fügen Sie eine Form in das Dokument ein, indem Sie das`InsertShape` Methode der`DocumentBuilder` Objekt. Legen Sie die gewünschten Abmessungen für die Form fest.

```csharp
Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
```

## Schritt 4: Den vertikalen Anker setzen
Legen Sie die vertikale Ankereigenschaft der Form fest, um ihre vertikale Ausrichtung zu steuern. In diesem Beispiel legen wir sie auf „Unten“ fest, um die Form am unteren Rand des Textes oder der Seite zu verankern.

```csharp
textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
```

## Schritt 5: Der Form Inhalt hinzufügen
 Verwenden Sie die`MoveTo` Methode der`DocumentBuilder` Objekt, um den Cursor zum ersten Absatz der Form zu bewegen. Verwenden Sie dann das`Write` Methode, um der Form Inhalt hinzuzufügen.

```csharp
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Textbox contents");
```

## Schritt 6: Speichern Sie das Dokument
 Speichern Sie das Dokument im angegebenen Verzeichnis mit dem`Save`Methode. Geben Sie den gewünschten Dateinamen mit der entsprechenden Dateierweiterung an. In diesem Beispiel speichern wir das Dokument als „WorkingWithShapes.VerticalAnchor.docx“.

```csharp
doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

### Beispielquellcode für Vertical Anchor mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
	textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
	builder.MoveTo(textBox.FirstParagraph);
	builder.Write("Textbox contents");
	doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

Das ist es! Sie haben die vertikale Ankerfunktion in Aspose.Words für .NET erfolgreich verwendet, um eine Form vertikal innerhalb eines Dokuments zu positionieren.