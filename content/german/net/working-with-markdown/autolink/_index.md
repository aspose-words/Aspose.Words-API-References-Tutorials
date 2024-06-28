---
title: Autolink
linktitle: Autolink
second_title: Aspose.Words-Dokumentverarbeitungs-API
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

// Hyperlink einfügen.
builder.InsertHyperlink("https://www.aspose.com“, „https://www.aspose.com“, false);
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```


Herzlichen Glückwunsch! Sie haben nun gelernt, wie Sie die Funktion „Autolink“ mit Aspose.Words für .NET verwenden.


### FAQs

#### F: Wie kann ich in Aspose.Words einen automatischen Link zu einer URL-Adresse erstellen?

 A: Um einen automatischen Link zu einer URL-Adresse in Aspose.Words zu erstellen, können Sie die verwenden`<a>` Tag mit dem`href` Attribut, das die URL-Adresse enthält. Sie können zum Beispiel verwenden`<a href="https://www.aspose.com">https://www.aspose.com</a>` um automatisch auf „https://www.aspose.com“ zu verlinken.

#### F: Ist es möglich, den Anzeigetext eines automatischen Links in Aspose.Words anzupassen?

 A: Ja, Sie können den Anzeigetext eines automatischen Links in Aspose.Words anpassen. Anstatt die URL-Adresse als Anzeigetext zu verwenden, können Sie einen beliebigen anderen Text verwenden, indem Sie den Inhalt zwischen den ersetzen`<a>` Stichworte. Sie können zum Beispiel verwenden`<a href="https://www.aspose.com">Click here</a>` um den Text „Hier klicken“ als automatischen Link anzuzeigen.

#### F: Wie kann ich einem Autolink in Aspose.Words zusätzliche Attribute hinzufügen?

A: Um einem automatischen Link in Aspose.Words zusätzliche Attribute hinzuzufügen, können Sie zusätzliche HTML-Attribute innerhalb von verwenden`<a>` Etikett. Sie können zum Beispiel verwenden`<a href="https://www.aspose.com" target="_blank">Link</a>` um den Link in einem neuen Fenster oder Tab zu öffnen` attribute target="_blank"`.