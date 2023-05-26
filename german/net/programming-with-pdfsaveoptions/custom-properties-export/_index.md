---
title: Benutzerdefinierte Eigenschaften exportieren
linktitle: Benutzerdefinierte Eigenschaften exportieren
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie benutzerdefinierte Eigenschaften exportieren, wenn Sie Dokumente mit Aspose.Words für .NET in PDF konvertieren.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/custom-properties-export/
---

In diesem Tutorial führen wir Sie durch die Schritte zum Exportieren der benutzerdefinierten Eigenschaften eines Dokuments mit Aspose.Words für .NET. Durch den Export benutzerdefinierter Eigenschaften können Sie zusätzliche Informationen in das generierte PDF-Dokument einfügen. Folgen Sie den unteren Schritten:

## Schritt 1: Erstellen eines Dokuments und Hinzufügen benutzerdefinierter Eigenschaften

Erstellen Sie zunächst eine Instanz der Document-Klasse:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Schritt 2: Benutzerdefinierte Eigenschaften hinzufügen
Fügen Sie als Nächstes die gewünschten benutzerdefinierten Eigenschaften hinzu. Um beispielsweise eine „Company“-Eigenschaft mit dem Wert „Aspose“ hinzuzufügen, verwenden Sie die`Add` Methode der CustomDocumentProperties-Sammlung:

```csharp
doc.CustomDocumentProperties.Add("Company", "Aspose");
```

Sie können beliebig viele benutzerdefinierte Eigenschaften hinzufügen.

## Schritt 3: PDF-Exportoptionen festlegen

Erstellen Sie eine Instanz der PdfSaveOptions-Klasse und geben Sie an, wie benutzerdefinierte Eigenschaften exportiert werden:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };
```

Diese Option steuert den Export benutzerdefinierter Eigenschaften beim Konvertieren in PDF.

## Schritt 4: Dokument in PDF konvertieren

 Benutzen Sie die`Save` Methode zum Konvertieren des Dokuments in PDF unter Angabe der Konvertierungsoptionen:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);
```

Stellen Sie sicher, dass Sie den richtigen Pfad zum Speichern der konvertierten PDF-Datei angeben.

### Beispielquellcode für den Export benutzerdefinierter Eigenschaften mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zum Exportieren benutzerdefinierter Eigenschaften aus einem Dokument mit Aspose.Words für .NET:


```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	doc.CustomDocumentProperties.Add("Company", "Aspose");

	PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);

```

Wenn Sie diese Schritte befolgen, können Sie beim Konvertieren in PDF mit Aspose.Words für .NET problemlos benutzerdefinierte Eigenschaften eines Dokuments exportieren.

