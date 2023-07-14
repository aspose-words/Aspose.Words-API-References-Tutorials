---
title: Auf die Signatur im Word-Dokument zugreifen und diese überprüfen
linktitle: Auf die Signatur im Word-Dokument zugreifen und diese überprüfen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET auf digitale Signaturen in einem Word-Dokument zugreifen und diese überprüfen.
type: docs
weight: 10
url: /de/net/programming-with-digital-signatures/access-and-verify-signature/
---
In diesem Tutorial führen wir Sie durch die Schritte zur Verwendung der Zugriffs- und Signaturüberprüfungsfunktion von Aspose.Words für .NET. Mit dieser Funktion können Sie auf digitale Signaturen in einem Word-Dokument zugreifen und deren Gültigkeit überprüfen. Folgen Sie den unteren Schritten:

## Schritt 1: Laden des Dokuments und Zugriff auf Signaturen

Beginnen Sie mit dem Hochladen des Dokuments mit digitalen Signaturen:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Digitally signed.docx");
```

## Schritt 2: Durchsuchen Sie digitale Signaturen

Verwenden Sie eine Schleife, um alle digitalen Signaturen im Dokument zu durchlaufen:

```csharp
foreach (DigitalSignature signature in doc.DigitalSignatures)
{
	// Greifen Sie auf Signaturinformationen zu
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

Passen Sie die angezeigten Meldungen unbedingt an Ihre Bedürfnisse an.

### Beispielquellcode für Access And Verify Signature mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für den Zugriff und die Signaturüberprüfung mit Aspose.Words für .NET:

```csharp
	
	// Der Pfad zum Dokumentenverzeichnis.
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

In diesem Tutorial haben wir die Funktion des Zugriffs und der Überprüfung digitaler Signaturen in einem Word-Dokument mithilfe von Aspose.Words für .NET untersucht. Wenn Sie die bereitgestellten Schritte befolgen, können Sie ganz einfach ein Dokument laden, auf seine digitalen Signaturen zugreifen und deren Gültigkeit überprüfen. Durch die Möglichkeit, auf digitale Signaturen zuzugreifen und diese zu überprüfen, können Sie die Integrität und Authentizität Ihrer Word-Dokumente sicherstellen. Aspose.Words für .NET bietet eine leistungsstarke API für die Textverarbeitung mit digitalen Signaturen, mit der Sie den Überprüfungsprozess automatisieren und die Sicherheit Ihrer Dokumente erhöhen können.

### FAQs

#### F: Was sind digitale Signaturen in einem Word-Dokument?

A: Digitale Signaturen in einem Word-Dokument sind elektronische Signaturen, die eine Möglichkeit bieten, die Integrität und Herkunft des Dokuments zu authentifizieren. Sie werden mithilfe digitaler Zertifikate und kryptografischer Algorithmen erstellt, sodass Empfänger überprüfen können, ob das Dokument nicht verändert wurde und von einer vertrauenswürdigen Quelle stammt.

#### F: Wie kann ich mit Aspose.Words für .NET auf digitale Signaturen in einem Word-Dokument zugreifen?

A: Um mit Aspose.Words für .NET auf digitale Signaturen in einem Word-Dokument zuzugreifen, können Sie die folgenden Schritte ausführen:
1.  Laden Sie das Dokument mit`Document` Klasse und geben Sie den Pfad zur Dokumentdatei an.
2.  Verwenden Sie eine Schleife, um die zu durchlaufen`DigitalSignatures` Sammlung des Dokuments. Jede Iteration stellt eine digitale Signatur dar.

#### F: Auf welche Informationen kann ich über eine digitale Signatur in einem Word-Dokument zugreifen?

A: Über eine digitale Signatur in einem Word-Dokument können Sie auf verschiedene Informationen zugreifen, wie zum Beispiel:
- Gültigkeit: Überprüfen Sie, ob die Signatur gültig ist.
- Kommentare: Rufen Sie den vom Unterzeichner angegebenen Grund für die Unterzeichnung ab.
- Signaturzeit: Ermitteln Sie die Zeit, zu der das Dokument signiert wurde.
- Betreffname: Rufen Sie den Namen des Unterzeichners oder Zertifikatsbetreffs ab.
- Name des Ausstellers: Rufen Sie den Namen des Zertifikatausstellers ab.

#### F: Kann ich die Gültigkeit einer digitalen Signatur in einem Word-Dokument mit Aspose.Words für .NET überprüfen?

 A: Ja, Sie können die Gültigkeit einer digitalen Signatur in einem Word-Dokument mit Aspose.Words für .NET überprüfen. Durch den Zugriff auf`IsValid`Eigentum der`DigitalSignature` Objekt können Sie feststellen, ob die Signatur gültig ist oder nicht.

#### F: Wie kann ich mit Aspose.Words für .NET die Gültigkeit digitaler Signaturen in einem Word-Dokument überprüfen?

A: Um die Gültigkeit digitaler Signaturen in einem Word-Dokument mit Aspose.Words für .NET zu überprüfen, können Sie die folgenden Schritte ausführen:
1.  Greife auf ... zu`DigitalSignatures` Sammlung des Dokuments.
2.  Durchlaufen Sie jedes einzelne`DigitalSignature` Objekt in der Sammlung.
3.  Benutzen Sie die`IsValid`Eigentum der`DigitalSignature` Objekt, um zu prüfen, ob die Signatur gültig ist.

#### F: Kann ich die Kommentare oder den Grund für die Unterzeichnung des Unterzeichners aus einer digitalen Signatur in einem Word-Dokument abrufen?

A: Ja, Sie können die Kommentare oder den Grund des Unterzeichners aus einer digitalen Signatur in einem Word-Dokument abrufen. Der`Comments`Eigentum der`DigitalSignature` Das Objekt bietet Zugriff auf die vom Unterzeichner während des Signiervorgangs angegebenen Kommentare.

#### F: Welche Art von Dokumenten unterstützt die Signaturüberprüfungsfunktion in Aspose.Words für .NET?

A: Die Signaturüberprüfungsfunktion in Aspose.Words für .NET unterstützt die Überprüfung digitaler Signaturen in Word-Dokumenten mit dem DOCX-Dateiformat. Mit dieser Funktion können Sie Signaturen in DOCX-Dateien überprüfen.

#### F: Wie kann ich mit Aspose.Words für .NET auf die Zertifikatsdetails einer digitalen Signatur in einem Word-Dokument zugreifen?

 A: Um mit Aspose.Words für .NET auf die Zertifikatsdetails einer digitalen Signatur in einem Word-Dokument zuzugreifen, können Sie auf Folgendes zugreifen`CertificateHolder`Eigentum der`DigitalSignature` Objekt. Von dem`CertificateHolder` -Objekt können Sie verschiedene Details des Zertifikats abrufen, z. B. den Namen des Antragstellers und den Namen des Ausstellers.

#### F: Kann ich die Anzeige oder Verarbeitung digitaler Signaturen in einem Word-Dokument mit Aspose.Words für .NET anpassen?

 A: Ja, Sie können die Anzeige oder Verarbeitung digitaler Signaturen in einem Word-Dokument mit Aspose.Words für .NET anpassen. Durch den Zugriff auf die Eigenschaften und Methoden des`DigitalSignature` Objekt können Sie die gewünschten Informationen extrahieren, zusätzliche Validierungen durchführen oder den Signaturüberprüfungsprozess in den Workflow Ihrer Anwendung integrieren.

#### F: Ist es möglich, mit Aspose.Words für .NET mehrere digitale Signaturen in einem Word-Dokument zu überprüfen?

 A: Ja, es ist möglich, mehrere digitale Signaturen in einem Word-Dokument mit Aspose.Words für .NET zu überprüfen. Durch Iterieren durch die`DigitalSignatures` Beim Sammeln des Dokuments können Sie auf jede digitale Signatur einzeln zugreifen und diese überprüfen.

