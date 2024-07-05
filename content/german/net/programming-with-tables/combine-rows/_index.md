---
title: Zeilen kombinieren
linktitle: Zeilen kombinieren
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Tabellenzeilen in einem Word-Dokument kombinieren.
type: docs
weight: 10
url: /de/net/programming-with-tables/combine-rows/
---

In diesem Tutorial lernen wir, wie man mit Aspose.Words für .NET Tabellenzeilen in einem Word-Dokument kombiniert. Wir folgen einer Schritt-für-Schritt-Anleitung, um den Code zu verstehen und diese Funktion zu implementieren. Am Ende dieses Tutorials können Sie Tabellenzeilen in Ihren Word-Dokumenten programmgesteuert bearbeiten und zusammenführen.

## Schritt 1: Projekt-Setup
1. Starten Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Fügen Sie einen Verweis auf die Aspose.Words-Bibliothek für .NET hinzu.

## Schritt 2: Laden des Dokuments und Zugriff auf die Tabellen
Um die Textverarbeitung mit Tabellen zu starten, müssen wir das Dokument, das sie enthält, laden und darauf zugreifen. Folgen Sie diesen Schritten:

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das Dokument
Document doc = new Document(dataDir + "Tables.docx");

// Zugriff auf Tabellen
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);
Table secondTable = (Table)doc.GetChild(NodeType.Table, 1, true);
```

Ersetzen Sie „IHR DOKUMENTVERZEICHNIS“ unbedingt durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 3: Tabellenzeilen kombinieren
Als nächstes werden wir die Zeilen der zweiten Tabelle mit dem Ende der ersten Tabelle kombinieren. Verwenden Sie den folgenden Code:

```csharp
// Kombination von Tabellenzeilen
while (secondTable.HasChildNodes)
     firstTable.Rows.Add(secondTable.FirstRow);
secondTable.Remove();
```

 Hier verwenden wir eine`while` Schleife, um über alle Zeilen des zweiten Arrays zu iterieren und sie am Ende des ersten Arrays hinzuzufügen, mit dem`Add` Methode. Als nächstes entfernen wir die zweite Tabelle aus dem Dokument mit der`Remove` Methode.

## Schritt 4: Speichern des geänderten Dokuments
Zum Schluss müssen wir das geänderte Dokument mit den kombinierten Tabellenzeilen speichern. Verwenden Sie dazu den folgenden Code:

```csharp
// Speichern des geänderten Dokuments
doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

Achten Sie darauf, den richtigen Pfad und Dateinamen für das Ausgabedokument anzugeben.

### Beispielquellcode für „Combine Rows“ mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// Die Zeilen der zweiten Tabelle werden an das Ende der ersten Tabelle angehängt.
	Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
	Table secondTable = (Table) doc.GetChild(NodeType.Table, 1, true);
	// Alle Zeilen der aktuellen Tabelle an die nächsten Tabellen anhängen
	// mit unterschiedlicher Zellenzahl und Breite können zu einer Tabelle zusammengeführt werden.
	while (secondTable.HasChildNodes)
		firstTable.Rows.Add(secondTable.FirstRow);
	secondTable.Remove();
	doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man Tabellenzeilen in einem Word-Dokument mit Aspose.Words für .NET kombiniert. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code implementieren, können Sie Tabellenzeilen in Ihren Word-Dokumenten programmgesteuert bearbeiten. Mit dieser Funktion können Sie Ihre Daten effizient in einer Tabelle zusammenführen und organisieren.