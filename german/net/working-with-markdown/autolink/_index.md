---
title: Autolink
linktitle: Autolink
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie Schritt-für-Schritt-Anleitung, wie Sie einen Autolink mit Aspose.Words für .NET einfügen.
type: docs
weight: 10
url: /de/net/working-with-markdown/autolink/
---

In diesem Beispiel erklären wir, wie Sie die Funktion „Autolink“ mit Aspose.Words für .NET verwenden. Mit dieser Funktion können Sie Hyperlinks automatisch in Ihr Dokument einfügen.

## Schritt 1: Verwendung eines Dokumentengenerators

Zuerst verwenden wir einen Dokumentgenerator, um Inhalte zu unserem Dokument hinzuzufügen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Schritt 2: Einfügen eines Hyperlinks

 Mit dem können wir einen Hyperlink einfügen`InsertHyperlink` Methode des Dokumentengenerators. Wir geben die URL und den anzuzeigenden Text für den Link an.

```csharp
builder.InsertHyperlink("https://www.aspose.com“, „https://www.aspose.com“, false);
```

## Schritt 3: E-Mail-Adresse als Link einfügen

Wir können auch eine E-Mail-Adresse als Link einfügen, indem wir das Präfix „mailto:“ verwenden. Dadurch können Benutzer auf den Link klicken, um ihren Standard-E-Mail-Client zu öffnen.

```csharp
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```

## Schritt 4: Speichern des Dokuments

Abschließend können wir das Dokument im gewünschten Format speichern.

### Beispielquellcode für Autolink mit Aspose.Words für .NET


```csharp
	// Verwenden Sie einen Dokumentersteller, um dem Dokument Inhalte hinzuzufügen.
	DocumentBuilder builder = new DocumentBuilder();

	//Hyperlink einfügen.
	builder.InsertHyperlink("https://www.aspose.com“, „https://www.aspose.com“, false);
	builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
            
```


Herzlichen Glückwunsch! Sie haben nun gelernt, wie Sie die Funktion „Autolink“ mit Aspose.Words für .NET verwenden.

