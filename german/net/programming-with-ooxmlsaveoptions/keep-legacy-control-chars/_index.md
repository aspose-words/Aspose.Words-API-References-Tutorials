---
title: Behalten Sie die alten Kontrollzeichen bei
linktitle: Behalten Sie die alten Kontrollzeichen bei
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie beim Speichern eines Dokuments mit Aspose.Words für .NET alte Steuerzeichen beibehalten.
type: docs
weight: 10
url: /de/net/programming-with-ooxmlsaveoptions/keep-legacy-control-chars/
---

In diesem Tutorial untersuchen wir den bereitgestellten C#-Quellcode, um beim Speichern eines Dokuments mit Aspose.Words für .NET alte Steuerzeichen beizubehalten. Mit dieser Funktion können Sie beim Konvertieren oder Speichern eines Dokuments spezielle Steuerzeichen beibehalten.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie Ihre Entwicklungsumgebung mit Aspose.Words für .NET eingerichtet haben. Stellen Sie sicher, dass Sie die erforderlichen Verweise hinzugefügt und die entsprechenden Namespaces importiert haben.

## Schritt 2: Laden des Dokuments

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Legacy control character.doc");
```

 In diesem Schritt laden wir das Dokument mit`Document` -Methode und Übergabe des Pfads zu der Datei, die die geerbten Steuerzeichen enthält.

## Schritt 3: OOXML-Sicherungsoptionen konfigurieren

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };
```

In diesem Schritt konfigurieren wir die OOXML-Speicheroptionen, indem wir eine neue erstellen`OoxmlSaveOptions`Objekt. Wir geben das gewünschte Speicherformat an (hier`FlatOpc` ) und aktivieren Sie die`KeepLegacyControlChars` Option zum Beibehalten älterer Steuerzeichen.

## Schritt 4: Speichern des Dokuments mit alten Steuerzeichen

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
```

 In diesem letzten Schritt speichern wir das Dokument mit`Save` -Methode und Übergabe des Pfads zur Ausgabedatei mit der`.docx` Erweiterung zusammen mit den angegebenen Speicheroptionen.

Jetzt können Sie Quellcode ausführen, um beim Speichern eines Dokuments alte Steuerzeichen beizubehalten. Die resultierende Datei wird im angegebenen Verzeichnis mit dem Namen „WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx“ gespeichert.

### Beispielquellcode für „Keep Legacy Control Chars“ mit Aspose.Words für .NET 
```csharp

//Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Legacy control character.doc");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
            
        
```

## Abschluss

In diesem Tutorial haben wir die Funktionalität der Beibehaltung älterer Steuerzeichen beim Speichern eines Dokuments mit Aspose.Words für .NET untersucht. Wir haben gelernt, wie man Sonderzeichen beibehält, die für die ordnungsgemäße Formatierung oder Anzeige eines Dokuments wichtig sein können.

 Die Beibehaltung älterer Steuerzeichen ist besonders nützlich bei der Textverarbeitung mit Dokumenten, die ältere oder spezifische Funktionen wie spezielle Steuerzeichen verwenden. Durch die Aktivierung des`KeepLegacyControlChars`Mit dieser Option beim Speichern des Dokuments stellen Sie sicher, dass diese Zeichen erhalten bleiben.

Aspose.Words für .NET bietet eine Reihe flexibler und leistungsstarker Sicherungsoptionen, um Ihre Anforderungen an die Dokumentenbearbeitung zu erfüllen. Mithilfe der entsprechenden Optionen können Sie den Backup-Prozess so anpassen, dass die spezifischen Eigenschaften Ihrer Dokumente erhalten bleiben.

Integrieren Sie diese Funktionalität gerne in Ihre Aspose.Words für .NET-Projekte, um die Integrität und Beibehaltung älterer Steuerzeichen in Ihren Dokumenten sicherzustellen.