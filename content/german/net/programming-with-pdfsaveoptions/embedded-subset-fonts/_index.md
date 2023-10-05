---
title: Teilmenge von Schriftarten in PDF-Dokument einbetten
linktitle: Teilmenge von Schriftarten in PDF-Dokument einbetten
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Einbetten von Schriftartteilmengen in ein PDF-Dokument mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/embedded-subset-fonts/
---

Dieser Artikel enthält eine Schritt-für-Schritt-Anleitung zur Verwendung der Funktion zum Einbetten von Schriftartteilmengen mit Aspose.Words für .NET. Wir werden jeden Teil des Codes im Detail erklären. Am Ende dieses Tutorials werden Sie verstehen, wie Sie Teilsätze von Schriftarten in ein Dokument einbetten und eine PDF-Datei erstellen, die nur die im Dokument verwendeten Glyphen enthält.

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

## Schritt 3: Konfigurieren Sie die Optionen zum Speichern als PDF

 Um eine PDF-Datei zu erstellen, die nur die Teilmengen der im Dokument verwendeten Schriftarten enthält, müssen wir die konfigurieren`PdfSaveOptions` Objekt mit dem`EmbedFullFonts` Eigenschaft festgelegt auf`false`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
```

## Schritt 4: Dokument als PDF mit Schriftart-Untergruppen speichern

 Schließlich können wir das Dokument mithilfe der Schriftarten-Untergruppen als PDF speichern. Geben Sie den Namen der Ausgabedatei und die Datei an`saveOptions` Objekt, das wir im vorherigen Schritt konfiguriert haben.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);
```

Das ist alles ! Sie haben Teilsätze von Schriftarten erfolgreich in ein Dokument eingebettet und mit Aspose.Words für .NET eine PDF-Datei generiert, die nur die im Dokument verwendeten Glyphen enthält.

### Beispielquellcode zum Einbetten von Schriftartteilmengen mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Die Ausgabe-PDF enthält Teilmengen der Schriftarten im Dokument.
	// In den PDF-Schriftarten sind nur die im Dokument verwendeten Glyphen enthalten.
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);

```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET Schriftartteilmengen in ein PDF-Dokument einbettet. Das Einbetten von Teilsätzen von Schriftarten trägt dazu bei, die Größe der PDF-Datei zu reduzieren und gleichzeitig das Erscheinungsbild des Dokuments beizubehalten, indem nur die tatsächlich verwendeten Zeichen verwendet werden. Dies sorgt für eine bessere Kompatibilität und Leistung beim Anzeigen und Drucken des PDFs. Erkunden Sie die Funktionen von Aspose.Words für .NET weiter, um die Generierung Ihrer PDF-Dokumente mit eingebetteten Schriftart-Teilsätzen zu optimieren.

### Häufig gestellte Fragen

#### F: Was bedeutet das Einbetten von Schriftartteilmengen in ein PDF-Dokument?
A: Beim Einbetten von Schriftartteilsätzen in ein PDF-Dokument werden nur die im Dokument verwendeten Glyphen einbezogen, nicht alle vollständigen Schriftarten. Dadurch wird die Größe der PDF-Datei reduziert, da nur die Schriftartdaten einbezogen werden, die zur Anzeige der tatsächlich im Dokument verwendeten Zeichen erforderlich sind.

#### F: Was ist der Unterschied zwischen dem Einbetten vollständiger Schriftarten und dem Einbetten von Teilsätzen von Schriftarten?
A: Vollständige Schriftarteneinbettung bedeutet, dass alle im Dokument verwendeten Schriftarten in die PDF-Datei einbezogen werden. Dadurch wird sichergestellt, dass das Dokument genau so angezeigt wird, wie es entworfen wurde, die Größe der PDF-Datei kann jedoch zunehmen. Im Gegensatz dazu enthält das Einbetten von Schriftartteilsätzen nur die im Dokument verwendeten Glyphen, wodurch sich die Größe der PDF-Datei verringert, aber die Möglichkeit, das Aussehen des Dokuments genau zu reproduzieren, eingeschränkt wird, wenn später zusätzliche Zeichen hinzugefügt werden.

#### F: Wie kann ich mit Aspose.Words für .NET Schriftartteilmengen in ein PDF-Dokument einbetten?
A: Um Schriftartteilmengen mithilfe von Aspose.Words für .NET in ein PDF-Dokument einzubetten, führen Sie die folgenden Schritte aus:

 Legen Sie den Dokumentverzeichnispfad durch Ersetzen fest`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad Ihres Dokumentenverzeichnisses.

 Laden Sie das Dokument, das Sie bearbeiten möchten, mit`Document` Klasse und den Dokumentpfad.

 Konfigurieren Sie PDF-Speicheroptionen, indem Sie eine Instanz davon erstellen`PdfSaveOptions` Klasse und Einstellung der`EmbedFullFonts`Eigentum zu`false`Dadurch wird sichergestellt, dass nur die im Dokument verwendeten Schriftarten-Untergruppen in die PDF-Datei aufgenommen werden.

 Speichern Sie das Dokument im PDF-Format mit den mithilfe von eingebetteten Schriftartteilsätzen`Save` Methode der`Document` -Objekt unter Angabe des Namens der Ausgabedatei und der zuvor konfigurierten Speicheroptionen.

#### F: Welche Vorteile bietet das Einbetten von Schriftartteilmengen in ein PDF-Dokument?
A: Das Einbetten von Schriftartteilmengen in ein PDF-Dokument bietet folgende Vorteile:

Reduzierte PDF-Dateigröße: Durch die Einbeziehung nur der im Dokument verwendeten Glyphen wird die PDF-Dateigröße im Vergleich zum Einbetten vollständiger Schriftarten reduziert.

Beibehaltung des Erscheinungsbilds des Dokuments: Die in der PDF-Datei enthaltenen Teilsätze der Schriftarten ermöglichen es, das Erscheinungsbild des Dokuments nur mit den tatsächlich verwendeten Zeichen zu reproduzieren.

Kompatibilität mit den Lizenzbeschränkungen: Das Einbetten von Teilsätzen von Schriftarten kann in Fällen bevorzugt werden, in denen vollständige Schriftarten aufgrund von Lizenzbeschränkungen nicht legal eingebettet werden können.