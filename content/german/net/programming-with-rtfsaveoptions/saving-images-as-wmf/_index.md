---
title: Bilder als WMF speichern
linktitle: Bilder als WMF speichern
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie Bilder als WMF speichern, wenn Sie sie mit Aspose.Words für .NET in RTF konvertieren.
type: docs
weight: 10
url: /de/net/programming-with-rtfsaveoptions/saving-images-as-wmf/
---

In diesem Tutorial untersuchen wir den C#-Quellcode für die Funktion „Bilder als WMF mit RTF-Speicheroptionen speichern“ mit Aspose.Words für .NET. Mit dieser Funktion können Sie Dokumentbilder beim Konvertieren in das RTF-Format im Windows Metafile-Format (WMF) speichern.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie Ihre Entwicklungsumgebung mit Aspose.Words für .NET eingerichtet haben. Stellen Sie sicher, dass Sie die erforderlichen Referenzen hinzugefügt und die entsprechenden Namespaces importiert haben.

## Schritt 2: Dokument einlegen

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 In diesem Schritt laden wir das Dokument mit dem`Document` Methode und Übergabe des Pfads an die zu ladende DOCX-Datei.

## Schritt 3: Konfigurieren der Sicherungsoptionen

```csharp
RtfSaveOptions saveOptions = new RtfSaveOptions { SaveImagesAsWmf = true };
```

 In diesem Schritt konfigurieren wir die RTF-Backup-Optionen. Wir erstellen ein neues`RtfSaveOptions` Objekt und setzen Sie den`SaveImagesAsWmf`Eigentum an`true`. Dies weist Aspose.Words an, die Dokumentbilder beim Konvertieren in RTF als WMF zu speichern.

## Schritt 4: Speichern des Dokuments

```csharp
doc.Save(dataDir + "WorkingWithRtfSaveOptions.SavingImagesAsWmf.rtf", saveOptions);
```

 In diesem letzten Schritt speichern wir das resultierende Dokument im RTF-Format mit dem`Save` Methode und Übergabe des Pfads zur Ausgabedatei zusammen mit den angegebenen Speicheroptionen.

Jetzt können Sie Quellcode ausführen, um Dokumentbilder im WMF-Format zu speichern, während Sie in das RTF-Format konvertieren. Das resultierende Dokument wird im angegebenen Verzeichnis unter dem Namen „WorkingWithRtfSaveOptions.SavingImagesAsWmf.rtf“ gespeichert.

### Beispiel-Quellcode für die Funktion zum Speichern von WMF-Bildern mit RTF-Speicheroptionen mit Aspose.Words für .NET".

```csharp

            
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");

RtfSaveOptions saveOptions = new RtfSaveOptions { SaveImagesAsWmf = true };

doc.Save(dataDir + "WorkingWithRtfSaveOptions.SavingImagesAsWmf.rtf", saveOptions);
            
        
```
## Abschluss

In diesem Tutorial haben wir die Funktion zum Speichern von Bildern als WMF mit RTF-Speicheroptionen in Aspose.Words für .NET untersucht. Wir haben gelernt, wie man Bilder aus einem Dokument im WMF-Format speichert, wenn man es in das RTF-Format konvertiert.

Diese Funktion ist nützlich, wenn Sie die Qualität und Auflösung von Bildern in Ihren RTF-Dokumenten beibehalten möchten. Indem Sie Bilder im WMF-Format speichern, können Sie sicherstellen, dass ihr Aussehen und ihre Schärfe erhalten bleiben.

Aspose.Words für .NET bietet viele erweiterte Funktionen zur Dokumentbearbeitung und -erstellung. Das Speichern von Bildern im WMF-Format während der Konvertierung in das RTF-Format ist eines der vielen leistungsstarken Tools, die es Ihnen bietet.

### Häufig gestellte Fragen

#### F: Was ist die Funktion „Bilder als WMF mit RTF-Speicheroptionen speichern“ in Aspose.Words für .NET?
A: Die Funktion „Bilder als WMF mit RTF-Speicheroptionen speichern“ von Aspose.Words für .NET ermöglicht das Speichern von Dokumentbildern im Windows Metafile-Format (WMF) beim Konvertieren in RTF. Dadurch können Bildqualität und Auflösung in RTF-Dokumenten beibehalten werden.

#### F: Wie kann ich diese Funktion mit Aspose.Words für .NET verwenden?
A: Um diese Funktion mit Aspose.Words für .NET zu verwenden, können Sie diese Schritte befolgen:

Richten Sie Ihre Entwicklungsumgebung ein, indem Sie die erforderlichen Referenzen hinzufügen und die entsprechenden Namespaces importieren.

 Laden Sie das Dokument mit dem`Document` Methode und geben Sie den Pfad der zu ladenden DOCX-Datei an.

 Konfigurieren Sie RTF-Speicheroptionen durch die Erstellung einer`RtfSaveOptions` Objekt und Festlegen der`SaveImagesAsWmf`Eigentum an`true`. Dies weist Aspose.Words an, die Dokumentbilder zu speichern als 
WMF beim Konvertieren in RTF.

 Speichern Sie das resultierende Dokument im RTF-Format mit dem`Save` Methode und geben Sie den vollständigen Pfad zur Ausgabedatei zusammen mit den angegebenen Speicheroptionen an.

#### F: Ist es mit den RTF-Speicheroptionen möglich, ein anderes Bildformat zum Speichern auszuwählen?
A: Nein, diese spezielle Funktion speichert Bilder beim Konvertieren in RTF im WMF-Format. Andere Bildformate werden von dieser Funktion nicht direkt unterstützt. Aspose.Words bietet jedoch andere Funktionen zur Bildbearbeitung und -konvertierung, mit denen Sie Bilder vor oder nach der Konvertierung in RTF in andere Formate konvertieren können.

#### F: Bieten die RTF-Speicheroptionen mit Aspose.Words für .NET andere Funktionen?
A: Ja, Aspose.Words für .NET bietet viele weitere Funktionen mit RTF-Speicheroptionen. Sie können verschiedene Aspekte der RTF-Konvertierung anpassen, z. B. Schriftartverwaltung, Layout, Bilder, Tabellen, Hyperlinks usw. Diese Optionen geben Ihnen präzise Kontrolle über das Endergebnis der RTF-Konvertierung.

#### F: Wie kann ich mit Aspose.Words für .NET Bilder in einem Dokument bearbeiten?
A: Aspose.Words für .NET bietet eine umfassende Palette an Funktionen zur Bearbeitung von Bildern in einem Dokument. Sie können Bilder extrahieren, einfügen, ihre Größe ändern, zuschneiden, Filter und Effekte anwenden, die Qualität anpassen, zwischen verschiedenen Bildformaten konvertieren und vieles mehr. Weitere Einzelheiten zur Bildbearbeitung finden Sie in der Aspose.Words-Dokumentation.