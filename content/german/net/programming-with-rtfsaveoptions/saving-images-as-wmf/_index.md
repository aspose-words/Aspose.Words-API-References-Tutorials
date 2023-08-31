---
title: Bilder als WMF speichern
linktitle: Bilder als WMF speichern
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie Bilder beim Konvertieren in RTF mit Aspose.Words für .NET als WMF speichern.
type: docs
weight: 10
url: /de/net/programming-with-rtfsaveoptions/saving-images-as-wmf/
---

In diesem Tutorial untersuchen wir den C#-Quellcode, der für die Funktion „Bilder als WMF mit RTF-Speicheroptionen speichern“ mit Aspose.Words für .NET bereitgestellt wird. Mit dieser Funktion können Sie Dokumentbilder beim Konvertieren in das RTF-Format im Windows Metafile-Format (WMF) speichern.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie Ihre Entwicklungsumgebung mit Aspose.Words für .NET eingerichtet haben. Stellen Sie sicher, dass Sie die erforderlichen Verweise hinzugefügt und die entsprechenden Namespaces importiert haben.

## Schritt 2: Laden des Dokuments

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 In diesem Schritt laden wir das Dokument mit`Document` -Methode und Übergabe des Pfads zur zu ladenden DOCX-Datei.

## Schritt 3: Backup-Optionen konfigurieren

```csharp
RtfSaveOptions saveOptions = new RtfSaveOptions { SaveImagesAsWmf = true };
```

 In diesem Schritt konfigurieren wir die RTF-Backup-Optionen. Wir schaffen ein Neues`RtfSaveOptions` Objekt und legen Sie das fest`SaveImagesAsWmf` Eigentum zu`true`. Dadurch wird Aspose.Words angewiesen, die Dokumentbilder bei der Konvertierung in RTF als WMF zu speichern.

## Schritt 4: Speichern des Dokuments

```csharp
doc.Save(dataDir + "WorkingWithRtfSaveOptions.SavingImagesAsWmf.rtf", saveOptions);
```

 In diesem letzten Schritt speichern wir das resultierende Dokument im RTF-Format mit`Save` -Methode und Übergabe des Pfads zur Ausgabedatei zusammen mit den angegebenen Speicheroptionen.

Jetzt können Sie Quellcode ausführen, um Dokumentbilder im WMF-Format zu speichern und gleichzeitig in das RTF-Format zu konvertieren. Das resultierende Dokument wird im angegebenen Verzeichnis mit dem Namen „WorkingWithRtfSaveOptions.SavingImagesAsWmf.rtf“ gespeichert.

### Beispielquellcode für die Funktionalität zum Speichern von WMF-Bildern mit RTF-Speicheroptionen mit Aspose.Words für .NET.

```csharp

            
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");

RtfSaveOptions saveOptions = new RtfSaveOptions { SaveImagesAsWmf = true };

doc.Save(dataDir + "WorkingWithRtfSaveOptions.SavingImagesAsWmf.rtf", saveOptions);
            
        
```
## Abschluss

In diesem Tutorial haben wir die Funktionalität des Speicherns von Bildern als WMF mit RTF-Speicheroptionen in Aspose.Words für .NET untersucht. Wir haben gelernt, wie man Bilder aus einem Dokument im WMF-Format speichert, wenn man es in das RTF-Format konvertiert.

Diese Funktion ist nützlich, wenn Sie die Qualität und Auflösung der Bilder in Ihren RTF-Dokumenten beibehalten möchten. Durch das Speichern von Bildern im WMF-Format können Sie sicherstellen, dass Aussehen und Schärfe erhalten bleiben.

Aspose.Words für .NET bietet viele erweiterte Funktionen für die Dokumentbearbeitung und -generierung. Das Speichern von Bildern im WMF-Format bei gleichzeitiger Konvertierung in das RTF-Format ist eines der vielen leistungsstarken Tools, die Ihnen zur Verfügung stehen.

### Häufig gestellte Fragen

#### F: Was ist die Funktion „Bilder als WMF mit RTF-Speicheroptionen speichern“ in Aspose.Words für .NET?
A: Die Funktion „Bilder als WMF mit RTF-Speicheroptionen speichern“ mit Aspose.Words für .NET ermöglicht das Speichern von Dokumentbildern im Windows Metafile (WMF)-Format bei der Konvertierung in RTF. Dies bietet die Möglichkeit, die Bildqualität und Auflösung in RTF-Dokumenten beizubehalten.

#### F: Wie kann ich diese Funktion mit Aspose.Words für .NET verwenden?
A: Um diese Funktion mit Aspose.Words für .NET zu verwenden, können Sie die folgenden Schritte ausführen:

Richten Sie Ihre Entwicklungsumgebung ein, indem Sie die erforderlichen Referenzen hinzufügen und die entsprechenden Namespaces importieren.

 Laden Sie das Dokument mit`Document` -Methode und Angabe des Pfads der zu ladenden DOCX-Datei.

 Konfigurieren Sie RTF-Speicheroptionen, indem Sie eine erstellen`RtfSaveOptions` Objekt und Einstellung der`SaveImagesAsWmf` Eigentum zu`true`. Dadurch wird Aspose.Words angewiesen, die Dokumentbilder als zu speichern 
WMF bei der Konvertierung in RTF.

 Speichern Sie das resultierende Dokument im RTF-Format mit`Save` -Methode und Angabe des vollständigen Pfads zur Ausgabedatei sowie der angegebenen Speicheroptionen.

#### F: Ist es möglich, mit den RTF-Speicheroptionen ein anderes Bildformat zum Speichern auszuwählen?
A: Nein, diese spezielle Funktion speichert Bilder beim Konvertieren in RTF im WMF-Format. Andere Bildformate werden von dieser Funktion nicht direkt unterstützt. Aspose.Words bietet jedoch weitere Funktionen zur Bildbearbeitung und -konvertierung, sodass Sie Bilder vor oder nach der Konvertierung in RTF in andere Formate konvertieren können.

#### F: Bieten die RTF-Speicheroptionen mit Aspose.Words für .NET weitere Funktionen?
A: Ja, Aspose.Words für .NET bietet viele weitere Funktionen mit RTF-Speicheroptionen. Sie können verschiedene Aspekte der RTF-Konvertierung anpassen, z. B. Schriftartenverwaltung, Layout, Bilder, Tabellen, Hyperlinks usw. Mit diesen Optionen haben Sie eine genaue Kontrolle über das Endergebnis der RTF-Konvertierung.

#### F: Wie kann ich Bilder in einem Dokument mit Aspose.Words für .NET bearbeiten?
A: Aspose.Words für .NET bietet eine umfassende Funktionalität zum Bearbeiten von Bildern in einem Dokument. Sie können Bilder extrahieren, einfügen, in der Größe ändern, zuschneiden, Filter und Effekte anwenden, die Qualität anpassen, zwischen verschiedenen Bildformaten konvertieren und vieles mehr. Weitere Informationen zur Bildbearbeitung finden Sie in der Aspose.Words-Dokumentation.