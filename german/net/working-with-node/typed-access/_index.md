---
title: Typisierter Zugriff
linktitle: Typisierter Zugriff
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie typisierten Zugriff zum Bearbeiten von Tabellen in Aspose.Words für .NET verwenden.
type: docs
weight: 10
url: /de/net/working-with-node/typed-access/
---

Hier finden Sie eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, der die Verwendung der Typed Access-Funktion mit Aspose.Words für .NET veranschaulicht.

## Schritt 1: Importieren Sie die erforderlichen Referenzen
Bevor Sie beginnen, stellen Sie sicher, dass Sie die erforderlichen Referenzen zur Verwendung von Aspose.Words für .NET in Ihr Projekt importiert haben. Dazu gehört das Importieren der Aspose.Words-Bibliothek und das Hinzufügen der erforderlichen Namespaces zu Ihrer Quelldatei.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

## Schritt 2: Erstellen Sie ein neues Dokument
 In diesem Schritt erstellen wir ein neues Dokument mit`Document` Klasse.

```csharp
Document doc = new Document();
```

## Schritt 3: Greifen Sie auf den Abschnitt und den Körper zu
Um auf die im Dokument enthaltenen Tabellen zuzugreifen, müssen wir zunächst auf den Abschnitt und den Hauptteil des Dokuments zugreifen.

```csharp
Section section = doc.FirstSection;
Body body = section.Body;
```

## Schritt 4: Schneller und getippter Zugriff auf Tabellen
Da wir nun den Hauptteil des Dokuments haben, können wir über den Schnell- und Eingabezugriff auf alle im Hauptteil enthaltenen Tabellen zugreifen.

```csharp
TableCollection tables = body.Tables;
```

## Schritt 5: Tabellen durchsuchen
 Durch die Verwendung von a`foreach` Mit einer Schleife können wir alle Tabellen durchlaufen und für jede Tabelle bestimmte Operationen ausführen.

```csharp
foreach(Table table in tables)
{
     // Schneller und getippter Zugriff auf die erste Zeile der Tabelle.
     table.FirstRow?.Remove();

     // Schneller und getippter Zugriff auf die letzte Zeile der Tabelle.
     table.LastRow?.Remove();
}
```

In diesem Beispiel löschen wir die erste und letzte Zeile jeder Tabelle mithilfe des von Aspose.Words bereitgestellten Schnell- und Eingabezugriffs.

### Beispielquellcode für typisierten Zugriff mit Aspose.Words für .NET

```csharp
	Document doc = new Document();

	Section section = doc.FirstSection;
	Body body = section.Body;
	
	// Schneller typisierter Zugriff auf alle im Hauptteil enthaltenen untergeordneten Tabellenknoten.
	TableCollection tables = body.Tables;

	foreach (Table table in tables)
	{
		// Schneller getippter Zugriff auf die erste Zeile der Tabelle.
		table.FirstRow?.Remove();

		// Schneller getippter Zugriff auf die letzte Zeile der Tabelle.
		table.LastRow?.Remove();
	}
            
```

Dies ist ein vollständiger Beispielcode für den typisierten Zugriff auf Tabellen mit Aspose.Words für .NET. Stellen Sie sicher, dass Sie die erforderlichen Referenzen importieren und die zuvor beschriebenen Schritte befolgen, um diesen Code in Ihr Projekt zu integrieren.

---
