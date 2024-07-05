---
title: Aufzählungsliste
linktitle: Aufzählungsliste
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie in der Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.Words für .NET eine Aufzählungsliste erstellen.
type: docs
weight: 10
url: /de/net/working-with-markdown/bulleted-list/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET eine Aufzählungsliste erstellen. Eine Aufzählungsliste wird verwendet, um Elemente ohne Nummerierung aufzulisten.

## Schritt 1: Einen Dokumentgenerator verwenden

Zuerst verwenden wir einen Dokumentgenerator, um unserem Dokument Inhalt hinzuzufügen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Schritt 2: Anwenden einer Standardaufzählungsliste

 Wir können eine Standard-Aufzählungsliste mit dem Dokument-Generator anwenden.`ApplyBulletDefault` Methode.

```csharp
builder.ListFormat.ApplyBulletDefault();
```

## Schritt 3: Anpassen des Aufzählungszeichenformats

 Wir können das Aufzählungsformat anpassen, indem wir auf die Eigenschaften von zugreifen`ListFormat.List.ListLevels[0]`. In diesem Beispiel verwenden wir den Bindestrich „-“ als Aufzählungszeichen.

```csharp
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";
```

## Schritt 4: Elemente zur Liste hinzufügen

 Nun können wir Elemente zur Aufzählungsliste hinzufügen, indem wir den Dokumentgenerator verwenden.`Writeln` Methode.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## Schritt 5: Einrückung aus der Liste entfernen

 Wenn wir eine Unterliste erstellen möchten, können wir die Einrückung vergrößern mit dem`ListFormat.ListIndent()` Methode. In diesem Beispiel fügen wir den Elementen 2a und 2b eine Unterliste hinzu.

```csharp
builder.ListFormat.ListIndent();
builder. Writeln("Element 2a");
builder.Writeln("Element 2b");
```
### Beispielquellcode für Aufzählungsliste mit Aspose.Words für .NET


```csharp
// Verwenden Sie einen Dokument-Generator, um dem Dokument Inhalt hinzuzufügen.
DocumentBuilder builder = new DocumentBuilder();

builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";

builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

Herzlichen Glückwunsch! Sie haben jetzt gelernt, wie Sie mit Aspose.Words für .NET eine Aufzählungsliste erstellen.

### Häufig gestellte Fragen

#### F: Wie erstelle ich eine Aufzählungsliste in Markdown?

A: Um eine Aufzählungsliste in Markdown zu erstellen, beginnen Sie jedes Listenelement mit einem Aufzählungssymbol (`-`, `*` , oder`+`), gefolgt von einem Leerzeichen.

#### F: Können Sie Aufzählungslisten in Markdown verschachteln?

A: Ja, es ist möglich, Aufzählungslisten in Markdown zu verschachteln, indem Sie vor jedem verschachtelten Listenelement vier versetzte Leerzeichen hinzufügen.

#### F: Wie kann ich Aufzählungszeichen anpassen?

A: In Standard-Markdown sind Aufzählungszeichen vordefiniert. Einige Markdown-Editoren ermöglichen es Ihnen jedoch, sie mithilfe bestimmter Erweiterungen anzupassen.

#### F: Unterstützen Aufzählungslisten in Markdown Einrückungen?

A: Ja, Aufzählungslisten in Markdown unterstützen Einrückungen. Sie können mit Leerzeichen oder Tabulatoren eine Linksverschiebung hinzufügen.

#### F: Können zu Listenelementen Links oder Inline-Text hinzugefügt werden?

A: Ja, Sie können mit der entsprechenden Markdown-Syntax Links oder Inline-Text zu Listenelementen hinzufügen.
