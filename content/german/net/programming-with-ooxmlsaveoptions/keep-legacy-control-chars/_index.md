---
title: Behalten Sie die alten Steuerzeichen bei
linktitle: Behalten Sie die alten Steuerzeichen bei
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie beim Speichern eines Dokuments mit Aspose.Words für .NET alte Steuerzeichen beibehalten.
type: docs
weight: 10
url: /de/net/programming-with-ooxmlsaveoptions/keep-legacy-control-chars/
---

In diesem Tutorial untersuchen wir den bereitgestellten C#-Quellcode, um beim Speichern eines Dokuments mit Aspose.Words für .NET ältere Steuerzeichen beizubehalten. Mit dieser Funktion können Sie beim Konvertieren oder Speichern eines Dokuments spezielle Steuerzeichen beibehalten.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie Ihre Entwicklungsumgebung mit Aspose.Words für .NET eingerichtet haben. Stellen Sie sicher, dass Sie die erforderlichen Referenzen hinzugefügt und die entsprechenden Namespaces importiert haben.

## Schritt 2: Dokument einlegen

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Legacy control character.doc");
```

 In diesem Schritt laden wir das Dokument mit dem`Document` -Methode und Übergabe des Pfads zur Datei, die die geerbten Steuerzeichen enthält.

## Schritt 3: OOXML-Sicherungsoptionen konfigurieren

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };
```

 In diesem Schritt konfigurieren wir OOXML-Speicheroptionen, indem wir eine neue`OoxmlSaveOptions` Objekt. Wir geben das gewünschte Speicherformat an (hier`FlatOpc` ) und aktivieren Sie die`KeepLegacyControlChars` Option zum Beibehalten von alten Steuerzeichen.

## Schritt 4: Speichern des Dokuments mit alten Steuerzeichen

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
```

 Im letzten Schritt speichern wir das Dokument mit dem`Save` -Methode und Übergabe des Pfades zur Ausgabedatei mit der`.docx` Erweiterung, zusammen mit den angegebenen Speicheroptionen.

Jetzt können Sie Quellcode ausführen, um beim Speichern eines Dokuments alte Steuerzeichen beizubehalten. Die resultierende Datei wird im angegebenen Verzeichnis unter dem Namen „WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx“ gespeichert.

### Beispielquellcode für „Keep Legacy Control Chars“ mit Aspose.Words für .NET 
```csharp

// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Legacy control character.doc");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
            
        
```

## Abschluss

In diesem Tutorial haben wir die Funktion zum Beibehalten von alten Steuerzeichen beim Speichern eines Dokuments mit Aspose.Words für .NET untersucht. Wir haben gelernt, wie man die Sonderzeichen beibehält, die für die korrekte Formatierung oder Anzeige des Dokuments wichtig sein können.

 Das Beibehalten von alten Steuerzeichen ist besonders nützlich, wenn Sie in Words Processing Dokumente bearbeiten, die ältere oder spezielle Funktionen verwenden, wie z. B. spezielle Steuerzeichen. Durch Aktivieren der`KeepLegacyControlChars` Mit der Option beim Speichern des Dokuments stellen Sie sicher, dass diese Zeichen erhalten bleiben.

Aspose.Words für .NET bietet eine Reihe flexibler und leistungsstarker Sicherungsoptionen, die Ihren Anforderungen an die Dokumentbearbeitung gerecht werden. Mithilfe der entsprechenden Optionen können Sie den Sicherungsvorgang anpassen, um die spezifischen Eigenschaften Ihrer Dokumente beizubehalten.

Integrieren Sie diese Funktionalität gerne in Ihre Aspose.Words-Projekte für .NET, um die Integrität und Beibehaltung älterer Steuerzeichen in Ihren Dokumenten sicherzustellen.