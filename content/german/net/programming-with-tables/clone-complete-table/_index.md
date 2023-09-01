---
title: Vollständige Tabelle klonen
linktitle: Vollständige Tabelle klonen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine ganze Tabelle in ein Word-Dokument klonen.
type: docs
weight: 10
url: /de/net/programming-with-tables/clone-complete-table/
---

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET eine ganze Tabelle in ein Word-Dokument klonen. Wir folgen einer Schritt-für-Schritt-Anleitung, um den Code zu verstehen und diese Funktion zu implementieren. Am Ende dieses Tutorials werden Sie in der Lage sein, Tabellen programmgesteuert in Ihre Word-Dokumente zu klonen.

## Schritt 1: Projekteinrichtung
1. Starten Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Fügen Sie einen Verweis auf die Aspose.Words für .NET-Bibliothek hinzu.

## Schritt 2: Laden des Dokuments und Zugriff auf die Tabelle
Um die Textverarbeitung mit der Tabelle zu starten, müssen wir das Dokument, das sie enthält, laden und darauf zugreifen. Folge diesen Schritten:

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das Dokument
Document doc = new Document(dataDir + "Tables.docx");

// Zugriff auf das Array
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Stellen Sie sicher, dass Sie „IHR DOKUMENTENVERZEICHNIS“ durch den tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis ersetzen.

## Schritt 3: Vollständiger Array-Klon
Als nächstes klonen wir die gesamte Tabelle und fügen sie nach dem Original in das Dokument ein. Verwenden Sie den folgenden Code:

```csharp
// Klonen Sie das Array
Table tableClone = (Table)table.Clone(true);

// Fügen Sie die geklonte Tabelle nach dem Original in das Dokument ein
table.ParentNode.InsertAfter(tableClone, table);

// Fügen Sie zwischen den beiden Tabellen einen leeren Absatz ein
// Andernfalls werden sie beim Speichern zu einem zusammengefasst (dies liegt an der Dokumentenvalidierung).
table.ParentNode.InsertAfter(new Paragraph(doc), table);
```

 Hier verwenden wir die`Clone` Methode zum Erstellen einer vollständigen Kopie des Arrays. Dann verwenden wir`InsertAfter` um die geklonte Tabelle nach der Originaltabelle in das Dokument einzufügen. Außerdem fügen wir zwischen den beiden Tabellen einen leeren Absatz ein, um zu verhindern, dass sie beim Speichern zusammengeführt werden.

## Schritt 4: Speichern des geänderten Dokuments
Abschließend müssen wir das geänderte Dokument mit der geklonten Tabelle speichern. Verwenden Sie den folgenden Code:

```csharp
// Speichern Sie das geänderte Dokument
doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen für das Ausgabedokument angeben.
  
### Beispielquellcode für Clone Complete Table mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	//Klonen Sie die Tabelle und fügen Sie sie nach dem Original in das Dokument ein.
	Table tableClone = (Table) table.Clone(true);
	table.ParentNode.InsertAfter(tableClone, table);
	// Fügen Sie zwischen den beiden Tabellen einen leeren Absatz ein.
	// Andernfalls werden sie beim Speichern zu einem zusammengefasst. Dies hat mit der Dokumentenvalidierung zu tun.
	table.ParentNode.InsertAfter(new Paragraph(doc), table);
	doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET eine ganze Tabelle in ein Word-Dokument klont. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code implementieren, können Sie Tabellen in Ihren Word-Dokumenten programmgesteuert klonen. Mit dieser Funktion können Sie erweiterte Manipulationen an Arrays durchführen, um sie Ihren spezifischen Anforderungen anzupassen.