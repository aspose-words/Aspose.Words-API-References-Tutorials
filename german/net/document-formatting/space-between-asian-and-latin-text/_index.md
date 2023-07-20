---
title: Leerzeichen zwischen asiatischem und lateinischem Text im Word-Dokument
linktitle: Leerzeichen zwischen asiatischem und lateinischem Text im Word-Dokument
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET den Abstand zwischen asiatischem und lateinischem Text in einem Word-Dokument automatisch anpassen.
type: docs
weight: 10
url: /de/net/document-formatting/space-between-asian-and-latin-text/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie die Leerzeichenfunktion zwischen asiatischem und lateinischem Text in der Word-Dokumentfunktion mit Aspose.Words für .NET verwenden. Führen Sie die folgenden Schritte aus, um den Quellcode zu verstehen und die Änderungen anzuwenden.

## Schritt 1: Dokument erstellen und konfigurieren

Erstellen Sie zunächst ein neues Dokument und ein zugehöriges DocumentBuilder-Objekt. Hier ist wie:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Den Abstand zwischen asiatischem und lateinischem Text einrichten

Wir konfigurieren nun den Abstand zwischen asiatischem und lateinischem Text mithilfe der Eigenschaften des ParagraphFormat-Objekts. Hier ist wie:

```csharp
ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

builder.Writeln("Auto adjust space between Asian and Latin text");
builder.Writeln("Auto adjust space between Asian text and numbers");
```

## Schritt 3: Speichern des Dokuments

 Nachdem Sie das Texteingabeformularfeld eingefügt haben, speichern Sie das Dokument mithilfe von am gewünschten Ort`Save` Methode. Stellen Sie sicher, dass Sie den richtigen Dateipfad angeben:

```csharp
doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
```

### Beispielquellcode für Leerzeichen zwischen asiatischem und lateinischem Text mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für die Funktion „Leerzeichen zwischen asiatischem und lateinischem Text“ mit Aspose.Words für .NET:


```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

builder.Writeln("Automatically adjust space between Asian and Latin text");
builder.Writeln("Automatically adjust space between Asian text and numbers");

doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
```

Mit diesem Code können Sie mithilfe von Aspose.Words für .NET den Abstand zwischen asiatischem und lateinischem Text in Ihrem Dokument automatisch anpassen.

## Abschluss

In diesem Tutorial haben wir den Prozess der Verwendung der Leerzeichenfunktion zum Anpassen des Abstands zwischen asiatischem und lateinischem Text in einem Word-Dokument mit Aspose.Words für .NET untersucht. Indem Sie die beschriebenen Schritte befolgen, können Sie den richtigen Abstand und die richtige Ausrichtung sicherstellen, was besonders hilfreich ist, wenn Sie mit gemischten asiatischen und lateinischen Inhalten arbeiten.

### FAQs

#### F: Was ist die Leerzeichenfunktion zwischen asiatischem und lateinischem Text in einem Word-Dokument?

A: Die Funktion „Abstand zwischen asiatischem und lateinischem Text“ in einem Word-Dokument bezieht sich auf die Möglichkeit, den Abstand zwischen Text, der in verschiedenen Schriftarten geschrieben wurde, wie asiatisch (z. B. Chinesisch, Japanisch) und lateinisch (z. B. Englisch), automatisch anzupassen.

#### F: Warum ist es wichtig, den Abstand zwischen asiatischem und lateinischem Text anzupassen?

A: Die Anpassung des Abstands zwischen asiatischem und lateinischem Text ist von entscheidender Bedeutung, um sicherzustellen, dass unterschiedliche Schriften harmonisch in das Dokument passen. Der richtige Abstand verbessert die Lesbarkeit und das allgemeine visuelle Erscheinungsbild und verhindert, dass der Text zu eng oder ausgebreitet erscheint.

#### F: Kann ich die Abstandsanpassungen zwischen verschiedenen Skripten anpassen?

 A: Ja, Sie können die Abstandsanpassungen zwischen verschiedenen Skripten mithilfe von anpassen`AddSpaceBetweenFarEastAndAlpha` Und`AddSpaceBetweenFarEastAndDigit` Eigenschaften. Durch Aktivieren oder Deaktivieren dieser Eigenschaften können Sie den Abstand zwischen asiatischem und lateinischem Text sowie zwischen asiatischem Text und Zahlen steuern.

#### F: Unterstützt Aspose.Words für .NET andere Dokumentformatierungsfunktionen?

A: Ja, Aspose.Words für .NET bietet umfassende Unterstützung für verschiedene Dokumentformatierungsfunktionen. Es umfasst Funktionen für Schriftarten, Absätze, Tabellen, Bilder und mehr. Sie können Ihre Word-Dokumente effektiv programmgesteuert bearbeiten und formatieren.

#### F: Wo finde ich zusätzliche Ressourcen und Dokumentation für Aspose.Words für .NET?

 A: Umfassende Ressourcen und Dokumentation zur Verwendung von Aspose.Words für .NET finden Sie unter[Aspose.Words API-Referenz](https://reference.aspose.com/words/net/). Dort finden Sie detaillierte Anleitungen, Tutorials, Codebeispiele und API-Referenzen, die Ihnen dabei helfen, die leistungsstarken Funktionen von Aspose.Words für .NET effektiv zu nutzen.