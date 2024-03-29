---
title: Creazione e firma di una nuova riga di firma
linktitle: Creazione e firma di una nuova riga di firma
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come creare e firmare una nuova riga della firma in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---
In questo tutorial, ti guideremo attraverso i passaggi per utilizzare la funzionalità di creazione e firma di una nuova riga di firma con Aspose.Words per .NET. Questa funzionalità ti consente di inserire una riga per la firma in un documento Word, impostare opzioni personalizzate e firmare il documento. Seguire i passaggi seguenti:

## Passaggio 1: creazione del documento e del generatore

Inizia creando un'istanza della classe Document e un oggetto DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: inserimento della riga della firma

Utilizza il metodo InsertSignatureLine() dell'oggetto DocumentBuilder per inserire una nuova riga della firma nel documento:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## Passaggio 3: salva il documento

Salva il documento modificato:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

Assicurati di specificare il percorso e il nome file corretti per salvare il documento.

## Passaggio 4: firma del documento

Per firmare il documento è necessario impostare le opzioni di firma e utilizzare la classe DigitalSignatureUtil:

```csharp
SignOptions signOptions = new SignOptions
{
	SignatureLineId = signatureLine.Id,
	SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
	dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);
```

Assicurati di specificare i percorsi corretti per il documento, l'immagine della riga della firma e il documento firmato.

### Codice sorgente di esempio per la creazione e la firma di una nuova riga di firma utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per creare e firmare una nuova riga di firma con Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
	
	doc.Save(dataDir + "SignDocuments.SignatureLine.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
		dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);

```

Seguendo questi passaggi, sarai in grado di creare e firmare facilmente una nuova riga di firma nel tuo documento Word con Aspose.Words per .NET.

## Conclusione

In questo tutorial, abbiamo imparato come creare e firmare una nuova riga della firma in un documento Word utilizzando Aspose.Words per .NET. Seguendo i passaggi forniti, puoi facilmente inserire una riga per la firma nel documento, personalizzarne le opzioni e firmare il documento utilizzando un certificato digitale. L'aggiunta di linee di firma e firme digitali ai tuoi documenti ne migliora l'autenticità e l'integrità, rendendoli più sicuri e affidabili. Aspose.Words per .NET fornisce una potente API per l'elaborazione di parole con firme e certificati digitali nei documenti Word, consentendoti di automatizzare il processo di firma e garantire la validità dei tuoi documenti.

### Domande frequenti

#### D: Cos'è una riga della firma in un documento di Word?

R: Una riga della firma in un documento Word è un segnaposto che indica dove deve essere posizionata la firma. In genere include il nome, il titolo e la data e fornisce spazio per una firma scritta a mano o digitale.

#### D: Come posso creare una riga della firma in un documento Word utilizzando Aspose.Words per .NET?

R: Per creare una riga della firma in un documento Word utilizzando Aspose.Words per .NET, puoi seguire questi passaggi:
1.  Crea un'istanza di`Document` classe e a`DocumentBuilder` oggetto.
2.  Usa il`InsertSignatureLine` metodo del`DocumentBuilder` oggetto per inserire una nuova riga della firma nel documento.
3. Salva il documento modificato.

#### D: Posso personalizzare le opzioni della riga della firma, come nome, titolo e data?

 R: Sì, puoi personalizzare le opzioni della riga della firma. IL`SignatureLineOptions` La classe fornisce proprietà per impostare le opzioni desiderate, come ad esempio`Signer`, `SignerTitle`, `ShowDate`, ecc. È possibile modificare queste proprietà prima di inserire la riga della firma.

#### D: Come posso firmare il documento dopo aver creato una riga per la firma?

 R: Per firmare il documento dopo aver creato una riga per la firma, è necessario impostare le opzioni della firma e utilizzare il file`DigitalSignatureUtil` classe. Ecco i passaggi:
1.  Impostare il`SignatureLineId` proprietà nel`SignOptions` opporsi all'ID della riga della firma.
2.  Impostare il`SignatureLineImage` proprietà nel`SignOptions` opporsi all'immagine della firma che si desidera utilizzare.
3.  Caricare il certificato di firma utilizzando il file`CertificateHolder` classe.
4.  Usa il`DigitalSignatureUtil.Sign` metodo per firmare il documento, fornendo i parametri necessari.

#### D: Posso utilizzare un'immagine della firma digitale per firmare il documento?

 R: Sì, puoi utilizzare un'immagine della firma digitale per firmare il documento. Per fare ciò, è necessario fornire il file immagine nel formato`SignOptions` oggetto utilizzando il`SignatureLineImage`proprietà. L'immagine può essere in qualsiasi formato immagine supportato, come JPEG, PNG o EMF.

#### D: Qual è lo scopo di creare e firmare una nuova riga di firma in un documento di Word?

R: La creazione e la firma di una nuova riga della firma in un documento Word utilizzando Aspose.Words per .NET consente di aggiungere un segnaposto per una firma e quindi firmare il documento utilizzando un certificato digitale. Questo processo garantisce l'autenticità e l'integrità del documento, fornendo prova dell'approvazione o dell'accordo.

#### D: Posso creare e firmare più righe di firma in un documento Word utilizzando Aspose.Words per .NET?

R: Sì, puoi creare e firmare più righe di firma in un documento Word utilizzando Aspose.Words per .NET. Ogni riga della firma può avere il proprio ID e opzioni univoci. È possibile ripetere i passaggi per creare e firmare ulteriori righe di firma nel documento.

#### D: Posso modificare la riga della firma o aggiungere ulteriori informazioni dopo averla firmata?

R: Una volta firmata, la riga della firma diventa parte del contenuto del documento e non può essere modificata separatamente. Tuttavia, puoi aggiungere ulteriori informazioni o contenuti dopo la riga della firma firmata.

#### D: Posso verificare la firma digitale di un documento che contiene una riga per la firma?

 R: Sì, Aspose.Words per .NET fornisce funzionalità per verificare la firma digitale di un documento che contiene una riga di firma. Puoi usare il`DigitalSignatureUtil.Verify` metodo per verificare la validità e l'autenticità della firma digitale.

#### D: Quale formato di file supporta Aspose.Words per .NET per creare e firmare righe di firma?

R: Aspose.Words per .NET supporta la creazione e la firma di righe di firma nel formato file DOCX. È possibile creare e firmare righe di firma nei file DOCX utilizzando i metodi e le classi forniti.