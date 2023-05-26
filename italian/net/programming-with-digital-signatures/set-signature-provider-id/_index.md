---
title: Imposta l'ID del fornitore della firma
linktitle: Imposta l'ID del fornitore della firma
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come impostare l'ID del provider di firma in un documento di Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-digital-signatures/set-signature-provider-id/
---

In questo tutorial, ti guideremo attraverso i passaggi per utilizzare la funzione Imposta ID provider firma con Aspose.Words per .NET. Questa funzione consente di specificare l'ID del fornitore della firma per una riga della firma in un documento di Word. Segui i passaggi seguenti:

## Passaggio 1: caricamento del documento e accesso alla riga della firma

Inizia caricando il documento contenente la riga della firma:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## Passaggio 2: impostazione delle opzioni di firma

Crea un'istanza della classe SignOptions e imposta le opzioni di firma, incluso l'ID del provider:

```csharp
SignOptions signOptions = new SignOptions
{
ProviderId = signatureLine.ProviderId,
 SignatureLineId = signatureLine.Id
};
```

## Passaggio 3: Firma del documento

Per firmare il documento è necessario utilizzare la classe DigitalSignatureUtil e specificare il certificato di firma:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);
```

Assicurati di specificare i percorsi corretti per il documento, il certificato e il documento firmato.

### Codice sorgente di esempio per Imposta ID provider firma utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per impostare l'ID del provider di firma con Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");

	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		ProviderId = signatureLine.ProviderId, SignatureLineId = signatureLine.Id
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);

```

Termina l'ID del provider di firme nel documento di Word con Aspose.Words per .NET.

