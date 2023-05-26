---
title: Posizione del cursore
linktitle: Posizione del cursore
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come recuperare la posizione del cursore in un documento di Word utilizzando Aspose.Words per .NET Guida dettagliata.
type: docs
weight: 10
url: /it/net/add-content-using-documentbuilder/cursor-position/
---

In questo esempio dettagliato, imparerai a conoscere la posizione del cursore in un documento di Word utilizzando Aspose.Words per .NET. Ti guideremo attraverso il processo e ti forniremo i frammenti di codice C# necessari. Alla fine di questa guida, sarai in grado di recuperare il nodo e il paragrafo correnti in cui è posizionato il cursore nel documento.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
- Aspose.Words per la libreria .NET installata sul tuo sistema.

## Passaggio 1: creare un nuovo documento e DocumentBuilder
Per iniziare, crea un nuovo documento utilizzando la classe Document e inizializza un oggetto DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: accedere al nodo e al paragrafo correnti
Successivamente, recupera il nodo e il paragrafo correnti in cui è posizionato il cursore. Ciò può essere ottenuto utilizzando le proprietà CurrentNode e CurrentParagraph della classe DocumentBuilder:

```csharp
Node curNode = builder.CurrentNode;
Paragraph curParagraph = builder.CurrentParagraph;
```

## Passaggio 3: recupero delle informazioni sulla posizione del cursore
Ora puoi recuperare informazioni sulla posizione del cursore. Nel seguente frammento di codice, stampiamo il testo del paragrafo corrente:

```csharp
Console.WriteLine("\nCursor move to paragraph: " + curParagraph.GetText());
```

### Esempio di codice sorgente per la posizione del cursore utilizzando Aspose.Words per .NET
Ecco il codice sorgente completo per comprendere la posizione del cursore utilizzando Aspose.Words per .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Node curNode = builder.CurrentNode;
Paragraph curParagraph = builder.CurrentParagraph;

Console.WriteLine("\nCursor move to paragraph: " + curParagraph.GetText());
```

## Conclusione
Congratulazioni! Hai imparato con successo come lavorare con la posizione del cursore in un documento Word utilizzando Aspose.Words per .NET. Seguendo la guida passo-passo e utilizzando il codice sorgente fornito, è ora possibile recuperare il nodo e il paragrafo corrente in cui è posizionato il cursore nel documento.

Comprendere la posizione del cursore è utile per vari scenari, come la manipolazione del contenuto del documento in base alla posizione del cursore o l'implementazione di funzioni di modifica personalizzate.

