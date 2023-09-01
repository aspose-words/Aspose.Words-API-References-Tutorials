---
title: Holen Sie sich den JPEG-Seitenbereich
linktitle: Holen Sie sich den JPEG-Seitenbereich
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine Reihe von JPEG-Seiten erhalten. Vollständiges Tutorial zum Extrahieren benutzerdefinierter Bilder.
type: docs
weight: 10
url: /de/net/programming-with-imagesaveoptions/get-jpeg-page-range/
---

In diesem Tutorial untersuchen wir den C#-Quellcode, der für die Funktion „Bereich von JPEG-Seiten abrufen“ mit Aspose.Words für .NET bereitgestellt wird. Mit dieser Funktion können Sie einen bestimmten Seitenbereich eines Dokuments in Bilder im JPEG-Format konvertieren.

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
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);
options. PageSet = new PageSet(0);
options. ImageBrightness = 0.3f;
options. ImageContrast = 0.7f;
options. HorizontalResolution = 72f;
```

 In diesem Schritt konfigurieren wir Sicherungsoptionen für Bilder. Wir schaffen ein Neues`ImageSaveOptions` Objekt, das das gewünschte Speicherformat angibt, hier „Jpeg“ für das JPEG-Format. Wir legen auch den Bereich der zu konvertierenden Seiten fest`PageSet`Objekt. Abschließend passen wir die Helligkeit und den Kontrast des Bildes mit an`ImageBrightness` Und`ImageContrast` Eigenschaften bzw. Wir ändern auch die horizontale Auflösung mit`HorizontalResolution` Eigentum.

## Schritt 4: Bilder sichern

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
```

 In diesem letzten Schritt speichern wir die Bilder des angegebenen Seitenbereichs im JPEG-Format mit`Save` -Methode und Übergabe des Pfads zur Ausgabedatei zusammen mit den angegebenen Speicheroptionen.

Jetzt können Sie den Quellcode ausführen, um einen bestimmten Seitenbereich in Ihrem Dokument in JPEG-Bilder zu konvertieren. Die resultierende Datei wird im angegebenen Verzeichnis mit dem Namen „WorkingWithImageSaveOptions.GetJpegPageRange.jpeg“ gespeichert.

### Beispielquellcode für „Jpeg-Seitenbereich abrufen“ mit Aspose.Words für .NET

```csharp 
 // Pfad zu Ihrem Dokumentenverzeichnis
 string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);

// Setzen Sie „PageSet“ auf „0“, um nur die erste Seite eines Dokuments zu konvertieren.
options.PageSet = new PageSet(0);

// Ändern Sie die Helligkeit und den Kontrast des Bildes.
// Beide liegen auf einer Skala von 0 bis 1 und liegen standardmäßig bei 0,5.
options.ImageBrightness = 0.3f;
options.ImageContrast = 0.7f;

// Ändern Sie die horizontale Auflösung.
// Der Standardwert für diese Eigenschaften ist 96,0 für eine Auflösung von 96 dpi.
options.HorizontalResolution = 72f;

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
            
        
```

## Abschluss

In diesem Tutorial haben wir die Funktionalität zum Abrufen eines JPEG-Seitenbereichs mit Aspose.Words für .NET untersucht. Wir haben gelernt, wie man einen bestimmten Seitenbereich eines Dokuments in Bilder im JPEG-Format umwandelt und gleichzeitig die Speicheroptionen anpasst.

Diese Funktion ist nützlich, wenn Sie bestimmte Seiten aus einem Dokument extrahieren und als JPEG-Bilder speichern möchten. Sie können auch die Helligkeit, den Kontrast und die horizontale Auflösung von Bildern anpassen, um personalisierte Ergebnisse zu erzielen.

Aspose.Words für .NET bietet eine umfangreiche Palette erweiterter Funktionen für die Dokumentbearbeitung und -generierung. Das Erstellen eines JPEG-Seitenbereichs ist eines der vielen leistungsstarken Tools, die Ihnen zur Verfügung stehen.

Integrieren Sie diese Funktion gerne in Ihre Aspose.Words für .NET-Projekte, um hochwertige JPEG-Bilder aus Ihren Dokumenten zu erhalten.