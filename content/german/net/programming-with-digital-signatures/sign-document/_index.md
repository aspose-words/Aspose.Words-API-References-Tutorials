---
title: Word-Dokument signieren
linktitle: Word-Dokument signieren
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Word-Dokument digital signieren.
type: docs
weight: 10
url: /de/net/programming-with-digital-signatures/sign-document/
---
In diesem Tutorial führen wir Sie durch die Schritte zur Verwendung der Dokumentsignaturfunktion mit Aspose.Words für .NET. Mit dieser Funktion können Sie ein Word-Dokument mithilfe eines Zertifikats digital signieren. Befolgen Sie die folgenden Schritte:

## Schritt 1: Zertifikat laden

Beginnen Sie mit dem Laden des Signaturzertifikats mithilfe der Klasse CertificateHolder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Achten Sie darauf, den richtigen Pfad zu Ihrem Zertifikat und dem zugehörigen Passwort anzugeben.

## Schritt 2: Unterzeichnen des Dokuments

Verwenden Sie die Klasse DigitalSignatureUtil, um das Dokument zu signieren:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
	certHolder);
```

Achten Sie darauf, die richtigen Pfade für das Quelldokument und das signierte Dokument anzugeben.

### Beispielquellcode zum Signieren von Dokumenten mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zum Signieren eines Dokuments mit Aspose.Words für .NET:

```csharp

	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
		certHolder);

```

Indem Sie diese Schritte befolgen, können Sie ein Word-Dokument ganz einfach mit Aspose.Words für .NET signieren.

## Abschluss

 In diesem Tutorial haben wir die Funktion zur Dokumentsignatur in Aspose.Words für .NET untersucht. Durch Laden eines Signaturzertifikats und Verwenden des`DigitalSignatureUtil.Sign` Methode können wir ein Word-Dokument digital signieren. Die Dokumentsignatur dient der Authentifizierung und stellt die Integrität des Dokumentinhalts sicher. Damit ist sie eine wertvolle Funktion für eine sichere und vertrauenswürdige Dokumentenverwaltung.

### FAQs zum Signieren von Word-Dokumenten

#### F: Was ist Dokumentsignierung in Aspose.Words für .NET?

A: Unter Dokumentsignierung in Aspose.Words für .NET versteht man den Vorgang, ein Word-Dokument mithilfe eines Zertifikats digital zu signieren. Diese Funktion fügt dem Dokument eine digitale Signatur hinzu und sorgt so für Authentizität, Integrität und Nichtabstreitbarkeit des Dokumentinhalts.

#### F: Wie kann ich das Signaturzertifikat in Aspose.Words für .NET laden?

 A: Um das Signaturzertifikat in Aspose.Words für .NET zu laden, können Sie den`CertificateHolder` Klasse. Erstellen Sie eine Instanz von`CertificateHolder` indem Sie den Pfad zur Zertifikatsdatei und das zugehörige Passwort angeben. Hier ein Beispiel:

```csharp
CertificateHolder certHolder = CertificateHolder.Create("path/to/certificate.pfx", "password");
```

Achten Sie darauf, den korrekten Pfad zu Ihrem Zertifikat und das dazugehörige Passwort anzugeben.

#### F: Wie signiere ich ein Word-Dokument mit Aspose.Words für .NET?

 A: Um ein Word-Dokument mit Aspose.Words für .NET zu signieren, können Sie das`DigitalSignatureUtil` Klasse. Rufen Sie die`Sign` Methode, die den Pfad zum Quelldokument, den Pfad zum signierten Dokument (Ausgabe) und den`CertificateHolder` Objekt. Hier ist ein Beispiel:

```csharp
DigitalSignatureUtil.Sign("path/to/source/document.docx", "path/to/signed/document.docx", certHolder);
```

Stellen Sie sicher, dass Sie die richtigen Pfade für das Quelldokument und das signierte Dokument (Ausgabe) angeben.

#### F: Was ist der Zweck der Dokumentensignatur?

A: Das Signieren von Dokumenten dient dazu, die Authentizität und Integrität eines Dokuments sicherzustellen. Durch das digitale Signieren eines Dokuments können Sie dessen Herkunft nachweisen, sicherstellen, dass sein Inhalt nicht verändert wurde, und die Nichtabstreitbarkeit nachweisen. Das Signieren von Dokumenten wird häufig für juristische, finanzielle und vertrauliche Dokumente verwendet.

#### F: Kann ich in Aspose.Words für .NET jedes beliebige Zertifikat zum Signieren von Dokumenten verwenden?

A: Zum Signieren von Dokumenten in Aspose.Words für .NET müssen Sie ein gültiges X.509-Zertifikat verwenden. Dieses Zertifikat kann von einer vertrauenswürdigen Zertifizierungsstelle (CA) bezogen werden, oder es kann zu Testzwecken ein selbstsigniertes Zertifikat verwendet werden.

#### F: Welches Dateiformat unterstützt Aspose.Words für .NET für die Dokumentsignierung?

 A: Aspose.Words für .NET unterstützt die Dokumentsignatur für Word-Dokumente im DOCX-Dateiformat. Sie können DOCX-Dateien mit dem`DigitalSignatureUtil` Klasse und das entsprechende Zertifikat.

#### F: Kann ich mehrere Word-Dokumente mit demselben Zertifikat signieren?

A: Ja, Sie können mehrere Word-Dokumente mit demselben Zertifikat signieren. Nachdem Sie das Zertifikat mit dem`CertificateHolder` Klasse können Sie sie wiederverwenden, um mehrere Dokumente zu signieren, indem Sie die`DigitalSignatureUtil.Sign` Methode mit unterschiedlichen Quell- und signierten Dokumentpfaden.

#### F: Wird durch die Dokumentsignierung das Originaldokument geändert?

A: Das Signieren von Dokumenten mit Aspose.Words für .NET ändert das Originaldokument nicht. Stattdessen wird eine digital signierte Kopie des Dokuments erstellt, wobei das Originaldokument unverändert bleibt. Die digital signierte Kopie enthält die hinzugefügte digitale Signatur und stellt so die Integrität des Dokumentinhalts sicher.

#### F: Kann ich die digitale Signatur eines signierten Dokuments mit Aspose.Words für .NET überprüfen?

 A: Ja, Aspose.Words für .NET bietet Funktionen zur Überprüfung der digitalen Signatur eines signierten Dokuments. Sie können die`DigitalSignatureUtil.Verify` Methode zur Überprüfung der Gültigkeit und Authentizität der digitalen Signatur.