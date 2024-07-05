---
title: Horizontale Regel
linktitle: Horizontale Regel
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie in der Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.Words für .NET eine horizontale Linie einfügen.
type: docs
weight: 10
url: /de/net/working-with-markdown/horizontal-rule/
---

In diesem Beispiel zeigen wir Ihnen, wie Sie die horizontale Linienfunktion mit Aspose.Words für .NET verwenden. Horizontale Linien werden verwendet, um Abschnitte eines Dokuments optisch zu trennen.

## Schritt 1: Einen Dokumentgenerator verwenden

Zuerst verwenden wir einen Dokumentgenerator, um unserem Dokument Inhalt hinzuzufügen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Schritt 2: Einfügen einer horizontalen Linie

 Wir können eine horizontale Linie einfügen mit dem`InsertHorizontalRule` Methode des Dokumentgenerators.

```csharp
builder. InsertHorizontalRule();
```

## Beispielquellcode für horizontale Linie mit Aspose.Words für .NET

```csharp
// Verwenden Sie einen Dokument-Generator, um dem Dokument Inhalt hinzuzufügen.
DocumentBuilder builder = new DocumentBuilder();

// Horizontale Linie einfügen.
builder.InsertHorizontalRule();
```

Herzlichen Glückwunsch! Sie haben jetzt gelernt, wie Sie die horizontale Regelfunktion mit Aspose.Words für .NET verwenden.


### Häufig gestellte Fragen

#### F: Wie erstelle ich in Markdown ein horizontales Lineal?

A: Um ein horizontales Lineal in Markdown zu erstellen, können Sie eines der folgenden Symbole in einer leeren Zeile verwenden: drei Sternchen (\***), drei Bindestriche (\---) oder drei Unterstriche (\___).

#### F: Kann ich das Erscheinungsbild eines horizontalen Lineals in Markdown anpassen?

A: In Standard-Markdown gibt es keine Möglichkeit, das Erscheinungsbild horizontaler Lineale anzupassen. Einige erweiterte Markdown-Editoren und -Erweiterungen bieten jedoch zusätzliche Anpassungsfunktionen.

#### F: Werden horizontale Lineale von allen Markdown-Editoren unterstützt?

A: Ja, die meisten gängigen Markdown-Editoren unterstützen horizontale Lineale. Es ist jedoch immer am besten, die Dokumentation Ihres jeweiligen Anbieters zu prüfen, um sicherzustellen, dass es unterstützt wird.

#### F: Welche anderen Elemente kann ich in Markdown erstellen?

A: Zusätzlich zu horizontalen Linealen können Sie in Markdown Titel, Absätze, Listen, Links, Bilder, Tabellen und mehr erstellen.