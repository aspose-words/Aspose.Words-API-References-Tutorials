---
title: Fetter Text
linktitle: Fetter Text
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie Schritt-für-Schritt-Anleitung, wie Sie Text mit Aspose.Words für .NET fett formatieren.
type: docs
weight: 10
url: /de/net/working-with-markdown/bold-text/
---

In diesem Beispiel erklären wir Ihnen, wie Sie Text mit Aspose.Words für .NET fett formatieren. Durch die Fettschrift wird der Text besser sichtbar und hervorgehoben.

## Schritt 1: Verwendung eines Dokumentengenerators

Zuerst verwenden wir einen Dokumentgenerator, um Inhalte zu unserem Dokument hinzuzufügen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Schritt 2: Fetter Text

 Wir können den Text fett formatieren, indem wir ihn im Document Builder festlegen`Font.Bold` Eigentum zu`true`.

```csharp
builder.Font.Bold = true;
```

## Schritt 3: Fügen Sie dem Dokument Inhalte hinzu

 Jetzt können wir mithilfe der Document Builder-Methoden Inhalte zum Dokument hinzufügen, z`Writeln`, wodurch eine Textzeile hinzugefügt wird.

```csharp
builder.Writeln("This text will be bold");
```

## Beispielquellcode für fetten Text mit Aspose.Words für .NET


```csharp
	// Verwenden Sie einen Dokumentersteller, um dem Dokument Inhalte hinzuzufügen.
	DocumentBuilder builder = new DocumentBuilder();

	// Machen Sie den Text fett.
	builder.Font.Bold = true;
	builder.Writeln("This text will be Bold");  
```

Herzlichen Glückwunsch! Sie haben jetzt gelernt, wie Sie mit Aspose.Words für .NET Text fett formatieren.


