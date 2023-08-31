---
title: Inserisci il collegamento ipertestuale nel documento di Word
linktitle: Inserisci il collegamento ipertestuale nel documento di Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come inserire collegamenti ipertestuali nei documenti di Word utilizzando Aspose.Words per .NET Guida passo passo.
type: docs
weight: 10
url: /it/net/add-content-using-documentbuilder/insert-hyperlink/
---
In questo tutorial completo imparerai come inserire collegamenti ipertestuali in un documento Word utilizzando Aspose.Words per .NET. Ti guideremo attraverso il processo e ti forniremo gli snippet di codice C# necessari. Al termine di questa guida sarai in grado di aggiungere collegamenti ipertestuali selezionabili ai tuoi documenti.

## Prerequisiti
Prima di iniziare, assicurati di possedere i seguenti prerequisiti:
- Aspose.Words per la libreria .NET installata sul tuo sistema.

## Passaggio 1: crea un nuovo documento e DocumentBuilder
Per iniziare, crea un nuovo documento utilizzando la classe Document e inizializza un oggetto DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: inserisci un collegamento ipertestuale
Successivamente, utilizza il metodo Write della classe DocumentBuilder per aggiungere testo e formattare il collegamento ipertestuale impostando le proprietà colore e sottolineatura:

```csharp
builder.Write("Please make sure to visit ");
builder.Font.Color = Color.Blue;
builder.Font.Underline = Underline.Single;

builder.InsertHyperlink("Aspose Website", "http://www.aspose.com", falso);

builder.Font.ClearFormatting();
builder.Write(" for more information.");
```

## Passaggio 3: salva il documento
Dopo aver inserito il collegamento ipertestuale, salva il documento in un file utilizzando il metodo Save della classe Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHyperlink.docx");
```

## Esempio di codice sorgente per inserire il collegamento ipertestuale utilizzando Aspose.Words per .NET
Ecco il codice sorgente completo per l'inserimento di un collegamento ipertestuale utilizzando Aspose.Words per .NET:

I collegamenti ipertestuali rappresentano un modo efficace per migliorare l'interattività e l'utilità dei documenti di Word. Possono essere utilizzati per fare riferimento a risorse esterne, fornire informazioni aggiuntive o creare elementi di navigazione all'interno del documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Please make sure to visit ");
builder.Font.Color = Color.Blue;
builder.Font.Underline = Underline.Single;

builder.InsertHyperlink("Aspose Website", "http://www.aspose.com", falso);

builder.Font.ClearFormatting();
builder.Write(" for more information.");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHyperlink.docx");
```

Ricordati di adattare il codice in base alle tue esigenze specifiche, incluso il testo del collegamento ipertestuale e l'URL. Miglioralo con formattazione o funzionalità aggiuntive secondo necessità.

## Conclusione
Congratulazioni! Hai imparato con successo come inserire collegamenti ipertestuali in un documento Word utilizzando Aspose.Words per .NET. Seguendo la guida passo passo e utilizzando il codice sorgente fornito, ora puoi aggiungere collegamenti ipertestuali cliccabili ai tuoi documenti, indirizzando i lettori a siti Web esterni o URL specifici.

### Domande frequenti sull'inserimento del collegamento ipertestuale nel documento Word

#### D: Posso inserire collegamenti ipertestuali a posizioni specifiche all'interno dello stesso documento?

R: Sì, Aspose.Words per .NET ti consente di inserire collegamenti ipertestuali che fanno riferimento a posizioni specifiche all'interno dello stesso documento. È possibile utilizzare tecniche di bookmarking per definire destinazioni all'interno del documento e creare collegamenti ipertestuali che raggiungano tali destinazioni.

#### D: Posso formattare l'aspetto dei collegamenti ipertestuali, ad esempio modificandone il colore o lo stile?

R: Assolutamente! Aspose.Words per .NET fornisce ampie opzioni di formattazione per i collegamenti ipertestuali. Puoi modificare il colore, lo stile della sottolineatura, il carattere e altre proprietà per personalizzare l'aspetto dei collegamenti ipertestuali in modo che corrispondano allo stile del documento.

#### D: È possibile creare collegamenti ipertestuali a indirizzi e-mail?

R: Sì, puoi creare collegamenti ipertestuali che aprono il client di posta elettronica predefinito con un indirizzo email precompilato. Utilizza semplicemente il prefisso "mailto:" seguito dall'indirizzo email come parametro URL quando inserisci il collegamento ipertestuale.

#### D: Posso aggiungere descrizioni comandi o descrizioni ai collegamenti ipertestuali?

R: Aspose.Words per .NET supporta l'aggiunta di descrizioni comandi o descrizioni ai collegamenti ipertestuali utilizzando l'attributo "titolo". Specificando l'attributo titolo nel collegamento ipertestuale inserito, è possibile fornire informazioni aggiuntive che verranno visualizzate quando si passa con il mouse sopra il collegamento ipertestuale.

#### D: Aspose.Words per .NET supporta il collegamento ai file sul sistema locale?

R: Sì, puoi creare collegamenti ipertestuali che si collegano ai file sul sistema locale utilizzando percorsi di file relativi o assoluti. Questa funzionalità consente di creare modelli di documento che includono collegamenti a file di supporto o documenti correlati.