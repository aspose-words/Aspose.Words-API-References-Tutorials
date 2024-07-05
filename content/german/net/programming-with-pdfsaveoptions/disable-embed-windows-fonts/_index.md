---
title: Reduzieren Sie die PDF-Größe, indem Sie eingebettete Schriftarten deaktivieren
linktitle: Reduzieren Sie die PDF-Größe, indem Sie eingebettete Schriftarten deaktivieren
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie die PDF-Größe reduzieren, indem Sie die Einbettung von Windows-Schriftarten deaktivieren, wenn Sie Dokumente mit Aspose.Words für .NET in PDF konvertieren.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/disable-embed-windows-fonts/
---

In diesem Tutorial führen wir Sie durch die Schritte zum Reduzieren der PDF-Größe durch Deaktivieren der Windows-Schriftarteneinbettung in einem PDF-Dokument mit Aspose.Words für .NET. Durch Deaktivieren der Schriftarteneinbettung können Sie die Größe der generierten PDF-Datei reduzieren. Befolgen Sie die folgenden Schritte:

## Schritt 1: Dokument einlegen

Beginnen Sie mit dem Hochladen des Dokuments, das Sie in PDF konvertieren möchten:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Achten Sie darauf, den richtigen Pfad zu Ihrem Dokument anzugeben.

## Schritt 2: PDF-Speicheroptionen festlegen

Erstellen Sie eine Instanz der Klasse PdfSaveOptions und geben Sie an, wie Schriftarten eingebettet werden:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
```

Mit dieser Option können Sie die Einbindung von Windows-Schriftarten in die erzeugte PDF-Datei deaktivieren.

## Schritt 3: Dokument in PDF konvertieren

 Verwenden Sie die`Save` Methode zum Konvertieren des Dokuments in PDF unter Angabe der Konvertierungsoptionen:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);
```

Stellen Sie sicher, dass Sie den richtigen Pfad zum Speichern der konvertierten PDF-Datei angeben.

### Beispielquellcode zum Deaktivieren des Einbettens von Windows-Schriftarten mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zum Deaktivieren der Einbettung von Windows-Schriftarten in ein PDF-Dokument mit Aspose.Words für .NET:

```csharp

	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Das Ausgabe-PDF wird ohne Einbettung von Standard-Windows-Schriftarten gespeichert.
	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);

```
Indem Sie diese Schritte befolgen, können Sie die Einbettung von Windows-Schriftarten in ein PDF-Dokument mit Aspose.Words für .NET ganz einfach deaktivieren.


## Abschluss

In diesem Tutorial haben wir gelernt, wie Sie die Größe einer PDF-Datei reduzieren können, indem Sie die Einbettung von Windows-Schriftarten mithilfe von Aspose.Words für .NET deaktivieren. Durch Deaktivieren der Schriftarteinbettung können Sie die Größe der generierten PDF-Datei reduzieren und so das Speichern, Teilen und Übertragen von Dateien erleichtern. Es ist jedoch wichtig zu beachten, dass das Deaktivieren der Windows-Schriftarteinbettung zu Änderungen des Erscheinungsbilds und der Formatierung im endgültigen PDF-Dokument führen kann. Berücksichtigen Sie diese Konsequenzen unbedingt, wenn Sie diese Funktion verwenden. Entdecken Sie gerne weitere Funktionen von Aspose.Words für .NET, um die Generierung Ihrer PDF-Dateien zu optimieren.

### Häufig gestellte Fragen

#### F: Was bedeutet das Deaktivieren der Einbettung von Windows-Schriftarten in ein PDF-Dokument und warum ist das wichtig?
A: Durch das Deaktivieren der Einbettung von Windows-Schriftarten in ein PDF-Dokument wird verhindert, dass Windows-Schriftarten in die generierte PDF-Datei aufgenommen werden. Dadurch wird die Größe der PDF-Datei reduziert, indem eingebettete Windows-Schriftartendaten entfernt werden. Dies kann wichtig sein, um die Größe von PDF-Dateien zu reduzieren, wodurch sie einfacher gespeichert, freigegeben und schneller übertragen werden können.

#### F: Wie kann ich die Einbettung von Windows-Schriftarten in ein PDF-Dokument mit Aspose.Words für .NET deaktivieren?
A: Um das Einbetten von Windows-Schriftarten in ein PDF-Dokument mit Aspose.Words für .NET zu deaktivieren, gehen Sie folgendermaßen vor:

 Laden Sie das Dokument, das Sie in PDF konvertieren möchten, mit dem`Document` Klasse und Dokumentpfad.

 Erstellen Sie eine Instanz des`PdfSaveOptions` Klasse und legen Sie die`FontEmbeddingMode`Eigentum an`PdfFontEmbeddingMode.EmbedNone`Dadurch wird die Einbettung von Windows-Schriftarten in die generierte PDF-Datei deaktiviert.

 Verwenden Sie die`Save` Methode der`Document` Objekt zum Konvertieren des Dokuments in PDF unter Angabe der zuvor konfigurierten Konvertierungsoptionen.

#### F: Welche Vorteile bietet das Deaktivieren der Einbettung von Windows-Schriftarten in einem PDF-Dokument?
A: Das Deaktivieren der Einbettung von Windows-Schriftarten in ein PDF-Dokument bietet folgende Vorteile:

Reduzierte PDF-Dateigröße: Durch Deaktivieren der Windows-Schriftarteneinbettung werden eingebettete Windows-Schriftartendaten entfernt, wodurch die Größe der generierten PDF-Datei reduziert wird.

Einfachere Speicherung: Kleinere PDF-Dateien lassen sich einfacher speichern und übertragen.

Schnelleres Teilen und Übertragen: Kleinere PDF-Dateien können schneller geteilt und übertragen werden, was Zeit und Ressourcen spart.

#### F: Welche Konsequenzen hat es, wenn ich die Einbettung von Windows-Schriftarten in einem PDF-Dokument deaktiviere?
A: Das Deaktivieren der Einbettung von Windows-Schriftarten in ein PDF-Dokument kann folgende Konsequenzen haben:

Verlust von Erscheinungsbild und Formatierung: Wenn die im Dokument angegebenen Windows-Schriftarten auf dem System, auf dem die PDF-Datei geöffnet wird, nicht verfügbar sind, werden Ersatzschriftarten verwendet. Dies kann zu einem falschen Erscheinungsbild und einer falschen Formatierung führen, d. h. zu einer anderen Form als erwartet.

Lesbarkeitsprobleme: Wenn die verwendeten Ersatzschriften nicht so gut lesbar sind wie die Originalschriften, kann dies die Lesbarkeit des Textes im PDF-Dokument beeinträchtigen.