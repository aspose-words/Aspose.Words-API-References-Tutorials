---
title: Vertikaler Anker
linktitle: Vertikaler Anker
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie eine Form mithilfe der vertikalen Ankerfunktion in Aspose.Words für .NET vertikal innerhalb eines Dokuments positionieren.
type: docs
weight: 10
url: /de/net/programming-with-shapes/vertical-anchor/
---

In diesem Tutorial wird erklärt, wie Sie die vertikale Ankerfunktion in Aspose.Words für .NET verwenden, um eine Form vertikal innerhalb eines Dokuments zu positionieren. Durch Festlegen der vertikalen Ankereigenschaft einer Form können Sie deren vertikale Ausrichtung relativ zum Text oder zur Seite steuern.

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

## Schritt 3: Fügen Sie eine Form ein und konfigurieren Sie sie
 Fügen Sie mithilfe von eine Form in das Dokument ein`InsertShape` Methode der`DocumentBuilder` Objekt. Stellen Sie die gewünschten Abmessungen für die Form ein.

```csharp
Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
```

## Schritt 4: Setzen Sie den vertikalen Anker
Legen Sie die vertikale Ankereigenschaft der Form fest, um ihre vertikale Ausrichtung zu steuern. In diesem Beispiel setzen wir es auf „Unten“, um die Form am unteren Rand des Textes oder der Seite zu verankern.

```csharp
textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
```

## Schritt 5: Fügen Sie der Form Inhalte hinzu
 Benutzen Sie die`MoveTo` Methode der`DocumentBuilder` Objekt, um den Cursor zum ersten Absatz der Form zu bewegen. Dann verwenden Sie die`Write` Methode zum Hinzufügen von Inhalten zur Form.

```csharp
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Textbox contents");
```

## Schritt 6: Speichern Sie das Dokument
 Speichern Sie das Dokument mit im angegebenen Verzeichnis`Save` Methode. Geben Sie den gewünschten Dateinamen mit der entsprechenden Dateierweiterung an. In diesem Beispiel speichern wir das Dokument als „WorkingWithShapes.VerticalAnchor.docx“.

```csharp
doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

### Beispielquellcode für Vertical Anchor mit Aspose.Words für .NET 

```csharp
	//Pfad zu Ihrem Dokumentenverzeichnis
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