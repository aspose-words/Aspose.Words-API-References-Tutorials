---
title: Optimieren Sie die PDF-Größe, indem Sie eingebettete Schriftarten wie Arial und Times Roman überspringen
linktitle: Optimieren Sie die PDF-Größe, indem Sie eingebettete Schriftarten wie Arial und Times Roman überspringen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Erstellen optimierter PDFs ohne Einbettung der Schriftarten Arial und Times Roman mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/skip-embedded-arial-and-times-roman-fonts/
---

Dieser Artikel enthält eine Schritt-für-Schritt-Anleitung zur Verwendung der Funktion zum Optimieren der PDF-Größe durch Überspringen eingebetteter Schriftarten Arial und Times Roman auf Metadateigröße mit Aspose.Words für .NET. Wir werden jeden Teil des Codes im Detail erklären. Am Ende dieses Tutorials werden Sie in der Lage sein, die Option für den Schriftarteinbettungsmodus in einem Dokument zu konfigurieren und ein PDF ohne Einbettung von Schriftarten Arial und Times Roman zu erstellen.

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

## Schritt 3: Konfigurieren Sie die Optionen zum Speichern als PDF mit Schriftarteinbettung

 Um das Einbetten der Schriftarten Arial und Times Roman in das generierte PDF zu überspringen, müssen wir die`PdfSaveOptions` Objekt und setzen Sie den`FontEmbeddingMode`Eigentum an`PdfFontEmbeddingMode.EmbedAll`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };
```

## Schritt 4: Speichern Sie das Dokument als PDF ohne eingebettete Schriftarten

Abschließend können wir das Dokument mit den zuvor konfigurierten Speicheroptionen im PDF-Format speichern.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
```

Das ist alles! Sie haben erfolgreich ein PDF erstellt, ohne die Schriftarten Arial und Times Roman mit Aspose.Words für .NET einzubetten.

### Beispielquellcode zum Überspringen eingebetteter Schriftarten Arial und Times Roman bei Metadateigröße mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
   
```

## Abschluss

In diesem Tutorial haben wir erklärt, wie Sie die Einbettung der Schriftarten Arial und Times Roman in ein PDF-Dokument mit Aspose.Words für .NET deaktivieren. Indem Sie die beschriebenen Schritte befolgen, können Sie eine PDF-Datei ohne Einbettung dieser spezifischen Schriftarten erstellen, was zur Reduzierung der Dateigröße beitragen und eine bessere Dokumentkompatibilität zwischen verschiedenen Plattformen gewährleisten kann. Denken Sie bei Verwendung dieser Funktion unbedingt an die Konsequenzen, die sich aus der Deaktivierung der Schriftarteneinbettung ergeben. Entdecken Sie gerne weitere Funktionen von Aspose.Words für .NET, um die Erstellung Ihrer PDF-Dateien zu optimieren.

### Häufig gestellte Fragen

#### F: Was bedeutet das Deaktivieren der Einbettung der Schriftarten Arial und Times Roman in ein PDF-Dokument und warum ist das wichtig?
A: Wenn Sie die Einbettung der Schriftarten Arial und Times Roman in einem PDF-Dokument deaktivieren, werden diese Schriftarten nicht in die generierte PDF-Datei aufgenommen. Dies kann wichtig sein, um die Größe der PDF-Datei zu reduzieren, indem die Einbindung von Schriftarten vermieden wird, die bereits allgemein in PDF-Lesesystemen verfügbar sind. Es kann auch dazu beitragen, eine bessere Kompatibilität und ein einheitliches Erscheinungsbild des PDF-Dokuments auf verschiedenen Geräten und Plattformen sicherzustellen.

#### F: Wie kann ich Aspose.Words für .NET so konfigurieren, dass die Schriftarten Arial und Times Roman nicht in ein PDF-Dokument eingebettet werden?
A: Um Aspose.Words für .NET so zu konfigurieren, dass die Schriftarten Arial und Times Roman nicht in ein PDF-Dokument eingebettet werden, befolgen Sie diese Schritte:

 Legen Sie den Verzeichnispfad fest, in dem sich Ihre Dokumente befinden, indem Sie ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad Ihres Dokumentverzeichnisses.

 Laden Sie das zu verarbeitende Dokument mit dem`Document` Klasse und dem angegebenen Dokumentpfad.

 Erstellen Sie eine Instanz des`PdfSaveOptions` Klasse und legen Sie die`FontEmbeddingMode`Eigentum an`PdfFontEmbeddingMode.EmbedAll`. Dadurch werden alle Schriftarten außer Arial und Times Roman in die generierte PDF-Datei eingebettet.

 Verwenden Sie die`Save` Methode der`Document` Objekt, um das Dokument im PDF-Format zu speichern und dabei die zuvor konfigurierten Speicheroptionen anzugeben.

#### F: Welche Vorteile bietet das Deaktivieren der Einbettung der Schriftarten Arial und Times Roman in einem PDF-Dokument?
A: Das Deaktivieren der Einbettung von Arial- und Times Roman-Schriftarten in ein PDF-Dokument bietet folgende Vorteile:

Reduzierung der PDF-Dateigröße: Durch den Verzicht auf die Einbettung allgemein verfügbarer Schriftarten wie Arial und Times Roman kann die PDF-Dateigröße reduziert werden, was das Speichern, Teilen und Übertragen von Dateien erleichtert.

Bessere Kompatibilität: Durch die Verwendung von Schriftarten, die auf PDF-Lesesystemen allgemein verfügbar sind, gewährleisten Sie eine bessere Kompatibilität und ein besseres Erscheinungsbild des Dokuments auf verschiedenen Geräten und Plattformen.

#### F: Welche Konsequenzen hat es, wenn ich die Einbettung der Schriftarten Arial und Times Roman in einem PDF-Dokument deaktiviere?
A: Das Deaktivieren der Einbettung der Schriftarten Arial und Times Roman in einem PDF-Dokument hat folgende Folgen:

Anderes Erscheinungsbild: Wenn die Schriftarten Arial und Times Roman auf dem System, auf dem die PDF-Datei geöffnet wird, nicht verfügbar sind, werden Ersatzschriften verwendet, was zu einem anderen Erscheinungsbild als beabsichtigt führen kann.

Probleme mit der Lesbarkeit: Die verwendeten Ersatzschriftarten sind möglicherweise nicht so gut lesbar wie die Originalschriftarten, was die Lesbarkeit des Dokuments beeinträchtigen kann.