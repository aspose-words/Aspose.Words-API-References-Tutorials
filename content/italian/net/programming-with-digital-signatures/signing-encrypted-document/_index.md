---
title: Firma del documento di Word crittografato
linktitle: Firma del documento di Word crittografato
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come firmare digitalmente un documento word crittografato con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-digital-signatures/signing-encrypted-document/
---
In questo tutorial, ti guideremo attraverso i passaggi per utilizzare la funzione di firma di un documento word crittografato con Aspose.Words per .NET. Questa funzione consente di firmare digitalmente un documento Word crittografato utilizzando una password di decrittografia. Segui i passaggi seguenti:

## Passaggio 1: impostazione delle opzioni di firma

Crea un'istanza della classe SignOptions e imposta la password di decrittografia:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionpassword" };
```

Assicurati di specificare la password di decrittografia corretta per il tuo documento crittografato.

## Passaggio 2: caricamento del certificato

Inizia caricando il certificato di firma utilizzando la classe CertificateHolder:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Assicurati di specificare il percorso corretto per il certificato e la password associata.

## Passaggio 3: Firma del documento crittografato

Utilizzare la classe DigitalSignatureUtil per firmare il documento crittografato:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
	certHolder, signOptions);
```

Assicurati di specificare i percorsi corretti per il documento crittografato, il documento firmato e il certificato.

### Esempio di codice sorgente per la firma di un documento crittografato utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per firmare un documento crittografato con Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionPassword" };

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
		certHolder, signOptions);
	

```
Seguendo questi passaggi, puoi facilmente firmare un documento Word crittografato con Aspose.Words per .NET.

## Conclusione

In questo tutorial, abbiamo esplorato il processo di firma di un documento Word crittografato utilizzando Aspose.Words per .NET. Fornendo la password di decrittazione e il certificato di firma, possiamo aggiungere una firma digitale a un documento crittografato. La firma di documenti crittografati garantisce la loro autenticità e integrità, fornendo un ulteriore livello di sicurezza. Aspose.Words per .NET ti consente di firmare documenti crittografati e mantenere la sicurezza e l'affidabilità dei tuoi file Word.

### FAQ

#### D: Cos'è la firma del documento in Aspose.Words per .NET?

R: La firma del documento in Aspose.Words per .NET si riferisce al processo di firma digitale di un documento Word per garantirne l'autenticità, l'integrità e il non ripudio. Implica l'aggiunta di una firma digitale al documento utilizzando un certificato.

#### D: Che cos'è un documento Word crittografato?

R: Un documento Word crittografato è un documento che è stato crittografato utilizzando una password. La crittografia è una misura di sicurezza che protegge il contenuto del documento codificandolo e rendendolo illeggibile senza la corretta password di decrittazione.

#### D: Come posso firmare un documento Word crittografato utilizzando Aspose.Words per .NET?

R: Per firmare un documento Word crittografato utilizzando Aspose.Words per .NET, è necessario fornire la password di decrittografia insieme al certificato di firma. Segui questi passi:
1.  Imposta la password di decrittazione nel file`SignOptions` oggetto.
2.  Carica il certificato di firma utilizzando il file`CertificateHolder` classe.
3.  Usa il`DigitalSignatureUtil.Sign` metodo per firmare il documento cifrato, fornendo i parametri necessari.

#### D: Qual è lo scopo della firma di un documento crittografato?

R: La firma di un documento crittografato con Aspose.Words per .NET consente di aggiungere una firma digitale al documento anche quando è crittografato. Ciò fornisce un ulteriore livello di sicurezza e garantisce l'autenticità e l'integrità del contenuto crittografato. Consente ai destinatari di verificare l'origine del documento e rilevare eventuali manomissioni.

#### D: Posso firmare un documento crittografato senza fornire la password di decrittazione?

R: No, per firmare un documento crittografato, devi fornire la password di decrittazione corretta. La password di decrittografia è necessaria per accedere e modificare il contenuto crittografato del documento prima di applicare la firma digitale.

#### D: Posso firmare un documento Word crittografato utilizzando qualsiasi certificato?

R: Per firmare un documento Word crittografato utilizzando Aspose.Words per .NET, è necessario un certificato X.509 valido. Il certificato può essere ottenuto da un'autorità di certificazione (CA) attendibile oppure è possibile utilizzare un certificato autofirmato a scopo di test.

#### D: Posso firmare più documenti Word crittografati utilizzando lo stesso certificato?

 R: Sì, puoi firmare più documenti Word crittografati utilizzando lo stesso certificato. Dopo aver caricato il certificato utilizzando il file`CertificateHolder` class, puoi riutilizzarlo per firmare più documenti crittografati.

#### D: Posso verificare la firma digitale di un documento cifrato firmato?

 R: Sì, Aspose.Words per .NET fornisce funzionalità per verificare la firma digitale di un documento crittografato firmato. Puoi usare il`DigitalSignatureUtil.Verify` metodo per verificare la validità e l'autenticità della firma digitale.

#### D: Quale formato di file supporta Aspose.Words per .NET per la firma di documenti crittografati?

 R: Aspose.Words per .NET supporta la firma di documenti Word crittografati nel formato file DOCX. Puoi firmare file DOCX crittografati utilizzando il formato`DigitalSignatureUtil.Sign` metodo insieme alla password e al certificato di decrittazione necessari.

#### D: In che modo la firma di un documento crittografato influisce sulla crittografia?

R: La firma di un documento crittografato con Aspose.Words per .NET non influisce sulla crittografia del documento. La crittografia rimane intatta e la firma digitale viene aggiunta al contenuto crittografato. La firma digitale fornisce ulteriore sicurezza e verifica senza compromettere la crittografia applicata al documento.