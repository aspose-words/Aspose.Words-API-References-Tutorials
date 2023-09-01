---
title: Zuletzt gedruckte Eigenschaft im PDF-Dokument aktualisieren
linktitle: Zuletzt gedruckte Eigenschaft im PDF-Dokument aktualisieren
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Aktualisieren der Eigenschaft „Zuletzt gedruckt“ bei der Konvertierung in PDF mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/update-last-printed-property/
---

Dieser Artikel enthält eine Schritt-für-Schritt-Anleitung zur Verwendung der Eigenschaft „Letzter Druck“ in der PDF-Dokumentaktualisierungsfunktion mit Aspose.Words für .NET. Wir werden jeden Teil des Codes im Detail erklären. Am Ende dieses Tutorials erfahren Sie, wie Sie die Option zum Aktualisieren der Eigenschaft „Zuletzt gedruckt“ beim Konvertieren in PDF konfigurieren.

Bevor Sie beginnen, stellen Sie sicher, dass Sie die Aspose.Words für .NET-Bibliothek in Ihrem Projekt installiert und konfiguriert haben. Die Bibliothek und Installationsanweisungen finden Sie auf der Aspose-Website.

## Schritt 1: Definieren Sie das Dokumentenverzeichnis

 Zunächst müssen Sie den Pfad zu dem Verzeichnis definieren, in dem sich Ihre Dokumente befinden. Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument hoch

Als nächstes müssen wir das Dokument laden, das wir verarbeiten möchten. In diesem Beispiel gehen wir davon aus, dass das Dokument „Rendering.docx“ heißt und sich im angegebenen Dokumentenverzeichnis befindet.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Schritt 3: Konfigurieren Sie die Optionen zum Speichern als PDF mit der aktualisierten Eigenschaft „Zuletzt gedruckt“.

 Um die Aktualisierung der Eigenschaft „Zuletzt gedruckt“ beim Konvertieren in PDF zu ermöglichen, müssen wir die konfigurieren`PdfSaveOptions` Objekt und legen Sie das fest`UpdateLastPrintedProperty` Eigentum zu`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };
```

## Schritt 4: Speichern Sie das Dokument als PDF mit der Aktualisierung der Eigenschaft „Zuletzt gedruckt“.

Schließlich können wir das Dokument mit den zuvor konfigurierten Speicheroptionen im PDF-Format speichern.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);
```

Das ist alles ! Sie haben die Aktualisierung der Eigenschaft „Zuletzt gedruckt“ erfolgreich aktiviert, wenn Sie ein Dokument mit Aspose.Words für .NET in PDF konvertieren.

### Beispielquellcode zum Aktualisieren der Eigenschaft „Zuletzt gedruckt“ mit Aspose.Words für .NET


```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);

```
## Abschluss

In diesem Tutorial haben wir erklärt, wie man die Eigenschaft „Zuletzt gedruckt“ in einem PDF-Dokument mit Aspose.Words für .NET aktualisiert. Indem Sie die angegebenen Schritte befolgen, können Sie die Option zum Aktualisieren der Eigenschaft „Zuletzt gedruckt“ beim Konvertieren eines Dokuments in PDF einfach konfigurieren. Verwenden Sie diese Funktion, um die Dokumentennutzung und zugehörige Informationen zu verfolgen.

### Häufig gestellte Fragen

#### F: Was ist die Eigenschaft „Zuletzt gedruckt“ in einem PDF-Dokument?
A: Die Eigenschaft „Zuletzt gedruckt“ in einem PDF-Dokument bezieht sich auf das Datum und die Uhrzeit, wann das Dokument zuletzt gedruckt wurde. Diese Eigenschaft kann nützlich sein, um Informationen zur Dokumentnutzung und -verwaltung zu verfolgen.

#### F: Wie kann ich die Eigenschaft „Zuletzt gedruckt“ in einem PDF-Dokument mit Aspose.Words für .NET aktualisieren?
A: Um die Eigenschaft „Zuletzt gedruckt“ in einem PDF-Dokument mit Aspose.Words für .NET zu aktualisieren, führen Sie die folgenden Schritte aus:

 Erstellen Sie eine Instanz von`Document` Klasse, die den Pfad zum Word-Dokument angibt.

 Erstellen Sie eine Instanz von`PdfSaveOptions` Klasse und legen Sie die fest`UpdateLastPrintedProperty` Eigentum zu`true` um die Aktualisierung der Eigenschaft „Zuletzt gedruckt“ zu ermöglichen.

 Benutzen Sie die`Save` Methode der`Document`Klasse zum Speichern des Dokuments im PDF-Format durch Angabe von Speicheroptionen.

#### F: Wie kann ich überprüfen, ob die Eigenschaft „Zuletzt gedruckt“ im generierten PDF-Dokument aktualisiert wurde?
A: Sie können überprüfen, ob die Eigenschaft „Zuletzt gedruckt“ im generierten PDF-Dokument aktualisiert wurde, indem Sie die PDF-Datei mit einem kompatiblen PDF-Viewer wie Adobe Acrobat Reader öffnen und die Dokumentinformationen anzeigen. Datum und Uhrzeit des letzten Drucks sollten mit Datum und Uhrzeit der Erstellung des PDF-Dokuments übereinstimmen.
