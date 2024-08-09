---
title: Inserisci oggetto Ole in Word con il pacchetto Ole
linktitle: Inserisci oggetto Ole in Word con il pacchetto Ole
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come inserire oggetti OLE nei documenti Word utilizzando Aspose.Words per .NET. Segui la nostra guida dettagliata passo dopo passo per incorporare i file senza problemi.
type: docs
weight: 10
url: /it/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---
## Introduzione

Se hai sempre desiderato incorporare un file in un documento Word, sei nel posto giusto. Che si tratti di un file ZIP, di un foglio Excel o di qualsiasi altro tipo di file, incorporarlo direttamente nel tuo documento Word può essere incredibilmente utile. Pensalo come se avessi uno scomparto segreto nel tuo documento dove puoi riporre ogni sorta di tesoro. E oggi spiegheremo come farlo utilizzando Aspose.Words per .NET. Pronto a diventare un mago di Word? Immergiamoci!

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

1. Aspose.Words per .NET: se non l'hai già fatto, scaricalo da[Qui](https://releases.aspose.com/words/net/).
2. Un ambiente di sviluppo: Visual Studio o qualsiasi altro ambiente di sviluppo .NET.
3. Comprensione di base di C#: non è necessario essere un esperto, ma conoscere il C# sarà utile.
4. Una directory dei documenti: una cartella in cui è possibile archiviare e recuperare i documenti.

## Importa spazi dei nomi

Per prima cosa, mettiamo in ordine i nostri spazi dei nomi. Devi includere i seguenti spazi dei nomi nel tuo progetto:

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Drawing;
```

Suddividiamolo in passaggi brevi, quindi è facile seguirli.

## Passaggio 1: imposta il documento

Immagina di essere un artista con una tela bianca. Innanzitutto, abbiamo bisogno della nostra tela bianca, che è il nostro documento Word. Ecco come configurarlo:

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Questo codice inizializza un nuovo documento Word e imposta un DocumentBuilder, che utilizzeremo per inserire contenuto nel nostro documento.

## Passaggio 2: leggi il tuo oggetto Ole

Successivamente, leggiamo il file che desideri incorporare. Pensa a questo come raccogliere il tesoro che vuoi nascondere nel tuo scompartimento segreto:

```csharp
byte[] bs = File.ReadAllBytes(dataDir + "Zip file.zip");
```

Questa riga legge tutti i byte dal tuo file ZIP e li memorizza in un array di byte.

## Passaggio 3: inserire l'oggetto Ole

Ora arriva la parte magica. Incorporeremo il file nel nostro documento Word:

```csharp
using (Stream stream = new MemoryStream(bs))
{
    Shape shape = builder.InsertOleObject(stream, "Package", true, null);
    OlePackage olePackage = shape.OleFormat.OlePackage;
    olePackage.FileName = "filename.zip";
    olePackage.DisplayName = "displayname.zip";
}
```

 Qui creiamo un flusso di memoria dall'array di byte e utilizziamo il file`InsertOleObject` metodo per incorporarlo nel documento. Impostiamo anche il nome del file e il nome visualizzato per l'oggetto incorporato.

## Passaggio 4: salva il documento

Infine, salviamo il nostro capolavoro:

```csharp
doc.Save(dataDir + "WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

Ciò salva il documento con il file incorporato nella directory specificata.

## Conclusione

Ed ecco qua! Hai incorporato con successo un oggetto OLE in un documento di Word utilizzando Aspose.Words per .NET. È come aggiungere una gemma nascosta all'interno del tuo documento che può essere svelata in qualsiasi momento. Questa tecnica può essere incredibilmente utile per una varietà di applicazioni, dalla documentazione tecnica ai report dinamici. 

## Domande frequenti

### Posso incorporare altri tipi di file utilizzando questo metodo?
Sì, puoi incorporare vari tipi di file come fogli Excel, PDF e immagini.

### Ho bisogno di una licenza per Aspose.Words?
 Sì, è necessaria una licenza valida. Puoi ottenere un[licenza temporanea](https://purchase.aspose.com/temporary-license/) per la valutazione.

### Come posso personalizzare il nome visualizzato dell'oggetto OLE?
 È possibile impostare il`DisplayName` proprietà del`OlePackage` per personalizzarlo.

### Aspose.Words è compatibile con .NET Core?
Sì, Aspose.Words supporta sia .NET Framework che .NET Core.

### Posso modificare l'oggetto OLE incorporato nel documento Word?
No, non puoi modificare l'oggetto OLE direttamente in Word. È necessario aprirlo nella sua applicazione nativa.