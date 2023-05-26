---
title: Accedi e verifica la firma
linktitle: Accedi e verifica la firma
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come accedere e verificare le firme digitali in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-digital-signatures/access-and-verify-signature/
---
In questo tutorial, ti guideremo attraverso i passaggi per utilizzare la funzionalità di verifica dell'accesso e della firma di Aspose.Words per .NET. Questa funzione consente di accedere alle firme digitali in un documento Word e verificarne la validità. Segui i passaggi seguenti:

## Passaggio 1: caricamento del documento e accesso alle firme

Inizia caricando il documento contenente le firme digitali:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Digitally signed.docx");
```

## Passaggio 2: sfoglia le firme digitali

Usa un ciclo per scorrere tutte le firme digitali nel documento:

```csharp
foreach (DigitalSignature signature in doc.DigitalSignatures)
{
	// Accedi alle informazioni sulla firma
	Console.WriteLine("*** Signature Found ***");
	Console.WriteLine("Is valid: " + signature.IsValid);
	// Questa proprietà è disponibile solo nei documenti MS Word.
	Console.WriteLine("Reason for signing: " + signature.Comments); 
	Console.WriteLine("Time of signing: " + signature.SignTime);
	Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
	Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
	Console.WriteLine();
}
```

Assicurarsi di personalizzare i messaggi visualizzati in base alle proprie esigenze.

### Codice sorgente di esempio per l'accesso e la verifica della firma utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per l'accesso e la verifica della firma utilizzando Aspose.Words per .NET:

```csharp
	
	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Digitally signed.docx");

	foreach (DigitalSignature signature in doc.DigitalSignatures)
	{
		Console.WriteLine("*** Signature Found ***");
		Console.WriteLine("Is valid: " + signature.IsValid);
		// Questa proprietà è disponibile solo nei documenti MS Word.
		Console.WriteLine("Reason for signing: " + signature.Comments); 
		Console.WriteLine("Time of signing: " + signature.SignTime);
		Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
		Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
		Console.WriteLine();
	}

```

Seguendo questi passaggi, sarai in grado di accedere e verificare facilmente le firme digitali nel tuo documento Word con Aspose.Words per .NET.


