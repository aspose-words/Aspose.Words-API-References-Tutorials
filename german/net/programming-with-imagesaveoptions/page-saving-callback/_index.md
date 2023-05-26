---
title: Rückruf zum Speichern der Seite
linktitle: Rückruf zum Speichern der Seite
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie das Speichern von Dokumentseiten in Bildern mit Aspose.Words für .NET anpassen.
type: docs
weight: 10
url: /de/net/programming-with-imagesaveoptions/page-saving-callback/
---

In diesem Tutorial untersuchen wir den C#-Quellcode, der für die Verwendung des Rückrufs zum Speichern von Seiten mit den Bildspeicheroptionen von Aspose.Words für .NET bereitgestellt wird. Mit dieser Funktion können Sie benutzerdefinierte Aktionen ausführen, wenn Sie jede Seite eines Dokuments als Bild speichern.

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
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
     PageSavingCallback = new HandlePageSavingCallback()
};
```

 In diesem Schritt konfigurieren wir die Bildspeicheroptionen, indem wir ein neues erstellen`ImageSaveOptions` Objekt. Wir geben das gewünschte Backup-Format an, hier „Png“ für das PNG-Format. Wir gebrauchen`PageSet` um den Bereich der zu speichernden Seiten anzugeben, hier von der ersten bis zur letzten Seite des Dokuments (`doc.PageCount - 1`). Wir haben auch eingestellt`PageSavingCallback` zu einer Instanz von`HandlePageSavingCallback`, eine benutzerdefinierte Klasse zur Verarbeitung des Rückrufs zum Speichern der Seite.

## Schritt 4: Implementieren des Rückrufs zum Speichern der Seite

```csharp
public class HandlePageSavingCallback : IPageSavingCallback
{
     public void PageSaving(PageSavingArgs args)
     {
         // Implementieren Sie hier Ihre benutzerdefinierten Aktionen
         // Sie können über die Eigenschaft „args.PageIndex“ auf Seiteninformationen zugreifen
         // Sie können die Speicheroptionen auch für jede Seite einzeln ändern
     }
}
```

 In diesem Schritt implementieren wir die`HandlePageSavingCallback` Klasse, die die implementiert`IPageSavingCallback` Schnittstelle. Sie können diese Klasse anpassen, indem Sie Ihre spezifischen Aktionen hinzufügen`PageSaving` Methode. Sie können über das auf Seiteninformationen zugreifen`args.PageIndex` Eigentum der`PageSavingArgs` Objekt, das als Argument übergeben wird.

## Schritt 5: Seiten als Bilder speichern

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

 In diesem letzten Schritt speichern wir jede Seite des Dokuments als Bild mit`Save` -Methode und Übergabe des Pfads zur Ausgabedatei mit der`.png` Erweiterung zusammen mit den angegebenen Speicheroptionen.

Jetzt können Sie den Quellcode ausführen, um beim Speichern jeder Seite des Dokuments als Bild benutzerdefinierte Aktionen auszuführen. Die resultierende Datei wird im angegebenen Verzeichnis mit dem Namen „WorkingWithImageSaveOptions.PageSavingCallback.png“ gespeichert.

### Beispielquellcode für Page Saving Callback mit Aspose.Words für .NET


```csharp 
// Pfad zu Ihrem Dokumentenverzeichnis
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

In diesem Tutorial haben wir die Rückruffunktion zum Speichern von Seiten mit den Bildspeicheroptionen von Aspose.Words für .NET untersucht. Wir haben gelernt, wie Sie benutzerdefinierte Aktionen ausführen, wenn Sie jede Seite eines Dokuments als Bild speichern.

Diese Funktion ist nützlich, wenn Sie beim Konvertieren in Bilder auf jeder Seite bestimmte Vorgänge ausführen möchten. Sie können auf Seiteninformationen zugreifen und diese verwenden, um Sicherungsoptionen anzupassen oder andere seitenspezifische Verarbeitungen durchzuführen.

Aspose.Words für .NET bietet eine umfangreiche Palette erweiterter Funktionen für die Dokumentbearbeitung und -generierung. Die Erinnerung zum Speichern von Seiten ist eines von vielen leistungsstarken Tools, mit denen Sie den Prozess des Speicherns von Seiten in Bildern anpassen können.