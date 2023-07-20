---
title: Vergleichsgranularität im Word-Dokument
linktitle: Vergleichsgranularität im Word-Dokument
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Lernen Sie die Funktion „Granularität vergleichen“ in der Word-Dokumentfunktion von Aspose.Words für .NET kennen, mit der Dokumente Zeichen für Zeichen verglichen und vorgenommene Änderungen gemeldet werden können.
type: docs
weight: 10
url: /de/net/compare-documents/comparison-granularity/
---
Hier finden Sie eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, der die Funktion „Granularität im Word-Dokument vergleichen“ von Aspose.Words für .NET verwendet.

## Schritt 1: Einführung

Mit der Funktion „Granularität vergleichen“ von Aspose.Words für .NET können Sie Dokumente auf Zeichenebene vergleichen. Das bedeutet, dass jedes Zeichen verglichen wird und Änderungen entsprechend gemeldet werden.

## Schritt 2: Einrichten der Umgebung

Bevor Sie beginnen, müssen Sie Ihre Entwicklungsumgebung für die Arbeit mit Aspose.Words für .NET einrichten. Stellen Sie sicher, dass Sie die Aspose.Words-Bibliothek installiert haben und über ein geeignetes C#-Projekt zum Einbetten des Codes verfügen.

## Schritt 3: Erforderliche Baugruppen hinzufügen

Um die Funktion „Granularität vergleichen“ von Aspose.Words für .NET verwenden zu können, müssen Sie Ihrem Projekt die erforderlichen Assemblys hinzufügen. Stellen Sie sicher, dass Ihr Projekt über die richtigen Verweise auf Aspose.Words verfügt.

```csharp
using Aspose.Words;
using Aspose.Words.DocumentBuilder;
```

## Schritt 4: Dokumente erstellen

In diesem Schritt erstellen wir zwei Dokumente mit der DocumentBuilder-Klasse. Diese Dokumente werden für den Vergleich herangezogen.

```csharp
// Erstellen Sie Dokument A.
DocumentBuilder builderA = new DocumentBuilder(new Document());
builderA.Writeln("This is a simple A word.");

// Erstellen Sie Dokument B.
DocumentBuilder builderB = new DocumentBuilder(new Document());
builderB.Writeln("This is simple B words.");
```

## Schritt 5: Vergleichsoptionen konfigurieren

In diesem Schritt konfigurieren wir die Vergleichsoptionen, um die Vergleichsgranularität festzulegen. Hier verwenden wir die Granularität auf Zeichenebene.

```csharp
CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };
```

## Schritt 6: Dokumentenvergleich

Vergleichen wir nun die Dokumente mit der Compare-Methode der Document-Klasse. Änderungen werden in Dokument A gespeichert.

```csharp
builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);
```

 Der`Compare` Die Methode vergleicht Dokument A mit Dokument B und speichert die Änderungen an Dokument A. Sie können den Namen des Autors und das Datum des Vergleichs als Referenz angeben.

## Abschluss

In diesem Artikel haben wir die Funktion „Granularität vergleichen“ von Aspose.Words für .NET untersucht. Mit dieser Funktion können Sie Dokumente auf Zeichenebene vergleichen und Änderungen melden. Mit diesem Wissen können Sie detaillierte Dokumentenvergleiche in Ihren Projekten durchführen.

### Beispielquellcode für Vergleichsgranularität mit Aspose.Words für .NET

```csharp
            
DocumentBuilder builderA = new DocumentBuilder(new Document());
DocumentBuilder builderB = new DocumentBuilder(new Document());

builderA.Writeln("This is A simple word");
builderB.Writeln("This is B simple words");

CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };

builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);            
        
```

## Abschluss

In diesem Tutorial haben wir die Vergleichsgranularitätsfunktion von Aspose.Words für .NET untersucht. Mit dieser Funktion können Sie den Detaillierungsgrad beim Vergleich von Dokumenten festlegen. Durch die Auswahl verschiedener Granularitätsstufen können Sie je nach Ihren spezifischen Anforderungen detaillierte Vergleiche auf Zeichen-, Wort- oder Blockebene durchführen. Aspose.Words für .NET bietet eine flexible und leistungsstarke Dokumentvergleichsfunktion, die es einfach macht, Unterschiede in Dokumenten mit unterschiedlichem Granularitätsgrad zu identifizieren.

### FAQs

#### F: Was ist der Zweck der Verwendung der Vergleichsgranularität in Aspose.Words für .NET?

A: Mit der Vergleichsgranularität in Aspose.Words für .NET können Sie den Detaillierungsgrad beim Vergleichen von Dokumenten angeben. Mit dieser Funktion können Sie Dokumente auf verschiedenen Ebenen vergleichen, beispielsweise auf Zeichenebene, Wortebene oder sogar Blockebene. Jede Granularitätsebene bietet einen anderen Detaillierungsgrad der Vergleichsergebnisse.

#### F: Wie verwende ich die Vergleichsgranularität in Aspose.Words für .NET?

A: Um die Vergleichsgranularität in Aspose.Words für .NET zu verwenden, führen Sie die folgenden Schritte aus:
1. Richten Sie Ihre Entwicklungsumgebung mit der Aspose.Words-Bibliothek ein.
2. Fügen Sie Ihrem Projekt die erforderlichen Assemblys hinzu, indem Sie auf Aspose.Words verweisen.
3.  Erstellen Sie die Dokumente, die Sie vergleichen möchten`DocumentBuilder` Klasse.
4.  Konfigurieren Sie die Vergleichsoptionen, indem Sie eine erstellen`CompareOptions` Objekt und Einstellung der`Granularity` Eigentum auf das gewünschte Niveau (z. B.`Granularity.CharLevel` zum Vergleich auf Zeichenebene).
5.  Benutzen Sie die`Compare` Methode für ein Dokument, Übergabe des anderen Dokuments und der`CompareOptions` Objekt als Parameter. Diese Methode vergleicht die Dokumente anhand der angegebenen Granularität und speichert die Änderungen im ersten Dokument.

#### F: Welche Ebenen der Vergleichsgranularität sind in Aspose.Words für .NET verfügbar?

A: Aspose.Words für .NET bietet drei Ebenen der Vergleichsgranularität:
- `Granularity.CharLevel`: Vergleicht Dokumente auf Zeichenebene.
- `Granularity.WordLevel`: Vergleicht Dokumente auf Wortebene.
- `Granularity.BlockLevel`: Vergleicht Dokumente auf Blockebene.

#### F: Wie kann ich die Vergleichsergebnisse mit Granularität auf Zeichenebene interpretieren?

A: Bei der Granularität auf Zeichenebene wird jedes Zeichen in den verglichenen Dokumenten auf Unterschiede analysiert. Die Vergleichsergebnisse zeigen Änderungen auf der Ebene einzelner Charaktere, einschließlich Hinzufügungen, Löschungen und Änderungen.