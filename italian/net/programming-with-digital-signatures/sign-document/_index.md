---
title: Firma il documento di Word
linktitle: Firma il documento di Word
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come firmare digitalmente un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-digital-signatures/sign-document/
---
In questo tutorial, ti guideremo attraverso i passaggi per utilizzare la funzionalità di firma del documento con Aspose.Words per .NET. Questa funzione consente di firmare digitalmente un documento Word utilizzando un certificato. Segui i passaggi seguenti:

## Passaggio 1: caricamento del certificato

Inizia caricando il certificato di firma utilizzando la classe CertificateHolder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Assicurati di specificare il percorso corretto per il certificato e la password associata.

## Passaggio 2: Firma del documento

Utilizzare la classe DigitalSignatureUtil per firmare il documento:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
	certHolder);
```

Assicurati di specificare i percorsi corretti per il documento di origine e il documento firmato.

### Codice sorgente di esempio per il documento di firma utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per firmare un documento con Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
		certHolder);

```

Seguendo questi passaggi, puoi facilmente firmare un documento Word con Aspose.Words per .NET.

## Conclusione

 In questo tutorial, abbiamo esplorato la funzionalità di firma del documento in Aspose.Words per .NET. Caricando un certificato di firma e utilizzando il file`DigitalSignatureUtil.Sign` metodo, possiamo firmare digitalmente un documento Word. La firma del documento fornisce l'autenticazione e garantisce l'integrità del contenuto del documento, rendendolo una funzionalità preziosa per una gestione dei documenti sicura e affidabile.

### Domande frequenti per il documento di parola d'ordine

#### D: Cos'è la firma del documento in Aspose.Words per .NET?

R: La firma del documento in Aspose.Words per .NET si riferisce al processo di firma digitale di un documento Word utilizzando un certificato. Questa funzione aggiunge una firma digitale al documento, fornendo autenticità, integrità e non ripudio del contenuto del documento.

#### D: Come posso caricare il certificato di firma in Aspose.Words per .NET?

 R: Per caricare il certificato di firma in Aspose.Words per .NET, puoi utilizzare il file`CertificateHolder` classe. Crea un'istanza di`CertificateHolder` fornendo il percorso del file del certificato e la relativa password. Ecco un esempio:

```csharp
CertificateHolder certHolder = CertificateHolder.Create("path/to/certificate.pfx", "password");
```

Assicurati di fornire il percorso corretto per il tuo certificato e la password associata.

#### D: Come posso firmare un documento Word utilizzando Aspose.Words per .NET?

 R: Per firmare un documento Word utilizzando Aspose.Words per .NET, puoi utilizzare il file`DigitalSignatureUtil` classe. Chiama il`Sign` metodo, fornendo il percorso del documento di origine, il percorso del documento firmato (output) e il file`CertificateHolder` oggetto. Ecco un esempio:

```csharp
DigitalSignatureUtil.Sign("path/to/source/document.docx", "path/to/signed/document.docx", certHolder);
```

Assicurati di fornire i percorsi corretti per il documento di origine e il documento firmato (output).

#### D: Qual è lo scopo della firma del documento?

R: La firma del documento serve come metodo per garantire l'autenticità e l'integrità di un documento. Firmando digitalmente un documento, puoi fornire la prova della sua origine, verificare che il suo contenuto non sia stato alterato e stabilire il non ripudio. La firma del documento è comunemente utilizzata per documenti legali, finanziari e sensibili.

#### D: Posso utilizzare qualsiasi certificato per la firma dei documenti in Aspose.Words per .NET?

R: Per la firma del documento in Aspose.Words per .NET, è necessario utilizzare un certificato X.509 valido. Questo certificato può essere ottenuto da un'autorità di certificazione (CA) attendibile oppure è possibile utilizzare un certificato autofirmato a scopo di test.

#### D: Quale formato di file supporta Aspose.Words per .NET per la firma dei documenti?

 R: Aspose.Words per .NET supporta la firma di documenti per documenti Word nel formato file DOCX. Puoi firmare i file DOCX utilizzando il formato`DigitalSignatureUtil` classe e il relativo certificato.

#### D: Posso firmare più documenti Word utilizzando lo stesso certificato?

R: Sì, puoi firmare più documenti Word utilizzando lo stesso certificato. Dopo aver caricato il certificato utilizzando il file`CertificateHolder` class, puoi riutilizzarla per firmare più documenti chiamando la classe`DigitalSignatureUtil.Sign` metodo con diversi percorsi di origine e documenti firmati.

#### D: La firma del documento modifica il documento originale?

R: La firma del documento con Aspose.Words per .NET non modifica il documento originale. Invece, crea una copia firmata digitalmente del documento, lasciando intatto il documento originale. La copia firmata digitalmente contiene la firma digitale aggiunta, garantendo l'integrità del contenuto del documento.

#### D: Posso verificare la firma digitale di un documento firmato utilizzando Aspose.Words per .NET?

 R: Sì, Aspose.Words per .NET fornisce funzionalità per verificare la firma digitale di un documento firmato. Puoi usare il`DigitalSignatureUtil.Verify` metodo per verificare la validità e l'autenticità della firma digitale.