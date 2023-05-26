---
title: Riavvia l'elenco in ogni sezione
linktitle: Riavvia l'elenco in ogni sezione
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come reimpostare un elenco numerato in ogni sezione in un documento di Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-list/restart-list-at-each-section/
---

In questo tutorial passo passo, ti mostreremo come reimpostare un elenco numerato in ogni sezione in un documento di Word utilizzando Aspose.Words per .NET. Spiegheremo il codice sorgente C# fornito e ti mostreremo come implementarlo nei tuoi progetti.

Per iniziare, assicurati di avere Aspose.Words per .NET installato e configurato nel tuo ambiente di sviluppo. Se non l'hai già fatto, scarica e installa la libreria dal sito ufficiale.

## Passaggio 1: creazione del documento e dell'elenco

Innanzitutto, crea un nuovo documento e aggiungi un elenco numerato predefinito:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;
```

## Passaggio 2: aggiunta di elementi all'elenco

 Quindi usa a`DocumentBuilder` per aggiungere elementi all'elenco. Puoi utilizzare un ciclo per aggiungere più elementi all'elenco:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
     builder.Writeln($"List item {i}");

     if (i == 15)
         builder.InsertBreak(BreakType.SectionBreakNewPage);
}
```

In questo esempio, stiamo inserendo un'interruzione di sezione dopo il 15° elemento dell'elenco per illustrare la rinumerazione.

## Passaggio 3: salvare il documento modificato

Infine, salva il documento modificato:

```csharp
OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);
```

COSÌ ! Hai reimpostato correttamente un elenco numerato in ogni sezione in un documento di Word utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per reimpostare l'elenco in ogni sezione

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;

DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
	 builder.Writeln($"List item {i}");

	 if (i == 15)
		 builder.InsertBreak(BreakType.SectionBreakNewPage);
}

OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);

```

Sentiti libero di utilizzare questo codice nei tuoi progetti e di modificarlo in base alle tue esigenze specifiche.
