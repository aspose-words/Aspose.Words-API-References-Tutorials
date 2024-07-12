---
title: Bevorzugten Breitentyp abrufen
linktitle: Bevorzugten Breitentyp abrufen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET den Typ und den bevorzugten Breitenwert einer Zelle in einer Word-Tabelle abrufen.
type: docs
weight: 10
url: /de/net/programming-with-tables/retrieve-preferred-width-type/
---

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET den bevorzugten Breitentyp und seinen Wert aus einer Tabellenzelle in einem Word-Dokument abrufen. Wir folgen einer Schritt-für-Schritt-Anleitung, um den Code zu verstehen und diese Funktion zu implementieren. Am Ende dieses Tutorials können Sie den bevorzugten Breitentyp (absolut, relativ oder automatisch) und seinen Wert für eine bestimmte Zelle in Ihren Word-Dokumenttabellen abrufen.

## Schritt 1: Projekt-Setup
1. Starten Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Fügen Sie einen Verweis auf die Aspose.Words-Bibliothek für .NET hinzu.

## Schritt 2: Dokument einlegen
Um die Textverarbeitung mit dem Dokument zu starten, führen Sie diese Schritte aus:

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das Dokument
Document doc = new Document(dataDir + "Tables.docx");
```

Ersetzen Sie „IHR DOKUMENTVERZEICHNIS“ durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis und geben Sie den richtigen Dateinamen an.

## Schritt 3: Abrufen des bevorzugten Breitentyps und -werts
Als Nächstes ermitteln wir den bevorzugten Breitentyp und dessen Wert für eine bestimmte Tabellenzelle. Verwenden Sie den folgenden Code:

```csharp
// Abrufen der Tabelle
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// Automatische Tischanpassung aktivieren
table. AllowAutoFit = true;

//Abrufen der ersten Zelle der ersten Zeile
Cell firstCell = table.FirstRow.FirstCell;

// Abrufen des bevorzugten Breitentyps und seines Wertes
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

 Hier verwenden wir das Dokument, um die erste Tabelle abzurufen. Anschließend aktivieren wir die automatische Tabellenanpassung mit dem`AllowAutoFit` Eigenschaft. Dann holen wir uns die erste Zelle der ersten Zeile der Tabelle. Aus dieser Zelle können wir den bevorzugten Breitentyp mit dem`PreferredWidth.Type` Eigentum und dessen Wert mit der`PreferredWidth.Value` Eigentum.

### Beispielquellcode zum Abrufen des bevorzugten Breitentyps mit Aspose.Words für .NET 

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
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