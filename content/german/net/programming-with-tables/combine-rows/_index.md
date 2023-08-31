---
title: Zeilen kombinieren
linktitle: Zeilen kombinieren
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie Tabellenzeilen in einem Word-Dokument mit Aspose.Words für .NET kombinieren.
type: docs
weight: 10
url: /de/net/programming-with-tables/combine-rows/
---

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET Tabellenzeilen in einem Word-Dokument kombinieren. Wir folgen einer Schritt-für-Schritt-Anleitung, um den Code zu verstehen und diese Funktion zu implementieren. Am Ende dieses Tutorials werden Sie in der Lage sein, Tabellenzeilen in Ihren Word-Dokumenten programmgesteuert zu bearbeiten und zusammenzuführen.

## Schritt 1: Projekteinrichtung
1. Starten Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Fügen Sie einen Verweis auf die Aspose.Words für .NET-Bibliothek hinzu.

## Schritt 2: Laden des Dokuments und Zugriff auf die Tabellen
Um die Textverarbeitung mit Tabellen zu starten, müssen wir das Dokument, das sie enthält, laden und darauf zugreifen. Folge diesen Schritten:

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das Dokument
Document doc = new Document(dataDir + "Tables.docx");

// Zugriff auf Tabellen
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);
Table secondTable = (Table)doc.GetChild(NodeType.Table, 1, true);
```

Stellen Sie sicher, dass Sie „IHR DOKUMENTENVERZEICHNIS“ durch den tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis ersetzen.

## Schritt 3: Tabellenzeilen kombinieren
Als Nächstes kombinieren wir die Zeilen der zweiten Tabelle mit dem Ende der ersten Tabelle. Verwenden Sie den folgenden Code:

```csharp
// Kombination von Tabellenzeilen
while (secondTable.HasChildNodes)
     firstTable.Rows.Add(secondTable.FirstRow);
secondTable.Remove();
```

 Hier verwenden wir a`while` Schleife, um alle Zeilen des zweiten Arrays zu durchlaufen und sie mithilfe von am Ende des ersten Arrays hinzuzufügen`Add` Methode. Als nächstes entfernen wir die zweite Tabelle mithilfe von aus dem Dokument`Remove` Methode.

## Schritt 4: Speichern des geänderten Dokuments
Abschließend müssen wir das geänderte Dokument mit den kombinierten Tabellenzeilen speichern. Verwenden Sie den folgenden Code:

```csharp
// Speichern Sie das geänderte Dokument
doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen für das Ausgabedokument angeben.

### Beispielquellcode für Combine Rows mit Aspose.Words für .NET 

```csharp
	//Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// Die Zeilen aus der zweiten Tabelle werden an das Ende der ersten Tabelle angehängt.
	Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
	Table secondTable = (Table) doc.GetChild(NodeType.Table, 1, true);
	// Hängen Sie alle Zeilen der aktuellen Tabelle an die nächsten Tabellen an
	// mit unterschiedlicher Zellenanzahl und -breite können in einer Tabelle zusammengefasst werden.
	while (secondTable.HasChildNodes)
		firstTable.Rows.Add(secondTable.FirstRow);
	secondTable.Remove();
	doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET Tabellenzeilen in einem Word-Dokument kombiniert. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code implementieren, können Sie Tabellenzeilen in Ihren Word-Dokumenten programmgesteuert bearbeiten. Mit dieser Funktion können Sie Ihre Daten effizient zusammenführen und in einer Tabelle organisieren.