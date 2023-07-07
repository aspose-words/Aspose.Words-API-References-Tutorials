---
title: Fügen Sie mithilfe des Zertifikatsinhabers eine digitale Signatur zu PDF hinzu
linktitle: Fügen Sie mithilfe des Zertifikatsinhabers eine digitale Signatur zu PDF hinzu
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mithilfe von Certificate Holder mit Aspose.Words für .NET eine digitale Signatur zu PDF hinzufügen.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/digitally-signed-pdf-using-certificate-holder/
---

In diesem Tutorial führen wir Sie durch die Schritte zum Hinzufügen einer digitalen Signatur zu PDF mithilfe des Zertifikatsinhabers mit Aspose.Words für .NET. Die digitale Signatur fügt dem PDF-Dokument eine Ebene der Sicherheit und Integrität hinzu. Folgen Sie den unteren Schritten:

## Schritt 1: Dokument erstellen und Inhalte hinzufügen

Erstellen Sie zunächst eine Instanz der Document-Klasse:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Inhalte zum Dokument hinzufügen

 Dann nutzen Sie die`DocumentBuilder`um dem Dokument Inhalte hinzuzufügen. Um beispielsweise einen Absatz mit dem Text „Test Signed PDF“ hinzuzufügen, verwenden Sie die`Writeln` Methode:

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
## Abschluss

In diesem Tutorial haben wir die Schritte zum Hinzufügen einer digitalen Signatur zu einem PDF-Dokument mithilfe eines Zertifikats mit Aspose.Words für .NET untersucht. Die digitale Signatur verleiht dem Dokument eine zusätzliche Sicherheits- und Integritätsebene, garantiert so seine Authentizität und ermöglicht die Erkennung späterer Änderungen. Wenn Sie die angegebenen Schritte befolgen, können Sie mit Aspose.Words für .NET ganz einfach ein digital signiertes PDF mithilfe eines Zertifikats erstellen.

### Häufig gestellte Fragen

#### F: Was ist eine digitale Signatur und warum ist sie in einem PDF-Dokument wichtig?
A: Eine digitale Signatur ist eine Sicherheitstechnik, die dabei hilft, die Authentizität, Integrität und Nichtabstreitbarkeit eines elektronischen Dokuments, beispielsweise einer PDF-Datei, sicherzustellen. Es verwendet ein digitales Zertifikat, um dem Dokument eine Sicherheitsebene hinzuzufügen, die dabei hilft, die Identität des Autors zu überprüfen und spätere Änderungen am Inhalt zu erkennen.

#### F: Wie kann ich mit Aspose.Words für .NET mithilfe eines Zertifikats eine digitale Signatur zu einem PDF-Dokument hinzufügen?
A: Um mithilfe eines Zertifikats mit Aspose.Words für .NET eine digitale Signatur zu einem PDF-Dokument hinzuzufügen, führen Sie die folgenden Schritte aus:

 Erstellen Sie eine Instanz von`Document` Klasse zur Darstellung des Dokuments.

 Benutzen Sie die`DocumentBuilder` Klasse, um dem Dokument den gewünschten Inhalt hinzuzufügen.

 Erstellen Sie eine Instanz von`PdfSaveOptions` Klasse und geben Sie die Details der digitalen Signatur mithilfe von an`PdfDigitalSignatureDetails` Klasse. Sie müssen den Pfad zum Zertifikat angeben (`CertificateHolder.Create`), das zugehörige Passwort sowie den Grund und Ort der Signatur.

 Benutzen Sie die`Save` Methode zum Speichern des Dokuments im PDF-Format unter Angabe der Speicheroptionen.

#### F: Wie erhalte ich ein Zertifikat zum Hinzufügen einer digitalen Signatur zu einem PDF-Dokument?
A: Um ein Zertifikat zum Hinzufügen einer digitalen Signatur zu einem PDF-Dokument zu erhalten, können Sie sich normalerweise an eine Zertifizierungsstelle (CA) oder einen Vertrauensdienstanbieter wenden. Diese Unternehmen stellen digitale Zertifikate aus, nachdem sie Ihre Identität überprüft und Ihre Anfrage validiert haben. Sobald Sie ein Zertifikat erhalten haben, können Sie es in Ihrer Bewerbung verwenden, um PDF-Dokumente mit digitalen Signaturen zu versehen.

#### F: Ist es möglich, die Details der digitalen Signatur, z. B. Grund und Ort, anzupassen?
 A: Ja, Sie können die Details der digitalen Signatur anpassen, indem Sie den Grund und den Ort der Signatur angeben. Im bereitgestellten Beispielcode können Sie die Werte von ändern`reason` Und`location` Parameter beim Erstellen der`PdfDigitalSignatureDetails` Objekt. Stellen Sie sicher, dass Sie für jeden Parameter geeignete Informationen angeben, um den Grund und die Position der Signatur in Ihrem PDF-Dokument widerzuspiegeln.