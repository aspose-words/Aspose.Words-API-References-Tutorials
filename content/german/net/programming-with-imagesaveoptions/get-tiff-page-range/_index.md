---
title: Holen Sie sich den TIFF-Seitenbereich
linktitle: Holen Sie sich den TIFF-Seitenbereich
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine Reihe von TIFF-Seiten extrahieren. Vollständiges Tutorial für benutzerdefinierte TIFF-Dateien.
type: docs
weight: 10
url: /de/net/programming-with-imagesaveoptions/get-tiff-page-range/
---

In diesem Tutorial untersuchen wir den bereitgestellten C#-Quellcode, um eine Reihe von TIFF-Seiten mit Aspose.Words für .NET zu erhalten. Mit dieser Funktion können Sie einen bestimmten Seitenbereich aus einem Dokument extrahieren und als TIFF-Datei speichern.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie Ihre Entwicklungsumgebung mit Aspose.Words für .NET eingerichtet haben. Stellen Sie sicher, dass Sie die erforderlichen Verweise hinzugefügt und die entsprechenden Namespaces importiert haben.

## Schritt 2: Laden des Dokuments

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 In diesem Schritt laden wir das Dokument mit`Document` -Methode und Übergabe des Pfads zur zu ladenden DOCX-Datei.

## Schritt 3: Speichern des gesamten Dokuments im TIFF

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");
```

 In diesem Schritt speichern wir das komplette Dokument im TIFF-Format mit`Save` -Methode und Angabe des Pfads zur Ausgabedatei mit der Erweiterung`.tiff`.

## Schritt 4: Konfigurieren Sie Sicherungsoptionen für den Seitenbereich

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
PageSet = new PageSet(new PageRange(0, 1)),
TiffCompression = TiffCompression.Ccitt4,
Resolution = 160
};
```

 In diesem Schritt konfigurieren wir Backup-Optionen für den spezifischen Seitenbereich. Wir schaffen ein Neues`ImageSaveOptions` Objekt, das das gewünschte Speicherformat angibt, hier „Tiff“ für das TIFF-Format. Wir gebrauchen`PageSet` um den Seitenbereich anzugeben, den wir extrahieren möchten, hier von Seite 0 bis Seite 1 (einschließlich). Wir haben auch die TIFF-Komprimierung auf eingestellt`Ccitt4` und die Auflösung auf 160 dpi.

## Schritt 5: Speichern des Seitenbereichs im TIFF

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
```

 In diesem letzten Schritt speichern wir den angegebenen Seitenbereich im TIFF-Format mit`Save`-Methode und Übergabe des Pfads zur Ausgabedatei mit`.tiff` Erweiterung zusammen mit den angegebenen Speicheroptionen.

Jetzt können Sie den Quellcode ausführen, um einen bestimmten Seitenbereich aus Ihrem Dokument abzurufen und diese als TIFF-Datei zu speichern. Die resultierenden Dateien werden im angegebenen Verzeichnis mit den Namen „WorkingWithImageSaveOptions.MultipageTiff.tiff“ für das gesamte Dokument und „WorkingWithImageSaveOptions.GetTiffPageRange.tiff“ für den angegebenen Seitenbereich gespeichert.

### Beispielquellcode für „Get Tiff Page Range“ mit Aspose.Words für .NET

```csharp 

//Pfad zu Ihrem Dokumentenverzeichnis
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

In diesem Tutorial haben wir die Funktionalität zum Abrufen einer Reihe von TIFF-Seiten mit Aspose.Words für .NET untersucht. Wir haben gelernt, wie man einen bestimmten Seitenbereich aus einem Dokument extrahiert und als TIFF-Datei speichert.

Diese Funktion ist nützlich, wenn Sie nur bestimmte Seiten aus einem Dokument extrahieren und sie in einem Standardbildformat wie TIFF speichern möchten. Sie können auch die Komprimierungs- und Auflösungsoptionen anpassen, um TIFF-Dateien in bester Qualität zu erhalten.

Aspose.Words für .NET bietet eine umfangreiche Palette erweiterter Funktionen für die Dokumentbearbeitung und -generierung. Das Erstellen eines TIFF-Seitenbereichs ist eines der vielen leistungsstarken Tools, die Ihnen zur Verfügung stehen.

Integrieren Sie diese Funktionalität gerne in Ihre Aspose.Words für .NET-Projekte, um bestimmte Seitenbereiche aus Ihren Dokumenten zu extrahieren und im TIFF-Format zu speichern.