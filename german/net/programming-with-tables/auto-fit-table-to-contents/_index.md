---
title: Tabelle automatisch an Inhalt anpassen
linktitle: Tabelle automatisch an Inhalt anpassen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine Tabelle automatisch an ihren Inhalt in einem Word-Dokument anpassen.
type: docs
weight: 10
url: /de/net/programming-with-tables/auto-fit-table-to-contents/
---

In diesem Tutorial erfahren Sie, wie Sie Aspose.Words für .NET verwenden, um mithilfe von C# automatisch eine Tabelle an ihren Inhalt in einem Word-Dokument anzupassen. Wir werden den Prozess des Codeschreibens Schritt für Schritt durchgehen, um diese Funktionalität zu erreichen. Am Ende dieses Tutorials werden Sie ein klares Verständnis dafür haben, wie Sie Tabellen in Word-Dokumenten programmgesteuert bearbeiten.

## Schritt 1: Richten Sie das Projekt ein
1. Starten Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Fügen Sie einen Verweis auf die Aspose.Words für .NET-Bibliothek hinzu.

## Schritt 2: Laden Sie das Word-Dokument
Um die Textverarbeitung mit der Tabelle zu starten, müssen wir das Word-Dokument laden, das die Tabelle enthält. Folge diesen Schritten:

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Laden Sie das Word-Dokument
Document doc = new Document(dataDir + "Tables.docx");
```

Stellen Sie sicher, dass Sie „IHR DOKUMENTVERZEICHNIS“ durch den tatsächlichen Pfad zu Ihrem Dokument ersetzen.

## Schritt 3: Greifen Sie auf die Tabelle zu und passen Sie sie automatisch an den Inhalt an
Als nächstes müssen wir auf die Tabelle im Dokument zugreifen und das automatische Anpassungsverhalten anwenden. Verwenden Sie den folgenden Code:

```csharp
// Greifen Sie auf die Tabelle zu
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

// Passen Sie die Tabelle automatisch an ihren Inhalt an
table. AutoFit(AutoFitBehavior.AutoFitToContents);
```

 Hier wandeln wir den ersten untergeordneten Knoten des Typs um`Table` aus dem Dokument und dann mit der`AutoFit` Methode mit der`AutoFitToContents` Verhalten, um die Tabellenbreite an den Inhalt anzupassen.

## Schritt 4: Speichern Sie das geänderte Dokument
Abschließend müssen wir das geänderte Dokument mit der automatisch angepassten Tabelle speichern. Verwenden Sie den folgenden Code:

```csharp
// Speichern Sie das geänderte Dokument
doc.Save(dataDir + "WorkingWithTables.AutoFitTableToContents.docx");
```

Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen für das Ausgabedokument angeben.

### Beispielquellcode für die automatische Anpassung von Tabellen an Inhalte mit Aspose.Words für .NET 

```csharp
	//Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	table.AutoFit(AutoFitBehavior.AutoFitToContents);
	doc.Save(dataDir + "WorkingWithTables.AutoFitTableToContents.docx");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET eine Tabelle automatisch an ihren Inhalt in einem Word-Dokument anpasst. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code implementieren, können Sie Tabellen in Ihren Word-Dokumenten programmgesteuert bearbeiten. Dadurch können Sie die Tabellenbreite basierend auf dem Inhalt dynamisch anpassen und so ein professionelleres und optisch ansprechenderes Dokument erstellen.