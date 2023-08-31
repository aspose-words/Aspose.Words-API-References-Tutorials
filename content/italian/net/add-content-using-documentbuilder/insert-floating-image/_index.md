---
title: Inserisci immagine mobile nel documento Word
linktitle: Inserisci immagine mobile nel documento Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come inserire immagini mobili nei documenti Word utilizzando Aspose.Words per .NET. Guida passo passo.
type: docs
weight: 10
url: /it/net/add-content-using-documentbuilder/insert-floating-image/
---
In questo esempio completo, imparerai come inserire un'immagine mobile in un documento Word utilizzando Aspose.Words per .NET. Ti guideremo attraverso il processo e ti forniremo gli snippet di codice C# necessari. Al termine di questa guida sarai in grado di aggiungere immagini ai tuoi documenti con opzioni di posizionamento e disposizione personalizzabili.

## Prerequisiti
Prima di iniziare, assicurati di possedere i seguenti prerequisiti:
- Aspose.Words per la libreria .NET installata sul tuo sistema.

## Passaggio 1: crea un nuovo documento e DocumentBuilder
Per iniziare, crea un nuovo documento utilizzando la classe Document e inizializza un oggetto DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: inserisci un'immagine mobile
Successivamente, utilizza il metodo InsertImage della classe DocumentBuilder per inserire un'immagine mobile. Fornire il percorso del file immagine, la posizione relativa orizzontale e verticale, la larghezza, l'altezza e le opzioni di disposizione come parametri:

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

## Passaggio 3: salva il documento
Dopo aver inserito l'immagine mobile, salva il documento in un file utilizzando il metodo Save della classe Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
```

## Esempio di codice sorgente per inserire immagine mobile utilizzando Aspose.Words per .NET
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

Ricordati di modificare il codice in base ai tuoi requisiti specifici, incluso il percorso del file immagine e le opzioni di posizionamento e avvolgimento desiderate.

## Conclusione
Congratulazioni! Hai imparato con successo come inserire un'immagine mobile in un documento Word utilizzando Aspose.Words per .NET. Seguendo la guida passo passo e utilizzando il codice sorgente fornito, ora puoi migliorare i tuoi documenti con immagini mobili visivamente accattivanti e personalizzabili.

### Domande frequenti sull'inserimento di un'immagine mobile nel documento Word

#### D: Posso inserire più immagini mobili in un unico documento?

R: Certamente! È possibile inserire tutte le immagini mobili necessarie in un documento Word utilizzando Aspose.Words per .NET. Ripeti semplicemente il processo di inserimento per aggiungere più immagini visivamente accattivanti.

#### D: Quali opzioni di disposizione sono disponibili per l'immagine mobile?

R: Aspose.Words per .NET fornisce varie opzioni di disposizione per le immagini mobili, tra cui Square, Tight, Through, TopBottom e None. Queste opzioni determinano il modo in cui il testo interagisce con l'immagine mobile.

#### D: Posso regolare la dimensione dell'immagine mobile?

R: Assolutamente! È possibile specificare la larghezza e l'altezza dell'immagine mobile utilizzando i rispettivi parametri nel metodo InsertImage. Ciò ti consente di controllare le dimensioni dell'immagine in base alle tue preferenze di progettazione.

#### D: Posso posizionare l'immagine mobile rispetto a un elemento specifico nel documento?

R: Sì, Aspose.Words per .NET ti consente di posizionare l'immagine mobile rispetto a elementi specifici, come il margine, la pagina, il paragrafo o la tabella. È possibile scegliere i parametri relativi di posizione orizzontale e verticale appropriati per ottenere il posizionamento desiderato.

#### D: Aspose.Words per .NET è adatto sia per applicazioni desktop che web?

R: Sì, Aspose.Words per .NET è una libreria versatile adatta sia per applicazioni desktop che web. Che tu stia creando un'applicazione Windows o un sistema basato sul Web, puoi integrare la libreria senza sforzo.
