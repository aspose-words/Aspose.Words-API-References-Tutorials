---
title: Offene Typfunktionen
linktitle: Offene Typfunktionen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie Open Type-Funktionen in Aspose.Words für .NET aktivieren und verwenden
type: docs
weight: 10
url: /de/net/enable-opentype-features/open-type-features/
---

In diesem umfassenden Tutorial erfahren Sie, wie Sie Open Type-Funktionen in Aspose.Words für .NET aktivieren und nutzen. Wir führen Sie durch den Prozess und stellen Ihnen die notwendigen C#-Code-Snippets zur Verfügung. Am Ende dieses Handbuchs werden Sie in der Lage sein, mit Open Type-Funktionen in Ihren Word-Dokumenten zu arbeiten.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Aspose.Words für .NET-Bibliothek auf Ihrem System installiert.

## Schritt 1: Laden Sie das Dokument
Laden Sie zunächst das Dokument mit der Document-Klasse:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");
```

## Schritt 2: Aktivieren Sie Open Type-Funktionen
Um Open Type-Funktionen zu aktivieren, legen Sie die TextShaperFactory-Eigenschaft der LayoutOptions-Klasse auf eine Instanz der gewünschten Textformer-Factory fest. In diesem Beispiel verwenden wir die HarfBuzzTextShaperFactory:

```csharp
doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;
```

## Schritt 3: Speichern Sie das Dokument
Nachdem Sie die Open Type-Funktionen aktiviert haben, speichern Sie das Dokument im gewünschten Ausgabeformat, z. B. PDF:

```csharp
doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

### Beispielquellcode für Open Type Features mit Aspose.Words für .NET
Hier ist der vollständige Quellcode für die Verwendung von Open Type-Funktionen in Aspose.Words für .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");

doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;

doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

## Abschluss
Glückwunsch! Sie haben erfolgreich gelernt, wie Sie Open Type-Funktionen in Aspose.Words für .NET aktivieren und nutzen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie jetzt mit Open Type-Funktionen in Ihren Word-Dokumenten arbeiten.

Open Type-Funktionen bieten erweiterte Möglichkeiten zur Typografie und Textgestaltung, sodass Sie optisch ansprechende und professionell aussehende Dokumente erstellen können. Experimentieren Sie mit verschiedenen Textformerfabriken und erkunden Sie die Möglichkeiten von Open Type-Funktionen in Ihren Projekten.

### FAQs

#### F: Wie aktiviere ich OpenType-Funktionen in Aspose.Words für .NET?

A: Um OpenType-Funktionen in Aspose.Words für .NET zu aktivieren, müssen Sie die im Tutorial genannten Schritte befolgen.

#### F: Welche OpenType-Funktionen werden in Aspose.Words für .NET unterstützt?

A: Aspose.Words für .NET unterstützt mehrere OpenType-Funktionen, wie Ligaturen, Glyphenvariationen, kontextbezogene Ersetzungen und mehr.

#### F: Wie kann ich überprüfen, ob eine OpenType-Funktion in einer bestimmten Schriftart unterstützt wird?

 A: Sie können mithilfe von überprüfen, ob eine OpenType-Funktion in einer bestimmten Schriftart unterstützt wird`Font.OpenTypeFeatures` Methode in Aspose.Words für .NET.

#### F: Welche anderen Textformatierungsfunktionen unterstützt Aspose.Words für .NET?

A: Neben OpenType-Funktionen unterstützt Aspose.Words für .NET auch andere Textformatierungsfunktionen wie das Formatieren von Absätzen, das Erstellen von Tabellen, das Hinzufügen von Bildern usw.

#### F: Kann ich OpenType-Funktionen in allen Versionen von Aspose.Words für .NET verwenden?

A: OpenType-Funktionen werden in neueren Versionen von Aspose.Words für .NET unterstützt. Stellen Sie sicher, dass Sie eine kompatible Version verwenden, um von diesen Funktionen profitieren zu können.