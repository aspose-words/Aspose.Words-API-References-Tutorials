---
title: Crea una nuova riga della firma e imposta l'ID del fornitore
linktitle: Crea una nuova riga della firma e imposta l'ID del fornitore
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come creare una nuova riga della firma e impostare l'ID del provider in un documento di Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---
In questo tutorial, ti guideremo attraverso i passaggi per utilizzare la funzione Crea nuova riga della firma e Imposta ID provider con Aspose.Words per .NET. Questa funzione consente di inserire una riga della firma in un documento Word, impostare opzioni personalizzate e firmare il documento. Segui i passaggi seguenti:

## Passaggio 1: creazione del documento e del generatore

Inizia creando un'istanza della classe Document e un oggetto DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: impostazione delle opzioni della riga della firma

Crea un'istanza della classe SignatureLineOptions e imposta le opzioni desiderate:

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
Sign = "vderyushev",
SignerTitle = "QA",
Email = "vderyushev@aspose.com",
ShowDate=true,
Default Instructions = false,
Instructions = "Please sign here.",
AllowComments = true
};
```

## Passaggio 3: Inserimento della riga della firma

Utilizzare il metodo InsertSignatureLine() dell'oggetto DocumentBuilder per inserire la riga della firma nel documento:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
```

## Passaggio 4: impostare l'ID del fornitore

Imposta l'ID del provider per la riga della firma utilizzando la proprietà ProviderId:

```csharp
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

Assicurati di specificare l'ID provider corretto per il tuo caso d'uso.

## Passaggio 5: salvare il documento

Salva il documento modificato:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

Assicurati di specificare il percorso e il nome file corretti per salvare il documento.

## Passaggio 6: Firma del documento

Per firmare il documento, è necessario impostare le opzioni di firma e utilizzare la classe DigitalSignatureUtil:

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
ProviderId = signatureLine.ProviderId,
Comments = "Document was signed by vderyushev",
SignTime = DateTime.Now
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
	dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions)
```

Assicurati di specificare i percorsi corretti per il documento, il certificato e il documento firmato.

### Codice sorgente di esempio per creare una nuova riga della firma e impostare l'ID del provider utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per creare una nuova riga della firma e impostare l'ID del provider con Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	SignatureLineOptions signatureLineOptions = new SignatureLineOptions
	{
		Signer = "vderyushev",
		SignerTitle = "QA",
		Email = "vderyushev@aspose.com",
		ShowDate = true,
		DefaultInstructions = false,
		Instructions = "Please sign here.",
		AllowComments = true
	};

	SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
	signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
	
	doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		ProviderId = signatureLine.ProviderId,
		Comments = "Document was signed by vderyushev",
		SignTime = DateTime.Now
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
		dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);

```

Seguendo questi passaggi, puoi facilmente creare una nuova riga della firma e impostare l'ID del provider nel tuo documento Word con Aspose.Words per .NET.

## Conclusione

In questo tutorial, abbiamo esplorato la funzionalità di creare una nuova riga della firma e impostare l'ID del provider in un documento di Word utilizzando Aspose.Words per .NET. Seguendo i passaggi forniti, puoi facilmente inserire una riga di firma con opzioni personalizzate e associarla a un provider specifico utilizzando l'ID provider. L'aggiunta di righe per la firma e la personalizzazione delle informazioni del provider migliorano l'autenticità e l'affidabilità dei tuoi documenti. Aspose.Words per .NET fornisce una potente API per l'elaborazione di testi con linee di firma e certificati digitali nei documenti Word, consentendoti di automatizzare il processo di firma e garantire la validità dei tuoi documenti.

### FAQ

#### D: Che cos'è un ID fornitore in una riga della firma?

R: Un ID provider in una riga della firma è un identificatore univoco che rappresenta il provider della firma digitale. Aiuta a identificare la fonte o l'organizzazione responsabile della firma.

#### D: Come posso creare una nuova riga della firma in un documento di Word utilizzando Aspose.Words per .NET?

R: Per creare una nuova riga della firma in un documento Word utilizzando Aspose.Words per .NET, puoi seguire questi passaggi:
1.  Crea un'istanza di`Document` classe e a`DocumentBuilder` oggetto.
2.  Crea un'istanza di`SignatureLineOptions` class e impostare le opzioni desiderate per la riga della firma.
3.  Usa il`InsertSignatureLine` metodo del`DocumentBuilder` oggetto per inserire la riga della firma nel documento.

#### D: Posso personalizzare le opzioni della riga della firma, come il nome del firmatario, il titolo e le istruzioni?

 R: Sì, puoi personalizzare le opzioni della riga della firma. IL`SignatureLineOptions` class fornisce le proprietà per impostare le opzioni desiderate, ad esempio`Signer`, `SignerTitle`, `Instructions`, `AllowComments`, ecc. È possibile modificare queste proprietà prima di inserire la riga della firma.

#### D: Qual è lo scopo dell'impostazione dell'ID provider per una riga della firma?

R: L'impostazione dell'ID del provider per una riga della firma consente di identificare la fonte o l'organizzazione responsabile della firma digitale. Consente di associare la firma a un fornitore o entità specifica, fornendo ulteriori informazioni sull'origine e l'attendibilità della firma.

#### D: Come posso impostare l'ID del provider per una riga della firma utilizzando Aspose.Words per .NET?

R: Per impostare l'ID del provider per una riga della firma utilizzando Aspose.Words per .NET, puoi seguire questi passaggi:
1.  Dopo aver inserito la riga della firma, accedere al file`ProviderId` proprietà del`SignatureLine` oggetto.
2.  Impostare il`ProviderId` al valore dell'ID provider desiderato utilizzando il`Guid` tipo di dati.

#### D: Posso firmare il documento dopo aver creato una nuova riga della firma e aver impostato l'ID del fornitore?

 R: Sì, dopo aver creato una nuova riga per la firma e aver impostato l'ID del fornitore, puoi firmare il documento. Per firmare il documento, è necessario impostare le opzioni di firma, inclusi l'ID della riga della firma, l'ID del provider, i commenti e l'ora della firma. Quindi, usa il`DigitalSignatureUtil.Sign` metodo per firmare il documento utilizzando un certificato digitale.

#### D: Posso specificare un ID provider specifico per ciascuna riga della firma in un documento Word?

R: Sì, puoi specificare un ID provider specifico per ciascuna riga della firma in un documento Word. Dopo aver inserito ciascuna riga della firma, è possibile impostare l'ID del provider per quella particolare riga della firma accedendo al file`ProviderId` proprietà del rispettivo`SignatureLine` oggetto.

#### D: Come posso salvare il documento modificato dopo aver creato una nuova riga della firma e aver impostato l'ID del provider?

 R: Per salvare il documento modificato dopo aver creato una nuova riga della firma e aver impostato l'ID del provider, puoi utilizzare il file`Save` metodo del`Document` oggetto. Specificare il percorso e il nome file corretti per salvare il documento.

#### D: Quale formato di file supporta Aspose.Words per .NET per la creazione e la firma di linee di firma?

R: Aspose.Words per .NET supporta la creazione e la firma di linee di firma nel formato di file DOCX. È possibile creare e firmare linee di firma nei file DOCX utilizzando i metodi e le classi forniti.

#### D: Posso modificare l'ID del provider o altre opzioni di una riga della firma dopo che è stata firmata?

R: Una volta che una riga della firma è stata firmata, diventa parte del contenuto del documento e non può essere modificata separatamente. Qualsiasi modifica alla riga della firma, come la modifica dell'ID del provider o altre opzioni, richiederebbe la rimozione della firma esistente e la creazione di una nuova riga della firma.