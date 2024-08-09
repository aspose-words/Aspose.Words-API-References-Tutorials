---
title: Creazione e firma di una nuova riga di firma
linktitle: Creazione e firma di una nuova riga di firma
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come creare e firmare digitalmente una riga di firma in un documento Word utilizzando Aspose.Words per .NET con questo tutorial passo passo. Perfetto per l'automazione dei documenti.
type: docs
weight: 10
url: /it/net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---
## Introduzione

Ehilà! Quindi, hai un documento Word e devi aggiungere una riga per la firma e quindi firmarlo digitalmente. Sembra complicato? Affatto! Grazie ad Aspose.Words per .NET, puoi raggiungere questo obiettivo senza problemi con solo poche righe di codice. In questo tutorial ti guideremo attraverso l'intero processo, dalla configurazione del tuo ambiente al salvataggio del tuo documento con una nuova firma brillante. Pronto? Immergiamoci!

## Prerequisiti

Prima di addentrarci nel codice, assicuriamoci di avere tutto ciò di cui hai bisogno:
1.  Aspose.Words per .NET - Puoi[scaricalo qui](https://releases.aspose.com/words/net/).
2. Si consiglia vivamente un ambiente di sviluppo .NET: Visual Studio.
3. Un documento da firmare: crea un semplice documento Word o utilizzane uno esistente.
4.  Un file di certificato: è necessario per le firme digitali. Puoi usare a`.pfx` file.
5. Immagini per la riga della firma: facoltativamente, un file immagine per la firma.

## Importa spazi dei nomi

Per prima cosa dobbiamo importare gli spazi dei nomi necessari. Questo passaggio è cruciale in quanto configura l'ambiente per l'utilizzo delle funzionalità Aspose.Words.

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Saving;
using Aspose.Words.Signing;
```

## Passaggio 1: impostazione della directory dei documenti

Ogni progetto ha bisogno di un buon inizio. Impostiamo il percorso della directory dei documenti. Qui è dove i tuoi documenti verranno salvati e recuperati.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: creazione di un nuovo documento

Ora creiamo un nuovo documento Word utilizzando Aspose.Words. Questa sarà la nostra tela in cui aggiungeremo la riga della firma.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 3: inserimento della riga della firma

 È qui che avviene la magia. Inseriamo una riga di firma nel nostro documento utilizzando il file`DocumentBuilder` classe.

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## Passaggio 4: salvataggio del documento con la riga della firma

Una volta posizionata la riga della firma, dobbiamo salvare il documento. Questo è un passaggio intermedio prima di procedere alla firma.

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

## Passaggio 5: impostazione delle opzioni di firma

Ora impostiamo le opzioni per firmare il documento. Ciò include la specifica dell'ID della riga della firma e dell'immagine da utilizzare.

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    SignatureLineImage = File.ReadAllBytes(dataDir + "Enhanced Windows MetaFile.emf")
};
```

## Passaggio 6: caricamento del certificato

Le firme digitali richiedono un certificato. Qui carichiamo il file del certificato che verrà utilizzato per firmare il documento.

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

## Passaggio 7: firma del documento

 Questo è il passo finale. Usiamo il`DigitalSignatureUtil`classe per firmare il documento. Il documento firmato viene salvato con un nuovo nome.

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
    dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);
```

## Conclusione

Ed ecco qua! Con questi passaggi, hai creato con successo un nuovo documento Word, aggiunto una riga della firma e firmato digitalmente utilizzando Aspose.Words per .NET. È uno strumento potente che rende l'automazione dei documenti un gioco da ragazzi. Che tu abbia a che fare con contratti, accordi o qualsiasi documento formale, questo metodo garantisce che siano firmati e autenticati in modo sicuro.

## Domande frequenti

### Posso utilizzare altri formati di immagine per la riga della firma?
Sì, puoi utilizzare vari formati di immagine come PNG, JPG, BMP, ecc.

###  È necessario utilizzare a`.pfx` file for the certificate?
 Sì, un`.pfx` file è un formato comune per l'archiviazione di informazioni crittografiche inclusi certificati e chiavi private.

### Posso aggiungere più righe di firma in un singolo documento?
Assolutamente! È possibile inserire più righe di firma ripetendo il passaggio di inserimento per ciascuna firma.

### Cosa succede se non ho un certificato digitale?
Dovrai ottenere un certificato digitale da un'autorità di certificazione attendibile o generarne uno utilizzando strumenti come OpenSSL.

### Come verifico la firma digitale nel documento?
Puoi aprire il documento firmato in Word e andare ai dettagli della firma per verificare l'autenticità e l'integrità della firma.