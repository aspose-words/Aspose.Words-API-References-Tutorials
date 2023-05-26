---
title: Bestellliste
linktitle: Bestellliste
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.Words für .NET eine geordnete Liste erstellen.
type: docs
weight: 10
url: /de/net/working-with-markdown/ordered-list/
---

In diesem Beispiel erklären wir, wie Sie die Funktionalität geordneter Listen mit Aspose.Words für .NET verwenden. Mit der geordneten Liste können Sie Elemente der Reihe nach mit Nummern organisieren.

## Schritt 1: Verwendung eines Dokumentengenerators

Zuerst verwenden wir einen Dokumentengenerator, um ein neues Dokument zu erstellen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Anwenden des geordneten Listenformats

Wir werden das geordnete Listenformat mit dem Document Builder anwenden`ApplyBulletDefault` Methode. Wir können das Nummerierungsformat auch anpassen, indem wir zu den Listenebenen gehen und das gewünschte Format festlegen.

```csharp
builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";
```

## Schritt 3: Elemente zur Liste hinzufügen

 Mithilfe des Dokumentengenerators können wir Elemente zur Liste hinzufügen`Writeln` Methode.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## Schritt 4: Liste einrücken

 Wir können die Liste mithilfe des Dokumentgenerators einrücken`ListIndent` Methode.

```csharp
builder.ListFormat.ListIndent();
builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

## Schritt 5: Speichern des Dokuments

Abschließend können wir das Dokument im gewünschten Format speichern.

### Beispielquellcode für eine geordnete Liste mit Aspose.Words für .NET

```csharp
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.ListFormat.ApplyBulletDefault();
	builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
	builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";

	builder.Writeln("Item 1");
	builder.Writeln("Item 2");

	builder.ListFormat.ListIndent();

	builder.Writeln("Item 2a");
	builder.Writeln("Item 2b");
            
```

Herzlichen Glückwunsch! Sie haben jetzt gelernt, wie Sie die Funktion für geordnete Listen mit Aspose.Words für .NET verwenden.

