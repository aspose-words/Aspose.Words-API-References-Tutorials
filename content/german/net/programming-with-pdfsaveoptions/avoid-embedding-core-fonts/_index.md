---
title: Reduzieren Sie die PDF-Dateigröße, indem Sie keine Kernschriftarten einbetten
linktitle: Reduzieren Sie die PDF-Dateigröße, indem Sie keine Kernschriftarten einbetten
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie die PDF-Dateigröße reduzieren, indem Sie beim Konvertieren von Word-Dokumenten in PDF mit Aspose.Words für .NET keine Kernschriftarten einbetten.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/avoid-embedding-core-fonts/
---

In diesem Tutorial führen wir Sie durch die Schritte, wie Sie die PDF-Dateigröße reduzieren können, indem Sie mit Aspose.Words für .NET keine Kernschriftarten einbetten. Mit dieser Funktion können Sie steuern, ob beim Konvertieren eines Word-Dokuments grundlegende Schriftarten wie Arial, Times New Roman usw. in das PDF eingebettet werden müssen. Befolgen Sie die folgenden Schritte:

## Schritt 1: Dokument einlegen

Beginnen Sie mit dem Hochladen des Word-Dokuments, das Sie in PDF konvertieren möchten:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Achten Sie darauf, den richtigen Pfad zu Ihrem Word-Dokument anzugeben.

## Schritt 2: PDF-Konvertierungsoptionen festlegen

Erstellen Sie eine Instanz der Klasse PdfSaveOptions und aktivieren Sie die Vermeidung grundlegender Schriftarteinbettungen:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
```

Diese Option steuert, ob Basisschriftarten in das PDF eingebettet werden sollen oder nicht.

## Schritt 3: Dokument in PDF konvertieren

 Verwenden Sie die`Save` Methode zum Konvertieren des Word-Dokuments in PDF durch Angabe der Konvertierungsoptionen:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);
```

Stellen Sie sicher, dass Sie den richtigen Pfad zum Speichern der konvertierten PDF-Datei angeben.

### Beispielquellcode zum Vermeiden der Einbettung von Core Fonts mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zur Verwendung der Funktion zum Vermeiden der Einbettung von Kernschriftarten mit Aspose.Words für .NET:

```csharp

	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// In das Ausgabe-PDF werden keine Kernschriftarten wie Arial, Times New Roman usw. eingebettet.
	PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);

```

Indem Sie diese Schritte befolgen, können Sie einfach steuern, ob beim Konvertieren eines Word-Dokuments mit Aspose.Words für .NET Basisschriftarten in das PDF eingebettet werden sollen.


## Abschluss

In diesem Tutorial haben wir erklärt, wie Sie die Größe einer PDF-Datei reduzieren können, indem Sie mit Aspose.Words für .NET keine Basisschriftarten einbetten. Mit dieser Funktion können Sie steuern, ob Basisschriftarten beim Konvertieren eines Word-Dokuments in die PDF-Datei eingebettet werden sollen. Indem Sie die beschriebenen Schritte befolgen, können Sie das Einbetten oder Nichteinbetten von Basisschriftarten problemlos steuern. Dies kann dazu beitragen, die PDF-Dateigröße zu reduzieren und eine bessere Kompatibilität und ein einheitliches Erscheinungsbild des Dokuments auf verschiedenen Geräten und Plattformen sicherzustellen. Vergessen Sie nicht, die Konsequenzen des Nichteinbettens von Basisschriftarten zu berücksichtigen und zu experimentieren, um sicherzustellen, dass das Dokument wie erwartet gerendert wird.

### Häufig gestellte Fragen

#### F: Welche Option gibt es, Basisschriftarten nicht in eine PDF-Datei einzubetten, und warum ist sie wichtig?
A: Die Option, Basisschriftarten nicht in eine PDF-Datei einzubetten, steuert, ob Basisschriftarten wie Arial, Times New Roman usw. beim Konvertieren eines Word-Dokuments in die PDF-Datei eingebettet werden müssen. Dies kann wichtig sein, um die Größe der PDF-Datei zu reduzieren, indem die Einbeziehung von Schriftarten vermieden wird, die allgemein in PDF-Lesesystemen verfügbar sind. Es kann auch dazu beitragen, eine bessere Kompatibilität und ein einheitliches Erscheinungsbild des PDF-Dokuments auf verschiedenen Geräten und Plattformen sicherzustellen.

#### F: Wie kann ich Aspose.Words für .NET so konfigurieren, dass keine Basisschriftarten in eine PDF-Datei eingebettet werden?
A: Um Aspose.Words für .NET so zu konfigurieren, dass keine Kernschriftarten in eine PDF-Datei eingebettet werden, befolgen Sie diese Schritte:

 Legen Sie den Verzeichnispfad fest, in dem sich Ihre Dokumente befinden, indem Sie ersetzen`"YOUR DOCUMENTS DIRECTORY"` durch den tatsächlichen Pfad Ihres Dokumentverzeichnisses.

 Laden Sie das Word-Dokument, das Sie in PDF konvertieren möchten, mit dem`Document` Klasse und dem angegebenen Dokumentpfad.

 Erstellen Sie eine Instanz des`PdfSaveOptions` Klasse und legen Sie die`UseCoreFonts`Eigentum an`true`. Dadurch wird das Einbetten von Basisschriftarten in die generierte PDF-Datei vermieden.

 Verwenden Sie die`Save` Methode der`Document` Objekt, um das Dokument im PDF-Format zu speichern und dabei die zuvor konfigurierten Konvertierungsoptionen anzugeben.

#### F: Welche Vorteile bietet es, keine Basisschriftarten in eine PDF-Datei einzubetten?
A: Das Nichteinbetten von Basisschriftarten in eine PDF-Datei hat folgende Vorteile:

Reduzierung der PDF-Dateigröße: Durch den Verzicht auf die Einbettung allgemein verfügbarer Schriftarten wie Arial, Times New Roman usw. kann die PDF-Dateigröße reduziert werden, was das Speichern, Teilen und Übertragen von Dateien erleichtert.

Bessere Kompatibilität: Durch die Verwendung grundlegender Schriftarten, die in PDF-Lesesystemen allgemein verfügbar sind, gewährleisten Sie eine bessere Kompatibilität und ein besseres Erscheinungsbild des Dokuments auf verschiedenen Geräten und Plattformen.

#### F: Welche Konsequenzen hat es, wenn Basisschriftarten nicht in eine PDF-Datei eingebettet werden?
A: Das Nichteinbetten von Basisschriftarten in eine PDF-Datei hat folgende Konsequenzen:

Anderes Erscheinungsbild: Wenn die Basisschriftarten auf dem System, auf dem die PDF-Datei geöffnet wird, nicht verfügbar sind, werden Ersatzschriftarten verwendet, was zu einem anderen Erscheinungsbild als beabsichtigt führen kann.

Probleme mit der Lesbarkeit: Die verwendeten Ersatzschriften sind möglicherweise nicht so gut lesbar wie die Originalschriften, was die Lesbarkeit des Dokuments beeinträchtigen kann.