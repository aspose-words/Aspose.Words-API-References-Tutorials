---
title: Crea una nuova riga di firma e imposta l'ID del provider
linktitle: Crea una nuova riga di firma e imposta l'ID del provider
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come creare una nuova riga della firma e impostare l'ID del provider nei documenti Word utilizzando Aspose.Words per .NET. Guida passo passo.
type: docs
weight: 10
url: /it/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---
## Introduzione

Ehi, appassionati di tecnologia! Ti sei mai chiesto come aggiungere una riga per la firma nei tuoi documenti Word a livello di codice? Bene, oggi approfondiremo proprio questo utilizzando Aspose.Words per .NET. Questa guida ti guiderà attraverso ogni passaggio, rendendo semplicissimo creare una nuova riga della firma e impostare l'ID del provider nei tuoi documenti Word. Che tu stia automatizzando l'elaborazione dei documenti o semplicemente cercando di semplificare il flusso di lavoro, questo tutorial fa al caso tuo.

## Prerequisiti

Prima di sporcarci le mani, assicuriamoci di avere tutto ciò di cui abbiamo bisogno:

1.  Aspose.Words per .NET: se non l'hai già fatto, scaricalo[Qui](https://releases.aspose.com/words/net/).
2. Ambiente di sviluppo: Visual Studio o qualsiasi altro ambiente di sviluppo C#.
3. .NET Framework: assicurati di avere .NET Framework installato.
4. Certificato PFX: per firmare i documenti avrai bisogno di un certificato PFX. Puoi ottenerne uno da un'autorità di certificazione attendibile.

## Importa spazi dei nomi

Per prima cosa, importiamo gli spazi dei nomi necessari nel tuo progetto C#:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Signing;
using System;
```

Va bene, veniamo al nocciolo della questione. Ecco una ripartizione dettagliata di ogni passaggio per creare una nuova riga di firma e impostare l'ID del provider.

## Passaggio 1: crea un nuovo documento

Per iniziare, dobbiamo creare un nuovo documento Word. Questa sarà la tela per la nostra linea distintiva.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 In questo frammento stiamo inizializzando un nuovo file`Document` e un`DocumentBuilder` . IL`DocumentBuilder` ci aiuta ad aggiungere elementi al nostro documento.

## Passaggio 2: definire le opzioni della riga della firma

Successivamente, definiamo le opzioni per la nostra riga della firma. Ciò include il nome, il titolo, l'e-mail e altri dettagli del firmatario.

```csharp
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
```

Queste opzioni personalizzano la linea della firma, rendendola chiara e professionale.

## Passaggio 3: inserire la riga della firma

Con le nostre opzioni impostate, ora possiamo inserire la riga della firma nel documento.

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

 Ecco, il`InsertSignatureLine` aggiunge la riga della firma e le assegniamo un ID provider univoco.

## Passaggio 4: salva il documento

Dopo aver inserito la riga della firma, salviamo il documento.

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

Ciò salva il documento con la riga della firma appena aggiunta.

## Passaggio 5: imposta le opzioni di firma

Ora dobbiamo impostare le opzioni per firmare il documento. Ciò include l'ID della riga della firma, l'ID del provider, i commenti e l'ora della firma.

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    ProviderId = signatureLine.ProviderId,
    Comments = "Document was signed by vderyushev",
    SignTime = DateTime.Now
};
```

Queste opzioni garantiscono che il documento venga firmato con i dettagli corretti.

## Passaggio 6: creare il titolare del certificato

Per firmare il documento, utilizzeremo un certificato PFX. Creiamo un titolare del certificato per questo.

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

 Assicurati di sostituire`"morzal.pfx"` con il file del certificato effettivo e`"aw"` con la password del certificato.

## Passaggio 7: firma il documento

Infine, firmiamo il documento utilizzando l'utilità di firma digitale.

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
    dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);
```

Questo firma il documento e lo salva come un nuovo file.

## Conclusione

Ed ecco qua! Hai creato con successo una nuova riga della firma e impostato l'ID del provider in un documento Word utilizzando Aspose.Words per .NET. Questa potente libreria semplifica incredibilmente la gestione e l'automazione delle attività di elaborazione dei documenti. Provalo e scopri come può semplificare il tuo flusso di lavoro.

## Domande frequenti

### Posso personalizzare l'aspetto della riga della firma?
Assolutamente! Puoi modificare varie opzioni nel file`SignatureLineOptions` per soddisfare le vostre esigenze.

### Cosa succede se non ho un certificato PFX?
Dovrai ottenerne uno da un'autorità di certificazione attendibile. È essenziale per firmare digitalmente i documenti.

### Posso aggiungere più righe di firma a un documento?
Sì, puoi aggiungere tutte le righe della firma necessarie ripetendo il processo di inserimento con diverse opzioni.

### Aspose.Words per .NET è compatibile con .NET Core?
Sì, Aspose.Words per .NET supporta .NET Core, rendendolo versatile per diversi ambienti di sviluppo.

### Quanto sono sicure le firme digitali?
Le firme digitali create con Aspose.Words sono altamente sicure, a condizione che si utilizzi un certificato valido e affidabile.