---
title: Signieren eines verschlüsselten Word-Dokuments
linktitle: Signieren eines verschlüsselten Word-Dokuments
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein verschlüsseltes Word-Dokument digital signieren.
type: docs
weight: 10
url: /de/net/programming-with-digital-signatures/signing-encrypted-document/
---
In diesem Tutorial führen wir Sie durch die Schritte zur Verwendung der Funktion zum Signieren eines verschlüsselten Word-Dokuments mit Aspose.Words für .NET. Mit dieser Funktion können Sie ein Word-Dokument digital signieren, das mit einem Entschlüsselungskennwort verschlüsselt ist. Folgen Sie den unteren Schritten:

## Schritt 1: Signaturoptionen festlegen

Erstellen Sie eine Instanz der SignOptions-Klasse und legen Sie das Entschlüsselungskennwort fest:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionpassword" };
```

Stellen Sie sicher, dass Sie das richtige Entschlüsselungskennwort für Ihr verschlüsseltes Dokument angeben.

## Schritt 2: Laden des Zertifikats

Laden Sie zunächst das Signaturzertifikat mithilfe der CertificateHolder-Klasse:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Stellen Sie sicher, dass Sie den richtigen Pfad zu Ihrem Zertifikat und das zugehörige Passwort angeben.

## Schritt 3: Signieren des verschlüsselten Dokuments

Verwenden Sie die DigitalSignatureUtil-Klasse, um das verschlüsselte Dokument zu signieren:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
	certHolder, signOptions);
```

Stellen Sie sicher, dass Sie die richtigen Pfade für das verschlüsselte Dokument, das signierte Dokument und das Zertifikat angeben.

### Beispielquellcode zum Signieren eines verschlüsselten Dokuments mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zum Signieren eines verschlüsselten Dokuments mit Aspose.Words für .NET:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionPassword" };

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
		certHolder, signOptions);
	

```
Wenn Sie diese Schritte befolgen, können Sie ganz einfach ein verschlüsseltes Word-Dokument mit Aspose.Words für .NET signieren.

## Abschluss

In diesem Tutorial haben wir den Prozess des Signierens eines verschlüsselten Word-Dokuments mit Aspose.Words für .NET untersucht. Durch die Bereitstellung des Entschlüsselungskennworts und des Signaturzertifikats können wir einem verschlüsselten Dokument eine digitale Signatur hinzufügen. Das Signieren verschlüsselter Dokumente stellt deren Authentizität und Integrität sicher und bietet eine zusätzliche Sicherheitsebene. Mit Aspose.Words für .NET können Sie verschlüsselte Dokumente signieren und die Sicherheit und Vertrauenswürdigkeit Ihrer Word-Dateien gewährleisten.

### FAQs

#### F: Was ist das Signieren von Dokumenten in Aspose.Words für .NET?

A: Das Signieren von Dokumenten in Aspose.Words für .NET bezieht sich auf den Prozess des digitalen Signierens eines Word-Dokuments, um dessen Authentizität, Integrität und Unbestreitbarkeit sicherzustellen. Dabei wird dem Dokument mithilfe eines Zertifikats eine digitale Signatur hinzugefügt.

#### F: Was ist ein verschlüsseltes Word-Dokument?

A: Ein verschlüsseltes Word-Dokument ist ein Dokument, das mit einem Passwort verschlüsselt wurde. Die Verschlüsselung ist eine Sicherheitsmaßnahme, die den Inhalt des Dokuments schützt, indem sie es verschlüsselt und ohne das richtige Entschlüsselungskennwort unlesbar macht.

#### F: Wie kann ich ein verschlüsseltes Word-Dokument mit Aspose.Words für .NET signieren?

A: Um ein verschlüsseltes Word-Dokument mit Aspose.Words für .NET zu signieren, müssen Sie das Entschlüsselungskennwort zusammen mit dem Signaturzertifikat angeben. Folge diesen Schritten:
1.  Legen Sie das Entschlüsselungskennwort fest`SignOptions` Objekt.
2.  Laden Sie das Signaturzertifikat mit`CertificateHolder` Klasse.
3.  Benutzen Sie die`DigitalSignatureUtil.Sign` Methode zum Signieren des verschlüsselten Dokuments unter Bereitstellung der erforderlichen Parameter.

#### F: Was ist der Zweck der Signatur eines verschlüsselten Dokuments?

A: Durch das Signieren eines verschlüsselten Dokuments mit Aspose.Words für .NET können Sie dem Dokument eine digitale Signatur hinzufügen, selbst wenn es verschlüsselt ist. Dies bietet eine zusätzliche Sicherheitsebene und stellt die Authentizität und Integrität der verschlüsselten Inhalte sicher. Es ermöglicht Empfängern, die Herkunft des Dokuments zu überprüfen und etwaige Manipulationen zu erkennen.

#### F: Kann ich ein verschlüsseltes Dokument signieren, ohne das Entschlüsselungskennwort anzugeben?

A: Nein, um ein verschlüsseltes Dokument zu signieren, müssen Sie das richtige Entschlüsselungskennwort angeben. Das Entschlüsselungskennwort ist erforderlich, um auf den verschlüsselten Inhalt des Dokuments zuzugreifen und ihn zu ändern, bevor die digitale Signatur angewendet wird.

#### F: Kann ich ein verschlüsseltes Word-Dokument mit einem beliebigen Zertifikat signieren?

A: Um ein verschlüsseltes Word-Dokument mit Aspose.Words für .NET zu signieren, benötigen Sie ein gültiges X.509-Zertifikat. Das Zertifikat kann von einer vertrauenswürdigen Zertifizierungsstelle (CA) bezogen werden oder zu Testzwecken ein selbstsigniertes Zertifikat verwendet werden.

#### F: Kann ich mehrere verschlüsselte Word-Dokumente mit demselben Zertifikat signieren?

 A: Ja, Sie können mehrere verschlüsselte Word-Dokumente mit demselben Zertifikat signieren. Sobald Sie das Zertifikat mit geladen haben`CertificateHolder` Klasse können Sie sie wiederverwenden, um mehrere verschlüsselte Dokumente zu signieren.

#### F: Kann ich die digitale Signatur eines signierten verschlüsselten Dokuments überprüfen?

 A: Ja, Aspose.Words für .NET bietet Funktionen zur Überprüfung der digitalen Signatur eines signierten verschlüsselten Dokuments. Du kannst den ... benutzen`DigitalSignatureUtil.Verify` Methode zur Überprüfung der Gültigkeit und Authentizität der digitalen Signatur.

#### F: Welches Dateiformat unterstützt Aspose.Words für .NET zum Signieren verschlüsselter Dokumente?

 A: Aspose.Words für .NET unterstützt das Signieren verschlüsselter Word-Dokumente im DOCX-Dateiformat. Sie können verschlüsselte DOCX-Dateien mit signieren`DigitalSignatureUtil.Sign` Methode zusammen mit dem notwendigen Entschlüsselungspasswort und Zertifikat.

#### F: Wie wirkt sich das Signieren eines verschlüsselten Dokuments auf die Verschlüsselung aus?

A: Das Signieren eines verschlüsselten Dokuments mit Aspose.Words für .NET hat keinen Einfluss auf die Verschlüsselung des Dokuments. Die Verschlüsselung bleibt erhalten und die digitale Signatur wird dem verschlüsselten Inhalt hinzugefügt. Die digitale Signatur bietet zusätzliche Sicherheit und Verifizierung, ohne die auf das Dokument angewendete Verschlüsselung zu beeinträchtigen.