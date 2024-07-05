---
title: Zuletzt gedruckte Eigenschaft im PDF-Dokument aktualisieren
linktitle: Zuletzt gedruckte Eigenschaft im PDF-Dokument aktualisieren
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Aktualisieren der Eigenschaft „Zuletzt gedruckt“ bei der Konvertierung in PDF mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/update-last-printed-property/
---

Dieser Artikel enthält eine Schritt-für-Schritt-Anleitung zur Verwendung der Eigenschaft „Letzter Druck“ in der PDF-Dokumentaktualisierungsfunktion mit Aspose.Words für .NET. Wir werden jeden Teil des Codes im Detail erklären. Am Ende dieses Tutorials werden Sie wissen, wie Sie die Option zum Aktualisieren der Eigenschaft „Zuletzt gedruckt“ bei der Konvertierung in PDF konfigurieren.

Stellen Sie vor dem Start sicher, dass Sie die Aspose.Words für .NET-Bibliothek in Ihrem Projekt installiert und konfiguriert haben. Sie finden die Bibliothek und Installationsanweisungen auf der Aspose-Website.

## Schritt 1: Dokumentverzeichnis festlegen

 Zunächst müssen Sie den Pfad zum Verzeichnis angeben, in dem sich Ihre Dokumente befinden. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Dokument hochladen

Als nächstes müssen wir das Dokument laden, das wir verarbeiten möchten. In diesem Beispiel gehen wir davon aus, dass das Dokument „Rendering.docx“ heißt und sich im angegebenen Dokumentverzeichnis befindet.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Schritt 3: Konfigurieren Sie die Optionen zum Speichern als PDF mit der aktualisierten Eigenschaft „Zuletzt gedruckt“

 Um die Aktualisierung der Eigenschaft "Zuletzt gedruckt" bei der Konvertierung in PDF zu aktivieren, müssen wir die`PdfSaveOptions` Objekt und setzen Sie den`UpdateLastPrintedProperty`Eigentum an`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };
```

## Schritt 4: Speichern Sie das Dokument als PDF mit der Aktualisierung der Eigenschaft „Zuletzt gedruckt“

Abschließend können wir das Dokument mit den zuvor konfigurierten Speicheroptionen im PDF-Format speichern.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);
```

Das ist alles! Sie haben die Aktualisierung der Eigenschaft „Zuletzt gedruckt“ beim Konvertieren eines Dokuments in PDF mit Aspose.Words für .NET erfolgreich aktiviert.

### Beispiel-Quellcode zum Aktualisieren der Eigenschaft „Zuletzt gedruckt“ mit Aspose.Words für .NET


```csharp

	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);

```
## Abschluss

In diesem Tutorial haben wir erklärt, wie Sie die Eigenschaft „Zuletzt gedruckt“ in einem PDF-Dokument mit Aspose.Words für .NET aktualisieren. Indem Sie die angegebenen Schritte befolgen, können Sie die Option zum Aktualisieren der Eigenschaft „Zuletzt gedruckt“ beim Konvertieren eines Dokuments in PDF ganz einfach konfigurieren. Verwenden Sie diese Funktion, um die Dokumentnutzung und zugehörige Informationen zu verfolgen.

### Häufig gestellte Fragen

#### F: Was ist die Eigenschaft „Zuletzt gedruckt“ in einem PDF-Dokument?
A: Die Eigenschaft „Zuletzt gedruckt“ in einem PDF-Dokument bezieht sich auf das Datum und die Uhrzeit, wann das Dokument zuletzt gedruckt wurde. Diese Eigenschaft kann nützlich sein, um Informationen zur Dokumentnutzung und -verwaltung zu verfolgen.

#### F: Wie kann ich die Eigenschaft „Zuletzt gedruckt“ in einem PDF-Dokument mit Aspose.Words für .NET aktualisieren?
A: Um die Eigenschaft „Zuletzt gedruckt“ in einem PDF-Dokument mit Aspose.Words für .NET zu aktualisieren, folgen Sie diesen Schritten:

 Erstellen Sie eine Instanz des`Document` Klasse, die den Pfad zum Word-Dokument angibt.

 Erstellen Sie eine Instanz des`PdfSaveOptions` Klasse und legen Sie die`UpdateLastPrintedProperty`Eigentum an`true` um die Aktualisierung der Eigenschaft „Zuletzt gedruckt“ zu ermöglichen.

 Verwenden Sie die`Save` Methode der`Document`Klasse, um das Dokument durch Angabe von Speicheroptionen im PDF-Format zu speichern.

#### F: Wie kann ich überprüfen, ob die Eigenschaft „Zuletzt gedruckt“ im generierten PDF-Dokument aktualisiert wurde?
A: Sie können überprüfen, ob die Eigenschaft „Zuletzt gedruckt“ im generierten PDF-Dokument aktualisiert wurde, indem Sie die PDF-Datei mit einem kompatiblen PDF-Viewer wie Adobe Acrobat Reader öffnen und die Dokumentinformationen anzeigen. Datum und Uhrzeit des letzten Ausdrucks sollten mit Datum und Uhrzeit der Generierung des PDF-Dokuments übereinstimmen.
