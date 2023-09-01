---
title: Seitenverhältnis gesperrt
linktitle: Seitenverhältnis gesperrt
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET das Seitenverhältnis einer Form in einem Word-Dokument sperren oder entsperren.
type: docs
weight: 10
url: /de/net/programming-with-shapes/aspect-ratio-locked/
---

In diesem Tutorial wird erklärt, wie Sie das Seitenverhältnis einer Form in einem Word-Dokument mit Aspose.Words für .NET sperren oder entsperren. Durch Sperren des Seitenverhältnisses können Sie bei der Größenänderung die ursprünglichen Proportionen der Form beibehalten.

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

## Schritt 3: Fügen Sie eine Bildform ein
 Benutzen Sie die`InsertImage` Methode der`DocumentBuilder` Objekt, um eine Bildform in das Dokument einzufügen. Geben Sie den Pfad zur Bilddatei als Parameter an.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## Schritt 4: Sperren oder entsperren Sie das Seitenverhältnis
 Stellen Sie die ein`AspectRatioLocked` Eigenschaft der Form zu`true` oder`false` um das Seitenverhältnis zu sperren bzw. zu entsperren.

```csharp
shape.AspectRatioLocked = false; //Entsperren Sie das Seitenverhältnis
```

## Schritt 5: Speichern Sie das Dokument
 Speichern Sie das Dokument mit im angegebenen Verzeichnis`Save` Methode. Geben Sie den gewünschten Dateinamen mit der entsprechenden Dateierweiterung an. In diesem Beispiel speichern wir das Dokument als „WorkingWithShapes.AspectRatioLocked.docx“.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

### Beispielquellcode für Aspect Ratio Locked mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

Das ist es! Sie haben das Seitenverhältnis einer Form in Ihrem Word-Dokument mit Aspose.Words für .NET erfolgreich gesperrt oder entsperrt.