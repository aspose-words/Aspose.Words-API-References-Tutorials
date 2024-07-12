---
title: Tiff-Seitenbereich abrufen
linktitle: Tiff-Seitenbereich abrufen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine Reihe von TIFF-Seiten extrahieren. Vollständiges Tutorial für benutzerdefinierte TIFF-Dateien.
type: docs
weight: 10
url: /de/net/programming-with-imagesaveoptions/get-tiff-page-range/
---

In diesem Tutorial untersuchen wir den bereitgestellten C#-Quellcode, um mit Aspose.Words für .NET einen Bereich von TIFF-Seiten abzurufen. Mit dieser Funktion können Sie einen bestimmten Seitenbereich aus einem Dokument extrahieren und als TIFF-Datei speichern.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie Ihre Entwicklungsumgebung mit Aspose.Words für .NET eingerichtet haben. Stellen Sie sicher, dass Sie die erforderlichen Referenzen hinzugefügt und die entsprechenden Namespaces importiert haben.

## Schritt 2: Dokument einlegen

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 In diesem Schritt laden wir das Dokument mit dem`Document` Methode und Übergabe des Pfads an die zu ladende DOCX-Datei.

## Schritt 3: Das komplette Dokument im TIFF-Format speichern

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");
```

In diesem Schritt speichern wir das komplette Dokument im TIFF-Format mit dem`Save` Methode und Angabe des Pfads zur Ausgabedatei mit der Erweiterung`.tiff`.

## Schritt 4: Konfigurieren Sie Sicherungsoptionen für den Seitenbereich

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
PageSet = new PageSet(new PageRange(0, 1)),
TiffCompression = TiffCompression.Ccitt4,
Resolution = 160
};
```

 In diesem Schritt konfigurieren wir Backup-Optionen für den spezifischen Seitenbereich. Wir erstellen eine neue`ImageSaveOptions` Objekt, das das gewünschte Speicherformat angibt, hier "Tiff" für das TIFF-Format. Wir verwenden`PageSet` um den Seitenbereich anzugeben, den wir extrahieren möchten, hier von Seite 0 bis Seite 1 (einschließlich). Wir setzen auch die TIFF-Komprimierung auf`Ccitt4` und die Auflösung auf 160 dpi.

## Schritt 5: Seitenbereich im TIFF-Format speichern

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
```

 Im letzten Schritt speichern wir den angegebenen Seitenbereich im TIFF-Format mit dem`Save` -Methode und Übergabe des Pfades zur Ausgabedatei mit`.tiff` Erweiterung, zusammen mit den angegebenen Speicheroptionen.

Jetzt können Sie den Quellcode ausführen, um einen bestimmten Seitenbereich aus Ihrem Dokument abzurufen und als TIFF-Datei zu speichern. Die resultierenden Dateien werden im angegebenen Verzeichnis unter den Namen "WorkingWithImageSaveOptions.MultipageTiff.tiff" für das gesamte Dokument und "WorkingWithImageSaveOptions.GetTiffPageRange.tiff" für den angegebenen Seitenbereich gespeichert.

### Beispiel-Quellcode von Get Tiff Page Range mit Aspose.Words für .NET

```csharp 

// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");



ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
	PageSet = new PageSet(new PageRange(0, 1)), TiffCompression = TiffCompression.Ccitt4, Resolution = 160
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
            
            
        
```

## Abschluss

In diesem Tutorial haben wir die Funktion zum Abrufen eines TIFF-Seitenbereichs mit Aspose.Words für .NET untersucht. Wir haben gelernt, wie man einen bestimmten Seitenbereich aus einem Dokument extrahiert und als TIFF-Datei speichert.

Diese Funktion ist nützlich, wenn Sie nur bestimmte Seiten aus einem Dokument extrahieren und in einem Standardbildformat wie TIFF speichern möchten. Sie können auch die Komprimierungs- und Auflösungsoptionen anpassen, um TIFF-Dateien in bester Qualität zu erhalten.

Aspose.Words für .NET bietet eine umfangreiche Palette an erweiterten Funktionen zur Dokumentbearbeitung und -erstellung. Das Abrufen eines TIFF-Seitenbereichs ist eines der vielen leistungsstarken Tools, die Ihnen zur Verfügung stehen.

Integrieren Sie diese Funktionalität gerne in Ihre Aspose.Words für .NET-Projekte, um bestimmte Seitenbereiche aus Ihren Dokumenten im TIFF-Format zu extrahieren und zu speichern.