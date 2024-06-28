---
title: Reduzieren Sie die PDF-Größe, indem Sie WMF-Schriftarten auf Metadateigröße skalieren
linktitle: Reduzieren Sie die PDF-Größe, indem Sie WMF-Schriftarten auf Metadateigröße skalieren
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Reduzieren der PDF-Größe durch Skalieren von WMF-Schriftarten auf Metadateigröße bei der Konvertierung in PDF mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/scale-wmf-fonts-to-metafile-size/
---

Dieser Artikel enthält eine Schritt-für-Schritt-Anleitung zum Reduzieren der PDF-Größe mit der Funktion „WMF-Schriftarten auf Metadateigröße skalieren“ mit Aspose.Words für .NET. Wir werden jeden Teil des Codes im Detail erklären. Am Ende dieses Tutorials erfahren Sie, wie Sie die WMF-Schriftskalierung beim Konvertieren in PDF aktivieren oder deaktivieren.

Bevor Sie beginnen, stellen Sie sicher, dass Sie die Aspose.Words für .NET-Bibliothek in Ihrem Projekt installiert und konfiguriert haben. Die Bibliothek und Installationsanweisungen finden Sie auf der Aspose-Website.

## Schritt 1: Definieren Sie das Dokumentenverzeichnis

 Zunächst müssen Sie den Pfad zu dem Verzeichnis definieren, in dem sich Ihre Dokumente befinden. Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument hoch

Als nächstes müssen wir das Dokument laden, das wir verarbeiten möchten. In diesem Beispiel gehen wir davon aus, dass das Dokument „WMF with text.docx“ heißt und sich im angegebenen Dokumentenverzeichnis befindet.

```csharp
Document doc = new Document(dataDir + "WMF with text.docx");
```

## Schritt 3: Konfigurieren Sie die Metadatei-Rendering-Optionen

 Um die WMF-Schriftskalierung auf die Metadateigröße zu aktivieren oder zu deaktivieren, müssen wir Folgendes konfigurieren`MetafileRenderingOptions` Objekt. In diesem Beispiel deaktivieren wir die Schriftskalierung, indem wir die festlegen`ScaleWmfFontsToMetafileSize`Eigentum zu`false`.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     ScaleWmfFontsToMetafileSize=false
};
```

## Schritt 4: Konfigurieren Sie die Optionen zum Speichern als PDF mit Metadatei-Rendering-Optionen

Schließlich können wir die Optionen zum Speichern in PDF mithilfe der zuvor konfigurierten Metadatei-Rendering-Optionen konfigurieren.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };
```

## Schritt 5: Speichern Sie das Dokument als PDF mit Metadatei-Rendering-Optionen

Speichern Sie das Dokument im PDF-Format mit den zuvor konfigurierten Speicheroptionen.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
```

Das ist alles ! Sie haben die Skalierung der WMF-Schriftarten auf die Metadateigröße beim Konvertieren erfolgreich aktiviert oder deaktiviert

ein PDF-Dokument mit Aspose.Words für .NET.

### Beispielquellcode zum Skalieren von WMF-Schriftarten auf Metadateigröße mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with text.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		ScaleWmfFontsToMetafileSize = false
	};

	//Wenn Aspose.Words einige der Metadateidatensätze nicht korrekt in Vektorgrafiken rendern kann
	// dann rendert Aspose.Words diese Metadatei in eine Bitmap.
	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
	
        
```

## Abschluss

In diesem Tutorial haben wir erklärt, wie Sie die Größenänderung von WMF-Schriftarten an die Metadateigröße in einem PDF-Dokument mit Aspose.Words für .NET aktivieren oder deaktivieren. Durch Befolgen der beschriebenen Schritte können Sie ganz einfach steuern, ob die Größe von WMF-Schriftarten beim Konvertieren in ein PDF-Dokument an die Metadateigröße angepasst werden soll. Dadurch können Sie die Größe der generierten PDF-Datei reduzieren und die Rendering-Leistung verbessern. Stellen Sie sicher, dass Sie den richtigen Pfad zu Ihren Dokumenten angeben und die Metadatei-Rendering-Optionen nach Bedarf konfigurieren.

### Häufig gestellte Fragen

#### F: Was bedeutet die Größenänderung von WMF-Schriftarten an die Metadateigröße in einem PDF-Dokument?
A: Das Anpassen der Größe von WMF-Schriftarten an die Metadateigröße in einem PDF-Dokument ist eine Funktion, die steuert, ob WMF-Schriftarten beim Konvertieren in ein PDF-Dokument so skaliert werden sollen, dass sie der Metadateigröße entsprechen. Wenn diese Funktion aktiviert ist, werden WMF-Schriftarten so skaliert, dass sie der Größe der Metadatei entsprechen, wodurch sich möglicherweise die Größe des generierten PDF-Dokuments verringert.

#### F: Wie kann ich Aspose.Words für .NET verwenden, um die Größenänderung von WMF-Schriftarten an die Metadateigröße in einem PDF-Dokument zu aktivieren oder zu deaktivieren?
A: Um die Größenänderung von WMF-Schriftarten an die Metadateigröße in einem PDF-Dokument mit Aspose.Words für .NET zu aktivieren oder zu deaktivieren, führen Sie die folgenden Schritte aus:

 Legen Sie den Verzeichnispfad fest, in dem sich Ihre Dokumente befinden, indem Sie ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad Ihres Dokumentenverzeichnisses.

 Laden Sie das Dokument, das Sie bearbeiten möchten, mit`Document` Klasse und geben Sie den Pfad zum Word-Dokument im angegebenen Dokumentenverzeichnis an.

 Konfigurieren Sie Metadatei-Rendering-Optionen, indem Sie eine Instanz davon erstellen`MetafileRenderingOptions` Klasse und Einstellung der`ScaleWmfFontsToMetafileSize`Eigentum zu`true` um die Skalierung von WMF-Schriftarten auf die Metadateigröße oder auf zu ermöglichen`false` um diese Funktion zu deaktivieren.

 Konfigurieren Sie die Optionen zum Speichern als PDF, indem Sie eine Instanz davon erstellen`PdfSaveOptions` Klasse und unter Verwendung der zuvor konfigurierten Metadatei-Renderingoptionen.

 Speichern Sie das Dokument im PDF-Format mit`Save` Methode der`Document` Klasse, die den Pfad und die Speicheroptionen angibt.

#### F: Welche Vorteile bietet die Größenänderung von WMF-Schriftarten an die Metadateigröße in einem PDF-Dokument?
A: Die Größenänderung von WMF-Schriftarten an die Metadateigröße in einem PDF-Dokument hat folgende Vorteile:

Reduzierung der PDF-Dateigröße: Durch Anpassen der Größe von WMF-Schriftarten an die Metadateigröße kann die Größe des generierten PDF-Dokuments reduziert werden, indem die Schriftgröße an die Anforderungen der Metadatei angepasst wird.

Verbesserte Leistung: Durch die Anpassung der Größe der WMF-Schriftarten an die Abmessungen der Metadatei kann die Darstellung des PDF-Dokuments schneller und effizienter erfolgen.