---
title: Signieren eines verschlüsselten Word-Dokuments
linktitle: Signieren eines verschlüsselten Word-Dokuments
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein verschlüsseltes Word-Dokument digital signieren.
type: docs
weight: 10
url: /de/net/programming-with-digital-signatures/signing-encrypted-document/
---
In diesem Tutorial führen wir Sie durch die Schritte zur Verwendung der Funktion zum Signieren eines verschlüsselten Word-Dokuments mit Aspose.Words für .NET. Mit dieser Funktion können Sie ein Word-Dokument digital signieren, das mit einem Entschlüsselungskennwort verschlüsselt ist. Befolgen Sie die folgenden Schritte:

## Schritt 1: Signaturoptionen festlegen

Erstellen Sie eine Instanz der SignOptions-Klasse und legen Sie das Entschlüsselungskennwort fest:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionpassword" };
```

Geben Sie unbedingt das richtige Entschlüsselungskennwort für Ihr verschlüsseltes Dokument an.

## Schritt 2: Zertifikat laden

Beginnen Sie mit dem Laden des Signaturzertifikats mithilfe der Klasse CertificateHolder:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Achten Sie darauf, den richtigen Pfad zu Ihrem Zertifikat und dem zugehörigen Passwort anzugeben.

## Schritt 3: Signieren des verschlüsselten Dokuments

Verwenden Sie die Klasse DigitalSignatureUtil, um das verschlüsselte Dokument zu signieren:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
	certHolder, signOptions);
```

Achten Sie darauf, die richtigen Pfade für das verschlüsselte Dokument, das signierte Dokument und das Zertifikat anzugeben.

### Beispielquellcode zum Signieren verschlüsselter Dokumente mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zum Signieren eines verschlüsselten Dokuments mit Aspose.Words für .NET:

```csharp

	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionPassword" };

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
		certHolder, signOptions);
	

```
Indem Sie diese Schritte befolgen, können Sie mit Aspose.Words für .NET ganz einfach ein verschlüsseltes Word-Dokument signieren.

## Abschluss

In diesem Tutorial haben wir den Prozess der Signierung eines verschlüsselten Word-Dokuments mit Aspose.Words für .NET untersucht. Indem wir das Entschlüsselungskennwort und das Signaturzertifikat angeben, können wir einem verschlüsselten Dokument eine digitale Signatur hinzufügen. Das Signieren verschlüsselter Dokumente stellt deren Authentizität und Integrität sicher und bietet eine zusätzliche Sicherheitsebene. Mit Aspose.Words für .NET können Sie verschlüsselte Dokumente signieren und die Sicherheit und Vertrauenswürdigkeit Ihrer Word-Dateien aufrechterhalten.

### Häufig gestellte Fragen

#### F: Was ist Dokumentsignierung in Aspose.Words für .NET?

A: Unter Dokumentsignierung in Aspose.Words für .NET versteht man den Vorgang, ein Word-Dokument digital zu signieren, um dessen Authentizität, Integrität und Nichtabstreitbarkeit sicherzustellen. Dabei wird dem Dokument mithilfe eines Zertifikats eine digitale Signatur hinzugefügt.

#### F: Was ist ein verschlüsseltes Word-Dokument?

A: Ein verschlüsseltes Word-Dokument ist ein Dokument, das mit einem Kennwort verschlüsselt wurde. Die Verschlüsselung ist eine Sicherheitsmaßnahme, die den Inhalt des Dokuments schützt, indem sie ihn verschlüsselt und ohne das richtige Entschlüsselungskennwort unlesbar macht.

#### F: Wie kann ich mit Aspose.Words für .NET ein verschlüsseltes Word-Dokument signieren?

A: Um ein verschlüsseltes Word-Dokument mit Aspose.Words für .NET zu signieren, müssen Sie das Entschlüsselungskennwort zusammen mit dem Signaturzertifikat angeben. Folgen Sie diesen Schritten:
1.  Legen Sie das Entschlüsselungskennwort im`SignOptions` Objekt.
2.  Laden Sie das Signaturzertifikat mit dem`CertificateHolder` Klasse.
3.  Verwenden Sie die`DigitalSignatureUtil.Sign` Methode zum Signieren des verschlüsselten Dokuments unter Angabe der erforderlichen Parameter.

#### F: Was ist der Zweck der Unterzeichnung eines verschlüsselten Dokuments?

A: Wenn Sie ein verschlüsseltes Dokument mit Aspose.Words für .NET signieren, können Sie dem Dokument auch dann eine digitale Signatur hinzufügen, wenn es verschlüsselt ist. Dies bietet eine zusätzliche Sicherheitsebene und gewährleistet die Authentizität und Integrität des verschlüsselten Inhalts. Empfänger können damit den Ursprung des Dokuments überprüfen und Manipulationen erkennen.

#### F: Kann ich ein verschlüsseltes Dokument unterzeichnen, ohne das Entschlüsselungskennwort anzugeben?

A: Nein, um ein verschlüsseltes Dokument zu signieren, müssen Sie das richtige Entschlüsselungskennwort eingeben. Das Entschlüsselungskennwort ist erforderlich, um auf den verschlüsselten Inhalt des Dokuments zuzugreifen und ihn zu ändern, bevor die digitale Signatur angewendet wird.

#### F: Kann ich ein verschlüsseltes Word-Dokument mit einem beliebigen Zertifikat signieren?

A: Um ein verschlüsseltes Word-Dokument mit Aspose.Words für .NET zu signieren, benötigen Sie ein gültiges X.509-Zertifikat. Das Zertifikat kann von einer vertrauenswürdigen Zertifizierungsstelle (CA) bezogen werden, oder es kann zu Testzwecken ein selbstsigniertes Zertifikat verwendet werden.

#### F: Kann ich mehrere verschlüsselte Word-Dokumente mit demselben Zertifikat signieren?

 A: Ja, Sie können mehrere verschlüsselte Word-Dokumente mit demselben Zertifikat signieren. Nachdem Sie das Zertifikat mit dem`CertificateHolder` Klasse können Sie sie wiederverwenden, um mehrere verschlüsselte Dokumente zu signieren.

#### F: Kann ich die digitale Signatur eines signierten verschlüsselten Dokuments überprüfen?

 A: Ja, Aspose.Words für .NET bietet Funktionen zur Überprüfung der digitalen Signatur eines signierten verschlüsselten Dokuments. Sie können die`DigitalSignatureUtil.Verify` Methode zur Überprüfung der Gültigkeit und Authentizität der digitalen Signatur.

#### F: Welches Dateiformat unterstützt Aspose.Words für .NET zum Signieren verschlüsselter Dokumente?

 A: Aspose.Words für .NET unterstützt das Signieren verschlüsselter Word-Dokumente im DOCX-Dateiformat. Sie können verschlüsselte DOCX-Dateien signieren mit dem`DigitalSignatureUtil.Sign` Methode zusammen mit dem erforderlichen Entschlüsselungskennwort und Zertifikat.

#### F: Welchen Einfluss hat das Signieren eines verschlüsselten Dokuments auf die Verschlüsselung?

A: Das Signieren eines verschlüsselten Dokuments mit Aspose.Words für .NET hat keine Auswirkungen auf die Verschlüsselung des Dokuments. Die Verschlüsselung bleibt erhalten und die digitale Signatur wird dem verschlüsselten Inhalt hinzugefügt. Die digitale Signatur bietet zusätzliche Sicherheit und Überprüfung, ohne die auf das Dokument angewendete Verschlüsselung zu beeinträchtigen.