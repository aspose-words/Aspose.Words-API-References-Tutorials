---
title: Mit dem Zertifikatsinhaber eine digitale Signatur zum PDF hinzufügen
linktitle: Mit dem Zertifikatsinhaber eine digitale Signatur zum PDF hinzufügen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Certificate Holder und Aspose.Words für .NET eine digitale Signatur zu PDF-Dateien hinzufügen.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/digitally-signed-pdf-using-certificate-holder/
---

In diesem Tutorial führen wir Sie durch die Schritte zum Hinzufügen einer digitalen Signatur zu PDF mithilfe des Zertifikatsinhabers mit Aspose.Words für .NET. Die digitale Signatur fügt dem PDF-Dokument eine Sicherheits- und Integritätsebene hinzu. Befolgen Sie die folgenden Schritte:

## Schritt 1: Dokument erstellen und Inhalt hinzufügen

Beginnen Sie mit der Erstellung einer Instanz der Klasse „Document“:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Dem Dokument Inhalt hinzufügen

 Verwenden Sie dann die`DocumentBuilder`um Inhalt zum Dokument hinzuzufügen. Um beispielsweise einen Absatz mit dem Text "Test Signiertes PDF" hinzuzufügen, verwenden Sie die`Writeln` Methode:

```csharp
builder.Writeln("Test Signed PDF.");
```

Sie können nach Bedarf weitere Inhaltselemente hinzufügen.

## Schritt 3: PDF-Speicheroptionen festlegen

Erstellen Sie eine Instanz der Klasse PdfSaveOptions und geben Sie die Details der digitalen Signatur an:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
	DigitalSignatureDetails = new PdfDigitalSignatureDetails(
		CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
		DateTime.Now)
};
```

Achten Sie darauf, den korrekten Pfad zu Ihrem Zertifikat und dem dazugehörigen Passwort anzugeben. Signaturgrund und -speicherort können Sie ebenfalls individuell anpassen.

## Schritt 4: Dokument als digital signiertes PDF speichern

 Verwenden Sie die`Save` Methode zum Speichern des Dokuments als PDF durch Angabe der Speicheroptionen:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
```

Stellen Sie sicher, dass Sie den richtigen Pfad zum Speichern der digital signierten PDF-Datei angeben.

Wenn Sie diese Schritte befolgen, können Sie mit Aspose.Words für .NET ganz einfach eine digital signierte PDF-Datei mit einem Zertifikat erstellen.

### Beispielquellcode für digital signiertes PDF mit Zertifikatsinhaber unter Verwendung von Aspose.Words für .NET

Hier ist der vollständige Quellcode zum digital signierten PDF mit Zertifikatsinhaber aus einem Dokument unter Verwendung von Aspose.Words für .NET:

```csharp

            // Der Pfad zum Dokumentverzeichnis.
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

In diesem Tutorial haben wir die Schritte zum Hinzufügen einer digitalen Signatur zu einem PDF-Dokument mithilfe eines Zertifikats mit Aspose.Words für .NET untersucht. Die digitale Signatur fügt dem Dokument eine Sicherheits- und Integritätsebene hinzu, garantiert so seine Authentizität und ermöglicht die Erkennung nachfolgender Änderungen. Indem Sie die angegebenen Schritte befolgen, können Sie mithilfe eines Zertifikats mit Aspose.Words für .NET ganz einfach ein digital signiertes PDF erstellen.

### Häufig gestellte Fragen

#### F: Was ist eine digitale Signatur und warum ist sie in einem PDF-Dokument wichtig?
A: Eine digitale Signatur ist eine Sicherheitstechnik, die die Authentizität, Integrität und Nichtabstreitbarkeit eines elektronischen Dokuments, beispielsweise einer PDF-Datei, gewährleistet. Mithilfe eines digitalen Zertifikats wird dem Dokument eine zusätzliche Sicherheitsebene hinzugefügt, mit der die Identität des Autors überprüft und nachträgliche Änderungen am Inhalt erkannt werden können.

#### F: Wie kann ich mit Aspose.Words für .NET mithilfe eines Zertifikats einem PDF-Dokument eine digitale Signatur hinzufügen?
A: Um einem PDF-Dokument mit einem Zertifikat mit Aspose.Words für .NET eine digitale Signatur hinzuzufügen, gehen Sie folgendermaßen vor:

 Erstellen Sie eine Instanz des`Document` Klasse zur Darstellung des Dokuments.

 Verwenden Sie die`DocumentBuilder` Klasse, um dem Dokument den gewünschten Inhalt hinzuzufügen.

 Erstellen Sie eine Instanz des`PdfSaveOptions` und geben Sie die Details der digitalen Signatur mit dem`PdfDigitalSignatureDetails` Klasse. Sie müssen den Pfad zum Zertifikat angeben (`CertificateHolder.Create`), das zugehörige Passwort sowie den Signaturgrund und -ort.

 Verwenden Sie die`Save` Methode zum Speichern des Dokuments im PDF-Format unter Angabe der Speicheroptionen.

#### F: Wie erhalte ich ein Zertifikat, um einem PDF-Dokument eine digitale Signatur hinzuzufügen?
A: Um ein Zertifikat zum Hinzufügen einer digitalen Signatur zu einem PDF-Dokument zu erhalten, können Sie sich normalerweise an eine Zertifizierungsstelle (CA) oder einen Vertrauensdienstanbieter wenden. Diese Stellen stellen digitale Zertifikate aus, nachdem sie Ihre Identität überprüft und Ihre Anfrage validiert haben. Sobald Sie ein Zertifikat erhalten haben, können Sie es in Ihrer Anwendung verwenden, um PDF-Dokumenten digitale Signaturen hinzuzufügen.

#### F: Ist es möglich, die Details der digitalen Signatur, wie etwa Grund und Ort, anzupassen?
 A: Ja, Sie können die Details der digitalen Signatur anpassen, indem Sie den Grund und den Ort der Signatur angeben. Im bereitgestellten Beispielcode können Sie die Werte der`reason`Und`location` Parameter beim Erstellen der`PdfDigitalSignatureDetails` Objekt. Stellen Sie sicher, dass Sie für jeden Parameter die entsprechenden Informationen angeben, um den Grund und den Ort der Signatur in Ihrem PDF-Dokument anzugeben.