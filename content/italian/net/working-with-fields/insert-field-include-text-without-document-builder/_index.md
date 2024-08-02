---
title: Inserisci campo Includi testo senza generatore di documenti
linktitle: Inserisci FieldIncludeText senza Document Builder
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come inserire un FieldIncludeText senza utilizzare DocumentBuilder in Aspose.Words per .NET con la nostra guida dettagliata passo passo.
type: docs
weight: 10
url: /it/net/working-with-fields/insert-field-include-text-without-document-builder/
---
## introduzione

Nel mondo dell'automazione e della manipolazione dei documenti, Aspose.Words per .NET si pone come uno strumento potente. Oggi ci immergeremo in una guida dettagliata su come inserire un FieldIncludeText senza utilizzare DocumentBuilder. Questo tutorial ti guiderà attraverso il processo passo dopo passo, assicurandoti di comprendere ogni parte del codice e il suo scopo.

## Prerequisiti

Prima di immergerci nel codice, assicuriamoci di avere tutto ciò di cui hai bisogno:

1.  Aspose.Words per .NET: assicurati di avere installata la versione più recente. Puoi scaricarlo da[Qui](https://releases.aspose.com/words/net/).
2. Ambiente di sviluppo .NET: qualsiasi IDE compatibile con .NET come Visual Studio.
3. Conoscenza di base di C#: la familiarità con la programmazione C# ti aiuterà a proseguire.

## Importa spazi dei nomi

Per prima cosa, dobbiamo importare gli spazi dei nomi necessari. Questi spazi dei nomi forniscono l'accesso alle classi e ai metodi richiesti per manipolare i documenti di Word.

```csharp
using Aspose.Words;
using Aspose.Words.Fields;
```

Ora suddividiamo l'esempio in più passaggi. Ogni passaggio verrà spiegato in dettaglio per garantire chiarezza.

## Passaggio 1: imposta il percorso della directory

Il primo passo è definire il percorso della directory dei documenti. Qui è dove verranno archiviati e accessibili i tuoi documenti Word.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: creare il documento e il paragrafo

Successivamente, creiamo un nuovo documento e un paragrafo all'interno di quel documento. Questo paragrafo conterrà il campo FieldIncludeText.

```csharp
// Creare il documento e il paragrafo.
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## Passaggio 3: inserire il campo FieldIncludeText

Ora inseriamo il campo FieldIncludeText nel paragrafo. Questo campo ti consente di includere il testo di un altro documento.

```csharp
// Inserisci il campo FieldIncludeText.
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);
```

## Passaggio 4: imposta le proprietà del campo

Dobbiamo specificare le proprietà per il campo FieldIncludeText. Ciò include l'impostazione del nome del segnalibro e del percorso completo del documento di origine.

```csharp
fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = dataDir + "IncludeText.docx";
```

## Passaggio 5: aggiungi paragrafo al documento

Con il campo impostato, aggiungiamo il paragrafo al corpo della prima sezione del documento.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Passaggio 6: campo di aggiornamento

Prima di salvare il documento, dobbiamo aggiornare FieldIncludeText per assicurarci che inserisca il contenuto corretto dal documento di origine.

```csharp
fieldIncludeText.Update();
```

## Passaggio 7: salva il documento

Infine, salviamo il documento nella directory specificata.

```csharp
doc.Save(dataDir + "InsertionFieldFieldIncludeTextWithoutDocumentBuilder.docx");
```

## Conclusione

E il gioco è fatto! Seguendo questi passaggi, puoi facilmente inserire un FieldIncludeText senza utilizzare DocumentBuilder in Aspose.Words per .NET. Questo approccio fornisce un modo semplificato per includere contenuto da un documento a un altro, rendendo le attività di automazione dei documenti molto più semplici.

## Domande frequenti

### Cos'è Aspose.Words per .NET?  
Aspose.Words per .NET è una potente libreria per lavorare con documenti Word nelle applicazioni .NET. Consente di creare, modificare e convertire documenti a livello di codice.

### Perché utilizzare FieldIncludeText?  
FieldIncludeText è utile per includere dinamicamente il contenuto da un documento a un altro, consentendo documenti più modulari e gestibili.

### Posso utilizzare questo metodo per includere testo da altri formati di file?  
FieldIncludeText funziona specificamente con i documenti Word. Per altri formati, potresti aver bisogno di metodi o classi diversi forniti da Aspose.Words.

### Aspose.Words per .NET è compatibile con .NET Core?  
Sì, Aspose.Words per .NET supporta .NET Framework, .NET Core e .NET 5/6.

### Come posso ottenere una prova gratuita di Aspose.Words per .NET?  
 Puoi ottenere una prova gratuita da[Qui](https://releases.aspose.com/).