---
title: Format 1Bpp indiziert
linktitle: Format 1Bpp indiziert
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET indizierte Bilder in 1 BPP formatieren. Vollständiges Tutorial für Bilder mit geringer Farbtiefe.
type: docs
weight: 10
url: /de/net/programming-with-imagesaveoptions/format-1bpp-indexed/
---
In diesem Tutorial untersuchen wir den C#-Quellcode, der für die Funktionalität „Format 1Bpp Indexed“ mit Aspose.Words für .NET bereitgestellt wird. Mit dieser Funktion können Sie Bilder in einem Dokument im PNG-Format mit einer Farbtiefe von 1 Bit pro Pixel (1 BPP) und einem indizierten Farbmodus formatieren.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie Ihre Entwicklungsumgebung mit Aspose.Words für .NET eingerichtet haben. Stellen Sie sicher, dass Sie die erforderlichen Verweise hinzugefügt und die entsprechenden Namespaces importiert haben.

## Schritt 2: Laden des Dokuments

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 In diesem Schritt laden wir das Dokument mit`Document` -Methode und Übergabe des Pfads zur zu ladenden DOCX-Datei.

## Schritt 3: Konfigurieren Sie die Image-Backup-Optionen

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(1),
     ImageColorMode = ImageColorMode.BlackAndWhite,
     PixelFormat = ImagePixelFormat.Format1bppIndexed
};
```

 In diesem Schritt konfigurieren wir Sicherungsoptionen für Bilder. Wir schaffen ein Neues`ImageSaveOptions`Objekt, das das gewünschte Speicherformat angibt, hier „Png“ für das PNG-Format. Wir definieren auch die Seite, die in das Bild einbezogen werden soll, den Schwarzweiß-Farbmodus und das indizierte 1-bpp-Pixelformat.

## Schritt 4: Bilder sichern

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
```

 In diesem letzten Schritt speichern wir die Dokumentbilder im PNG-Format mit`Save` -Methode und Übergabe des Pfads zur Ausgabedatei zusammen mit den angegebenen Speicheroptionen.

Jetzt können Sie den Quellcode ausführen, um die Dokumentbilder im PNG-Format mit einer indizierten Farbtiefe von 1 bpp zu formatieren. Die resultierende Datei wird im angegebenen Verzeichnis mit dem Namen „WorkingWithImageSaveOptions.Format1BppIndexed.Png“ gespeichert.

### Beispielquellcode für Format 1Bpp, indiziert mit Aspose.Words für .NET

```csharp 
 
			 //Pfad zu Ihrem Dokumentenverzeichnis
			 string dataDir = "YOUR DOCUMENT DIRECTORY"; 
            
            Document doc = new Document(dataDir + "Rendering.docx");

            ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
            {
                PageSet = new PageSet(1),
                ImageColorMode = ImageColorMode.BlackAndWhite,
                PixelFormat = ImagePixelFormat.Format1bppIndexed
            };

            doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
            
        
```

### Abschluss

In diesem Tutorial haben wir die Funktion des 1Bpp-indizierten Formats mit Aspose.Words für .NET untersucht. Wir haben gelernt, wie man Bilder in einem Dokument im PNG-Format mit einer Farbtiefe von 1 Bit pro Pixel (1 BPP) und einem indizierten Farbmodus formatiert.

Diese Funktion ist nützlich, wenn Sie Bilder mit geringer Farbtiefe und kleiner Dateigröße erhalten möchten. Das 1Bpp Indexed-Format ermöglicht die Darstellung von Bildern mithilfe einer indizierten Farbpalette, was für bestimmte Anwendungen von Vorteil sein kann.

Aspose.Words für .NET bietet eine breite Palette erweiterter Funktionen für die Dokumentbearbeitung und -generierung. Das 1Bpp Indexed-Format ist eines der vielen leistungsstarken Tools, die es Ihnen zur Verfügung stellt.