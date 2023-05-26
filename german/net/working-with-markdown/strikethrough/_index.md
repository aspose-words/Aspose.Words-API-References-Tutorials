---
title: Durchgestrichen
linktitle: Durchgestrichen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie Schritt-für-Schritt-Anleitung, wie Sie den durchgestrichenen Textstil mit Aspose.Words für .NET anwenden.
type: docs
weight: 10
url: /de/net/working-with-markdown/strikethrough/
---


In diesem Beispiel zeigen wir Ihnen, wie Sie den durchgestrichenen Textstil mit Aspose.Words für .NET anwenden. Durchgestrichener Text wird verwendet, um anzuzeigen, dass der Text gelöscht wurde oder nicht mehr gültig ist.

## Schritt 1: Verwendung eines Dokumentengenerators

Zuerst verwenden wir einen Dokumentgenerator, um Inhalte zu unserem Dokument hinzuzufügen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Schritt 2: Durchgestrichenen Textstil anwenden

 Wir aktivieren den durchgestrichenen Textstil, indem wir festlegen`StrikeThrough` Eigentum der`Font` widersprechen`true`.

```csharp
builder.Font.StrikeThrough = true;
```

## Schritt 3: Durchgestrichenen Text hinzufügen

 Wir können jetzt mit dem Dokumentgenerator durchgestrichenen Text hinzufügen`Writeln` Methode.

```csharp
builder.Writeln("This text will be StrikeThrough");
```


### Beispielquellcode für durchgestrichenen Text mit Aspose.Words für .NET

```csharp
	// Verwenden Sie einen Dokumentersteller, um dem Dokument Inhalte hinzuzufügen.
	DocumentBuilder builder = new DocumentBuilder();

	// Machen Sie den Text durchgestrichen.
	builder.Font.StrikeThrough = true;
	builder.Writeln("This text will be StrikeThrough");
            
```

Herzlichen Glückwunsch! Sie haben jetzt gelernt, wie Sie den durchgestrichenen Textstil mit Aspose.Words für .NET anwenden.
