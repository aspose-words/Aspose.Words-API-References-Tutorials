---
title: Specificare il livello dell'elenco
linktitle: Specificare il livello dell'elenco
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come specificare il livello dell'elenco in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-list/specify-list-level/
---

In questo tutorial passo passo, ti mostreremo come specificare il livello dell'elenco in un documento Word utilizzando Aspose.Words per .NET. Spiegheremo il codice sorgente C# fornito e ti mostreremo come implementarlo nei tuoi progetti.

 Per iniziare, assicurati di avere Aspose.Words per .NET installato e configurato nel tuo ambiente di sviluppo. Se non l'hai già fatto, scarica e installa la libreria da[Aspose.Releases]https://releases.aspose.com/words/net/.

## Passaggio 1: creazione del documento e del generatore di documenti

Innanzitutto, crea un nuovo documento e un generatore di documenti associato:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: creazione e applicazione di un elenco numerato

Successivamente, crea un elenco numerato basato su uno dei modelli di elenco di Microsoft Word e applicalo al paragrafo corrente nel generatore di documenti:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);
```

## Passaggio 3: specifica del livello di elenco

 Utilizza il generatore di documenti`ListLevelNumber` proprietà per specificare il livello dell'elenco e aggiungere testo al paragrafo:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

Ripetere questi passaggi per specificare i livelli dell'elenco e aggiungere testo a ciascun livello.

## Passaggio 4: creazione e applicazione di un elenco puntato

Puoi anche creare e applicare un elenco puntato utilizzando uno dei modelli di elenco di Microsoft Word:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);
```

## Passaggio 5: aggiunta di testo ai livelli dell'elenco puntato

 Usa il`ListLevelNumber` proprietà nuovamente per specificare il livello dell'elenco puntato e aggiungere testo:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

## Passaggio 6: interrompere la formattazione dell'elenco

 Per interrompere la formattazione dell'elenco, impostare`null` al`List` proprietà del generatore di documenti:

```csharp
builder. ListFormat. List = null;
```

## Passaggio 7: salvataggio del documento modificato

Salva il documento modificato:

```csharp
builder.Document.Save(dataDir + "SpecifyListLevel.docx");
```

COSÌ ! Hai specificato con successo il livello dell'elenco in un documento Word utilizzando Aspose.Words per .NET.

### Codice sorgente di esempio per specificare il livello dell'elenco

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Crea un elenco numerato basato su uno dei modelli di elenco di Microsoft Word
// applicarlo al paragrafo corrente del generatore di documenti.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);

// Ci sono nove livelli in questo elenco, proviamoli tutti.
for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// Crea un elenco puntato basato su uno dei modelli di elenco di Microsoft Word
// applicarlo al paragrafo corrente del generatore di documenti.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);

for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// Questo è un modo per interrompere la formattazione dell'elenco.
builder.ListFormat.List = null;

builder.Document.Save(dataDir + "WorkingWithList.SpecifyListLevel.docx");
            
```

### Domande frequenti

#### D: Come posso specificare il livello dell'elenco in Aspose.Words?

 R: Per specificare il livello dell'elenco in Aspose.Words, è necessario creare un'istanza di`List` classe e fornirgli un elenco numerato. Quindi puoi usare il`Paragraph.ListFormat.ListLevelNumber` proprietà per specificare il livello di ciascun elemento dell'elenco. Puoi associare questo elenco a una sezione del tuo documento in modo che gli elementi dell'elenco abbiano il livello desiderato.

#### D: È possibile modificare il formato di numerazione degli elementi dell'elenco in Aspose.Words?

 R: Sì, puoi modificare il formato di numerazione degli elementi dell'elenco in Aspose.Words. IL`ListLevel` class offre diverse proprietà per questo, come ad esempio`ListLevel.NumberFormat`, `ListLevel.NumberStyle`, `ListLevel.NumberPosition`, ecc. È possibile utilizzare queste proprietà per impostare il formato di numerazione per gli elementi dell'elenco, ad esempio numeri arabi, numeri romani, lettere, ecc.

#### D: Posso aggiungere ulteriori livelli a un elenco numerato in Aspose.Words?

 R: Sì, è possibile aggiungere ulteriori livelli a un elenco numerato in Aspose.Words. IL`ListLevel` La classe consente di impostare le proprietà di formattazione per ogni livello dell'elenco. Puoi impostare opzioni come prefisso, suffisso, allineamento, rientro, ecc. Ciò ti consente di creare elenchi con più livelli di gerarchia.


