---
title: Reduzieren Sie die PDF-Größe, indem Sie WMF-Schriftarten auf Metadateigröße skalieren
linktitle: Reduzieren Sie die PDF-Größe, indem Sie WMF-Schriftarten auf Metadateigröße skalieren
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Reduzieren der PDF-Größe durch Skalieren von WMF-Schriftarten auf Metadateigröße bei der Konvertierung in PDF mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/scale-wmf-fonts-to-metafile-size/
---

Dieser Artikel enthält eine Schritt-für-Schritt-Anleitung zum Reduzieren der PDF-Größe mit der Funktion zum Skalieren von WMF-Schriftarten auf Metadateigröße mit Aspose.Words für .NET. Wir werden jeden Teil des Codes im Detail erklären. Am Ende dieses Tutorials werden Sie wissen, wie Sie die Skalierung von WMF-Schriftarten beim Konvertieren in PDF aktivieren oder deaktivieren.

Stellen Sie vor dem Start sicher, dass Sie die Aspose.Words für .NET-Bibliothek in Ihrem Projekt installiert und konfiguriert haben. Sie finden die Bibliothek und Installationsanweisungen auf der Aspose-Website.

## Schritt 1: Dokumentverzeichnis festlegen

 Zunächst müssen Sie den Pfad zum Verzeichnis angeben, in dem sich Ihre Dokumente befinden. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Dokument hochladen

Als nächstes müssen wir das zu verarbeitende Dokument laden. In diesem Beispiel gehen wir davon aus, dass das Dokument „WMF mit Text.docx“ heißt und sich im angegebenen Dokumentenverzeichnis befindet.

```csharp
Document doc = new Document(dataDir + "WMF with text.docx");
```

## Schritt 3: Konfigurieren von Optionen für das Metadatei-Rendering

 Um die Skalierung von WMF-Schriftarten auf die Größe der Metadatei zu aktivieren oder zu deaktivieren, müssen wir Folgendes konfigurieren:`MetafileRenderingOptions` Objekt. In diesem Beispiel deaktivieren wir die Schriftskalierung, indem wir den`ScaleWmfFontsToMetafileSize`Eigentum an`false`.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     ScaleWmfFontsToMetafileSize=false
};
```

## Schritt 4: Konfigurieren Sie die Optionen zum Speichern als PDF mit Optionen zum Rendern von Metadateien

Schließlich können wir die Optionen zum Speichern als PDF mithilfe der zuvor konfigurierten Optionen zum Rendern der Metadatei konfigurieren.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };
```

## Schritt 5: Dokument als PDF mit Metadatei-Rendering-Optionen speichern

Speichern Sie das Dokument im PDF-Format mit den zuvor konfigurierten Speicheroptionen.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
```

Das ist alles! Sie haben die Skalierung der WMF-Schriftart auf Metadateigröße beim Konvertieren erfolgreich aktiviert oder deaktiviert.

ein PDF-Dokument mit Aspose.Words für .NET.

### Beispielquellcode zum Skalieren von WMF-Schriftarten auf Metadateigröße mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with text.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		ScaleWmfFontsToMetafileSize = false
	};

	//Wenn Aspose.Words einige der Metadatei-Datensätze nicht korrekt in Vektorgrafiken umwandeln kann
	// dann rendert Aspose.Words diese Metadatei in eine Bitmap.
	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
	
        
```

## Abschluss

In diesem Tutorial haben wir erklärt, wie Sie die Größenanpassung von WMF-Schriftarten an die Metadateigröße in einem PDF-Dokument mit Aspose.Words für .NET aktivieren oder deaktivieren. Indem Sie die beschriebenen Schritte befolgen, können Sie ganz einfach steuern, ob die Größe von WMF-Schriftarten beim Konvertieren in ein PDF-Dokument an die Metadateigröße angepasst werden soll. Dies kann Ihnen helfen, die Größe der generierten PDF-Datei zu reduzieren und die Rendering-Leistung zu verbessern. Geben Sie unbedingt den richtigen Pfad zu Ihren Dokumenten an und konfigurieren Sie die Metadatei-Rendering-Optionen nach Bedarf.

### Häufig gestellte Fragen

#### F: Was bedeutet die Größenanpassung von WMF-Schriftarten auf Metadateigröße in einem PDF-Dokument?
A: Die Größenanpassung von WMF-Schriftarten an die Metadateigröße in einem PDF-Dokument ist eine Funktion, die steuert, ob WMF-Schriftarten bei der Konvertierung in ein PDF-Dokument an die Größe der Metadatei angepasst werden sollen. Wenn diese Funktion aktiviert ist, werden WMF-Schriftarten an die Größe der Metadatei angepasst, wodurch die Größe des generierten PDF-Dokuments verringert werden kann.

#### F: Wie kann ich Aspose.Words für .NET verwenden, um die Größenanpassung von WMF-Schriftarten auf Metadateigröße in einem PDF-Dokument zu aktivieren oder zu deaktivieren?
A: Um die Größenanpassung von WMF-Schriftarten auf Metadateigröße in einem PDF-Dokument mit Aspose.Words für .NET zu aktivieren oder zu deaktivieren, führen Sie die folgenden Schritte aus:

 Legen Sie den Verzeichnispfad fest, in dem sich Ihre Dokumente befinden, indem Sie ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad Ihres Dokumentverzeichnisses.

 Laden Sie das zu verarbeitende Dokument mit dem`Document` Klasse und geben Sie den Pfad zum Word-Dokument im angegebenen Dokumentverzeichnis an.

 Konfigurieren Sie die Rendering-Optionen für Metadateien, indem Sie eine Instanz des`MetafileRenderingOptions` Klasse und Festlegen der`ScaleWmfFontsToMetafileSize`Eigentum an`true` um die Skalierung von WMF-Schriftarten auf Metadateigröße zu ermöglichen oder`false` um diese Funktion zu deaktivieren.

 Konfigurieren Sie die Optionen zum Speichern als PDF, indem Sie eine Instanz des`PdfSaveOptions` -Klasse und unter Verwendung der zuvor konfigurierten Optionen zur Metadateiwiedergabe.

 Speichern Sie das Dokument im PDF-Format mit dem`Save` Methode der`Document` Klasse, die den Pfad und die Speicheroptionen angibt.

#### F: Welche Vorteile bietet die Größenanpassung von WMF-Schriftarten auf Metadateigröße in einem PDF-Dokument?
A: Die Vorteile der Größenanpassung von WMF-Schriftarten auf Metadateigröße in einem PDF-Dokument sind:

Reduzierung der PDF-Dateigröße: Durch die Größenanpassung von WMF-Schriftarten an die Metadateigröße kann die Größe des generierten PDF-Dokuments reduziert werden, indem die Schriftgröße an die Anforderungen der Metadatei angepasst wird.

Verbesserte Leistung: Durch die Anpassung der Größe von WMF-Schriftarten an die Abmessungen der Metadatei kann das Rendern des PDF-Dokuments schneller und effizienter erfolgen.