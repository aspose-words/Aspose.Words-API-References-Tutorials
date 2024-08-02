---
title: Numero elenco riavvio
linktitle: Numero elenco riavvio
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come reimpostare il numero di un elenco in un documento di Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-list/restart-list-number/
---
In questo tutorial passo passo, ti mostreremo come reimpostare il numero di un elenco in un documento Word utilizzando Aspose.Words per .NET. Spiegheremo il codice sorgente C# fornito e ti mostreremo come implementarlo nei tuoi progetti.

 Per iniziare, assicurati di avere Aspose.Words per .NET installato e configurato nel tuo ambiente di sviluppo. Se non l'hai già fatto, scarica e installa la libreria da[Aspose.Releases]https://releases.aspose.com/words/net/.

## Passaggio 1: creazione del documento e del generatore di documenti

Innanzitutto, crea un nuovo documento e un generatore di documenti associato:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: creazione e personalizzazione del primo elenco

Successivamente, crea un elenco basato su un modello esistente, quindi personalizza i suoi livelli:

```csharp
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;
```

## Passaggio 3: aggiunta di elementi al primo elenco

Utilizza il generatore di documenti per aggiungere elementi al primo elenco e rimuovere i numeri dell'elenco:

```csharp
builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## Passaggio 4: creazione e personalizzazione del secondo elenco

Per riutilizzare il primo elenco reimpostando il numero, crea una copia del layout dell'elenco originale:

```csharp
List list2 = doc.Lists.AddCopy(list1);
list2.ListLevels[0].StartAt = 10;
```

Se necessario, puoi anche apportare ulteriori modifiche al secondo elenco.

## Passaggio 5: aggiunta di elementi al secondo elenco

Utilizza nuovamente il generatore di documenti per aggiungere elementi al secondo elenco e rimuovere i numeri dell'elenco:

```csharp
builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## Passaggio 6: salva il documento modificato

Infine, salva il documento modificato:

```csharp
builder.Document.Save(dataDir + "ResetListNumber.docx");
```

COSÌ ! Hai reimpostato con successo il numero di un elenco in un documento di Word utilizzando Aspose.Words per .NET.

### Codice sorgente di esempio per la reimpostazione del numero di elenco

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Crea un elenco basato su un modello.
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;

builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

// Per riutilizzare il primo elenco è necessario riavviare la numerazione creando una copia della formattazione dell'elenco originale.
List list2 = doc.Lists.AddCopy(list1);

// Possiamo modificare il nuovo elenco in qualsiasi modo, anche impostando un nuovo numero di partenza.
list2.ListLevels[0].StartAt = 10;

builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

builder.Document.Save(dataDir + "WorkingWithList.RestartListNumber.docx");
            
```

### Domande frequenti

#### D: Come posso riavviare la numerazione di un elenco in Aspose.Words?

 R: Per riavviare la numerazione di un elenco in Aspose.Words, è possibile utilizzare il file`ListRestartAtNumber` metodo del`List` classe. Questo metodo consente di impostare un nuovo valore di composizione da cui riavviare l'elenco. Ad esempio, puoi usare`list.ListRestartAtNumber(1)` per ricominciare la numerazione da 1.

#### D: È possibile personalizzare il prefisso e il suffisso della numerazione dell'elenco riavviato in Aspose.Words?

 R: Sì, puoi personalizzare il prefisso e il suffisso della numerazione dell'elenco riavviato in Aspose.Words. IL`ListLevel`class offre proprietà come`ListLevel.NumberPrefix`E`ListLevel.NumberSuffix` che consentono di specificare il prefisso e il suffisso per ciascun livello nell'elenco. È possibile utilizzare queste proprietà per personalizzare il prefisso e il suffisso secondo necessità.

#### D: Come posso specificare un valore di numerazione specifico da cui riavviare l'elenco?

 R: Per specificare un valore numerico specifico da cui riavviare l'elenco, è possibile utilizzare il comando`ListRestartAtNumber` metodo che passa il valore desiderato come argomento. Ad esempio, per riavviare la numerazione da 5, è possibile utilizzare`list.ListRestartAtNumber(5)`.

#### D: È possibile riavviare la numerazione degli elenchi a più livelli in Aspose.Words?

 R: Sì, Aspose.Words supporta il riavvio della numerazione di più livelli di elenco. Puoi applicare il`ListRestartAtNumber` metodo a ogni livello di elenco per riavviare la numerazione individualmente. Ad esempio, puoi usare`list.Levels[0].ListRestartAtNumber(1)` per riavviare il primo livello dell'elenco da 1 e`list.Levels[1].ListRestartAtNumber(1)` per riavviare la lista di secondo livello partendo da 1, e così via.



