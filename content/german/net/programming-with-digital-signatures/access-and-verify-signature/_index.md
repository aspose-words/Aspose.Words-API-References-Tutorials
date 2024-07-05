---
title: Auf die Signatur im Word-Dokument zugreifen und diese überprüfen
linktitle: Auf die Signatur im Word-Dokument zugreifen und diese überprüfen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET auf digitale Signaturen in einem Word-Dokument zugreifen und diese überprüfen.
type: docs
weight: 10
url: /de/net/programming-with-digital-signatures/access-and-verify-signature/
---
In diesem Tutorial führen wir Sie durch die Schritte zur Verwendung der Zugriffs- und Signaturüberprüfungsfunktion von Aspose.Words für .NET. Mit dieser Funktion können Sie auf digitale Signaturen in einem Word-Dokument zugreifen und deren Gültigkeit überprüfen. Befolgen Sie die folgenden Schritte:

## Schritt 1: Dokument laden und Signaturen abrufen

Beginnen Sie mit dem Hochladen des Dokuments mit den digitalen Signaturen:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Digitally signed.docx");
```

## Schritt 2: Digitale Signaturen durchsuchen

Verwenden Sie eine Schleife, um alle digitalen Signaturen im Dokument zu durchlaufen:

```csharp
foreach (DigitalSignature signature in doc.DigitalSignatures)
{
	// Zugriff auf Signaturinformationen
	Console.WriteLine("* Signature Found *");
	Console.WriteLine("Is valid: " + signature.IsValid);
	// Diese Eigenschaft ist nur in MS Word-Dokumenten verfügbar.
	Console.WriteLine("Reason for signing: " + signature.Comments); 
	Console.WriteLine("Time of signing: " + signature.SignTime);
	Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
	Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
	Console.WriteLine();
}
```

Denken Sie daran, die Anzeigemeldungen Ihren Bedürfnissen entsprechend anzupassen.

### Beispielquellcode für Access And Verify Signature mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für die Zugriffs- und Signaturüberprüfung mit Aspose.Words für .NET:

```csharp
	
	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Digitally signed.docx");

	foreach (DigitalSignature signature in doc.DigitalSignatures)
	{
		Console.WriteLine("* Signature Found *");
		Console.WriteLine("Is valid: " + signature.IsValid);
		// Diese Eigenschaft ist nur in MS Word-Dokumenten verfügbar.
		Console.WriteLine("Reason for signing: " + signature.Comments); 
		Console.WriteLine("Time of signing: " + signature.SignTime);
		Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
		Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
		Console.WriteLine();
	}

```

Wenn Sie diese Schritte befolgen, können Sie mit Aspose.Words für .NET problemlos auf die digitalen Signaturen in Ihrem Word-Dokument zugreifen und diese überprüfen.

## Abschluss

In diesem Tutorial haben wir die Funktion zum Zugreifen auf und Überprüfen digitaler Signaturen in einem Word-Dokument mithilfe von Aspose.Words für .NET untersucht. Indem Sie die angegebenen Schritte befolgen, können Sie problemlos ein Dokument laden, auf seine digitalen Signaturen zugreifen und deren Gültigkeit überprüfen. Die Möglichkeit, auf digitale Signaturen zuzugreifen und diese zu überprüfen, bietet eine Möglichkeit, die Integrität und Authentizität Ihrer Word-Dokumente sicherzustellen. Aspose.Words für .NET bietet eine leistungsstarke API für die Textverarbeitung mit digitalen Signaturen, mit der Sie den Überprüfungsprozess automatisieren und die Sicherheit Ihrer Dokumente verbessern können.

### Häufig gestellte Fragen

#### F: Was sind digitale Signaturen in einem Word-Dokument?

A: Digitale Signaturen in einem Word-Dokument sind elektronische Signaturen, mit denen die Integrität und Herkunft des Dokuments authentifiziert werden kann. Sie werden mithilfe digitaler Zertifikate und kryptografischer Algorithmen erstellt, sodass Empfänger überprüfen können, dass das Dokument nicht verändert wurde und aus einer vertrauenswürdigen Quelle stammt.

#### F: Wie kann ich mit Aspose.Words für .NET auf digitale Signaturen in einem Word-Dokument zugreifen?

A: Um mit Aspose.Words für .NET auf digitale Signaturen in einem Word-Dokument zuzugreifen, können Sie diese Schritte befolgen:
1.  Laden Sie das Dokument mit dem`Document` Klasse und geben Sie den Pfad zur Dokumentdatei an.
2.  Verwenden Sie eine Schleife zum Durchlaufen der`DigitalSignatures` Sammlung des Dokuments. Jede Iteration stellt eine digitale Signatur dar.

#### F: Auf welche Informationen kann ich aus einer digitalen Signatur in einem Word-Dokument zugreifen?

A: Über eine digitale Signatur in einem Word-Dokument können Sie auf verschiedene Informationen zugreifen, beispielsweise:
- Gültigkeit: Überprüfen Sie, ob die Signatur gültig ist.
- Kommentare: Erhalten Sie den vom Unterzeichner angegebenen Grund für die Unterschrift.
- Zeitpunkt der Unterzeichnung: Erhalten Sie den Zeitpunkt der Unterzeichnung des Dokuments.
- Betreffname: Rufen Sie den Namen des Unterzeichners oder des Zertifikatsbetreffs ab.
- Name des Ausstellers: Rufen Sie den Namen des Zertifikatsausstellers ab.

#### F: Kann ich mit Aspose.Words für .NET die Gültigkeit einer digitalen Signatur in einem Word-Dokument überprüfen?

 A: Ja, Sie können die Gültigkeit einer digitalen Signatur in einem Word-Dokument mit Aspose.Words für .NET überprüfen. Durch Zugriff auf die`IsValid` Eigentum der`DigitalSignature` Objekt können Sie feststellen, ob die Signatur gültig ist oder nicht.

#### F: Wie kann ich mit Aspose.Words für .NET die Gültigkeit digitaler Signaturen in einem Word-Dokument überprüfen?

A: Um die Gültigkeit digitaler Signaturen in einem Word-Dokument mit Aspose.Words für .NET zu überprüfen, können Sie diese Schritte ausführen:
1.  Greife auf ... zu`DigitalSignatures` Sammlung des Dokuments.
2.  Durchlaufen Sie alle`DigitalSignature` Objekt in der Sammlung.
3.  Verwenden Sie die`IsValid` Eigentum der`DigitalSignature` Objekt, um zu überprüfen, ob die Signatur gültig ist.

#### F: Kann ich aus einer digitalen Signatur in einem Word-Dokument die Kommentare oder den Grund für die Unterschrift des Unterzeichners abrufen?

A: Ja, Sie können die Kommentare oder den Grund für die Unterschrift des Unterzeichners aus einer digitalen Signatur in einem Word-Dokument abrufen.`Comments` Eigentum der`DigitalSignature` -Objekt bietet Zugriff auf die vom Unterzeichner während des Signaturvorgangs angegebenen Kommentare.

#### F: Welche Dokumenttypen werden von der Signaturüberprüfungsfunktion in Aspose.Words für .NET unterstützt?

A: Die Signaturüberprüfungsfunktion in Aspose.Words für .NET unterstützt die Überprüfung digitaler Signaturen in Word-Dokumenten im DOCX-Dateiformat. Sie können diese Funktion verwenden, um Signaturen in DOCX-Dateien zu überprüfen.

#### F: Wie kann ich mit Aspose.Words für .NET auf die Zertifikatsdetails einer digitalen Signatur in einem Word-Dokument zugreifen?

 A: Um auf die Zertifikatsdetails einer digitalen Signatur in einem Word-Dokument mit Aspose.Words für .NET zuzugreifen, können Sie auf die`CertificateHolder` Eigentum der`DigitalSignature` Objekt. Aus dem`CertificateHolder` -Objekt können Sie verschiedene Details des Zertifikats abrufen, beispielsweise den Betreff und den Namen des Ausstellers.

#### F: Kann ich die Anzeige oder Verarbeitung digitaler Signaturen in einem Word-Dokument mit Aspose.Words für .NET anpassen?

 A: Ja, Sie können die Anzeige oder Verarbeitung digitaler Signaturen in einem Word-Dokument mit Aspose.Words für .NET anpassen. Durch Zugriff auf die Eigenschaften und Methoden des`DigitalSignature` Objekt können Sie die gewünschten Informationen extrahieren, zusätzliche Validierungen durchführen oder den Signaturüberprüfungsprozess in den Workflow Ihrer Anwendung integrieren.

#### F: Ist es möglich, mit Aspose.Words für .NET mehrere digitale Signaturen in einem Word-Dokument zu überprüfen?

 A: Ja, es ist möglich, mehrere digitale Signaturen in einem Word-Dokument mit Aspose.Words für .NET zu überprüfen. Durch Iteration durch die`DigitalSignatures` Durch die Dokumentensammlung können Sie auf jede digitale Signatur einzeln zugreifen und diese prüfen.

