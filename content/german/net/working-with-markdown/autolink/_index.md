---
title: Autolink
linktitle: Autolink
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie in der Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.Words für .NET einen Autolink einfügen.
type: docs
weight: 10
url: /de/net/working-with-markdown/autolink/
---

In diesem Beispiel erklären wir, wie Sie die Funktion „Autolink“ mit Aspose.Words für .NET verwenden. Mit dieser Funktion können Sie Hyperlinks automatisch in Ihr Dokument einfügen.

## Schritt 1: Einen Dokumentgenerator verwenden

Zuerst verwenden wir einen Dokumentgenerator, um unserem Dokument Inhalt hinzuzufügen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Schritt 2: Einfügen eines Hyperlinks

 Wir können einen Hyperlink einfügen mit dem`InsertHyperlink` Methode des Dokumentgenerators. Wir geben die URL und den anzuzeigenden Text für den Link an.

```csharp
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", false);
```

## Schritt 3: E-Mail-Adresse als Link einfügen

Wir können auch eine E-Mail-Adresse als Link mit dem Präfix „mailto:“ einfügen. So können Benutzer auf den Link klicken, um ihren Standard-E-Mail-Client zu öffnen.

```csharp
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```

## Schritt 4: Speichern des Dokuments

Abschließend können wir das Dokument im gewünschten Format speichern.

### Beispiel-Quellcode für Autolink mit Aspose.Words für .NET


```csharp
// Verwenden Sie einen Dokument-Generator, um dem Dokument Inhalt hinzuzufügen.
DocumentBuilder builder = new DocumentBuilder();

// Hyperlink einfügen.
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", false);
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```


Herzlichen Glückwunsch! Sie haben jetzt gelernt, wie Sie die Funktion "Autolink" mit Aspose.Words für .NET verwenden.


### Häufig gestellte Fragen

#### F: Wie kann ich in Aspose.Words einen automatischen Link zu einer URL-Adresse erstellen?

 A: Um einen automatischen Link zu einer URL-Adresse in Aspose.Words zu erstellen, können Sie den`<a>` Tag mit dem`href` Attribut, das die URL-Adresse enthält. Sie können beispielsweise`<a href="https://www.aspose.com">https://www.aspose.com</a>` um automatisch eine Verknüpfung zu "https://www.aspose.com" herzustellen.

#### F: Ist es möglich, den Anzeigetext eines automatischen Links in Aspose.Words anzupassen?

 A: Ja, Sie können den Anzeigetext eines automatischen Links in Aspose.Words anpassen. Anstatt die URL-Adresse als Anzeigetext zu verwenden, können Sie jeden anderen Text verwenden, indem Sie den Inhalt zwischen den`<a>` Tags. Sie können beispielsweise`<a href="https://www.aspose.com">Click here</a>` um den Text „Klicken Sie hier“ als automatischen Link anzuzeigen.

#### F: Wie kann ich einem Autolink in Aspose.Words zusätzliche Attribute hinzufügen?

A: Um zusätzliche Attribute zu einem automatischen Link in Aspose.Words hinzuzufügen, können Sie zusätzliche HTML-Attribute innerhalb des`<a>` Tag. Sie können beispielsweise`<a href="https://www.aspose.com" target="_blank">Link</a>` , um den Link in einem neuen Fenster oder Tab zu öffnen, indem Sie` attribute target="_blank"`.