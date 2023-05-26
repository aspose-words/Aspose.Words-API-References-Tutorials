---
title: Inserisci un'immagine mobile
linktitle: Inserisci un'immagine mobile
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come inserire immagini mobili nei documenti di Word utilizzando Aspose.Words per .NET. Guida passo dopo passo.
type: docs
weight: 10
url: /it/net/add-content-using-documentbuilder/insert-floating-image/
---

In questo esempio completo, imparerai come inserire un'immagine mobile in un documento di Word utilizzando Aspose.Words per .NET. Ti guideremo attraverso il processo e ti forniremo i frammenti di codice C# necessari. Alla fine di questa guida, sarai in grado di aggiungere immagini con opzioni di posizionamento e wrapping personalizzabili ai tuoi documenti.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
- Aspose.Words per la libreria .NET installata sul tuo sistema.

## Passaggio 1: creare un nuovo documento e DocumentBuilder
Per iniziare, crea un nuovo documento utilizzando la classe Document e inizializza un oggetto DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: inserisci un'immagine mobile
Utilizzare quindi il metodo InsertImage della classe DocumentBuilder per inserire un'immagine mobile. Fornisci il percorso del file immagine, la posizione orizzontale e verticale relativa, la larghezza, l'altezza e le opzioni di avvolgimento come parametri:

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png",
	RelativeHorizontalPosition.Margin,
	100,
	RelativeVerticalPosition.Margin,
	100,
	200,
	100,
	WrapType.Square);
```

## Passaggio 3: salvare il documento
Dopo aver inserito l'immagine mobile, salvare il documento in un file utilizzando il metodo Save della classe Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
```

## Esempio di codice sorgente per inserire un'immagine mobile utilizzando Aspose.Words per .NET
Ecco il codice sorgente completo per l'inserimento di un'immagine mobile utilizzando Aspose.Words per .NET:
Le immagini mobili sono utili per vari scenari, come l'aggiunta di loghi, illustrazioni o elementi decorativi che possono essere posizionati indipendentemente dal testo del documento.

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.InsertImage(ImagesDir + "Transparent background logo.png",
		RelativeHorizontalPosition.Margin,
		100,
		RelativeVerticalPosition.Margin,
		100,
		200,
		100,
		WrapType.Square);

	doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
	
```

Ricorda di regolare il codice in base ai tuoi requisiti specifici, incluso il percorso del file immagine e le opzioni di posizionamento e wrapping desiderate.

## Conclusione
Congratulazioni! Hai imparato con successo come inserire un'immagine mobile in un documento di Word utilizzando Aspose.Words per .NET. Seguendo la guida dettagliata e utilizzando il codice sorgente fornito, ora puoi migliorare i tuoi documenti con immagini mobili visivamente accattivanti e personalizzabili.

