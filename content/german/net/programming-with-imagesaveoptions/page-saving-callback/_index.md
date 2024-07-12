---
title: Rückruf zum Speichern der Seite
linktitle: Rückruf zum Speichern der Seite
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET das Speichern von Dokumentseiten als Bilder anpassen.
type: docs
weight: 10
url: /de/net/programming-with-imagesaveoptions/page-saving-callback/
---

In diesem Tutorial untersuchen wir den bereitgestellten C#-Quellcode für die Verwendung des Seitenspeicher-Rückrufs mit Aspose.Words-Bildspeicheroptionen für .NET. Mit dieser Funktion können Sie benutzerdefinierte Aktionen ausführen, wenn Sie jede Seite eines Dokuments als Bild speichern.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie Ihre Entwicklungsumgebung mit Aspose.Words für .NET eingerichtet haben. Stellen Sie sicher, dass Sie die erforderlichen Referenzen hinzugefügt und die entsprechenden Namespaces importiert haben.

## Schritt 2: Dokument einlegen

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 In diesem Schritt laden wir das Dokument mit dem`Document` Methode und Übergabe des Pfads an die zu ladende DOCX-Datei.

## Schritt 3: Konfigurieren von Image-Backup-Optionen

```csharp
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
     PageSavingCallback = new HandlePageSavingCallback()
};
```

 In diesem Schritt konfigurieren wir die Bildspeicheroptionen, indem wir ein neues`ImageSaveOptions` Objekt. Wir geben das gewünschte Backup-Format an, hier „Png“ für das PNG-Format. Wir verwenden`PageSet` um den zu speichernden Seitenbereich anzugeben, hier von der ersten bis zur letzten Seite des Dokuments (`doc.PageCount - 1`). Wir setzen auch`PageSavingCallback` zu einer Instanz von`HandlePageSavingCallback`, eine benutzerdefinierte Klasse zum Verarbeiten des Rückrufs zum Speichern der Seite.

## Schritt 4: Implementieren des Rückrufs „Seite speichern“

```csharp
public class HandlePageSavingCallback : IPageSavingCallback
{
     public void PageSaving(PageSavingArgs args)
     {
         // Implementieren Sie hier Ihre benutzerdefinierten Aktionen
         // Sie können auf Seiteninformationen über die Eigenschaft „args.PageIndex“ zugreifen
         // Sie können die Speicheroptionen auch für jede Seite einzeln ändern
     }
}
```

 In diesem Schritt implementieren wir die`HandlePageSavingCallback` Klasse, die implementiert die`IPageSavingCallback` Schnittstelle. Sie können diese Klasse anpassen, indem Sie Ihre spezifischen Aktionen in der`PageSaving` Methode. Sie können auf Seiteninformationen zugreifen über die`args.PageIndex` Eigentum der`PageSavingArgs` als Argument übergebenes Objekt.

## Schritt 5: Seiten als Bilder speichern

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

 In diesem letzten Schritt speichern wir jede Seite des Dokuments als Bild mit dem`Save` -Methode und Übergabe des Pfades zur Ausgabedatei mit der`.png` Erweiterung, zusammen mit den angegebenen Speicheroptionen.

Jetzt können Sie den Quellcode ausführen, um benutzerdefinierte Aktionen auszuführen, wenn jede Seite des Dokuments als Bild gespeichert wird. Die resultierende Datei wird im angegebenen Verzeichnis unter dem Namen „WorkingWithImageSaveOptions.PageSavingCallback.png“ gespeichert.

### Beispielquellcode für Page Saving Callback mit Aspose.Words für .NET


```csharp 
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY"; 


Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
	PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
	PageSavingCallback = new HandlePageSavingCallback()
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
        
```

## Abschluss

In diesem Tutorial haben wir die Rückruffunktion zum Speichern von Seiten mit den Bildspeicheroptionen von Aspose.Words für .NET untersucht. Wir haben gelernt, wie man benutzerdefinierte Aktionen ausführt, wenn jede Seite eines Dokuments als Bild gespeichert wird.

Diese Funktion ist nützlich, wenn Sie bei der Konvertierung in Bilder auf jeder Seite bestimmte Vorgänge ausführen möchten. Sie können auf Seiteninformationen zugreifen und diese verwenden, um Sicherungsoptionen anzupassen oder andere seitenspezifische Verarbeitungen durchzuführen.

Aspose.Words für .NET bietet eine umfangreiche Palette an erweiterten Funktionen zur Dokumentbearbeitung und -erstellung. Die Seite speichern-Erinnerung ist eines von vielen leistungsstarken Tools, mit denen Sie den Vorgang zum Speichern von Seiten in Bildern anpassen können.