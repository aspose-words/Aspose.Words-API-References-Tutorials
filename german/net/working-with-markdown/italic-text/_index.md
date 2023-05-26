---
title: Kursiver Text
linktitle: Kursiver Text
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie Schritt-für-Schritt-Anleitung, wie Sie Text mit Aspose.Words für .NET kursiv formatieren.
type: docs
weight: 10
url: /de/net/working-with-markdown/italic-text/
---

In diesem Beispiel zeigen wir Ihnen, wie Sie die Funktion für kursiven Text mit Aspose.Words für .NET verwenden. Kursiver Text wird verwendet, um bestimmte Teile eines Dokuments hervorzuheben.

## Schritt 1: Verwendung eines Dokumentengenerators

Zuerst verwenden wir einen Dokumentgenerator, um Inhalte zu unserem Dokument hinzuzufügen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Schritt 2: Text kursiv schreiben

 Wir können Text kursiv formatieren, indem wir die Schriftart festlegen`Italic` Eigentum zu`true`.

```csharp
builder.Font.Italic = true;
builder.Writeln("This text will be in italics");
```

### Beispielquellcode für kursiven Text mit Aspose.Words für .NET


```csharp
	// Verwenden Sie einen Dokumentersteller, um dem Dokument Inhalte hinzuzufügen.
	DocumentBuilder builder = new DocumentBuilder();

	// Machen Sie den Text kursiv.
	builder.Font.Italic = true;
	builder.Writeln("This text will be Italic");
            
```

Herzlichen Glückwunsch! Sie haben jetzt gelernt, wie Sie die Funktion für kursiven Text mit Aspose.Words für .NET verwenden.

