---
title: Riavvia il numero dell'elenco
linktitle: Riavvia il numero dell'elenco
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come reimpostare il numero di un elenco in un documento di Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-list/restart-list-number/
---
In questo tutorial passo-passo, ti mostreremo come reimpostare il numero di un elenco in un documento di Word utilizzando Aspose.Words per .NET. Spiegheremo il codice sorgente C# fornito e ti mostreremo come implementarlo nei tuoi progetti.

Per iniziare, assicurati di avere Aspose.Words per .NET installato e configurato nel tuo ambiente di sviluppo. Se non l'hai già fatto, scarica e installa la libreria dal sito ufficiale.

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

Utilizza il generatore di documenti per aggiungere elementi al primo elenco e rimuovere i numeri di elenco:

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

È inoltre possibile apportare ulteriori modifiche al secondo elenco, se necessario.

## Passaggio 5: aggiunta di elementi al secondo elenco

Utilizza nuovamente il generatore di documenti per aggiungere elementi al secondo elenco e rimuovere i numeri dell'elenco:

```csharp
builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## Passaggio 6: salvare il documento modificato

Infine, salva il documento modificato:

```csharp
builder.Document.Save(dataDir + "ResetListNumber.docx");
```

COSÌ ! Hai reimpostato correttamente il numero di un elenco in un documento di Word utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per il ripristino del numero di elenco

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

// Per riutilizzare il primo elenco, è necessario riavviare la numerazione creando una copia della formattazione originale dell'elenco.
List list2 = doc.Lists.AddCopy(list1);

//Possiamo modificare la nuova lista in qualsiasi modo, inclusa l'impostazione di un nuovo pettorale.
list2.ListLevels[0].StartAt = 10;

builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

builder.Document.Save(dataDir + "WorkingWithList.RestartListNumber.docx");
            
```

### FAQ

#### D: Come posso riavviare la numerazione di un elenco in Aspose.Words?

 R: Per riavviare la numerazione di un elenco in Aspose.Words, puoi utilizzare il`ListRestartAtNumber` metodo del`List` classe. Questo metodo consente di impostare un nuovo valore di chiamata da cui riavviare l'elenco. Ad esempio, puoi usare`list.ListRestartAtNumber(1)` per ricominciare la numerazione da 1.

#### D: È possibile personalizzare il prefisso e il suffisso della numerazione dell'elenco riavviato in Aspose.Words?

 A: Sì, puoi personalizzare il prefisso e il suffisso della numerazione dell'elenco riavviato in Aspose.Words. IL`ListLevel` class offre proprietà come`ListLevel.NumberPrefix` E`ListLevel.NumberSuffix` che consentono di specificare il prefisso e il suffisso per ogni livello nell'elenco. È possibile utilizzare queste proprietà per personalizzare il prefisso e il suffisso secondo necessità.

#### D: Come posso specificare un valore di numerazione specifico da cui riavviare l'elenco?

 R: Per specificare un valore numerico specifico da cui riavviare l'elenco, è possibile utilizzare il file`ListRestartAtNumber`metodo passando il valore desiderato come argomento. Ad esempio, per riavviare la numerazione da 5, puoi utilizzare`list.ListRestartAtNumber(5)`.

#### D: È possibile riavviare la numerazione di elenchi multilivello in Aspose.Words?

 A: Sì, Aspose.Words supporta il riavvio della numerazione di più livelli di elenco. Puoi applicare il`ListRestartAtNumber` metodo a ogni livello di elenco per riavviare la numerazione individualmente. Ad esempio, puoi usare`list.Levels[0].ListRestartAtNumber(1)` per riavviare il primo livello di elenco da 1, e`list.Levels[1].ListRestartAtNumber(1)` per riavviare la lista di secondo livello partendo da 1, e così via.



