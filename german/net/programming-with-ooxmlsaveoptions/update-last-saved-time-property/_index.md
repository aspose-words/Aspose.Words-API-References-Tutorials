---
title: Eigenschaft „Letzte gespeicherte Zeit“ aktualisieren
linktitle: Eigenschaft „Letzte gespeicherte Zeit“ aktualisieren
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie die Eigenschaft „Letzte gespeicherte Zeit“ automatisch aktualisieren, wenn Sie ein Dokument mit Aspose.Words für .NET speichern.
type: docs
weight: 10
url: /de/net/programming-with-ooxmlsaveoptions/update-last-saved-time-property/
---
In diesem Tutorial untersuchen wir den bereitgestellten C#-Quellcode, um die Eigenschaft „Letzte Speicherzeit“ zu aktualisieren, wenn ein Dokument mit Aspose.Words für .NET gespeichert wird. Mit dieser Funktion können Sie die Eigenschaft „Letzte Speicherzeit“ des generierten Dokuments automatisch aktualisieren.

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
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };
```

 In diesem Schritt konfigurieren wir OOXML-Speicheroptionen mithilfe von`OoxmlSaveOptions` Klasse. Wir aktivieren die automatische Aktualisierung der Eigenschaft „Letzte Speicherzeit“ durch Einstellung`UpdateLastSavedTimeProperty` Zu`true`.

## Schritt 4: Dokument mit aktualisierter Eigenschaft speichern

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
```

 In diesem letzten Schritt speichern wir das Dokument mit`Save` -Methode und Übergabe des Pfads zur Ausgabedatei mit der`.docx` Erweiterung zusammen mit den angegebenen Speicheroptionen.

Jetzt können Sie den Quellcode ausführen, um die Eigenschaft „Letzte Speicherzeit“ beim Speichern eines Dokuments automatisch zu aktualisieren. Die resultierende Datei wird im angegebenen Verzeichnis mit dem Namen „WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx“ gespeichert.

### Beispielquellcode für die Eigenschaft „Letzte gespeicherte Zeit aktualisieren“ mit Aspose.Words für .NET 

```csharp

// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
            
        
```

## Abschluss

In diesem Tutorial haben wir die Funktion der automatischen Aktualisierung der Eigenschaft „Letzte Speicherzeit“ beim Speichern eines Dokuments mit Aspose.Words für .NET untersucht. Durch die Aktivierung dieser Funktion mit OOXML-Speicheroptionen können Sie sicherstellen, dass die Eigenschaft „Letzter Speicherzeitpunkt“ im generierten Dokument automatisch aktualisiert wird.

Das Aktualisieren der Eigenschaft „Letzte Speicherzeit“ kann hilfreich sein, um Änderungen und Versionen eines Dokuments nachzuverfolgen. Es verfolgt auch, wann das Dokument zuletzt gespeichert wurde, was in verschiedenen Szenarien nützlich sein kann.

Aspose.Words für .NET erleichtert die automatische Aktualisierung der Eigenschaft „Letzte Sicherungszeit“ durch die Bereitstellung flexibler und leistungsstarker Sicherungsoptionen. Sie können diese Funktion in Ihre Projekte integrieren, um sicherzustellen, dass generierte Dokumente über korrekte Sicherungsinformationen verfügen.