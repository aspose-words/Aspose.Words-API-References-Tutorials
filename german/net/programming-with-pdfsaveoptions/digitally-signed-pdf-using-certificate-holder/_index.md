---
title: Digital signiertes PDF mit Zertifikatsinhaber
linktitle: Digital signiertes PDF mit Zertifikatsinhaber
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein PDF mithilfe eines Zertifikatsinhabers digital signieren.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/digitally-signed-pdf-using-certificate-holder/
---

In diesem Tutorial führen wir Sie durch die Schritte zum Erstellen einer digital signierten PDF-Datei mithilfe eines Zertifikats mit Aspose.Words für .NET. Die digitale Signatur fügt dem PDF-Dokument eine Ebene der Sicherheit und Integrität hinzu. Folgen Sie den unteren Schritten:

## Schritt 1: Dokument erstellen und Inhalte hinzufügen

Erstellen Sie zunächst eine Instanz der Document-Klasse:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Inhalte zum Dokument hinzufügen

 Dann nutzen Sie die`DocumentBuilder` um dem Dokument Inhalte hinzuzufügen. Um beispielsweise einen Absatz mit dem Text „Test Signed PDF“ hinzuzufügen, verwenden Sie die`Writeln` Methode:

```csharp
builder.Writeln("Test Signed PDF.");
```

Sie können bei Bedarf weitere Inhaltselemente hinzufügen.

## Schritt 3: Legen Sie die PDF-Speicheroptionen fest

Erstellen Sie eine Instanz der PdfSaveOptions-Klasse und geben Sie die Details der digitalen Signatur an:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
	DigitalSignatureDetails = new PdfDigitalSignatureDetails(
		CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
		DateTime.Now)
};
```

Stellen Sie sicher, dass Sie den richtigen Pfad zu Ihrem Zertifikat und das zugehörige Passwort angeben. Sie können auch den Grund und den Ort der Signatur anpassen.

## Schritt 4: Dokument als digital signiertes PDF speichern

 Benutzen Sie die`Save` Methode zum Speichern des Dokuments als PDF durch Angabe der Speicheroptionen:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
```

Stellen Sie sicher, dass Sie den richtigen Pfad zum Speichern der digital signierten PDF-Datei angeben.

Wenn Sie diese Schritte befolgen, können Sie mit Aspose.Words für .NET ganz einfach eine digital signierte PDF-Datei mit einem Zertifikat erstellen.

### Beispielquellcode für digital signiertes PDF mit Zertifikatsinhaber unter Verwendung von Aspose.Words für .NET

Hier ist der vollständige Quellcode zum digital signierten PDF mithilfe des Zertifikatsinhabers aus einem Dokument mit Aspose.Words für .NET:

```csharp

            // Der Pfad zum Dokumentenverzeichnis.
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);
            
            builder.Writeln("Test Signed PDF.");

            PdfSaveOptions saveOptions = new PdfSaveOptions
            {
                DigitalSignatureDetails = new PdfDigitalSignatureDetails(
                    CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
                    DateTime.Now)
            };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
            
        
```
