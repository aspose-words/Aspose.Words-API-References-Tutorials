---
title: Firma il documento Word
linktitle: Firma il documento Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come firmare digitalmente un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-digital-signatures/sign-document/
---
In questo tutorial, ti guideremo attraverso i passaggi per utilizzare la funzionalità di firma dei documenti con Aspose.Words per .NET. Questa funzionalità consente di firmare digitalmente un documento Word utilizzando un certificato. Seguire i passaggi seguenti:

## Passaggio 1: caricamento del certificato

Inizia caricando il certificato di firma utilizzando la classe CertificateHolder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Assicurati di specificare il percorso corretto del certificato e della password associata.

## Passaggio 2: firma del documento

Utilizza la classe DigitalSignatureUtil per firmare il documento:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
	certHolder);
```

Assicurati di specificare i percorsi corretti per il documento di origine e il documento firmato.

### Codice sorgente di esempio per Sign Document utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per firmare un documento con Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
		certHolder);

```

Seguendo questi passaggi, puoi firmare facilmente un documento Word con Aspose.Words per .NET.

## Conclusione

 In questo tutorial, abbiamo esplorato la funzionalità di firma dei documenti in Aspose.Words per .NET. Caricando un certificato di firma e utilizzando il file`DigitalSignatureUtil.Sign` metodo, possiamo firmare digitalmente un documento Word. La firma dei documenti fornisce l'autenticazione e garantisce l'integrità dei contenuti del documento, rendendolo una funzionalità preziosa per una gestione dei documenti sicura e affidabile.

### Domande frequenti sui documenti con parole chiave

#### D: Cos'è la firma dei documenti in Aspose.Words per .NET?

R: La firma dei documenti in Aspose.Words per .NET si riferisce al processo di firma digitale di un documento Word utilizzando un certificato. Questa funzionalità aggiunge una firma digitale al documento, garantendo autenticità, integrità e non ripudiabilità dei contenuti del documento.

#### D: Come posso caricare il certificato di firma in Aspose.Words per .NET?

 R: Per caricare il certificato di firma in Aspose.Words per .NET, è possibile utilizzare il file`CertificateHolder` classe. Crea un'istanza di`CertificateHolder` fornendo il percorso del file del certificato e la password associata. Ecco un esempio:

```csharp
CertificateHolder certHolder = CertificateHolder.Create("path/to/certificate.pfx", "password");
```

Assicurati di fornire il percorso corretto del certificato e la password associata.

#### D: Come posso firmare un documento Word utilizzando Aspose.Words per .NET?

 R: Per firmare un documento Word utilizzando Aspose.Words per .NET, puoi utilizzare il file`DigitalSignatureUtil` classe. Chiama il`Sign` metodo, fornendo il percorso del documento di origine, il percorso del documento firmato (output) e il file`CertificateHolder` oggetto. Ecco un esempio:

```csharp
DigitalSignatureUtil.Sign("path/to/source/document.docx", "path/to/signed/document.docx", certHolder);
```

Assicurati di fornire i percorsi corretti per il documento di origine e il documento firmato (output).

#### D: Qual è lo scopo della firma dei documenti?

R: La firma del documento serve come metodo per garantire l'autenticità e l'integrità di un documento. Firmando digitalmente un documento puoi fornire prova della sua origine, verificare che il suo contenuto non sia stato alterato e stabilirne il non ripudio. La firma dei documenti viene comunemente utilizzata per documenti legali, finanziari e sensibili.

#### D: Posso utilizzare qualsiasi certificato per la firma dei documenti in Aspose.Words per .NET?

R: Per la firma dei documenti in Aspose.Words per .NET, è necessario utilizzare un certificato X.509 valido. Questo certificato può essere ottenuto da un'autorità di certificazione (CA) attendibile oppure è possibile utilizzare un certificato autofirmato a scopo di test.

#### D: Quale formato di file supporta Aspose.Words per .NET per la firma dei documenti?

 R: Aspose.Words per .NET supporta la firma dei documenti per documenti Word nel formato file DOCX. È possibile firmare file DOCX utilizzando il file`DigitalSignatureUtil` classe e il relativo certificato.

#### D: Posso firmare più documenti Word utilizzando lo stesso certificato?

R: Sì, puoi firmare più documenti Word utilizzando lo stesso certificato. Dopo aver caricato il certificato utilizzando il file`CertificateHolder` class, puoi riutilizzarlo per firmare più documenti chiamando il file`DigitalSignatureUtil.Sign` metodo con percorsi di documenti firmati e di origine diversi.

#### D: La firma del documento modifica il documento originale?

R: La firma del documento con Aspose.Words per .NET non modifica il documento originale. Crea invece una copia firmata digitalmente del documento, lasciando intatto il documento originale. La copia firmata digitalmente contiene la firma digitale aggiunta, garantendo l'integrità del contenuto del documento.

#### D: Posso verificare la firma digitale di un documento firmato utilizzando Aspose.Words per .NET?

 R: Sì, Aspose.Words per .NET fornisce funzionalità per verificare la firma digitale di un documento firmato. Puoi usare il`DigitalSignatureUtil.Verify` metodo per verificare la validità e l'autenticità della firma digitale.