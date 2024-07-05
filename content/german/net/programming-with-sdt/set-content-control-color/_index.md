---
title: Farbe für Inhaltssteuerelement festlegen
linktitle: Farbe für Inhaltssteuerelement festlegen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die Farbe eines Inhaltssteuerelements in einem Word-Dokument festlegen und dessen Erscheinungsbild anpassen.
type: docs
weight: 10
url: /de/net/programming-with-sdt/set-content-control-color/
---

In diesem Tutorial wird erklärt, wie Sie mit Aspose.Words für .NET die Farbe eines Inhaltssteuerelements in einem Word-Dokument festlegen. Sie können das Erscheinungsbild von Inhaltssteuerelementen anpassen, indem Sie ihre Farbe ändern.

## Voraussetzungen
Um diesem Tutorial folgen zu können, benötigen Sie Folgendes:

- Aspose.Words für .NET-Bibliothek installiert.
- Grundkenntnisse in C# und Textverarbeitung mit Word-Dokumenten.

## Schritt 1: Einrichten des Dokumentverzeichnisses
 Beginnen Sie mit der Einrichtung des Pfades zu Ihrem Dokumentverzeichnis. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zum Verzeichnis, in dem sich Ihr Dokument befindet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument und rufen Sie das Inhaltssteuerelement ab
 Laden Sie das Word-Dokument mit dem`Document` Konstruktor, wobei der Pfad zum Dokument als Parameter übergeben wird. Rufen Sie das gewünschte Inhaltssteuerelement aus dem Dokument ab. In diesem Beispiel gehen wir davon aus, dass das Inhaltssteuerelement das erste strukturierte Dokument-Tag im Dokument ist.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Schritt 3: Festlegen der Inhaltssteuerelementfarbe
 Legen Sie die Farbe des Inhaltssteuerelements fest, indem Sie ihm eine`Color` Wert für die`Color` Eigenschaft des strukturierten Dokument-Tags. In diesem Beispiel setzen wir die Farbe auf Rot.

```csharp
sdt.Color = Color.Red;
```

## Schritt 4: Speichern Sie das Dokument
 Speichern Sie das geänderte Dokument im angegebenen Verzeichnis mit dem`Save` Methode. Geben Sie den gewünschten Dateinamen mit der entsprechenden Dateierweiterung an. In diesem Beispiel speichern wir das Dokument als „WorkingWithSdt.SetContentControlColor.docx“.

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

### Beispielquellcode zum Festlegen der Inhaltssteuerelementfarbe mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Color = Color.Red;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

Das ist es! Sie haben die Farbe eines Inhaltssteuerelements in Ihrem Word-Dokument mit Aspose.Words für .NET erfolgreich festgelegt.