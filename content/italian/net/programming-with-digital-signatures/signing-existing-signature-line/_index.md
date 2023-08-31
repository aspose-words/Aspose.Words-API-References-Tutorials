---
title: Firma della riga della firma esistente nel documento di Word
linktitle: Firma della riga della firma esistente nel documento di Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come firmare una riga di firma esistente in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-digital-signatures/signing-existing-signature-line/
---
In questo tutorial, ti guideremo attraverso i passaggi per utilizzare la funzionalità di firma di una riga di firma esistente con Aspose.Words per .NET. Questa funzionalità permette di firmare digitalmente una riga della firma già presente in un documento Word. Seguire i passaggi seguenti:

## Passaggio 1: caricamento del documento e accesso alla riga della firma

Inizia caricando il documento contenente la riga della firma esistente:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## Passaggio 2: impostazione delle opzioni di firma

Crea un'istanza della classe SignOptions e imposta le opzioni della firma, inclusi l'ID della riga della firma e l'immagine della riga della firma:

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};
```

Assicurati di specificare il percorso corretto dell'immagine della riga della firma.

## Passaggio 3: caricamento del certificato

Inizia caricando il certificato di firma utilizzando la classe CertificateHolder:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Assicurati di specificare il percorso corretto del certificato e della password associata.

## Passaggio 4: firma della riga della firma esistente

Utilizza la classe DigitalSignatureUtil per firmare la riga della firma esistente:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
```

Assicurati di specificare i percorsi corretti per il documento di origine, il documento firmato e il certificato.

### Codice sorgente di esempio per la firma della riga della firma esistente utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per firmare una riga di firma esistente con Aspose.Words per .NET:


```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");
	
	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
	

```

Seguendo questi passaggi, puoi facilmente firmare una riga di firma esistente in un documento di Word con Aspose.Words per .NET.

## Conclusione

In questo tutorial, abbiamo imparato come firmare una riga di firma esistente in un documento di Word utilizzando Aspose.Words per .NET. Seguendo i passaggi forniti, puoi caricare facilmente il documento, accedere alla riga della firma esistente, impostare le opzioni di firma e firmare il documento. La possibilità di firmare una riga di firma esistente fornisce un modo conveniente per aggiungere firme digitali ad aree predefinite dei documenti Word, garantendo l'integrità e l'autenticazione del documento. Aspose.Words per .NET offre una potente API per l'elaborazione di parole con firme digitali, consentendoti di personalizzare il processo di firma e migliorare la sicurezza dei tuoi documenti Word.

### Domande frequenti

#### D: Cos'è una riga della firma esistente in un documento di Word?

R: Una riga della firma esistente in un documento Word è un'area predefinita in cui è possibile inserire una firma. In genere è rappresentato da una forma o un oggetto nel documento e funge da spazio designato in cui il firmatario può aggiungere la propria firma digitale.

#### D: Come posso firmare una riga di firma esistente in un documento di Word utilizzando Aspose.Words per .NET?

R: Per firmare una riga della firma esistente in un documento di Word utilizzando Aspose.Words per .NET, è possibile seguire questi passaggi:
1.  Caricare il documento utilizzando`Document` class e specificare il percorso del file del documento.
2.  Accedi alla riga della firma esistente utilizzando il metodo o la proprietà appropriati. Ad esempio, puoi usare`GetChild` metodo per recuperare la forma della linea della firma.
3.  Crea un'istanza di`SignOptions`classe e impostare il file`SignatureLineId` proprietà all'ID della riga della firma esistente.
4.  Impostare il`SignatureLineImage` proprietà del`SignOptions` classe all'immagine che rappresenta la firma digitale.
5.  Caricare il certificato di firma utilizzando il file`CertificateHolder` classe e fornire il certificato e la password necessari.
6.  Usa il`DigitalSignatureUtil.Sign` metodo per firmare il documento, fornendo i parametri necessari tra cui il`SignOptions` oggetto.

#### D: Come posso accedere alla riga della firma esistente in un documento Word utilizzando Aspose.Words per .NET?

 R: Per accedere alla riga della firma esistente in un documento Word utilizzando Aspose.Words per .NET, è possibile utilizzare il metodo o la proprietà appropriati per recuperare la forma della linea della firma dalla struttura del documento. Ad esempio, puoi utilizzare il file`GetChild` metodo con i parametri appropriati per ottenere la forma della linea della firma desiderata.

#### D: Posso personalizzare l'aspetto della firma digitale in una riga di firma esistente?

R: Sì, puoi personalizzare l'aspetto della firma digitale in una riga di firma esistente fornendo un file immagine che rappresenta la firma. L'immagine può essere un logo, una firma scritta a mano o qualsiasi altra rappresentazione grafica della firma. È possibile impostare il`SignatureLineImage` proprietà del`SignOptions` classe ai byte del file immagine.

#### D: Posso firmare più righe di firma esistenti in un documento Word?
 R: Sì, puoi firmare più righe di firma esistenti in un documento Word. È necessario seguire i passaggi per ciascuna riga della firma individualmente, impostando il valore appropriato`SignatureLineId` E`SignatureLineImage` valori nel`SignOptions` oggetto per ogni riga della firma.

#### D: Quale formato deve essere il file immagine per la firma digitale in una riga di firma esistente?

 R: Il file immagine per la firma digitale in una riga di firma esistente può essere in vari formati, come PNG, JPEG, BMP o GIF. È possibile specificare il percorso del file o leggere i byte del file immagine e assegnarlo al file`SignatureLineImage` proprietà del`SignOptions` classe.
