---
title: Klare Inhaltssteuerung
linktitle: Klare Inhaltssteuerung
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET den Inhalt eines Steuerelements in einem Word-Dokument löschen.
type: docs
weight: 10
url: /de/net/programming-with-sdt/clear-contents-control/
---

Dieses Tutorial zeigt, wie Sie den Inhalt eines SDT in einem Word-Dokument mit Aspose.Words für .NET löschen. Durch das Löschen des Inhalts eines SDT werden sämtlicher Text oder alle untergeordneten Knoten innerhalb des Inhaltssteuerelements entfernt.

## Voraussetzungen
Um diesem Tutorial folgen zu können, benötigen Sie Folgendes:

- Aspose.Words für .NET-Bibliothek installiert.
- Grundkenntnisse in C# und Textverarbeitung mit Word-Dokumenten.

## Schritt 1: Einrichten des Dokumentverzeichnisses
 Beginnen Sie mit der Einrichtung des Pfades zu Ihrem Dokumentverzeichnis. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zum Verzeichnis, in dem sich Ihr Dokument befindet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument und holen Sie sich das StructuredDocumentTag
 Laden Sie das Word-Dokument mit dem`Document` Konstruktor, wobei der Pfad zum Dokument als Parameter übergeben wird. Rufen Sie dann die gewünschte`StructuredDocumentTag`aus dem Dokument. In diesem Beispiel gehen wir davon aus, dass der SDT der erste untergeordnete Knoten im Dokument ist.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Schritt 3: Löschen Sie den Inhalt des StructuredDocumentTag
 Löschen Sie den Inhalt des SDT mit dem`Clear` -Methode. Dadurch werden sämtlicher Text oder alle untergeordneten Knoten innerhalb des Inhaltssteuerelements entfernt.

```csharp
sdt.Clear();
```

## Schritt 4: Speichern Sie das Dokument
 Speichern Sie das geänderte Dokument mit dem`Save` Methode. Geben Sie den gewünschten Dateinamen mit der entsprechenden Dateierweiterung an. In diesem Beispiel speichern wir das Dokument als „WorkingWithSdt.ClearContentsControl.doc“.

```csharp
doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

### Beispielquellcode für Clear Contents Control mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Clear();
	doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

Das ist es! Sie haben den Inhalt eines StructuredDocumentTag in Ihrem Word-Dokument erfolgreich mit Aspose.Words für .NET gelöscht.