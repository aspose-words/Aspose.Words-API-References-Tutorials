---
title: Reduzieren Sie die PDF-Größe, indem Sie eingebettete Schriftarten deaktivieren
linktitle: Reduzieren Sie die PDF-Größe, indem Sie eingebettete Schriftarten deaktivieren
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie die PDF-Größe reduzieren, indem Sie die Einbettung von Windows-Schriftarten deaktivieren, wenn Sie Dokumente mit Aspose.Words für .NET in PDF konvertieren.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/disable-embed-windows-fonts/
---

In diesem Tutorial führen wir Sie durch die Schritte zum Reduzieren der PDF-Größe und Deaktivieren der Einbettung von Windows-Schriftarten in ein PDF-Dokument mit Aspose.Words für .NET. Durch Deaktivieren der Schriftarteinbettung können Sie die Größe der generierten PDF-Datei reduzieren. Folgen Sie den unteren Schritten:

## Schritt 1: Laden des Dokuments

Laden Sie zunächst das Dokument hoch, das Sie in PDF konvertieren möchten:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Stellen Sie sicher, dass Sie den korrekten Pfad zu Ihrem Dokument angeben.

## Schritt 2: PDF-Speicheroptionen festlegen

Erstellen Sie eine Instanz der PdfSaveOptions-Klasse und geben Sie an, wie Schriftarten eingebettet werden sollen:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
```

Mit dieser Option können Sie die Integration von Windows-Schriftarten in der generierten PDF-Datei deaktivieren.

## Schritt 3: Dokument in PDF konvertieren

 Benutzen Sie die`Save` Methode zum Konvertieren des Dokuments in PDF unter Angabe der Konvertierungsoptionen:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);
```

Stellen Sie sicher, dass Sie den richtigen Pfad zum Speichern der konvertierten PDF-Datei angeben.

### Beispielquellcode für die Deaktivierung der Einbettung von Windows-Schriftarten mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zum Deaktivieren der Einbettung von Windows-Schriftarten in ein PDF-Dokument mit Aspose.Words für .NET:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Das Ausgabe-PDF wird ohne Einbettung von Standard-Windows-Schriftarten gespeichert.
	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);

```
Wenn Sie diese Schritte befolgen, können Sie die Einbettung von Windows-Schriftarten in ein PDF-Dokument mit Aspose.Words für .NET ganz einfach deaktivieren.


## Abschluss

In diesem Tutorial haben wir gelernt, wie man die Größe einer PDF-Datei reduziert, indem man die Einbettung von Windows-Schriftarten mit Aspose.Words für .NET deaktiviert. Durch Deaktivieren der Schriftarteinbettung können Sie die Größe der generierten PDF-Datei reduzieren und so das Speichern, Teilen und Übertragen von Dateien vereinfachen. Es ist jedoch wichtig zu beachten, dass die Deaktivierung der Windows-Schriftarteinbettung zu Änderungen im Aussehen und in der Formatierung des endgültigen PDF-Dokuments führen kann. Berücksichtigen Sie unbedingt diese Konsequenzen, wenn Sie diese Funktion verwenden. Entdecken Sie gerne weitere Funktionen von Aspose.Words für .NET, um die Generierung Ihrer PDF-Dateien zu optimieren.

### Häufig gestellte Fragen

#### F: Was bedeutet die Deaktivierung der Einbettung von Windows-Schriftarten in ein PDF-Dokument und warum ist das wichtig?
A: Durch das Deaktivieren der Einbettung von Windows-Schriftarten in ein PDF-Dokument wird verhindert, dass Windows-Schriftarten in die generierte PDF-Datei einbezogen werden. Dadurch wird die Größe der PDF-Datei reduziert, indem eingebettete Windows-Schriftartdaten entfernt werden. Dies kann wichtig sein, um die Größe von PDF-Dateien zu reduzieren, wodurch sie einfacher gespeichert, geteilt und schneller übertragen werden können.

#### F: Wie kann ich die Einbettung von Windows-Schriftarten in ein PDF-Dokument mit Aspose.Words für .NET deaktivieren?
A: Um das Einbetten von Windows-Schriftarten in ein PDF-Dokument mit Aspose.Words für .NET zu deaktivieren, gehen Sie folgendermaßen vor:

 Laden Sie das Dokument, das Sie in PDF konvertieren möchten, mit`Document` Klasse und Dokumentpfad.

 Erstellen Sie eine Instanz von`PdfSaveOptions` Klasse und legen Sie die fest`FontEmbeddingMode` Eigentum zu`PdfFontEmbeddingMode.EmbedNone`. Dadurch wird die Einbettung von Windows-Schriftarten in die generierte PDF-Datei deaktiviert.

 Benutzen Sie die`Save` Methode der`Document` Objekt zum Konvertieren des Dokuments in PDF unter Angabe der zuvor konfigurierten Konvertierungsoptionen.

#### F: Welche Vorteile bietet es, die Einbettung von Windows-Schriftarten in einem PDF-Dokument zu deaktivieren?
A: Die Deaktivierung der Einbettung von Windows-Schriftarten in ein PDF-Dokument bietet folgende Vorteile:

Reduzierte PDF-Dateigröße: Durch Deaktivieren der Windows-Schriftarteinbettung werden eingebettete Windows-Schriftartdaten entfernt, wodurch die Größe der generierten PDF-Datei verringert wird.

Einfachere Speicherung: Kleinere PDF-Dateien lassen sich einfacher speichern, speichern und übertragen.

Schnelleres Teilen und Übertragen: Kleinere PDF-Dateien können schneller geteilt und übertragen werden, was Zeit und Ressourcen spart.

#### F: Welche Konsequenzen hat es, wenn die Einbettung von Windows-Schriftarten in einem PDF-Dokument deaktiviert wird?
A: Das Deaktivieren der Einbettung von Windows-Schriftarten in ein PDF-Dokument kann folgende Konsequenzen haben:

Verlust von Darstellung und Formatierung: Wenn die im Dokument angegebenen Windows-Schriftarten auf dem System, auf dem die PDF-Datei geöffnet wird, nicht verfügbar sind, werden Ersatzschriftarten verwendet, was zu einer falschen Darstellung und Formatierung führen kann. in der Form anders als erwartet.

Probleme mit der Lesbarkeit: Wenn die verwendeten Ersatzschriftarten nicht so gut lesbar sind wie die Originalschriftarten, kann dies die Lesbarkeit des Textes im PDF-Dokument beeinträchtigen.