---
title: Aufzählungsliste
linktitle: Aufzählungsliste
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.Words für .NET eine Aufzählungsliste erstellen.
type: docs
weight: 10
url: /de/net/working-with-markdown/bulleted-list/
---

In diesem Tutorial erklären wir Ihnen, wie Sie mit Aspose.Words für .NET eine Liste mit Aufzählungszeichen erstellen. Eine Liste mit Aufzählungszeichen wird verwendet, um Elemente ohne Nummerierung aufzulisten.

## Schritt 1: Verwendung eines Dokumentengenerators

Zuerst verwenden wir einen Dokumentgenerator, um Inhalte zu unserem Dokument hinzuzufügen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Schritt 2: Anwenden einer Standardliste mit Aufzählungszeichen

 Mit dem Document Builder können wir eine standardmäßige Aufzählungsliste anwenden`ApplyBulletDefault` Methode.

```csharp
builder.ListFormat.ApplyBulletDefault();
```

## Schritt 3: Anpassen des Bullet-Formats

 Wir können das Aufzählungsformat anpassen, indem wir auf die Eigenschaften von zugreifen`ListFormat.List.ListLevels[0]`. In diesem Beispiel verwenden wir den Bindestrich „-“ als Aufzählungszeichen.

```csharp
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";
```

## Schritt 4: Elemente zur Liste hinzufügen

 Jetzt können wir mit dem Document Builder Elemente zur Aufzählungsliste hinzufügen`Writeln` Methode.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## Schritt 5: Einrückung aus der Liste entfernen

 Wenn wir eine Unterliste erstellen möchten, können wir die Einrückung mithilfe von vergrößern`ListFormat.ListIndent()` Methode. In diesem Beispiel fügen wir den Elementen 2a und 2b eine Unterliste hinzu.

```csharp
builder.ListFormat.ListIndent();
builder. Writeln("Element 2a");
builder.Writeln("Element 2b");
```
### Beispielquellcode für eine Aufzählungsliste mit Aspose.Words für .NET


```csharp
	// Verwenden Sie einen Dokumentersteller, um dem Dokument Inhalte hinzuzufügen.
	DocumentBuilder builder = new DocumentBuilder();

	builder.ListFormat.ApplyBulletDefault();
	builder.ListFormat.List.ListLevels[0].NumberFormat = "-";

	builder.Writeln("Item 1");
	builder.Writeln("Item 2");

	builder.ListFormat.ListIndent();

	builder.Writeln("Item 2a");
	builder.Writeln("Item 2b");
            
```

Herzlichen Glückwunsch! Sie haben nun gelernt, wie Sie mit Aspose.Words für .NET eine Aufzählungsliste erstellen.

