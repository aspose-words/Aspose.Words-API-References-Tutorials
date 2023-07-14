---
title: Accedi e verifica la firma nel documento di Word
linktitle: Accedi e verifica la firma nel documento di Word
second_title: Aspose.Words API di elaborazione dei documenti
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
	Console.WriteLine("* Signature Found *");
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
		Console.WriteLine("* Signature Found *");
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

## Conclusione

In questo tutorial, abbiamo esplorato la funzionalità di accesso e verifica delle firme digitali in un documento di Word utilizzando Aspose.Words per .NET. Seguendo i passaggi forniti, puoi facilmente caricare un documento, accedere alle sue firme digitali e verificarne la validità. La possibilità di accedere e verificare le firme digitali fornisce un modo per garantire l'integrità e l'autenticità dei documenti Word. Aspose.Words per .NET offre una potente API per l'elaborazione di testi con firme digitali, che consente di automatizzare il processo di verifica e migliorare la sicurezza dei documenti.

### FAQ

#### D: Cosa sono le firme digitali in un documento Word?

R: Le firme digitali in un documento Word sono firme elettroniche che forniscono un modo per autenticare l'integrità e l'origine del documento. Vengono creati utilizzando certificati digitali e algoritmi crittografici, consentendo ai destinatari di verificare che il documento non sia stato alterato e che provenga da una fonte attendibile.

#### D: Come posso accedere alle firme digitali in un documento Word utilizzando Aspose.Words per .NET?

R: Per accedere alle firme digitali in un documento Word utilizzando Aspose.Words per .NET, puoi seguire questi passaggi:
1.  Caricare il documento utilizzando il`Document` class e specificare il percorso del file del documento.
2.  Usa un ciclo per scorrere il file`DigitalSignatures` raccolta del documento. Ogni iterazione rappresenta una firma digitale.

#### D: A quali informazioni posso accedere da una firma digitale in un documento Word?

R: Da una firma digitale in un documento Word, puoi accedere a varie informazioni, come:
- Validità: controlla se la firma è valida.
- Commenti: ottieni il motivo della firma specificato dal firmatario.
- Ora della firma: ottenere l'ora in cui il documento è stato firmato.
- Nome oggetto: recupera il nome del firmatario o dell'oggetto del certificato.
- Nome emittente: ottenere il nome dell'emittente del certificato.

#### D: Posso verificare la validità di una firma digitale in un documento Word utilizzando Aspose.Words per .NET?

 R: Sì, puoi verificare la validità di una firma digitale in un documento Word utilizzando Aspose.Words per .NET. Accedendo al`IsValid`proprietà del`DigitalSignature` oggetto, è possibile determinare se la firma è valida o meno.

#### D: Come posso verificare la validità delle firme digitali in un documento Word utilizzando Aspose.Words per .NET?

R: Per verificare la validità delle firme digitali in un documento Word utilizzando Aspose.Words per .NET, puoi seguire questi passaggi:
1.  Accedi al`DigitalSignatures` raccolta del documento.
2.  Itera attraverso ciascuno`DigitalSignature` oggetto della collezione.
3.  Usa il`IsValid`proprietà del`DigitalSignature` oggetto per verificare se la firma è valida.

#### D: Posso recuperare i commenti o il motivo della firma del firmatario da una firma digitale in un documento Word?

R: Sì, puoi recuperare i commenti o il motivo della firma del firmatario da una firma digitale in un documento Word. IL`Comments`proprietà del`DigitalSignature` oggetto fornisce l'accesso ai commenti specificati dal firmatario durante il processo di firma.

#### D: Che tipo di documenti supporta la funzione di verifica della firma in Aspose.Words per .NET?

R: La funzione di verifica della firma in Aspose.Words per .NET supporta la verifica delle firme digitali nei documenti Word con il formato file DOCX. Puoi utilizzare questa funzione per verificare le firme nei file DOCX.

#### D: Come posso accedere ai dettagli del certificato di una firma digitale in un documento Word utilizzando Aspose.Words per .NET?

 R: Per accedere ai dettagli del certificato di una firma digitale in un documento Word utilizzando Aspose.Words per .NET, è possibile accedere al`CertificateHolder`proprietà del`DigitalSignature` oggetto. Dal`CertificateHolder` oggetto, è possibile recuperare vari dettagli del certificato, come il nome del soggetto e il nome dell'emittente.

#### D: Posso personalizzare la visualizzazione o l'elaborazione delle firme digitali in un documento Word utilizzando Aspose.Words per .NET?

 R: Sì, puoi personalizzare la visualizzazione o l'elaborazione delle firme digitali in un documento Word utilizzando Aspose.Words per .NET. Accedendo alle proprietà e ai metodi del`DigitalSignature` oggetto, è possibile estrarre le informazioni desiderate, eseguire convalide aggiuntive o integrare il processo di verifica della firma nel flusso di lavoro dell'applicazione.

#### D: È possibile verificare più firme digitali in un documento Word utilizzando Aspose.Words per .NET?

 R: Sì, è possibile verificare più firme digitali in un documento Word utilizzando Aspose.Words per .NET. Iterando attraverso il`DigitalSignatures` raccolta del documento, puoi accedere e verificare singolarmente ogni firma digitale.

