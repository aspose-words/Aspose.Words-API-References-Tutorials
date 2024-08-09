---
title: Numero elenco riavvio
linktitle: Numero elenco riavvio
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come riavviare i numeri dell'elenco nei documenti di Word utilizzando Aspose.Words per .NET. Questa guida dettagliata di 2000 parole copre tutto ciò che devi sapere, dalla configurazione alla personalizzazione avanzata.
type: docs
weight: 10
url: /it/net/working-with-list/restart-list-number/
---
## Introduzione

Stai cercando di padroneggiare l'arte della manipolazione degli elenchi nei tuoi documenti Word utilizzando Aspose.Words per .NET? Bene, sei nel posto giusto! In questo tutorial, approfondiremo il riavvio dei numeri dell'elenco, una funzionalità elegante che porterà le tue capacità di automazione dei documenti a un livello superiore. Allacciate le cinture e iniziamo!

## Prerequisiti

Prima di addentrarci nel codice, assicuriamoci di avere tutto ciò di cui hai bisogno:

1.  Aspose.Words per .NET: è necessario che sia installato Aspose.Words per .NET. Se non l'hai ancora installato, puoi farlo[scaricalo qui](https://releases.aspose.com/words/net/).
2. Ambiente di sviluppo: assicurati di disporre di un ambiente di sviluppo adatto come Visual Studio.
3. Conoscenza di base di C#: una conoscenza di base di C# ti aiuterà a seguire il tutorial.

## Importa spazi dei nomi

Per prima cosa, importiamo gli spazi dei nomi necessari. Questi sono fondamentali per accedere alle funzionalità di Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Lists;
using System.Drawing;
```

Ora suddividiamo il processo in passaggi facili da seguire. Tratteremo tutto, dalla creazione di un elenco al riavvio della sua numerazione.

## Passaggio 1: imposta il documento e il generatore

Prima di poter iniziare a manipolare gli elenchi, sono necessari un documento e un DocumentBuilder. DocumentBuilder è il tuo strumento di riferimento per aggiungere contenuto al tuo documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: crea e personalizza la tua prima lista

Successivamente, creeremo un elenco basato su un modello e ne personalizzeremo l'aspetto. In questo esempio utilizziamo il formato numerico arabo con parentesi.

```csharp
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;
```

Qui abbiamo impostato il colore del carattere su rosso e allineato il testo a destra.

## Passaggio 3: aggiungi elementi al tuo primo elenco

 Con l'elenco pronto, è il momento di aggiungere alcuni elementi. Quello di DocumentBuilder`ListFormat.List` La proprietà aiuta ad applicare il formato elenco al testo.

```csharp
builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();
```

## Passaggio 4: riavviare la numerazione dell'elenco

Per riutilizzare l'elenco e ricominciare la sua numerazione è necessario creare una copia dell'elenco originale. Ciò consente di modificare il nuovo elenco in modo indipendente.

```csharp
List list2 = doc.Lists.AddCopy(list1);
list2.ListLevels[0].StartAt = 10;
```

In questo esempio, il nuovo elenco inizia dal numero 10.

## Passaggio 5: aggiungi elementi al nuovo elenco

Proprio come prima, aggiungi elementi al tuo nuovo elenco. Ciò dimostra che l'elenco riparte dal numero specificato.

```csharp
builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();
```

## Passaggio 6: salva il documento

Infine, salva il documento nella directory specificata.

```csharp
builder.Document.Save(dataDir + "WorkingWithList.RestartListNumber.docx");
```

## Conclusione

Riavviare i numeri dell'elenco nei documenti di Word utilizzando Aspose.Words per .NET è semplice e incredibilmente utile. Che tu stia generando report, creando documenti strutturati o semplicemente abbia bisogno di un migliore controllo sui tuoi elenchi, questa tecnica è coperta.

## Domande frequenti

### Posso utilizzare altri modelli di elenco oltre a NumberArabicParenthesis?

Assolutamente! Aspose.Words offre vari modelli di elenchi come elenchi puntati, lettere, numeri romani e altro. Puoi scegliere quello che meglio si adatta alle tue esigenze.

### Come posso modificare il livello dell'elenco?

 È possibile modificare il livello dell'elenco modificando il file`ListLevels` proprietà. Per esempio,`list1.ListLevels[1]` si riferirebbe al secondo livello dell'elenco.

### Posso ricominciare la numerazione da qualsiasi numero?

 Sì, puoi impostare il numero iniziale su qualsiasi valore intero utilizzando il comando`StartAt` proprietà del livello elenco.

### È possibile avere una formattazione diversa per diversi livelli di elenco?

Infatti! Ogni livello dell'elenco può avere le proprie impostazioni di formattazione, come carattere, allineamento e stile di numerazione.

### Cosa succede se voglio continuare la numerazione da un elenco precedente invece di ricominciare?

Se vuoi continuare la numerazione, non è necessario creare una copia dell'elenco. Continua semplicemente ad aggiungere elementi all'elenco originale.


