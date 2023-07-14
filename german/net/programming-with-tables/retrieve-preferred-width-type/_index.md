---
title: Rufen Sie den bevorzugten Breitentyp ab
linktitle: Rufen Sie den bevorzugten Breitentyp ab
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET den Typ und den bevorzugten Breitenwert einer Zelle in einer Word-Tabelle abrufen.
type: docs
weight: 10
url: /de/net/programming-with-tables/retrieve-preferred-width-type/
---

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET den bevorzugten Breitentyp und seinen Wert aus einer Tabellenzelle in einem Word-Dokument abrufen. Wir folgen einer Schritt-für-Schritt-Anleitung, um den Code zu verstehen und diese Funktion zu implementieren. Am Ende dieses Tutorials können Sie den bevorzugten Breitentyp (absolut, relativ oder automatisch) und seinen Wert für eine bestimmte Zelle in Ihren Word-Dokumenttabellen abrufen.

## Schritt 1: Projekteinrichtung
1. Starten Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Fügen Sie einen Verweis auf die Aspose.Words für .NET-Bibliothek hinzu.

## Schritt 2: Laden des Dokuments
Gehen Sie folgendermaßen vor, um die Textverarbeitung mit dem Dokument zu starten:

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das Dokument
Document doc = new Document(dataDir + "Tables.docx");
```

Stellen Sie sicher, dass Sie „IHR DOKUMENTENVERZEICHNIS“ durch den tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis ersetzen und den korrekten Dateinamen angeben.

## Schritt 3: Abrufen des bevorzugten Breitentyps und -werts
Als Nächstes rufen wir den bevorzugten Breitentyp und seinen Wert für eine bestimmte Tabellenzelle ab. Verwenden Sie den folgenden Code:

```csharp
// Rufen Sie die Tabelle ab
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// Automatische Tischanpassung aktivieren
table. AllowAutoFit = true;

// Rufen Sie die erste Zelle der ersten Zeile ab
Cell firstCell = table.FirstRow.FirstCell;

// Rufen Sie den bevorzugten Breitentyp und seinen Wert ab
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

Hier verwenden wir das Dokument, um die erste Tabelle abzurufen, und aktivieren dann die automatische Tabellenanpassung mit`AllowAutoFit` Eigentum. Dann rufen wir die erste Zelle der ersten Zeile der Tabelle ab. Aus dieser Zelle können wir den bevorzugten Breitentyp mit abrufen`PreferredWidth.Type` Eigentum und sein Wert mit dem`PreferredWidth.Value` Eigentum.

### Beispielquellcode für „Bevorzugten Breitentyp abrufen“ mit Aspose.Words für .NET 

```csharp
//Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
table.AllowAutoFit = true;
Cell firstCell = table.FirstRow.FirstCell;
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET den bevorzugten Breitentyp und seinen Wert aus einer Tabellenzelle in einem Word-Dokument abruft. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code implementieren, können Sie diese Informationen für bestimmte Zellen in Ihren Word-Dokumenttabellen abrufen.