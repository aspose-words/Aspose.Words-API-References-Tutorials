---
title: Seitenverhältnis gesperrt
linktitle: Seitenverhältnis gesperrt
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET das Seitenverhältnis einer Form in einem Word-Dokument sperren oder entsperren.
type: docs
weight: 10
url: /de/net/programming-with-shapes/aspect-ratio-locked/
---

In diesem Tutorial wird erklärt, wie Sie das Seitenverhältnis einer Form in einem Word-Dokument mit Aspose.Words für .NET sperren oder entsperren. Durch Sperren des Seitenverhältnisses können Sie die ursprünglichen Proportionen der Form beibehalten, wenn Sie ihre Größe ändern.

## Voraussetzungen
Um diesem Tutorial folgen zu können, benötigen Sie Folgendes:

- Aspose.Words für .NET-Bibliothek installiert.
- Grundkenntnisse in C# und Textverarbeitung mit Word-Dokumenten.

## Schritt 1: Einrichten des Dokumentverzeichnisses
 Beginnen Sie mit der Einrichtung des Pfades zu Ihrem Dokumentverzeichnis. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"`durch den tatsächlichen Pfad zum Verzeichnis, in dem Sie das Dokument speichern möchten.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Neues Dokument und DocumentBuilder erstellen
 Erstellen Sie eine neue Instanz des`Document` Klasse und eine`DocumentBuilder` Objekt, um mit dem Dokument zu arbeiten.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 3: Einfügen einer Bildform
 Verwenden Sie die`InsertImage` Methode der`DocumentBuilder`Objekt, um eine Bildform in das Dokument einzufügen. Geben Sie den Pfad zur Bilddatei als Parameter an.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## Schritt 4: Sperren oder Entsperren des Seitenverhältnisses
 Legen Sie die`AspectRatioLocked` Eigenschaft der Form zu`true` oder`false` um das Seitenverhältnis zu sperren bzw. zu entsperren.

```csharp
shape.AspectRatioLocked = false; // Entsperren Sie das Seitenverhältnis
```

## Schritt 5: Speichern Sie das Dokument
 Speichern Sie das Dokument im angegebenen Verzeichnis mit dem`Save` Methode. Geben Sie den gewünschten Dateinamen mit der entsprechenden Dateierweiterung an. In diesem Beispiel speichern wir das Dokument als „WorkingWithShapes.AspectRatioLocked.docx“.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

### Beispielquellcode für Aspect Ratio Locked mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

Das ist es! Sie haben das Seitenverhältnis einer Form in Ihrem Word-Dokument mit Aspose.Words für .NET erfolgreich gesperrt oder entsperrt.