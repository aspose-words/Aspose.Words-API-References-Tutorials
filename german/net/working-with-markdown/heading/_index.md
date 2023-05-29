---
title: Überschrift
linktitle: Überschrift
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie Schritt-für-Schritt-Anleitung, wie Sie Überschriften mit Aspose.Words für .NET verwenden.
type: docs
weight: 10
url: /de/net/working-with-markdown/heading/
---

In diesem Beispiel zeigen wir Ihnen, wie Sie die Überschriftenfunktion mit Aspose.Words für .NET verwenden. Überschriften dienen der Strukturierung und Priorisierung des Inhalts eines Dokuments.

## Schritt 1: Verwendung eines Dokumentengenerators

Zuerst verwenden wir einen Dokumentgenerator, um Inhalte zu unserem Dokument hinzuzufügen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Schritt 2: Überschriftenstile anpassen

Überschriftenformate in Word können standardmäßig fett und kursiv formatiert sein. Wenn wir nicht möchten, dass diese Eigenschaften erzwungen werden, müssen wir sie explizit auf „false“ setzen.

```csharp
builder.Font.Bold = false;
builder.Font.Italic = false;
```

## Schritt 3: Hinzufügen eines Level-1-Titels

 Wir können einen Titel der Ebene 1 hinzufügen, indem wir den entsprechenden Absatzstilnamen angeben und verwenden`Writeln` Methode zum Schreiben des Inhalts des Titels.

```csharp
builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

### Beispielquellcode für Überschrift mit Aspose.Words für .NET


```csharp
// Verwenden Sie einen Dokumentersteller, um dem Dokument Inhalte hinzuzufügen.
DocumentBuilder builder = new DocumentBuilder();

// Standardmäßig können Überschriftenstile in Word die Formatierung Fett und Kursiv haben.
//Wenn wir nicht hervorgehoben werden möchten, setzen Sie diese Eigenschaften explizit auf „false“.
builder.Font.Bold = false;
builder.Font.Italic = false;

builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

Herzlichen Glückwunsch! Sie haben jetzt gelernt, wie Sie die Überschriftenfunktion mit Aspose.Words für .NET verwenden.


