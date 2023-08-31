---
title: Verknüpfung
linktitle: Verknüpfung
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie Links mit Aspose.Words für .NET einfügen. Schritt für Schritt Anleitung.
type: docs
weight: 10
url: /de/net/working-with-markdown/link/
---

In diesem Beispiel zeigen wir Ihnen, wie Sie die Links-Funktion mit Aspose.Words für .NET verwenden. Mithilfe von Links werden anklickbare Verweise auf Websites oder andere Dokumente erstellt.

## Schritt 1: Verwendung eines Dokumentengenerators

Zuerst verwenden wir einen Dokumentgenerator, um Inhalte zu unserem Dokument hinzuzufügen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Schritt 2: Einen Link einfügen

 Wir können einen Link mit einfügen`Insertlink` Methode des Dokumentengenerators. Wir müssen den Linktext, hier „Aspose“, sowie die Ziel-URL angeben.

```csharp
builder.Insertlink("Aspose", "https://www.aspose.com", false);
```

### Beispielquellcode für Links mit Aspose.Words für .NET


```csharp
// Verwenden Sie einen Dokumentersteller, um dem Dokument Inhalte hinzuzufügen.
DocumentBuilder builder = new DocumentBuilder();

// Link einfügen.
builder.Insertlink("Aspose", "https://www.aspose.com", false);
```
Herzlichen Glückwunsch! Sie haben jetzt gelernt, wie Sie die Links-Funktion mit Aspose.Words für .NET verwenden.


### FAQs

#### F: Wie kann ich in Aspose.Words auf eine URL verlinken?

 A: Um eine Verknüpfung zu einer URL-Adresse in Aspose.Words herzustellen, können Sie die verwenden`<a>` Tag mit dem`href` Attribut, das die URL-Adresse enthält. Sie können zum Beispiel verwenden`<a href="https://www.aspose.com">Click Here</a>` um einen Hyperlink zur URL „https://www.example.com“ mit dem Anzeigetext „Hier klicken“ zu erstellen.

#### F: Ist es möglich, in Aspose.Words auf ein internes Lesezeichen zu verlinken?

 A: Ja, es ist möglich, in Aspose.Words auf ein internes Lesezeichen zu verlinken. Du kannst den ... benutzen`<a>` Tag mit dem`href` Attribut, das den Namen des Lesezeichens enthält, dem ein Hash (#) vorangestellt ist. Zum Beispiel,`<a href="#bookmark1">Go to bookmark 1</a>` wird auf das Lesezeichen mit dem Namen „bookmark1“ im Dokument verlinkt.

#### F: Wie kann ich den Anzeigetext eines Links in Aspose.Words anpassen?

A: Um den Anzeigetext eines Links in Aspose.Words anzupassen, können Sie den Inhalt zwischen den ändern`<a>` Stichworte. Zum Beispiel,`<a href="https://www.aspose.com">Click here</a>` zeigt den Text „Hier klicken“ als Hyperlink an.

#### F: Kann ich in Aspose.Words ein Ziel für einen Link angeben?

 A: Ja, Sie können in Aspose.Words mithilfe von ein Ziel für einen Link angeben`target` Attribut der`<a>` Etikett. Zum Beispiel,`<a href="https://www.aspose.com" target="_blank">Open in new window</a>` öffnet den Link in einem neuen Fenster oder Tab.