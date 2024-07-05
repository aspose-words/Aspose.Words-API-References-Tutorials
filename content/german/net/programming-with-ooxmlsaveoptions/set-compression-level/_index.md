---
title: Komprimierungsstufe festlegen
linktitle: Komprimierungsstufe festlegen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie die Komprimierungsstufe beim Speichern eines Dokuments mit Aspose.Words für .NET festlegen.
type: docs
weight: 10
url: /de/net/programming-with-ooxmlsaveoptions/set-compression-level/
---
In diesem Tutorial untersuchen wir den bereitgestellten C#-Quellcode, um den Komprimierungsgrad beim Speichern eines Dokuments mit Aspose.Words für .NET festzulegen. Mit dieser Funktion können Sie den Komprimierungsgrad des generierten Dokuments steuern.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie Ihre Entwicklungsumgebung mit Aspose.Words für .NET eingerichtet haben. Stellen Sie sicher, dass Sie die erforderlichen Referenzen hinzugefügt und die entsprechenden Namespaces importiert haben.

## Schritt 2: Dokument einlegen

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 In diesem Schritt laden wir das Dokument mit dem`Document` Methode und Übergabe des Pfads an die zu ladende DOCX-Datei.

## Schritt 3: OOXML-Sicherungsoptionen konfigurieren

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };
```

 In diesem Schritt konfigurieren wir OOXML-Speicheroptionen mit dem`OoxmlSaveOptions` Klasse. Wir setzen den Komprimierungsgrad auf`SuperFast` um eine schnellere Komprimierung zu erreichen.

## Schritt 4: Speichern Sie das Dokument mit der angegebenen Komprimierungsstufe

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
```

 Im letzten Schritt speichern wir das Dokument mit dem`Save` -Methode und Übergabe des Pfades zur Ausgabedatei mit der`.docx` Erweiterung, zusammen mit den angegebenen Speicheroptionen.

Jetzt können Sie den Quellcode ausführen, um die Komprimierungsstufe beim Speichern eines Dokuments festzulegen. Die resultierende Datei wird im angegebenen Verzeichnis unter dem Namen „WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx“ gespeichert.

### Beispielquellcode zum Festlegen der Komprimierungsstufe mit Aspose.Words für .NET 

```csharp

// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
            
        
```

## Abschluss

In diesem Tutorial haben wir die Funktion zum Festlegen der Komprimierungsstufe beim Speichern eines Dokuments mit Aspose.Words für .NET untersucht. Durch Festlegen der entsprechenden Komprimierungsstufe können Sie die Dokumentgröße und die Generierungsgeschwindigkeit optimieren.

 Der`OoxmlSaveOptions` Klasse bietet Flexibilität bei der Steuerung des Komprimierungsniveaus durch Festlegen der`CompressionLevel` Eigenschaft auf einen geeigneten Wert, wie`SuperFast`. So können Sie entsprechend Ihren spezifischen Anforderungen das richtige Gleichgewicht zwischen Dateigröße und Sicherungsgeschwindigkeit finden.

Die Verwendung der Komprimierung kann von Vorteil sein, wenn Sie die Größe der generierten Dateien reduzieren müssen, insbesondere bei großen Dokumenten. Dies kann das Speichern, Freigeben und Übertragen von Dokumenten erleichtern.

Aspose.Words für .NET bietet eine Reihe leistungsstarker Optionen und Funktionen zur Dokumentbearbeitung. Mithilfe der entsprechenden Sicherungsoptionen können Sie den Dokumentgenerierungsprozess anpassen und die Leistung Ihrer Anwendung optimieren.

Entdecken Sie weitere Funktionen von Aspose.Words für .NET, um Ihren Workflow zur Dokumenterstellung zu verbessern.
