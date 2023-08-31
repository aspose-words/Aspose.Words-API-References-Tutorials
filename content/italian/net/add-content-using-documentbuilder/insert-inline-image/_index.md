---
title: Inserisci un'immagine in linea nel documento di Word
linktitle: Inserisci un'immagine in linea nel documento di Word
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come inserire immagini in linea nei documenti di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/add-content-using-documentbuilder/insert-inline-image/
---
In questo tutorial completo imparerai come inserire immagini in linea in un documento di Word utilizzando Aspose.Words per .NET. Ti guideremo attraverso il processo e ti forniremo i frammenti di codice C# necessari. Alla fine di questa guida, sarai in grado di aggiungere immagini direttamente nel testo dei tuoi documenti.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
- Aspose.Words per la libreria .NET installata sul tuo sistema.

## Passaggio 1: creare un nuovo documento e DocumentBuilder
Per iniziare, crea un nuovo documento utilizzando la classe Document e inizializza un oggetto DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: inserire un'immagine in linea
Utilizzare quindi il metodo InsertImage della classe DocumentBuilder per inserire un'immagine incorporata nel documento. Fornire il percorso del file immagine come parametro:

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## Passaggio 3: salvare il documento
Dopo aver inserito l'immagine in linea, salvare il documento in un file utilizzando il metodo Save della classe Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

### Codice sorgente di esempio per Inserisci immagine in linea utilizzando Aspose.Words per .NET
Ecco il codice sorgente completo per l'inserimento di un'immagine in linea utilizzando Aspose.Words per .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(ImagesDir + "Transparent background logo.png");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

## Conclusione
Congratulazioni! Hai imparato con successo come inserire immagini in linea in un documento di Word utilizzando Aspose.Words per .NET. Seguendo la guida passo-passo e utilizzando il codice sorgente fornito, ora puoi aggiungere immagini senza problemi all'interno del testo dei tuoi documenti.

Le immagini incorporate sono utili per vari scenari, come l'aggiunta di illustrazioni, loghi o altri elementi visivi direttamente nel flusso del documento.

### Domande frequenti per inserire un'immagine in linea nel documento di Word

#### D: Posso ridimensionare le immagini in linea all'interno del documento Word?

A: Sì, puoi ridimensionare le immagini in linea utilizzando Aspose.Words per .NET. Dopo aver inserito l'immagine, è possibile manipolarne le dimensioni regolando le proprietà di larghezza e altezza dell'oggetto Shape che rappresenta l'immagine.

#### D: È possibile aggiungere testo alternativo alle immagini incorporate per motivi di accessibilità?

R: Sì, puoi aggiungere testo alternativo alle immagini incorporate per migliorare l'accessibilità. Aspose.Words per .NET supporta l'aggiunta di testo alternativo alle immagini, consentendo agli screen reader e ad altre tecnologie assistive di descrivere il contenuto dell'immagine agli utenti ipovedenti.

#### D: Posso applicare formattazione o stili alle immagini incorporate?

R: Assolutamente! Aspose.Words per .NET fornisce ampie opzioni di formattazione per le immagini in linea. Puoi applicare vari stili, bordi, effetti e altri attributi di formattazione alle immagini in modo che corrispondano al design visivo del tuo documento.

#### D: Aspose.Words per .NET supporta l'inserimento di immagini da un flusso o da un array di byte?

R: Sì, puoi inserire immagini in linea da flussi o array di byte utilizzando Aspose.Words per .NET. Ciò consente di lavorare con immagini caricate da fonti esterne o immagini generate dinamicamente.

#### D: Posso inserire immagini in posizioni specifiche all'interno del contenuto del testo?

R: Sì, la classe DocumentBuilder in Aspose.Words per .NET fornisce un controllo preciso sulla posizione di inserimento delle immagini in linea. È possibile specificare la posizione esatta all'interno del testo in cui inserire l'immagine.