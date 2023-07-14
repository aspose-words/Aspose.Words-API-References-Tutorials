---
title: Bestellliste
linktitle: Bestellliste
second_title: Aspose.Words-Dokumentverarbeitungs-API
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

 Wir werden das geordnete Listenformat mit dem Document Builder anwenden`ApplyBulletDefault`Methode. Wir können das Nummerierungsformat auch anpassen, indem wir zu den Listenebenen gehen und das gewünschte Format festlegen.

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


### FAQs

#### F: Wie erstelle ich eine geordnete Liste in Markdown?

A: Um eine geordnete Liste in Markdown zu erstellen, beginnen Sie jedes Listenelement mit einer Zahl gefolgt von einem Punkt (`1.`, `2.`, `3.`), gefolgt von einem Leerzeichen.

#### F: Können wir geordnete Listen in Markdown verschachteln?

A: Ja, es ist möglich, geordnete Listen in Markdown zu verschachteln, indem vor jedem verschachtelten Listenelement vier versetzte Leerzeichen hinzugefügt werden.

#### F: Wie kann ich die Nummerierung geordneter Listen anpassen?

A: Im Standard-Markdown wird die geordnete Listennummerierung automatisch generiert. Bei einigen Markdown-Editoren können Sie es jedoch mithilfe bestimmter Erweiterungen anpassen.

#### F: Unterstützen geordnete Listen in Markdown die Einrückung?

A: Ja, geordnete Listen in Markdown unterstützen die Einrückung. Sie können eine Linksverschiebung mithilfe von Leerzeichen oder Tabulatoren hinzufügen.

#### F: Können Links oder Inline-Text zu Listenelementen hinzugefügt werden?

A: Ja, Sie können mithilfe der entsprechenden Markdown-Syntax Links oder Inline-Text zu Listenelementen hinzufügen.