---
title: Inhaltsverzeichnis im Word-Dokument entfernen
linktitle: Inhaltsverzeichnis im Word-Dokument entfernen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie das Inhaltsverzeichnis in einem Word-Dokument mit Aspose.Words für .NET entfernen.
type: docs
weight: 10
url: /de/net/remove-content/remove-table-of-contents/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie das Inhaltsverzeichnis in einem Word-Dokument mithilfe der Aspose.Words-Bibliothek für .NET entfernen. Das Inhaltsverzeichnis kann manchmal überflüssig oder unnötig sein, und dieser Code hilft Ihnen, es effektiv zu entfernen. Wir stellen Ihnen eine Schritt-für-Schritt-Anleitung zur Verfügung, die Ihnen hilft, den Code zu verstehen und in Ihrem eigenen .NET-Projekt zu implementieren.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über die folgenden Artikel verfügen:
- Grundkenntnisse der Programmiersprache C#
- Die in Ihrem Projekt installierte Aspose.Words-Bibliothek für .NET
- Ein Word-Dokument mit einem Inhaltsverzeichnis, das Sie löschen möchten

## Schritt 1: Definieren Sie das Dokumentenverzeichnis
 Zuerst müssen Sie den Verzeichnispfad auf den Speicherort Ihres Word-Dokuments festlegen. Ersetzen`"YOUR DOCUMENT DIRECTORY"` im Code mit dem entsprechenden Pfad.

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument hoch
 Als nächstes laden wir das Word-Dokument in eine Instanz von`Document` Klasse mit der`Load` Methode.

```csharp
// Laden Sie das Dokument
Document doc = new Document(dataDir + "your-document.docx");
```

## Schritt 3: Löschen Sie das Inhaltsverzeichnis
 Um das Inhaltsverzeichnis zu entfernen, durchlaufen wir den Typ TOC (Inhaltsverzeichnis).`FieldStart` Knoten im Dokument. Wir werden diese Knoten speichern, damit wir schnell darauf zugreifen und eine Liste der zu löschenden Knoten erstellen können.

```csharp
// Speichern Sie FieldStart-Knoten von Inhaltsverzeichnisfeldern im Dokument, um schnell darauf zugreifen zu können.
List<FieldStart> fieldStarts = new List<FieldStart>();
// Dies ist eine Liste zum Speichern der im angegebenen Inhaltsverzeichnis gefundenen Knoten. Sie werden am Ende dieser Methode gelöscht.
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
     if (start.FieldType == FieldType.FieldTOC)
     {
         fieldStarts.Add(start);
     }
}

// Überprüfen Sie, ob der angegebene TOC-Index vorhanden ist.
if (index > fieldStarts.Count - 1)
     throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
     // Es ist sicherer, diese Knoten zu speichern und am Ende alle zu löschen.
     nodeList.Add(currentNode);
     currentNode = currentNode.NextPreOrder(doc);

     // Wenn wir auf einen FieldEnd-Knoten vom Typ FieldTOC stoßen,
     //Wir wissen, dass wir am Ende des aktuellen Inhaltsverzeichnisses angelangt sind und hören hier auf.
     if (currentNode.NodeType == NodeType.FieldEnd)
     {
         FieldEnd fieldEnd = (FieldEnd)currentNode;
         if (fieldEnd.FieldType == FieldType.FieldTOC)


             isRemoving = false;
     }
}

foreach(Node node in nodeList)
{
     node. Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```


### Beispielquellcode zum Entfernen des Inhaltsverzeichnisses mit Aspose.Words für .NET 
```csharp

//Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
// Laden Sie das Dokument
Document doc = new Document(dataDir + "your-document.docx");

// Speichern Sie die FieldStart-Knoten von TOC-Feldern im Dokument, um schnell darauf zugreifen zu können.
List<FieldStart> fieldStarts = new List<FieldStart>();
// Dies ist eine Liste zum Speichern der im angegebenen Inhaltsverzeichnis gefundenen Knoten. Sie werden am Ende dieser Methode entfernt.
List<Node> nodeList = new List<Node>();

foreach (FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
	if (start.FieldType == FieldType.FieldTOC)
	{
		fieldStarts.Add(start);
	}
}

// Stellen Sie sicher, dass das durch den übergebenen Index angegebene Inhaltsverzeichnis vorhanden ist.
if (index > fieldStarts.Count - 1)
	throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
	// Es ist sicherer, diese Knoten zu speichern und später alle auf einmal zu löschen.
	nodeList.Add(currentNode);
	currentNode = currentNode.NextPreOrder(doc);

	// Sobald wir auf einen FieldEnd-Knoten vom Typ FieldTOC stoßen,
	// Wir wissen, dass wir am Ende des aktuellen Inhaltsverzeichnisses angelangt sind und hören hier auf.
	if (currentNode.NodeType == NodeType.FieldEnd)
	{
		FieldEnd fieldEnd = (FieldEnd) currentNode;
		if (fieldEnd.FieldType == FieldType.FieldTOC)
			isRemoving = false;
	}
}

foreach (Node node in nodeList)
{
	node.Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
        
```

## Abschluss
In diesem Tutorial haben wir eine Schritt-für-Schritt-Anleitung zum Entfernen des Inhaltsverzeichnisses aus einem Word-Dokument mithilfe der Aspose.Words-Bibliothek für .NET vorgestellt. Indem Sie den bereitgestellten Code und die Anweisungen befolgen, können Sie das Inhaltsverzeichnis ganz einfach entfernen und das Layout Ihres Dokuments verbessern. Denken Sie daran, den Verzeichnispfad und die Dateinamen an Ihre spezifischen Bedürfnisse anzupassen.

### FAQs

#### F: Warum sollte ich Aspose.Words verwenden, um das Inhaltsverzeichnis in einem Word-Dokument zu entfernen?

A: Aspose.Words ist eine leistungsstarke und vielseitige Klassenbibliothek zum Bearbeiten von Word-Dokumenten in .NET-Anwendungen. Durch die Verwendung von Aspose.Words können Sie das Inhaltsverzeichnis effektiv aus Ihren Dokumenten entfernen, was nützlich sein kann, wenn das Inhaltsverzeichnis überflüssig oder unnötig ist. Dadurch können Sie den Inhalt Ihres Dokuments individuell anpassen und seine Gesamtpräsentation verbessern.

#### F: Wie lade ich ein Dokument in Aspose.Words für .NET hoch?

A: Um das Inhaltsverzeichnis in einem Word-Dokument zu entfernen, müssen Sie das Dokument zunächst mit der Load()-Methode von Aspose.Words in den Speicher laden. Hier ist ein Beispielcode zum Laden eines Dokuments aus einem bestimmten Verzeichnis:

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das Dokument
Document doc = new Document(dataDir + "your-document.docx");
```

 Ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokument.

#### F: Wie entferne ich das Inhaltsverzeichnis in einem Dokument mit Aspose.Words?

 A: Um das Inhaltsverzeichnis zu entfernen, müssen Sie es durchlaufen`FieldStart` Typknoten des Inhaltsverzeichnisses im Dokument. Sie können diese Knoten für den schnellen Zugriff speichern und eine Liste der zu löschenden Knoten erstellen. Hier ist ein Beispielcode:

```csharp
// Speichern Sie FieldStart-Knoten von Inhaltsverzeichnisfeldern im Dokument, um schnell darauf zugreifen zu können.
List<FieldStart> fieldStarts = new List<FieldStart>();
//Dies ist eine Liste zum Speichern von Knoten, die innerhalb des angegebenen Inhaltsverzeichnisses gefunden werden. Sie werden am Ende dieser Methode gelöscht.
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
if (start.FieldType == FieldType.FieldTOC)
{
fieldStarts.Add(start);
}
}

// Überprüfen Sie, ob der angegebene Inhaltsverzeichnisindex vorhanden ist.
if (index > fieldStarts.Count - 1)
throw new ArgumentOutOfRangeException("Table of contents index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
// Es ist sicherer, diese Knoten zu speichern und am Ende alle zu löschen.
nodeList.Add(currentNode);
currentNode = currentNode.NextPreOrder(doc);

// Wenn wir auf einen FieldEnd-Knoten vom Typ FieldTOC stoßen,
//Wir wissen, dass wir am Ende des aktuellen Inhaltsverzeichnisses angelangt sind und hören hier auf.
if (currentNode.NodeType == NodeType.FieldEnd)
{
FieldEnd fieldEnd = (FieldEnd)currentNode;
if (fieldEnd.FieldType == FieldType.FieldTOC)
isRemoving = false;
}
}

foreach(Node node in nodeList)
{
node. Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```

#### F: Wie speichere ich ein bearbeitetes Dokument in Aspose.Words für .NET?

A: Nach dem Löschen des Inhaltsverzeichnisses müssen Sie das geänderte Dokument mit der Save()-Methode speichern. Geben Sie den gewünschten Ausgabedateipfad und das Format (z. B. DOCX) für das bearbeitete Dokument an. Hier ist ein Beispielcode:

```csharp
doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```