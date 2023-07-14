---
title: Holen Sie sich das Trennzeichen für den Absatzstil
linktitle: Holen Sie sich das Trennzeichen für den Absatzstil
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET das Absatzformat-Trennzeichen erhalten.
type: docs
weight: 10
url: /de/net/document-formatting/get-paragraph-style-separator/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie die Funktion „Absatzstiltrennzeichen abrufen“ mit Aspose.Words für .NET verwenden. Führen Sie die folgenden Schritte aus, um den Quellcode zu verstehen und die Änderungen anzuwenden.

## Schritt 1: Laden des Dokuments

Geben Sie zunächst das Verzeichnis für Ihre Dokumente an und laden Sie das Dokument in ein Document-Objekt. Hier ist wie:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Document.docx");
```

## Schritt 2: Trennzeichen für Absatzstile finden

Wir durchlaufen nun alle Absätze im Dokument und prüfen, ob ein Absatz ein Stiltrennzeichen ist. Hier ist wie:

```csharp
foreach(Paragraph paragraph in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (paragraph.BreakIsStyleSeparator)
     {
         Console.WriteLine("Separator found!");
     }
}
```

### Beispielquellcode für Get Paragraph Style Separator mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für die Funktion „Absatzstiltrennzeichen abrufen“ mit Aspose.Words für .NET:

```csharp

            Document doc = new Document(MyDir + "Document.docx");

            foreach (Paragraph paragraph in doc.GetChildNodes(NodeType.Paragraph, true))
            {
                if (paragraph.BreakIsStyleSeparator)
                {
                    Console.WriteLine("Separator Found!");
                }
            }
        
```

Mit diesem Code können Sie mit Aspose.Words für .NET die Absatztrennzeichen in einem Dokument finden.

