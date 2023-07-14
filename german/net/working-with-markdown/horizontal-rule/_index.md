---
title: Horizontale Regel
linktitle: Horizontale Regel
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.Words für .NET eine horizontale Regel einfügen.
type: docs
weight: 10
url: /de/net/working-with-markdown/horizontal-rule/
---

In diesem Beispiel zeigen wir Ihnen, wie Sie die horizontale Regelfunktion mit Aspose.Words für .NET verwenden. Horizontale Lineale werden verwendet, um Abschnitte eines Dokuments visuell zu trennen.

## Schritt 1: Verwendung eines Dokumentengenerators

Zuerst verwenden wir einen Dokumentgenerator, um Inhalte zu unserem Dokument hinzuzufügen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Schritt 2: Einfügen eines horizontalen Lineals

 Mit dem können wir eine horizontale Regel einfügen`InsertHorizontalRule` Methode des Dokumentengenerators.

```csharp
builder. InsertHorizontalRule();
```

## Beispielquellcode für eine horizontale Regel mit Aspose.Words für .NET

```csharp
// Verwenden Sie einen Dokumentersteller, um dem Dokument Inhalte hinzuzufügen.
DocumentBuilder builder = new DocumentBuilder();

// Horizontales Lineal einfügen.
builder.InsertHorizontalRule();
```

Herzlichen Glückwunsch! Sie haben jetzt gelernt, wie Sie die horizontale Regelfunktion mit Aspose.Words für .NET verwenden.


### FAQs

#### F: Wie erstelle ich in Markdown ein horizontales Lineal?

A: Um in Markdown ein horizontales Lineal zu erstellen, können Sie eines der folgenden Symbole in einer leeren Zeile verwenden: drei Sternchen (\***), drei Bindestriche (\---) oder drei Unterstriche (\___).

#### F: Kann ich das Erscheinungsbild eines horizontalen Lineals in Markdown anpassen?

A: Im Standard-Markdown gibt es keine Möglichkeit, das Erscheinungsbild horizontaler Lineale anzupassen. Einige erweiterte Markdown-Editoren und -Erweiterungen bieten jedoch zusätzliche Anpassungsfunktionen.

#### F: Werden horizontale Lineale von allen Markdown-Editoren unterstützt?

A: Ja, die meisten gängigen Markdown-Editoren unterstützen horizontale Lineale. Es ist jedoch immer am besten, die Dokumentation Ihres jeweiligen Anbieters zu überprüfen, um sicherzustellen, dass dieser unterstützt wird.

#### F: Welche anderen Elemente kann ich in Markdown erstellen?

A: Zusätzlich zu horizontalen Linealen können Sie in Markdown Titel, Absätze, Listen, Links, Bilder, Tabellen und mehr erstellen.