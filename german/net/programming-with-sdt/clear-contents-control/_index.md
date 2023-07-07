---
title: Klare Inhaltskontrolle
linktitle: Klare Inhaltskontrolle
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET den Inhalt eines Steuerelements in einem Word-Dokument löschen.
type: docs
weight: 10
url: /de/net/programming-with-sdt/clear-contents-control/
---

Dieses Tutorial zeigt, wie Sie den Inhalt eines SDT in einem Word-Dokument mit Aspose.Words für .NET löschen. Durch das Löschen des Inhalts eines SDT werden alle Text- oder untergeordneten Knoten innerhalb des Inhaltssteuerelements entfernt.

## Voraussetzungen
Um diesem Tutorial folgen zu können, benötigen Sie Folgendes:

- Aspose.Words für .NET-Bibliothek installiert.
- Grundkenntnisse in C# und der Arbeit mit Word-Dokumenten.

## Schritt 1: Richten Sie das Dokumentenverzeichnis ein
 Beginnen Sie mit der Einrichtung des Pfads zu Ihrem Dokumentenverzeichnis. Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu dem Verzeichnis, in dem sich Ihr Dokument befindet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument und rufen Sie das StructuredDocumentTag ab
 Laden Sie das Word-Dokument mit`Document` Konstruktor, der den Pfad zum Dokument als Parameter übergibt. Rufen Sie dann das Gewünschte ab`StructuredDocumentTag` aus dem Dokument. In diesem Beispiel gehen wir davon aus, dass der SDT der erste untergeordnete Knoten im Dokument ist.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Schritt 3: Löschen Sie den Inhalt des StructuredDocumentTag
 Löschen Sie den Inhalt des SDT mit`Clear` Methode. Dadurch werden alle Text- oder untergeordneten Knoten innerhalb des Inhaltssteuerelements entfernt.

```csharp
sdt.Clear();
```

## Schritt 4: Speichern Sie das Dokument
Speichern Sie das geänderte Dokument mit`Save`Methode. Geben Sie den gewünschten Dateinamen mit der entsprechenden Dateierweiterung an. In diesem Beispiel speichern wir das Dokument als „WorkingWithSdt.ClearContentsControl.doc“.

```csharp
doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

### Beispielquellcode für Clear Contents Control mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Clear();
	doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

Das ist es! Sie haben den Inhalt eines StructuredDocumentTag in Ihrem Word-Dokument mit Aspose.Words für .NET erfolgreich gelöscht.