---
title: Verknüpfung
linktitle: Verknüpfung
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Links einfügen. Schritt-für-Schritt-Anleitung.
type: docs
weight: 10
url: /de/net/working-with-markdown/link/
---

In diesem Beispiel zeigen wir Ihnen, wie Sie die Linkfunktion mit Aspose.Words für .NET verwenden. Links werden verwendet, um anklickbare Verweise auf Websites oder andere Dokumente zu erstellen.

## Schritt 1: Einen Dokumentgenerator verwenden

Zuerst verwenden wir einen Dokumentgenerator, um unserem Dokument Inhalt hinzuzufügen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Schritt 2: Link einfügen

 Wir können einen Link einfügen mit dem`InsertHyperlink` Methode des Dokumentgenerators. Wir müssen den Linktext, hier „Aspose“, sowie die Ziel-URL angeben.

```csharp
builder.InsertHyperlink("Aspose", "https://www.aspose.com", false);
```

### Beispielquellcode für Links mit Aspose.Words für .NET


```csharp
// Verwenden Sie einen Dokument-Generator, um dem Dokument Inhalt hinzuzufügen.
DocumentBuilder builder = new DocumentBuilder();

// Link einfügen.
builder.InsertHyperlink("Aspose", "https://www.aspose.com", false);
```
Herzlichen Glückwunsch! Sie haben jetzt gelernt, wie Sie die Linkfunktion mit Aspose.Words für .NET verwenden.


### Häufig gestellte Fragen

#### F: Wie kann ich in Aspose.Words auf eine URL verlinken?

 A: Um auf eine URL-Adresse in Aspose.Words zu verlinken, können Sie den`<a>` Tag mit dem`href` Attribut, das die URL-Adresse enthält. Sie können beispielsweise`<a href="https://www.aspose.com">Click Here</a>` um einen Hyperlink zur URL „https://www.example.com“ mit dem Anzeigetext „Klicken Sie hier“ zu erstellen.

#### F: Ist es möglich, in Aspose.Words auf ein internes Lesezeichen zu verlinken?

 A: Ja, es ist möglich, auf ein internes Lesezeichen in Aspose.Words zu verlinken. Sie können das`<a>` Tag mit dem`href` Attribut, das den Namen des Lesezeichens enthält, dem ein Hash (#) vorangestellt ist. Beispiel:`<a href="#bookmark1">Go to bookmark 1</a>` wird auf das Lesezeichen mit dem Namen „bookmark1“ im Dokument verwiesen.

#### F: Wie kann ich den Anzeigetext eines Links in Aspose.Words anpassen?

A: Um den Anzeigetext eines Links in Aspose.Words anzupassen, können Sie den Inhalt zwischen den`<a>` Tags. Zum Beispiel`<a href="https://www.aspose.com">Click here</a>` wird der Text „Klicken Sie hier“ als Hyperlink angezeigt.

#### F: Kann ich in Aspose.Words ein Ziel für einen Link angeben?

 A: Ja, Sie können ein Ziel für einen Link in Aspose.Words angeben, indem Sie`target` Attribut des`<a>` Tag. Beispiel:`<a href="https://www.aspose.com" target="_blank">Open in new window</a>` öffnet den Link in einem neuen Fenster oder Tab.