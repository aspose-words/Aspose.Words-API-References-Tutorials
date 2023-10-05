---
title: Reduzieren Sie die PDF-Dateigröße, indem Sie keine Kernschriftarten einbetten
linktitle: Reduzieren Sie die PDF-Dateigröße, indem Sie keine Kernschriftarten einbetten
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie die Größe von PDF-Dateien reduzieren können, indem Sie beim Konvertieren von Word-Dokumenten in PDF mit Aspose.Words für .NET keine Kernschriftarten einbetten.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/avoid-embedding-core-fonts/
---

In diesem Tutorial führen wir Sie durch die Schritte, wie Sie die Größe von PDF-Dateien reduzieren können, indem Sie Kernschriftarten nicht mit Aspose.Words für .NET einbetten. Mit dieser Funktion können Sie steuern, ob beim Konvertieren eines Word-Dokuments grundlegende Schriftarten wie Arial, Times New Roman usw. in das PDF eingebettet werden müssen. Folgen Sie den unteren Schritten:

## Schritt 1: Laden des Dokuments

Laden Sie zunächst das Word-Dokument hoch, das Sie in PDF konvertieren möchten:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Stellen Sie sicher, dass Sie den richtigen Pfad zu Ihrem Word-Dokument angeben.

## Schritt 2: PDF-Konvertierungsoptionen festlegen

Erstellen Sie eine Instanz der PdfSaveOptions-Klasse und aktivieren Sie die grundlegende Vermeidung der Schriftarteinbettung:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
```

Diese Option steuert, ob Basisschriftarten in das PDF eingebettet werden sollen oder nicht.

## Schritt 3: Dokument in PDF konvertieren

 Benutzen Sie die`Save` Methode zum Konvertieren des Word-Dokuments in PDF durch Angabe von Konvertierungsoptionen:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);
```

Stellen Sie sicher, dass Sie den richtigen Pfad zum Speichern der konvertierten PDF-Datei angeben.

### Beispielquellcode für „Vermeiden Sie das Einbetten von Kernschriftarten“ mithilfe von Aspose.Words für .NET

Hier ist der vollständige Quellcode zur Verwendung der Funktion, um die Einbettung von Kernschriftarten mit Aspose.Words für .NET zu vermeiden:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Das Ausgabe-PDF wird nicht in Kernschriftarten wie Arial, Times New Roman usw. eingebettet.
	PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);

```

Wenn Sie diese Schritte befolgen, können Sie ganz einfach steuern, ob beim Konvertieren eines Word-Dokuments mit Aspose.Words für .NET Basisschriftarten in die PDF-Datei eingebettet werden sollen.


## Abschluss

In diesem Tutorial haben wir erklärt, wie Sie die Größe einer PDF-Datei reduzieren können, indem Sie mit Aspose.Words für .NET auf die Einbettung grundlegender Schriftarten verzichten. Mit dieser Funktion können Sie steuern, ob beim Konvertieren eines Word-Dokuments Basisschriftarten in die PDF-Datei eingebettet werden sollen. Indem Sie die beschriebenen Schritte befolgen, können Sie das Einbetten oder Nichteinbetten grundlegender Schriftarten einfach steuern, was dazu beitragen kann, die Größe der PDF-Datei zu reduzieren und eine bessere Kompatibilität und ein einheitliches Erscheinungsbild des Dokuments auf verschiedenen Geräten und Plattformen sicherzustellen. Vergessen Sie nicht, die Konsequenzen zu bedenken, wenn Basisschriftarten nicht eingebettet werden, und zu experimentieren, um sicherzustellen, dass das Dokument wie erwartet gerendert wird.

### Häufig gestellte Fragen

#### F: Welche Option gibt es, Basisschriftarten nicht in eine PDF-Datei einzubetten, und warum ist das wichtig?
A: Die Option, Basisschriftarten nicht in eine PDF-Datei einzubetten, steuert, ob Basisschriftarten wie Arial, Times New Roman usw. beim Konvertieren eines Word-Dokuments in die PDF-Datei eingebettet werden müssen. Dies kann wichtig sein, um die Größe der PDF-Datei zu reduzieren, indem die Einbeziehung von Schriftarten vermieden wird, die üblicherweise auf PDF-Reader-Systemen verfügbar sind. Es kann auch dazu beitragen, eine bessere Kompatibilität und ein einheitliches Erscheinungsbild des PDF-Dokuments auf verschiedenen Geräten und Plattformen sicherzustellen.

#### F: Wie kann ich Aspose.Words für .NET so konfigurieren, dass Basisschriftarten nicht in eine PDF-Datei eingebettet werden?
A: Um Aspose.Words für .NET so zu konfigurieren, dass Kernschriftarten nicht in eine PDF-Datei eingebettet werden, führen Sie die folgenden Schritte aus:

 Legen Sie den Verzeichnispfad fest, in dem sich Ihre Dokumente befinden, indem Sie ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem tatsächlichen Pfad Ihres Dokumentenverzeichnisses.

 Laden Sie das Word-Dokument, das Sie in PDF konvertieren möchten, mit`Document` -Klasse und den angegebenen Dokumentpfad.

 Erstellen Sie eine Instanz von`PdfSaveOptions` Klasse und legen Sie die fest`UseCoreFonts`Eigentum zu`true`. Dadurch wird das Einbetten von Basisschriftarten in die generierte PDF-Datei vermieden.

 Benutzen Sie die`Save` Methode der`Document` Objekt zum Speichern des Dokuments im PDF-Format unter Angabe der zuvor konfigurierten Konvertierungsoptionen.

#### F: Welche Vorteile hat es, Basisschriftarten nicht in eine PDF-Datei einzubetten?
A: Die Vorteile, Basisschriftarten nicht in eine PDF-Datei einzubetten, sind:

Reduzierung der PDF-Dateigröße: Durch die Vermeidung der Einbettung allgemein verfügbarer Schriftarten wie Arial, Times New Roman usw. kann die PDF-Dateigröße reduziert werden, was das Speichern, Teilen und Übertragen von Dateien erleichtert.

Bessere Kompatibilität: Durch die Verwendung grundlegender Schriftarten, die üblicherweise auf PDF-Reader-Systemen verfügbar sind, stellen Sie eine bessere Kompatibilität und Dokumentdarstellung auf verschiedenen Geräten und Plattformen sicher.

#### F: Welche Konsequenzen hat es, wenn Basisschriftarten nicht in eine PDF-Datei eingebettet werden?
A: Wenn Basisschriftarten nicht in eine PDF-Datei eingebettet werden, hat dies folgende Konsequenzen:

Anderes Erscheinungsbild: Wenn die Basisschriftarten auf dem System, auf dem das PDF geöffnet wird, nicht verfügbar sind, werden Ersatzschriftarten verwendet, was zu einem anderen Erscheinungsbild als beabsichtigt führen kann.

Probleme mit der Lesbarkeit: Die verwendeten Ersatzschriftarten sind möglicherweise nicht so gut lesbar wie die Originalschriftarten, was die Lesbarkeit des Dokuments beeinträchtigen kann.