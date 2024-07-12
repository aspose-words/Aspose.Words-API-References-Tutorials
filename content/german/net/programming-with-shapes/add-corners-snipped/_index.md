---
title: Abgeschnittene Ecken hinzufügen
linktitle: Abgeschnittene Ecken hinzufügen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET einem Word-Dokument eine Form mit abgeschnittenen Ecken hinzufügen.
type: docs
weight: 10
url: /de/net/programming-with-shapes/add-corners-snipped/
---

 In diesem Tutorial wird erklärt, wie Sie mit Aspose.Words für .NET eine Form mit abgeschnittenen Ecken zu einem Word-Dokument hinzufügen. Die Form mit abgeschnittenen Ecken kann angepasst und mithilfe des`InsertShape` Methode.

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

## Schritt 3: Fügen Sie die abgeschnittene Form für die Ecken ein
 Verwenden Sie die`InsertShape` Methode der`DocumentBuilder` Objekt, um eine Form mit abgeschnittenen Ecken einzufügen. Geben Sie den Formtyp an (in diesem Fall`ShapeType.TopCornersSnipped`) und geben Sie die gewünschte Größe für die Form an.

```csharp
builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
```

## Schritt 4: Speichern Sie das Dokument
 Speichern Sie das Dokument im angegebenen Verzeichnis mit dem`Save`Methode. Geben Sie den gewünschten Dateinamen mit der entsprechenden Dateierweiterung an. In diesem Beispiel speichern wir das Dokument als „WorkingWithShapes.AddCornersSnipped.docx“.

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);
```

### Beispielquellcode für Add Corners Snipped mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
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

Das ist es! Sie haben Ihrem Word-Dokument mit Aspose.Words für .NET erfolgreich eine Form mit abgeschnittenen Ecken hinzugefügt.