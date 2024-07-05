---
title: Exportieren benutzerdefinierter Eigenschaften in ein PDF-Dokument
linktitle: Exportieren benutzerdefinierter Eigenschaften in ein PDF-Dokument
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie benutzerdefinierte Eigenschaften exportieren, wenn Sie Dokumente mit Aspose.Words für .NET in PDF konvertieren.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/custom-properties-export/
---

In diesem Tutorial führen wir Sie durch die Schritte zum Exportieren der benutzerdefinierten Eigenschaften eines Dokuments in ein PDF-Dokument mit Aspose.Words für .NET. Durch das Exportieren benutzerdefinierter Eigenschaften können Sie zusätzliche Informationen in das generierte PDF-Dokument aufnehmen. Befolgen Sie die folgenden Schritte:

## Schritt 1: Erstellen eines Dokuments und Hinzufügen benutzerdefinierter Eigenschaften

Beginnen Sie mit der Erstellung einer Instanz der Klasse „Document“:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Schritt 2: Benutzerdefinierte Eigenschaften hinzufügen
 Fügen Sie als Nächstes die gewünschten benutzerdefinierten Eigenschaften hinzu. Um beispielsweise eine Eigenschaft „Firma“ mit dem Wert „Aspose“ hinzuzufügen, verwenden Sie die`Add` Methode der CustomDocumentProperties-Sammlung:

```csharp
doc.CustomDocumentProperties.Add("Company", "Aspose");
```

Sie können beliebig viele benutzerdefinierte Eigenschaften hinzufügen.

## Schritt 3: PDF-Exportoptionen festlegen

Erstellen Sie eine Instanz der Klasse PdfSaveOptions und geben Sie an, wie benutzerdefinierte Eigenschaften exportiert werden sollen:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };
```

Diese Option steuert den Export benutzerdefinierter Eigenschaften bei der Konvertierung in PDF.

## Schritt 4: Dokument in PDF konvertieren

 Verwenden Sie die`Save` Methode zum Konvertieren des Dokuments in PDF unter Angabe der Konvertierungsoptionen:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);
```

Stellen Sie sicher, dass Sie den richtigen Pfad zum Speichern der konvertierten PDF-Datei angeben.

### Beispielquellcode für den Export benutzerdefinierter Eigenschaften mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zum Exportieren benutzerdefinierter Eigenschaften aus einem Dokument mit Aspose.Words für .NET:


```csharp

	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	doc.CustomDocumentProperties.Add("Company", "Aspose");

	PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);

```

Wenn Sie diese Schritte befolgen, können Sie benutzerdefinierte Eigenschaften eines Dokuments beim Konvertieren in PDF mit Aspose.Words für .NET problemlos exportieren.


## Abschluss

In diesem Tutorial haben wir erklärt, wie Sie mit Aspose.Words für .NET benutzerdefinierte Eigenschaften aus einem Dokument in ein PDF-Dokument exportieren. Indem Sie die beschriebenen Schritte befolgen, können Sie ganz einfach zusätzliche Informationen in das generierte PDF-Dokument aufnehmen, indem Sie die benutzerdefinierten Eigenschaften des Dokuments exportieren. Nutzen Sie die Funktionen von Aspose.Words für .NET, um Ihre PDF-Dokumente durch den Export benutzerdefinierter Eigenschaften zu personalisieren und zu erweitern.

### Häufig gestellte Fragen

#### F: Was bedeutet das Exportieren benutzerdefinierter Eigenschaften in ein PDF-Dokument?
A: Durch das Exportieren benutzerdefinierter Eigenschaften in ein PDF-Dokument können zusätzliche Informationen in das generierte PDF-Dokument aufgenommen werden. Benutzerdefinierte Eigenschaften sind Metadaten, die für Ihr Dokument spezifisch sind, wie z. B. Tags, Schlüsselwörter oder Anmeldeinformationen. Durch das Exportieren dieser benutzerdefinierten Eigenschaften können Sie sie Benutzern beim Anzeigen des PDF-Dokuments zur Verfügung stellen.

#### F: Wie kann ich die benutzerdefinierten Eigenschaften eines Dokuments mit Aspose.Words für .NET in ein PDF-Dokument exportieren?
A: Um die benutzerdefinierten Eigenschaften eines Dokuments mit Aspose.Words für .NET in ein PDF-Dokument zu exportieren, gehen Sie folgendermaßen vor:

 Erstellen Sie eine Instanz des`Document` Klasse.

 Fügen Sie die gewünschten benutzerdefinierten Eigenschaften hinzu, indem Sie`CustomDocumentProperties` Sammlung. Verwenden Sie beispielsweise die`Add` Methode, um eine „Company“-Eigenschaft mit dem Wert „Aspose“ hinzuzufügen.

 Erstellen Sie eine Instanz des`PdfSaveOptions` und geben Sie an, wie benutzerdefinierte Eigenschaften exportiert werden sollen. Dazu verwenden Sie die`CustomPropertiesExport` Eigentum. Die`PdfCustomPropertiesExport.Standard` Wert exportiert benutzerdefinierte Eigenschaften gemäß den Standardeinstellungen.

 Verwenden Sie die`Save` Methode der`Document` Klasse zum Konvertieren des Dokuments in PDF unter Angabe der Konvertierungsoptionen.

#### F: Wie kann ich auf benutzerdefinierte Eigenschaften eines PDF-Dokuments zugreifen?
A: Um auf die benutzerdefinierten Eigenschaften eines PDF-Dokuments zuzugreifen, können Sie einen kompatiblen PDF-Reader verwenden, der das Anzeigen von Dokumenteigenschaften unterstützt. Die meisten gängigen PDF-Reader, wie beispielsweise Adobe Acrobat Reader, bieten Zugriff auf Metadaten und Eigenschaften eines PDF-Dokuments. Normalerweise finden Sie diese Optionen im Menü „Datei“ oder indem Sie mit der rechten Maustaste auf das Dokument klicken und „Eigenschaften“ auswählen.