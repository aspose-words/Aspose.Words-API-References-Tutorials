---
title: Doc zu Docx
linktitle: Doc zu Docx
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie Word-Dokumente mit Aspose.Words für .NET vom .doc- in das Docx-Format konvertieren. Schritt-für-Schritt-Anleitung mit Beispielquellcode.
type: docs
weight: 10
url: /de/net/basic-conversions/doc-to-docx/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess der Verwendung von Aspose.Words für .NET zum Konvertieren eines Word-Dokuments im .doc-Format in das Docx-Format. Wir erklären Ihnen den bereitgestellten C#-Quellcode und begleiten Sie bei der Implementierung in Ihren eigenen Projekten.

Stellen Sie zunächst sicher, dass Aspose.Words für .NET in Ihrer Entwicklungsumgebung installiert und eingerichtet ist. Wenn Sie dies noch nicht getan haben, laden Sie die Bibliothek von der offiziellen Website herunter und installieren Sie sie.

## Schritt 1: Einrichten der Entwicklungsumgebung

Bevor Sie mit dem Codieren beginnen, stellen Sie sicher, dass Sie über eine geeignete Entwicklungsumgebung verfügen. Öffnen Sie Visual Studio oder Ihre bevorzugte C#-IDE und erstellen Sie ein neues Projekt.

## Schritt 2: Referenzen hinzufügen und Namespaces importieren

Um Aspose.Words für .NET verwenden zu können, müssen Sie in Ihrem Projekt Verweise auf die Bibliothek hinzufügen. Klicken Sie mit der rechten Maustaste auf den Ordner „Referenzen“ in Ihrem Projekt, wählen Sie „Referenz hinzufügen“ und navigieren Sie zu dem Speicherort, an dem Sie die Aspose.Words für .NET-Bibliothek installiert haben. Wählen Sie die entsprechende Version aus und klicken Sie auf „OK“, um die Referenz hinzuzufügen.

Importieren Sie als Nächstes die erforderlichen Namespaces oben in Ihre C#-Datei:

```csharp
using Aspose.Words;
```

## Schritt 3: Initialisieren des Dokumentobjekts

 In diesem Schritt initialisieren Sie die`Document` Objekt mit dem Pfad zu Ihrem Quelldokument im .doc-Format. Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Verzeichnispfad, in dem sich Ihr Dokument befindet, und`"Document.doc"` mit dem Namen Ihres Quelldokuments. Hier ist der Codeausschnitt:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.doc");
```

## Schritt 4: Konvertieren des Dokuments in das Docx-Format

 Nachdem Sie nun das initialisiert haben`Document`Objekt, können Sie mit dem Konvertierungsprozess fortfahren. Aspose.Words für .NET bietet verschiedene Optionen und Einstellungen zur Anpassung, für eine grundlegende Konvertierung sind jedoch keine zusätzlichen Parameter erforderlich.

## Schritt 5: Speichern des konvertierten Dokuments

 Um das konvertierte Dokument im Docx-Format zu speichern, müssen Sie das aufrufen`Save` Methode auf der`Document` Objekt. Geben Sie den Pfad und Dateinamen für das Ausgabedokument an. In diesem Beispiel speichern wir es als`"BaseConversions.DocToDocx.docx"`. Hier ist der Codeausschnitt:

```csharp
doc.Save(dataDir + "BaseConversions.DocToDocx.docx");
```

Das ist es! Sie haben mit Aspose.Words für .NET erfolgreich ein Word-Dokument im .doc-Format in das Docx-Format konvertiert.

### Beispielquellcode für Doc To Docx mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.doc");

	doc.Save(dataDir + "BaseConversions.DocToDocx.docx");
	
```

Sie können diesen Code gerne in Ihren eigenen Projekten verwenden und entsprechend Ihren spezifischen Anforderungen modifizieren.




