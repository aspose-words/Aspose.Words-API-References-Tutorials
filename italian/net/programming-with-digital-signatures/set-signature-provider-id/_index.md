---
title: Imposta l'ID del provider di firme nel documento di Word
linktitle: Imposta l'ID del provider di firme nel documento di Word
second_title: Aspose.Words API di elaborazione dei documenti
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


## Conclusione

In questo tutorial, abbiamo imparato come impostare l'ID del provider di firma per una riga della firma in un documento di Word utilizzando Aspose.Words per .NET. Seguendo i passaggi forniti, è possibile caricare facilmente il documento, accedere alla riga della firma, impostare l'ID del fornitore e firmare il documento. La possibilità di impostare l'ID del fornitore della firma aiuta a stabilire l'identità e l'affidabilità del firmatario, migliorando la sicurezza e l'integrità dei documenti Word. Aspose.Words per .NET fornisce una robusta API per l'elaborazione di testi con firme digitali, che consente di personalizzare e gestire il processo di firma con facilità.

### Domande frequenti per impostare l'ID del provider di firma nel documento di Word

#### D: Che cos'è un ID provider di firma in un documento di Word?

R: Un ID provider di firma in un documento Word è un identificatore univoco che specifica il provider di una firma digitale. Aiuta a identificare l'entità o l'organizzazione responsabile della creazione e della gestione della firma digitale.

#### D: Come posso impostare l'ID del provider di firma per una riga della firma in un documento di Word utilizzando Aspose.Words per .NET?

R: Per impostare l'ID del provider di firma per una riga della firma in un documento Word utilizzando Aspose.Words per .NET, puoi seguire questi passaggi:
1.  Caricare il documento utilizzando il`Document` class e specificare il percorso del file del documento.
2.  Accedere alla riga della firma utilizzando il metodo o la proprietà appropriati. Ad esempio, puoi usare`GetChild` metodo per recuperare la forma della linea della firma.
3. Recupera l'ID del provider dalla riga della firma.
4.  Crea un'istanza di`SignOptions`classe e impostare il`ProviderId` property all'ID provider recuperato.
5.  Usa il`DigitalSignatureUtil.Sign` metodo per firmare il documento, fornendo i parametri necessari tra cui il`SignOptions` oggetto.

#### D: Come posso accedere alla riga della firma in un documento Word utilizzando Aspose.Words per .NET?

 R: Per accedere alla riga della firma in un documento Word utilizzando Aspose.Words per .NET, è possibile utilizzare il metodo o la proprietà appropriati per recuperare la forma della riga della firma dalla struttura del documento. Ad esempio, puoi utilizzare il`GetChild` metodo con i parametri appropriati per ottenere la forma della linea della firma desiderata.

#### D: Posso impostare l'ID del fornitore della firma per più righe di firma in un documento Word?

 R: Sì, puoi impostare l'ID del fornitore della firma per più righe di firma in un documento Word. È possibile scorrere la raccolta di righe della firma nel documento e impostare individualmente l'ID del provider per ciascuna riga della firma utilizzando il file`SignOptions.ProviderId` proprietà.

#### D: Qual è lo scopo dell'ID del fornitore della firma in un documento di Word?

R: L'ID del fornitore della firma in un documento Word ha lo scopo di identificare l'entità o l'organizzazione responsabile della creazione e della gestione della firma digitale. Aiuta a stabilire l'autenticità e l'affidabilità della firma digitale associandola a un provider specifico.

#### D: Che tipo di certificati digitali possono essere utilizzati per impostare l'ID del fornitore della firma in un documento Word?

R: È possibile utilizzare i certificati digitali X.509 con le informazioni del provider appropriate per impostare l'ID del provider della firma in un documento Word. Il certificato digitale deve essere emesso da un'autorità di certificazione (CA) attendibile e contenere i metadati necessari per identificare il provider.