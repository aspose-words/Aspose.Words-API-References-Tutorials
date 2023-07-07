---
title: Bereiche erhalten Text
linktitle: Bereiche erhalten Text
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ganz einfach Text aus einem Word-Dokument extrahieren.
type: docs
weight: 10
url: /de/net/programming-with-ranges/ranges-get-text/
---

Aspose.Words für .NET ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten und Bearbeiten von Word-Dokumenten in einer C#-Anwendung. Zu den von Aspose.Words angebotenen Funktionen gehört die Möglichkeit, den in bestimmten Bereichen eines Dokuments enthaltenen Text abzurufen. In dieser Anleitung zeigen wir Ihnen, wie Sie den C#-Quellcode von Aspose.Words für .NET verwenden, um Text aus einem Word-Dokument zu extrahieren.

## Grundlegendes zur Aspose.Words-Bibliothek

Bevor Sie in den Code eintauchen, ist es wichtig, die Aspose.Words-Bibliothek für .NET zu verstehen. Aspose.Words ist eine beliebte Bibliothek, die die Arbeit mit Word-Dokumenten einfach und effizient macht. Es bietet zahlreiche Funktionen zum Erstellen, Bearbeiten und Bearbeiten von Word-Dokumenten, einschließlich der Extraktion von Text aus bestimmten Bereichen.

## Laden des Word-Dokuments

Der erste Schritt besteht darin, das Word-Dokument zu laden, aus dem Sie den Text extrahieren möchten. Verwenden Sie die Document-Klasse, um das Dokument aus der Quelldatei zu laden. Hier ist ein Beispiel :

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

In diesem Beispiel laden wir das Dokument „Document.docx“, das sich im Dokumentenverzeichnis befindet.

## Extrahieren von Text aus einem bestimmten Bereich

Sobald das Dokument geladen ist, können Sie auf die verschiedenen Bereiche des Dokuments zugreifen und den gewünschten Text extrahieren. In diesem Beispiel extrahieren wir den gesamten Text aus dem Dokument. Hier ist wie:

```csharp
string text = doc.Range.Text;
```

In diesem Beispiel verwenden wir die Range-Eigenschaft der Document-Klasse, um auf den gesamten Bereich des Dokuments zuzugreifen. Dann verwenden wir die Text-Eigenschaft, um den in diesem Bereich enthaltenen Text abzurufen.

## Anzeige des extrahierten Textes

Nachdem wir nun den Text aus dem angegebenen Bereich extrahiert haben, können wir ihn je nach Bedarf Ihrer Anwendung anzeigen oder verarbeiten. Sie können es beispielsweise auf dem Bildschirm anzeigen oder in einer Ausgabedatei speichern. Hier ist ein Beispiel, um den extrahierten Text anzuzeigen:

```csharp
Console.WriteLine(text);
```

In diesem Beispiel verwenden wir die WriteLine-Methode der Console-Klasse, um den extrahierten Text in der Konsole anzuzeigen.

### Beispielquellcode für die Funktion „Text aus Bereichen abrufen“ mit Aspose.Words für .NET

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das Word-Dokument
Document doc = new Document(dataDir + "Document.docx");

// Extrahieren Sie den Text aus dem Dokument
string text = doc.Range.Text;

// Zeigen Sie den extrahierten Text an
Console.WriteLine(text);
```

## Abschluss

In diesem Handbuch haben wir beschrieben, wie Sie mit Aspose.Words für .NET mithilfe des bereitgestellten C#-Quellcodes Text aus einem Word-Dokument extrahieren. Indem Sie die bereitgestellten Schritte befolgen, können Sie problemlos Text aus bestimmten Bereichen in Ihren Word-Dokumenten in Ihrer C#-Anwendung extrahieren. Aspose.Words bietet enorme Flexibilität und Leistungsfähigkeit für die Arbeit mit Dokumentinhalten und ermöglicht Ihnen die Verarbeitung und Verwendung von Text entsprechend Ihren spezifischen Anforderungen.