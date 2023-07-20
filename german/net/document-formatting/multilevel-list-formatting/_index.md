---
title: Mehrstufige Listenformatierung in Word-Dokumenten
linktitle: Mehrstufige Listenformatierung in Word-Dokumenten
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine mehrstufige Liste erstellen und benutzerdefinierte Formatierungen in Word-Dokumenten anwenden.
type: docs
weight: 10
url: /de/net/document-formatting/multilevel-list-formatting/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie die Funktion zur mehrstufigen Listenformatierung in Word-Dokumenten mit Aspose.Words für .NET verwenden. Führen Sie die folgenden Schritte aus, um den Quellcode zu verstehen und die Änderungen anzuwenden.

## Schritt 1: Dokument erstellen und konfigurieren

Erstellen Sie zunächst ein neues Dokument und ein zugehöriges DocumentBuilder-Objekt. Hier ist wie:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Formatieren der mehrstufigen Liste

Wir wenden nun die mehrstufige Listenformatierung mit den im DocumentBuilder-Objekt verfügbaren Methoden an. Hier ist wie:

```csharp
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder. Writen("Element 2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.1");
builder.Writeln("Element 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.2.1");
builder.Writeln("Element 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 3");

builder.ListFormat.RemoveNumbers();
```

## Schritt 3: Speichern des Dokuments

 Nachdem Sie das Texteingabeformularfeld eingefügt haben, speichern Sie das Dokument mithilfe von am gewünschten Ort`Save` Methode. Stellen Sie sicher, dass Sie den richtigen Dateipfad angeben:

```csharp
doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");
```

### Beispielquellcode für die mehrstufige Listenformatierung mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für die Funktion zur mehrstufigen Listenformatierung mit Aspose.Words für .NET:


```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyNumberDefault();
builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();
builder.Writeln("Item 2.1");
builder.Writeln("Item 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Item 2.2.1");
builder.Writeln("Item 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Item 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Item 3");

builder.ListFormat.RemoveNumbers();

doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");

```

Mit diesem Code können Sie mit Aspose.Words für .NET eine Liste mit mehreren Ebenen erstellen und auf jede Ebene die richtige Formatierung anwenden.


## Abschluss

In diesem Tutorial haben wir den Prozess der Verwendung der Funktion zur mehrstufigen Listenformatierung in einem Word-Dokument mit Aspose.Words für .NET untersucht. Indem Sie die beschriebenen Schritte befolgen, können Sie gut organisierte Listen mit mehreren Ebenen erstellen und so die Struktur und Lesbarkeit Ihrer Dokumente verbessern.

### FAQs

#### F: Was ist eine mehrstufige Liste in einem Word-Dokument?

A: Eine mehrstufige Liste in einem Word-Dokument ist eine hierarchische Liste, die es Ihnen ermöglicht, Elemente in verschiedenen Ebenen von Unterelementen zu organisieren. Es trägt dazu bei, Informationen strukturiert darzustellen und den Lesern das Verständnis des Inhalts zu erleichtern.

#### F: Kann ich das Erscheinungsbild der mehrstufigen Liste anpassen?

A: Ja, Sie können das Erscheinungsbild der mehrstufigen Liste in Ihrem Word-Dokument anpassen. Durch die Anwendung verschiedener Stile wie Aufzählungspunkte, Zahlen oder Buchstaben sowie durch Anpassen von Einzügen und Abständen können Sie eine optisch ansprechende und organisierte Liste erstellen.

#### F: Unterstützt Aspose.Words für .NET andere Listenformatierungsoptionen?

A: Ja, Aspose.Words für .NET bietet umfassende Funktionen zur Listenformatierung. Es unterstützt verschiedene Listentypen, darunter Listen mit Aufzählungszeichen, nummerierte Listen und Listen mit mehreren Ebenen. Sie können die Formatierung von Listen bearbeiten, Elemente hinzufügen oder entfernen und deren Erscheinungsbild anpassen.

#### F: Kann ich Aspose.Words für .NET verwenden, um mit anderen Dokumentelementen zu arbeiten?

A: Ja, Aspose.Words für .NET bietet umfangreiche Funktionen für die Arbeit mit verschiedenen Dokumentelementen wie Absätzen, Tabellen, Bildern und mehr. Es ermöglicht Ihnen, Word-Dokumente programmgesteuert zu erstellen, zu ändern und zu konvertieren und so die Dokumentenverarbeitungsaufgaben zu rationalisieren.