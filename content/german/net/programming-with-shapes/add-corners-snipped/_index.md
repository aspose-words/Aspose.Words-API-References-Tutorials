---
title: Abgeschnittene Ecken hinzufügen
linktitle: Abgeschnittene Ecken hinzufügen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine Form mit abgeschnittenen Ecken zu einem Word-Dokument hinzufügen.
type: docs
weight: 10
url: /de/net/programming-with-shapes/add-corners-snipped/
---

 In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET eine Form mit abgeschnittenen Ecken zu einem Word-Dokument hinzufügen. Die Form der abgeschnittenen Ecken kann mit angepasst und eingefügt werden`InsertShape` Methode.

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

## Schritt 3: Fügen Sie die Form mit abgeschnittenen Ecken ein
 Benutzen Sie die`InsertShape` Methode der`DocumentBuilder` Objekt, um eine Form mit abgeschnittenen Ecken einzufügen. Geben Sie den Formtyp an (in diesem Fall`ShapeType.TopCornersSnipped`) und geben Sie die gewünschte Größe für die Form ein.

```csharp
builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
```

## Schritt 4: Speichern Sie das Dokument
 Speichern Sie das Dokument mit im angegebenen Verzeichnis`Save` Methode. Geben Sie den gewünschten Dateinamen mit der entsprechenden Dateierweiterung an. In diesem Beispiel speichern wir das Dokument als „WorkingWithShapes.AddCornersSnipped.docx“.

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);
```

### Beispielquellcode für Add Corners Snipped mit Aspose.Words für .NET 

```csharp
	//Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
	{
		Compliance = OoxmlCompliance.Iso29500_2008_Transitional
	};
	doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);

```

Das ist es! Sie haben Ihrem Word-Dokument mit Aspose.Words für .NET erfolgreich eine Form mit ausgeschnittenen Ecken hinzugefügt.