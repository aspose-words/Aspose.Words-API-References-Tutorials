---
title: TCField einfügen
linktitle: TCField einfügen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie TCFields in Word-Dokumente mit C# und Aspose.Words für .NET einfügen und bearbeiten.
type: docs
weight: 10
url: /de/net/add-content-using-documentbuilder/insert-tcfield/
---

In diesem Beispiel führen wir Sie durch den Prozess der Verwendung der Funktion „TCField einfügen“ von Aspose.Words für .NET. Das TCField stellt einen Inhaltsverzeichniseintrag in einem Word-Dokument dar. Wir werden eine Schritt-für-Schritt-Erklärung des C#-Quellcodes zusammen mit der erwarteten Ausgabe im Markdown-Format bereitstellen. Lass uns anfangen!

## Schritt 1: Initialisieren des Dokuments und des Dokument-Builders

Zunächst müssen wir das Dokument und den Document Builder initialisieren. Der Document Builder ist ein leistungsstarkes Tool von Aspose.Words für .NET, mit dem wir Word-Dokumente programmgesteuert erstellen und bearbeiten können. So können Sie es machen:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Einfügen des TCField

 Als nächstes fügen wir das TCField mithilfe von in das Dokument ein`InsertField` Methode. Das TCField stellt einen Inhaltsverzeichniseintrag mit dem angegebenen Eintragstext dar. Hier ist ein Beispiel:

```csharp
builder.InsertField("TC \"Entry Text\" \\f t");
```

Der obige Code fügt ein TCField mit dem Eintragstext „Entry Text“ in das Dokument ein.

## Schritt 3: Speichern des Dokuments

 Nach dem Einfügen des TCField können wir das Dokument mithilfe von an einem bestimmten Ort speichern`Save` Methode. Stellen Sie sicher, dass Sie den gewünschten Pfad und Dateinamen für das Ausgabedokument angeben. Hier ist ein Beispiel:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTCField.docx");
```

Der obige Code speichert das Dokument mit dem TCField im angegebenen Verzeichnis.

## Ausgabe-Markdown-Formate

Wenn der Code erfolgreich ausgeführt wird, enthält das Ausgabedokument einen Inhaltsverzeichniseintrag mit dem angegebenen Eintragstext. Das TCField wird als Feld im Word-Dokument dargestellt und das resultierende Markdown-Format hängt davon ab, wie das Dokument verarbeitet wird.

Bitte beachten Sie, dass das Ausgabedokument nicht direkt im Markdown-Format, sondern im Word-Format vorliegt. Wenn Sie jedoch das Word-Dokument mit geeigneten Tools oder Bibliotheken in Markdown konvertieren, wird das TCField entsprechend verarbeitet.

### Beispielquellcode für das Einfügen von TCField mit Aspose.Words für .NET

Hier ist der vollständige Beispielquellcode zum Einfügen eines TCField mit Aspose.Words für .NET:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.InsertField("TC \"Entry Text\" \\f t");

	doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTCField.docx");
			
```

Fühlen Sie sich frei, den Code entsprechend Ihren Anforderungen zu ändern und andere Funktionen von Aspose.Words für .NET zu erkunden.

Das ist es! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Words für .NET ein TCField einfügen.

