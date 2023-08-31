---
title: Stellen Sie die Komprimierungsstufe ein
linktitle: Stellen Sie die Komprimierungsstufe ein
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie die Komprimierungsstufe beim Speichern eines Dokuments mit Aspose.Words für .NET festlegen.
type: docs
weight: 10
url: /de/net/programming-with-ooxmlsaveoptions/set-compression-level/
---
In diesem Tutorial untersuchen wir den bereitgestellten C#-Quellcode, um die Komprimierungsstufe beim Speichern eines Dokuments mit Aspose.Words für .NET festzulegen. Mit dieser Funktion können Sie die Komprimierungsstufe des generierten Dokuments steuern.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie Ihre Entwicklungsumgebung mit Aspose.Words für .NET eingerichtet haben. Stellen Sie sicher, dass Sie die erforderlichen Verweise hinzugefügt und die entsprechenden Namespaces importiert haben.

## Schritt 2: Laden des Dokuments

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 In diesem Schritt laden wir das Dokument mit`Document` -Methode und Übergabe des Pfads zur zu ladenden DOCX-Datei.

## Schritt 3: OOXML-Sicherungsoptionen konfigurieren

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };
```

 In diesem Schritt konfigurieren wir OOXML-Speicheroptionen mithilfe von`OoxmlSaveOptions` Klasse. Wir stellen die Komprimierungsstufe auf ein`SuperFast` um eine schnellere Komprimierung zu erreichen.

## Schritt 4: Speichern Sie das Dokument mit der angegebenen Komprimierungsstufe

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
```

 In diesem letzten Schritt speichern wir das Dokument mit`Save` -Methode und Übergabe des Pfads zur Ausgabedatei mit der`.docx` Erweiterung zusammen mit den angegebenen Speicheroptionen.

Jetzt können Sie den Quellcode ausführen, um die Komprimierungsstufe beim Speichern eines Dokuments festzulegen. Die resultierende Datei wird im angegebenen Verzeichnis mit dem Namen „WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx“ gespeichert.

### Beispielquellcode für „Komprimierungsstufe festlegen“ mit Aspose.Words für .NET 

```csharp

//Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
            
        
```

## Abschluss

In diesem Tutorial haben wir die Funktionalität zum Festlegen der Komprimierungsstufe beim Speichern eines Dokuments mit Aspose.Words für .NET untersucht. Durch Angabe der geeigneten Komprimierungsstufe können Sie die Dokumentgröße und die Generierungsgeschwindigkeit optimieren.

 Der`OoxmlSaveOptions`Die Klasse bietet Flexibilität zur Steuerung des Komprimierungsgrades durch Festlegen der`CompressionLevel` Eigenschaft auf einen angemessenen Wert, wie z`SuperFast`. Auf diese Weise können Sie je nach Ihren spezifischen Anforderungen das richtige Gleichgewicht zwischen Dateigröße und Sicherungsgeschwindigkeit finden.

Die Verwendung der Komprimierung kann hilfreich sein, wenn Sie die Größe der generierten Dateien reduzieren müssen, insbesondere bei großen Dokumenten. Dies kann das Speichern, Teilen und Übertragen von Dokumenten erleichtern.

Aspose.Words für .NET bietet eine Reihe leistungsstarker Optionen und Funktionen zur Dokumentenbearbeitung. Durch die Verwendung der entsprechenden Sicherungsoptionen können Sie den Dokumentenerstellungsprozess anpassen und die Leistung Ihrer Anwendung optimieren.

Entdecken Sie gerne weitere Funktionen von Aspose.Words für .NET, um Ihren Workflow bei der Dokumentenerstellung zu verbessern.
