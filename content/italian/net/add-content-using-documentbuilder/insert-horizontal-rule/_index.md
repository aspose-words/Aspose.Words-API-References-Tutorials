---
title: Inserisci la regola orizzontale nel documento di Word
linktitle: Inserisci la regola orizzontale nel documento di Word
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come inserire regole orizzontali nei documenti di Word utilizzando Aspose.Words per .NET. Guida passo dopo passo.
type: docs
weight: 10
url: /it/net/add-content-using-documentbuilder/insert-horizontal-rule/
---
In questo esempio completo, imparerai come inserire una regola orizzontale in un documento di Word utilizzando Aspose.Words per .NET. Ti guideremo attraverso il processo e ti forniremo i frammenti di codice C# necessari. Alla fine di questa guida, sarai in grado di aggiungere regole orizzontali ai tuoi documenti per la separazione visiva e l'organizzazione.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
- Aspose.Words per la libreria .NET installata sul tuo sistema.

## Passaggio 1: creare un nuovo documento e DocumentBuilder
Per iniziare, crea un nuovo documento utilizzando la classe Document e inizializza un oggetto DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: inserire una regola orizzontale
Successivamente, utilizza il metodo Writeln della classe DocumentBuilder per aggiungere un testo descrittivo e quindi inserire una riga orizzontale:

```csharp
builder.Writeln("Insert a horizontal rule shape into the document.");
builder.InsertHorizontalRule();
```

## Passaggio 3: salvare il documento
Dopo aver inserito il filetto orizzontale, salvare il documento in un file utilizzando il metodo Save della classe Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHorizontalRule.docx");
```

### Esempio di codice sorgente per inserire una regola orizzontale utilizzando Aspose.Words per .NET
Ecco il codice sorgente completo per l'inserimento di una regola orizzontale utilizzando Aspose.Words per .NET:
Le regole orizzontali sono utili per vari scenari, come la divisione di sezioni, la creazione di interruzioni visive o l'evidenziazione di informazioni importanti.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Insert a horizontal rule shape into the document.");
builder.InsertHorizontalRule();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHorizontalRule.docx");
```

Ricorda di adattare il codice in base alle tue esigenze specifiche e di migliorarlo con funzionalità aggiuntive secondo necessità.

## Conclusione
Congratulazioni! Hai imparato con successo come inserire una regola orizzontale in un documento di Word utilizzando Aspose.Words per .NET. Seguendo la guida passo passo e utilizzando il codice sorgente fornito, ora puoi separare visivamente e organizzare i tuoi documenti utilizzando regole orizzontali.

### Domande frequenti per inserire la regola orizzontale nel documento word

#### D: Posso personalizzare l'aspetto del filetto orizzontale?

R: Sì, assolutamente! Aspose.Words per .NET fornisce varie proprietà per personalizzare l'aspetto della regola orizzontale. Puoi regolarne la larghezza, l'altezza, l'allineamento, il colore e l'ombreggiatura per adattarli all'estetica del tuo documento.

#### D: Posso aggiungere più filetti orizzontali in un singolo documento?

R: Certamente! È possibile inserire tutte le regole orizzontali necessarie in un documento di Word utilizzando Aspose.Words per .NET. Ripeti semplicemente il processo di inserimento per aggiungere più interruzioni visive o divisori di sezione.

#### D: I filetti orizzontali sono compatibili con altri formati di file, come il PDF?

R: Sì, le regole orizzontali inserite utilizzando Aspose.Words per .NET sono compatibili con vari formati di file, inclusi DOCX e PDF. Ciò significa che puoi esportare i tuoi documenti in diversi formati mantenendo le regole orizzontali.

#### D: Posso inserire a livello di codice una regola orizzontale in posizioni specifiche nel documento?

R: Assolutamente! Aspose.Words per .NET consente di posizionare la regola orizzontale in posizioni specifiche all'interno del documento a livello di codice. Puoi controllarne la posizione in base al contenuto e alla struttura del documento.

#### D: Aspose.Words per .NET è adatto sia per applicazioni desktop che web?

R: Sì, Aspose.Words per .NET è versatile e può essere utilizzato sia in applicazioni desktop che web. Che tu stia creando un'applicazione Windows o un sistema basato sul Web, puoi integrare la libreria senza problemi.