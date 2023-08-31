---
title: Controlla l'effetto di testo DrawingML
linktitle: Controlla l'effetto di testo DrawingML
second_title: Aspose.Words API di elaborazione dei documenti
description: In questo tutorial, scopri come controllare gli effetti di testo DrawingML in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fonts/check-drawingml-text-effect/
---

In questo tutorial, ti illustreremo come controllare gli effetti di testo DrawingML in un documento Word utilizzando Aspose.Words Library per .NET. Il controllo degli effetti di testo di DrawingML consente di determinare se un effetto specifico viene applicato a una parte del testo. Ti guideremo passo dopo passo per aiutarti a comprendere e implementare il codice nel tuo progetto .NET.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti elementi:
- Conoscenza operativa del linguaggio di programmazione C#
- La libreria Aspose.Words per .NET installata nel tuo progetto
- Un documento Word contenente effetti di testo DrawingML

## Passaggio 1: definire la directory dei documenti
 Innanzitutto, devi impostare il percorso della directory nella posizione del documento di Word. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel codice con il percorso appropriato.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: caricare il documento e controllare gli effetti del testo
Successivamente, caricheremo il documento Word e accederemo alla raccolta di sequenze (sequenze di caratteri) nel primo paragrafo del corpo del documento. Verificheremo quindi se al carattere della prima esecuzione vengono applicati effetti di testo specifici di DrawingML.

```csharp
// Carica il documento
Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// Controlla gli effetti di testo DrawingML
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));
```

### Esempio di codice sorgente per Check DMLText Effect utilizzando Aspose.Words per .NET 

```csharp

//Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// Una corsa potrebbe avere diversi effetti di testo Dml applicati.
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));

```

## Conclusione
In questo tutorial, abbiamo visto come controllare gli effetti di testo DrawingML in un documento Word utilizzando Aspose.Words per .NET. Il controllo degli effetti di testo di DrawingML consente di identificare parti di testo a cui sono applicati effetti specifici. Sentiti libero di usare questa funzione per manipolare e analizzare gli effetti di testo nei tuoi documenti Word.

### FAQ

#### D: Come posso accedere agli effetti di testo DrawingML in un documento Word utilizzando Aspose.Words?

R: Con Aspose.Words, puoi accedere agli effetti di testo DrawingML in un documento Word utilizzando l'API fornita. Puoi sfogliare gli elementi di testo e controllare proprietà specifiche degli effetti di testo, come colore, dimensione, ecc.

#### D: Quali tipi di effetti di testo DrawingML sono comunemente usati nei documenti di Word?

R: I tipi comunemente usati di effetti di testo DrawingML nei documenti Word includono ombre, riflessi, bagliori, sfumature e così via. Questi effetti possono essere applicati per migliorare l'aspetto e la formattazione del testo.

#### D: Come posso controllare il colore di un effetto di testo DrawingML in un documento Word?

R: Per verificare il colore di un effetto di testo DrawingML in un documento Word, è possibile utilizzare i metodi forniti da Aspose.Words per accedere alle proprietà del colore dell'effetto di testo. In questo modo puoi ottenere il colore utilizzato per l'effetto di testo specifico.

#### D: È possibile controllare gli effetti di testo nei documenti Word contenenti più sezioni?

R: Sì, Aspose.Words consente di controllare gli effetti di testo nei documenti Word contenenti più sezioni. Puoi navigare attraverso ogni sezione del documento e accedere agli effetti di testo per ogni sezione individualmente.

#### D: Come posso controllare l'opacità di un effetto testo DrawingML in un documento Word?

R: Per verificare l'opacità di un effetto di testo DrawingML in un documento Word, è possibile utilizzare i metodi forniti da Aspose.Words per accedere alle proprietà di opacità dell'effetto di testo. Ciò ti consentirà di ottenere il valore di opacità applicato all'effetto di testo specifico.