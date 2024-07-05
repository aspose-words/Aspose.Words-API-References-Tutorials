---
title: Eigenschaft „Zuletzt gespeicherter Zeitpunkt aktualisieren“
linktitle: Eigenschaft „Zuletzt gespeicherter Zeitpunkt aktualisieren“
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie die Eigenschaft „Letzte Speicherzeit“ beim Speichern eines Dokuments mit Aspose.Words für .NET automatisch aktualisieren.
type: docs
weight: 10
url: /de/net/programming-with-ooxmlsaveoptions/update-last-saved-time-property/
---
In diesem Tutorial untersuchen wir den bereitgestellten C#-Quellcode, um die Eigenschaft „Letzte Speicherzeit“ beim Speichern eines Dokuments mit Aspose.Words für .NET zu aktualisieren. Mit dieser Funktion können Sie die Eigenschaft „Letzte Speicherzeit“ des generierten Dokuments automatisch aktualisieren.

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
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };
```

 In diesem Schritt konfigurieren wir OOXML-Speicheroptionen mit dem`OoxmlSaveOptions` Klasse. Wir aktivieren die automatische Aktualisierung der Eigenschaft „Letzte Speicherzeit“, indem wir`UpdateLastSavedTimeProperty` Zu`true`.

## Schritt 4: Dokument mit aktualisierter Eigenschaft speichern

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
```

 Im letzten Schritt speichern wir das Dokument mit dem`Save` -Methode und Übergabe des Pfades zur Ausgabedatei mit der`.docx` Erweiterung, zusammen mit den angegebenen Speicheroptionen.

Jetzt können Sie den Quellcode ausführen, um die Eigenschaft „Letzte Speicherzeit“ beim Speichern eines Dokuments automatisch zu aktualisieren. Die resultierende Datei wird im angegebenen Verzeichnis unter dem Namen „WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx“ gespeichert.

### Beispielquellcode zum Aktualisieren der Eigenschaft „Zuletzt gespeicherte Zeit“ mit Aspose.Words für .NET 

```csharp

// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
            
        
```

## Abschluss

In diesem Tutorial haben wir die Funktion zum automatischen Aktualisieren der Eigenschaft „Letzte Speicherzeit“ beim Speichern eines Dokuments mit Aspose.Words für .NET untersucht. Indem Sie diese Funktion mit OOXML-Speicheroptionen aktivieren, können Sie sicherstellen, dass die Eigenschaft „Letzte Speicherzeit“ im generierten Dokument automatisch aktualisiert wird.

Das Aktualisieren der Eigenschaft „Letzte Speicherzeit“ kann hilfreich sein, um Änderungen und Versionen eines Dokuments zu verfolgen. Außerdem wird protokolliert, wann das Dokument zuletzt gespeichert wurde, was in verschiedenen Szenarien nützlich sein kann.

Aspose.Words für .NET erleichtert die automatische Aktualisierung der Eigenschaft „Letzte Sicherungszeit“, indem es flexible und leistungsstarke Sicherungsoptionen bereitstellt. Sie können diese Funktion in Ihre Projekte integrieren, um sicherzustellen, dass generierte Dokumente über genaue Sicherungsinformationen verfügen.