---
title: Vollständige Tabelle klonen
linktitle: Vollständige Tabelle klonen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine ganze Tabelle in ein Word-Dokument klonen.
type: docs
weight: 10
url: /de/net/programming-with-tables/clone-complete-table/
---

In diesem Tutorial lernen wir, wie man mit Aspose.Words für .NET eine ganze Tabelle in ein Word-Dokument klonen kann. Wir folgen einer Schritt-für-Schritt-Anleitung, um den Code zu verstehen und diese Funktion zu implementieren. Am Ende dieses Tutorials können Sie Tabellen programmgesteuert in Ihre Word-Dokumente klonen.

## Schritt 1: Projekt-Setup
1. Starten Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Fügen Sie einen Verweis auf die Aspose.Words-Bibliothek für .NET hinzu.

## Schritt 2: Laden des Dokuments und Zugriff auf die Tabelle
Um Words Processing mit der Tabelle zu starten, müssen wir das Dokument, das sie enthält, laden und darauf zugreifen. Folgen Sie diesen Schritten:

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das Dokument
Document doc = new Document(dataDir + "Tables.docx");

// Zugriff auf das Array
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Ersetzen Sie „IHR DOKUMENTVERZEICHNIS“ unbedingt durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 3: Vollständiges Array-Klonen
Als nächstes klonen wir die gesamte Tabelle und fügen sie nach dem Original in das Dokument ein. Verwenden Sie den folgenden Code:

```csharp
// Klonen Sie das Array
Table tableClone = (Table)table.Clone(true);

// Fügen Sie die geklonte Tabelle nach der Originaltabelle in das Dokument ein.
table.ParentNode.InsertAfter(tableClone, table);

// Fügen Sie zwischen den beiden Tabellen einen leeren Absatz ein.
// Andernfalls werden sie beim Speichern zu einem zusammengefasst (dies liegt an der Dokumentvalidierung).
table.ParentNode.InsertAfter(new Paragraph(doc), table);
```

 Hier verwenden wir die`Clone` Methode, um eine vollständige Kopie des Arrays zu erstellen. Dann verwenden wir`InsertAfter` um die geklonte Tabelle nach der Originaltabelle in das Dokument einzufügen. Wir fügen außerdem einen leeren Absatz zwischen den beiden Tabellen ein, um zu verhindern, dass sie beim Speichern zusammengeführt werden.

## Schritt 4: Speichern des geänderten Dokuments
Zum Schluss müssen wir das geänderte Dokument mit der geklonten Tabelle speichern. Verwenden Sie dazu den folgenden Code:

```csharp
// Speichern des geänderten Dokuments
doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

Achten Sie darauf, den richtigen Pfad und Dateinamen für das Ausgabedokument anzugeben.
  
### Beispielquellcode zum Klonen vollständiger Tabellen mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Klonen Sie die Tabelle und fügen Sie sie nach dem Original in das Dokument ein.
	Table tableClone = (Table) table.Clone(true);
	table.ParentNode.InsertAfter(tableClone, table);
	// Fügen Sie zwischen den beiden Tabellen einen leeren Absatz ein.
	// oder sie werden beim Speichern zu einem zusammengefasst. Dies hat mit der Dokumentvalidierung zu tun.
	table.ParentNode.InsertAfter(new Paragraph(doc), table);
	doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET eine ganze Tabelle in ein Word-Dokument klont. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code implementieren, können Sie Tabellen in Ihren Word-Dokumenten programmgesteuert klonen. Mit dieser Funktion können Sie erweiterte Manipulationen an Arrays durchführen, um sie Ihren spezifischen Anforderungen anzupassen.