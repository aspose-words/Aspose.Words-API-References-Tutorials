---
title: Specifica livello elenco
linktitle: Specifica livello elenco
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come specificare il livello di elenco in un documento di Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-list/specify-list-level/
---

In questo tutorial passo-passo, ti mostreremo come specificare il livello di elenco in un documento di Word utilizzando Aspose.Words per .NET. Spiegheremo il codice sorgente C# fornito e ti mostreremo come implementarlo nei tuoi progetti.

Per iniziare, assicurati di avere Aspose.Words per .NET installato e configurato nel tuo ambiente di sviluppo. Se non l'hai già fatto, scarica e installa la libreria dal sito ufficiale.

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

## Passaggio 3: Specifica del livello di elenco

 Usa il generatore di documenti`ListLevelNumber`proprietà per specificare il livello di elenco e aggiungere testo al paragrafo:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

Ripetere questi passaggi per specificare i livelli di elenco e aggiungere testo a ogni livello.

## Passaggio 4: creazione e applicazione di un elenco puntato

Puoi anche creare e applicare un elenco puntato utilizzando uno dei modelli di elenco di Microsoft Word:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);
```

## Passaggio 5: aggiunta di testo ai livelli di elenchi puntati

 Usa il`ListLevelNumber` proprietà di nuovo per specificare il livello dell'elenco puntato e aggiungere il testo:

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

## Passaggio 7: salvare il documento modificato

Salva il documento modificato:

```csharp
builder.Document.Save(dataDir + "SpecifyListLevel.docx");
```

COSÌ ! Hai specificato correttamente il livello di elenco in un documento di Word utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per specificare il livello di elenco

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Crea un elenco numerato basato su uno dei modelli di elenco di Microsoft Word
// e applicarlo al paragrafo corrente del generatore di documenti.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);

// Ci sono nove livelli in questo elenco, proviamoli tutti.
for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

//Crea un elenco puntato basato su uno dei modelli di elenco di Microsoft Word
// e applicarlo al paragrafo corrente del generatore di documenti.
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



