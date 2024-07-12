---
title: Einbetten von Teilmengen von Schriftarten in PDF-Dokumente
linktitle: Einbetten von Teilmengen von Schriftarten in PDF-Dokumente
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Einbetten von Schriftart-Teilmengen in ein PDF-Dokument mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/embedded-subset-fonts/
---

Dieser Artikel enthält eine Schritt-für-Schritt-Anleitung zur Verwendung der Funktion zum Einbetten von Schriftart-Teilmengen mit Aspose.Words für .NET. Wir werden jeden Teil des Codes im Detail erklären. Am Ende dieses Tutorials werden Sie wissen, wie Sie Schriftart-Teilmengen in ein Dokument einbetten und ein PDF generieren, das nur die im Dokument verwendeten Glyphen enthält.

Stellen Sie vor dem Start sicher, dass Sie die Aspose.Words für .NET-Bibliothek in Ihrem Projekt installiert und konfiguriert haben. Sie finden die Bibliothek und Installationsanweisungen auf der Aspose-Website.

## Schritt 1: Dokumentverzeichnis festlegen

 Zunächst müssen Sie den Pfad zum Verzeichnis angeben, in dem sich Ihre Dokumente befinden. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Dokument hochladen

Als nächstes müssen wir das Dokument laden, das wir verarbeiten möchten. In diesem Beispiel gehen wir davon aus, dass das Dokument „Rendering.docx“ heißt und sich im angegebenen Dokumentenverzeichnis befindet.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Schritt 3: Konfigurieren Sie die Optionen zum Speichern als PDF

 Um ein PDF zu erstellen, das nur die Teilmengen der im Dokument verwendeten Schriftarten enthält, müssen wir die`PdfSaveOptions` Objekt mit dem`EmbedFullFonts` Eigenschaft festgelegt auf`false`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
```

## Schritt 4: Dokument als PDF mit Schriftuntergruppen speichern

 Abschließend können wir das Dokument unter Verwendung der Schriftuntergruppen als PDF speichern. Geben Sie den Ausgabedateinamen und die`saveOptions` Objekt, das wir im vorherigen Schritt konfiguriert haben.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);
```

Das ist alles! Sie haben erfolgreich Teilmengen von Schriftarten in ein Dokument eingebettet und mit Aspose.Words für .NET ein PDF generiert, das nur die im Dokument verwendeten Glyphen enthält.

### Beispielquellcode zum Einbetten von Schriftart-Subsets mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Das Ausgabe-PDF enthält Teilmengen der Schriftarten im Dokument.
	// In den PDF-Schriftarten sind nur die im Dokument verwendeten Glyphen enthalten.
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);

```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET Schriftuntergruppen in ein PDF-Dokument einbettet. Das Einbetten von Schriftuntergruppen hilft, die Größe der PDF-Datei zu reduzieren und gleichzeitig das Erscheinungsbild des Dokuments beizubehalten, indem nur die tatsächlich verwendeten Zeichen verwendet werden. Dies gewährleistet eine bessere Kompatibilität und Leistung beim Anzeigen und Drucken der PDF-Datei. Erkunden Sie die Funktionen von Aspose.Words für .NET weiter, um die Generierung Ihrer PDF-Dokumente mit eingebetteten Schriftuntergruppen zu optimieren.

### Häufig gestellte Fragen

#### F: Was bedeutet das Einbetten von Schriftart-Teilmengen in ein PDF-Dokument?
A: Beim Einbetten von Schriftuntergruppen in ein PDF-Dokument werden nur die im Dokument verwendeten Glyphen und nicht alle vollständigen Schriftarten einbezogen. Dadurch wird die Größe der PDF-Datei reduziert, da nur die Schriftdaten einbezogen werden, die zur Anzeige der tatsächlich im Dokument verwendeten Zeichen erforderlich sind.

#### F: Was ist der Unterschied zwischen dem Einbetten vollständiger Schriftarten und dem Einbetten von Schriftartenteilmengen?
A: Vollständige Schriftarteinbettung bedeutet, dass alle im Dokument verwendeten Schriftarten in die PDF-Datei aufgenommen werden. Dadurch wird sichergestellt, dass das Dokument genau so angezeigt wird, wie es entworfen wurde. Die Größe der PDF-Datei kann jedoch zunehmen. Im Gegensatz dazu enthält die Einbettung von Schriftartuntergruppen nur die im Dokument verwendeten Glyphen. Dadurch wird die Größe der PDF-Datei reduziert, die Möglichkeit, das Erscheinungsbild des Dokuments exakt zu reproduzieren, wenn später zusätzliche Zeichen hinzugefügt werden, ist jedoch eingeschränkt.

#### F: Wie kann ich mit Aspose.Words für .NET Schriftarten-Teilmengen in ein PDF-Dokument einbetten?
A: Um Schriftarten-Teilmengen mit Aspose.Words für .NET in ein PDF-Dokument einzubetten, folgen Sie diesen Schritten:

 Legen Sie den Dokumentverzeichnispfad fest, indem Sie`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad Ihres Dokumentverzeichnisses.

 Laden Sie das zu verarbeitende Dokument mit dem`Document` Klasse und der Dokumentpfad.

 Konfigurieren Sie PDF-Speicheroptionen, indem Sie eine Instanz des`PdfSaveOptions` Klasse und Festlegen der`EmbedFullFonts`Eigentum an`false`Dadurch wird sichergestellt, dass nur die im Dokument verwendeten Schriftartenuntergruppen in die PDF-Datei aufgenommen werden.

 Speichern Sie das Dokument im PDF-Format mit den eingebetteten Schriftuntergruppen mithilfe des`Save` Methode der`Document` Objekt, das den Namen der Ausgabedatei und die zuvor konfigurierten Speicheroptionen angibt.

#### F: Welche Vorteile bietet das Einbetten von Schriftarten-Untergruppen in ein PDF-Dokument?
A: Das Einbetten von Schriftarten-Untergruppen in ein PDF-Dokument bietet folgende Vorteile:

Reduzierte PDF-Dateigröße: Durch die Einbeziehung nur der im Dokument verwendeten Glyphen wird die PDF-Dateigröße im Vergleich zum Einbetten vollständiger Schriftarten reduziert.

Beibehaltung des Erscheinungsbilds des Dokuments: Die in der PDF-Datei enthaltenen Schriftarten-Untermengen ermöglichen es, das Erscheinungsbild des Dokuments nur mit den tatsächlich verwendeten Zeichen zu reproduzieren.

Kompatibilität mit den Einschränkungen der Lizenz: Das Einbetten von Schriftarten-Teilmengen kann in Fällen vorzuziehen sein, in denen vollständige Schriftarten aufgrund von Lizenzbeschränkungen nicht legal eingebettet werden können.