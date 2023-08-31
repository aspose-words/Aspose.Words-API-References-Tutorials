---
title: Word-Dokument unterschreiben
linktitle: Word-Dokument unterschreiben
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie ein Word-Dokument mit Aspose.Words für .NET digital signieren.
type: docs
weight: 10
url: /de/net/programming-with-digital-signatures/sign-document/
---
In diesem Tutorial führen wir Sie durch die Schritte zur Verwendung der Funktion zum Signieren von Dokumenten mit Aspose.Words für .NET. Mit dieser Funktion können Sie ein Word-Dokument mithilfe eines Zertifikats digital signieren. Folgen Sie den unteren Schritten:

## Schritt 1: Laden des Zertifikats

Laden Sie zunächst das Signaturzertifikat mithilfe der CertificateHolder-Klasse:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Stellen Sie sicher, dass Sie den richtigen Pfad zu Ihrem Zertifikat und das zugehörige Passwort angeben.

## Schritt 2: Unterschreiben des Dokuments

Verwenden Sie die DigitalSignatureUtil-Klasse, um das Dokument zu signieren:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
	certHolder);
```

Stellen Sie sicher, dass Sie die richtigen Pfade für das Quelldokument und das signierte Dokument angeben.

### Beispielquellcode für Sign Document mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zum Signieren eines Dokuments mit Aspose.Words für .NET:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
		certHolder);

```

Wenn Sie diese Schritte befolgen, können Sie ganz einfach ein Word-Dokument mit Aspose.Words für .NET signieren.

## Abschluss

 In diesem Tutorial haben wir die Funktion zum Signieren von Dokumenten in Aspose.Words für .NET untersucht. Durch Laden eines Signaturzertifikats und Verwendung des`DigitalSignatureUtil.Sign` Mit dieser Methode können wir ein Word-Dokument digital signieren. Das Signieren von Dokumenten sorgt für die Authentifizierung und stellt die Integrität des Dokumentinhalts sicher, was es zu einer wertvollen Funktion für eine sichere und vertrauenswürdige Dokumentenverwaltung macht.

### FAQs zum Signieren von Word-Dokumenten

#### F: Was ist das Signieren von Dokumenten in Aspose.Words für .NET?

A: Das Signieren von Dokumenten in Aspose.Words für .NET bezieht sich auf den Prozess des digitalen Signierens eines Word-Dokuments mithilfe eines Zertifikats. Diese Funktion fügt dem Dokument eine digitale Signatur hinzu und sorgt so für Authentizität, Integrität und Nichtabstreitbarkeit des Inhalts des Dokuments.

#### F: Wie kann ich das Signaturzertifikat in Aspose.Words für .NET laden?

 A: Um das Signaturzertifikat in Aspose.Words für .NET zu laden, können Sie das verwenden`CertificateHolder` Klasse. Erstellen Sie eine Instanz von`CertificateHolder` indem Sie den Pfad zur Zertifikatsdatei und das zugehörige Passwort angeben. Hier ist ein Beispiel:

```csharp
CertificateHolder certHolder = CertificateHolder.Create("path/to/certificate.pfx", "password");
```

Stellen Sie sicher, dass Sie den richtigen Pfad zu Ihrem Zertifikat und das zugehörige Passwort angeben.

#### F: Wie signiere ich ein Word-Dokument mit Aspose.Words für .NET?

 A: Um ein Word-Dokument mit Aspose.Words für .NET zu signieren, können Sie das verwenden`DigitalSignatureUtil` Klasse. Ruf den`Sign` -Methode, die den Pfad zum Quelldokument, den Pfad zum signierten Dokument (Ausgabe) und die angibt`CertificateHolder` Objekt. Hier ist ein Beispiel:

```csharp
DigitalSignatureUtil.Sign("path/to/source/document.docx", "path/to/signed/document.docx", certHolder);
```

Stellen Sie sicher, dass Sie die richtigen Pfade für das Quelldokument und das signierte Dokument (Ausgabe) angeben.

#### F: Was ist der Zweck der Dokumentensignierung?

A: Das Signieren von Dokumenten dient als Methode zur Sicherstellung der Authentizität und Integrität eines Dokuments. Durch die digitale Signatur eines Dokuments können Sie dessen Herkunft nachweisen, sicherstellen, dass der Inhalt nicht verändert wurde, und die Unbestreitbarkeit feststellen. Das Signieren von Dokumenten wird häufig für rechtliche, finanzielle und sensible Dokumente verwendet.

#### F: Kann ich jedes beliebige Zertifikat zum Signieren von Dokumenten in Aspose.Words für .NET verwenden?

A: Zum Signieren von Dokumenten in Aspose.Words für .NET müssen Sie ein gültiges X.509-Zertifikat verwenden. Dieses Zertifikat kann von einer vertrauenswürdigen Zertifizierungsstelle (CA) bezogen werden oder zu Testzwecken ein selbstsigniertes Zertifikat verwendet werden.

#### F: Welches Dateiformat unterstützt Aspose.Words für .NET zum Signieren von Dokumenten?

 A: Aspose.Words für .NET unterstützt das Signieren von Dokumenten für Word-Dokumente im DOCX-Dateiformat. Sie können DOCX-Dateien mit signieren`DigitalSignatureUtil` Klasse und das entsprechende Zertifikat.

#### F: Kann ich mehrere Word-Dokumente mit demselben Zertifikat signieren?

A: Ja, Sie können mehrere Word-Dokumente mit demselben Zertifikat signieren. Sobald Sie das Zertifikat mit geladen haben`CertificateHolder` Klasse können Sie sie zum Signieren mehrerer Dokumente wiederverwenden, indem Sie die aufrufen`DigitalSignatureUtil.Sign` Methode mit unterschiedlichen Quell- und signierten Dokumentpfaden.

#### F: Verändert das Signieren eines Dokuments das Originaldokument?

A: Durch das Signieren von Dokumenten mit Aspose.Words für .NET wird das Originaldokument nicht geändert. Stattdessen wird eine digital signierte Kopie des Dokuments erstellt, wobei das Originaldokument intakt bleibt. Die digital signierte Kopie enthält die hinzugefügte digitale Signatur und stellt so die Integrität des Dokumentinhalts sicher.

#### F: Kann ich die digitale Signatur eines signierten Dokuments mit Aspose.Words für .NET überprüfen?

 A: Ja, Aspose.Words für .NET bietet Funktionen zur Überprüfung der digitalen Signatur eines signierten Dokuments. Du kannst den ... benutzen`DigitalSignatureUtil.Verify` Methode zur Überprüfung der Gültigkeit und Authentizität der digitalen Signatur.