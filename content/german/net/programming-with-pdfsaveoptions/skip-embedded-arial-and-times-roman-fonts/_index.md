---
title: Optimieren Sie die PDF-Größe mit Skip Embedded Arial & Times Roman Fonts
linktitle: Optimieren Sie die PDF-Größe mit Skip Embedded Arial & Times Roman Fonts
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Generieren optimierter PDF-Dateien ohne Einbetten der Schriftarten Arial und Times Roman mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/skip-embedded-arial-and-times-roman-fonts/
---

Dieser Artikel enthält eine Schritt-für-Schritt-Anleitung zur Verwendung der Funktion zur Optimierung der PDF-Größe durch Überspringen eingebetteter Arial- und Times Roman-Schriftarten auf Metadateigröße mit Aspose.Words für .NET. Wir werden jeden Teil des Codes im Detail erklären. Am Ende dieses Tutorials erfahren Sie, wie Sie die Option zum Einbetten von Schriftarten in einem Dokument konfigurieren und eine PDF-Datei erstellen, ohne die Schriftarten Arial und Times Roman einzubetten.

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

## Schritt 3: Konfigurieren Sie die Optionen zum Speichern als PDF mit Schriftarteinbettung

 Um das Einbetten der Schriftarten Arial und Times Roman in das generierte PDF zu überspringen, müssen wir das konfigurieren`PdfSaveOptions` Objekt und legen Sie das fest`FontEmbeddingMode` Eigentum zu`PdfFontEmbeddingMode.EmbedAll`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };
```

## Schritt 4: Speichern Sie das Dokument als PDF ohne eingebettete Schriftarten

Schließlich können wir das Dokument mit den zuvor konfigurierten Speicheroptionen im PDF-Format speichern.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
```

Das ist alles ! Sie haben mit Aspose.Words für .NET erfolgreich eine PDF-Datei ohne Einbettung der Schriftarten Arial und Times Roman generiert.

### Beispielquellcode zum Überspringen eingebetteter Arial- und Times Roman-Schriftarten in Metadateigröße mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
   
```

## Abschluss

In diesem Tutorial haben wir erklärt, wie Sie die Einbettung von Arial- und Times Roman-Schriftarten in ein PDF-Dokument mit Aspose.Words für .NET deaktivieren. Wenn Sie die beschriebenen Schritte befolgen, können Sie eine PDF-Datei erstellen, ohne diese spezifischen Schriftarten einzubetten. Dies kann dazu beitragen, die Dateigröße zu reduzieren und eine bessere Dokumentkompatibilität auf verschiedenen Plattformen sicherzustellen. Berücksichtigen Sie unbedingt die Konsequenzen, die sich aus der Deaktivierung der Schriftarteinbettung ergeben, wenn Sie diese Funktion verwenden. Entdecken Sie gerne weitere Funktionen von Aspose.Words für .NET, um die Generierung Ihrer PDF-Dateien zu optimieren.

### Häufig gestellte Fragen

#### F: Was bedeutet die Deaktivierung der Einbettung der Schriftarten Arial und Times Roman in ein PDF-Dokument und warum ist das wichtig?
A: Das Deaktivieren der Einbettung von Arial- und Times Roman-Schriftarten in ein PDF-Dokument bedeutet, dass diese Schriftarten nicht in die generierte PDF-Datei einbezogen werden. Dies kann wichtig sein, um die Größe der PDF-Datei zu reduzieren, indem Schriftarten vermieden werden, die bereits häufig auf PDF-Reader-Systemen verfügbar sind. Es kann auch dazu beitragen, eine bessere Kompatibilität und ein einheitliches Erscheinungsbild des PDF-Dokuments auf verschiedenen Geräten und Plattformen sicherzustellen.

#### F: Wie kann ich Aspose.Words für .NET so konfigurieren, dass Arial- und Times Roman-Schriftarten nicht in ein PDF-Dokument eingebettet werden?
A: Um Aspose.Words für .NET so zu konfigurieren, dass Arial- und Times Roman-Schriftarten nicht in ein PDF-Dokument eingebettet werden, führen Sie die folgenden Schritte aus:

 Legen Sie den Verzeichnispfad fest, in dem sich Ihre Dokumente befinden, indem Sie ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad Ihres Dokumentenverzeichnisses.

 Laden Sie das Dokument, das Sie bearbeiten möchten, mit`Document` -Klasse und den angegebenen Dokumentpfad.

 Erstellen Sie eine Instanz von`PdfSaveOptions` Klasse und legen Sie die fest`FontEmbeddingMode` Eigentum zu`PdfFontEmbeddingMode.EmbedAll`. Dadurch werden alle Schriftarten außer Arial und Times Roman in die generierte PDF-Datei eingebettet.

 Benutzen Sie die`Save` Methode der`Document` Objekt zum Speichern des Dokuments im PDF-Format unter Angabe der zuvor konfigurierten Speicheroptionen.

#### F: Welche Vorteile bietet es, die Einbettung der Schriftarten Arial und Times Roman in einem PDF-Dokument zu deaktivieren?
A: Die Deaktivierung der Einbettung der Schriftarten Arial und Times Roman in ein PDF-Dokument bietet folgende Vorteile:

Reduzierung der PDF-Dateigröße: Durch die Vermeidung der Einbettung allgemein verfügbarer Schriftarten wie Arial und Times Roman kann die PDF-Dateigröße reduziert werden, was das Speichern, Teilen und Übertragen von Dateien erleichtert.

Bessere Kompatibilität: Durch die Verwendung von Schriftarten, die allgemein auf PDF-Reader-Systemen verfügbar sind, stellen Sie eine bessere Kompatibilität und ein besseres Erscheinungsbild des Dokuments auf verschiedenen Geräten und Plattformen sicher.

#### F: Welche Konsequenzen hat es, wenn die Einbettung der Schriftarten Arial und Times Roman in einem PDF-Dokument deaktiviert wird?
A: Die Deaktivierung der Einbettung der Schriftarten Arial und Times Roman in ein PDF-Dokument hat folgende Konsequenzen:

Anderes Erscheinungsbild: Wenn die Schriftarten Arial und Times Roman auf dem System, auf dem das PDF geöffnet wird, nicht verfügbar sind, werden Ersatzschriftarten verwendet, was zu einem anderen Erscheinungsbild als beabsichtigt führen kann.

Probleme mit der Lesbarkeit: Die verwendeten Ersatzschriftarten sind möglicherweise nicht so gut lesbar wie die ursprünglichen Schriftarten, was die Lesbarkeit des Dokuments beeinträchtigen kann.