---
title: Riavvia l'elenco in ogni sezione
linktitle: Riavvia l'elenco in ogni sezione
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come reimpostare un elenco numerato in ciascuna sezione in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-list/restart-list-at-each-section/
---

In questo tutorial passo passo, ti mostreremo come reimpostare un elenco numerato su ciascuna sezione in un documento Word utilizzando Aspose.Words per .NET. Spiegheremo il codice sorgente C# fornito e ti mostreremo come implementarlo nei tuoi progetti.

 Per iniziare, assicurati di avere Aspose.Words per .NET installato e configurato nel tuo ambiente di sviluppo. Se non l'hai già fatto, scarica e installa la libreria da[Aspose.Releases]https://releases.aspose.com/words/net/.

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

 Quindi utilizzare a`DocumentBuilder` per aggiungere elementi all'elenco. Puoi utilizzare un ciclo per aggiungere più elementi all'elenco:

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

In questo esempio, stiamo inserendo un'interruzione di sezione dopo la quindicesima voce dell'elenco per illustrare la rinumerazione.

## Passaggio 3: salva il documento modificato

Infine, salva il documento modificato:

```csharp
OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);
```

COSÌ ! Hai reimpostato con successo un elenco numerato in ciascuna sezione in un documento di Word utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per reimpostare l'elenco in ciascuna sezione

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

Sentiti libero di utilizzare questo codice nei tuoi progetti e modificarlo per adattarlo alle tue esigenze specifiche.

### Domande frequenti

#### D: Come posso riavviare un elenco in ogni sezione di Aspose.Words?

 R: Per riavviare un elenco in ogni sezione di Aspose.Words, è necessario creare un'istanza di`List`classe e assegnarle un elenco numerato. Quindi puoi usare il`List.IsRestartAtEachSection` proprietà per specificare che la numerazione deve essere riavviata ad ogni sezione. Puoi associare questo elenco ad una o più sezioni del tuo documento in modo che la numerazione ricominci correttamente ad ogni sezione.

#### D: Posso personalizzare il formato di numerazione degli elenchi in Aspose.Words?

 R: Sì, puoi personalizzare il formato di numerazione degli elenchi in Aspose.Words. IL`List` class offre diverse proprietà per questo, come ad esempio`List.ListFormat.ListType`, `List.ListLevels`, `ListLevel.NumberFormat`, ecc. È possibile utilizzare queste proprietà per impostare il tipo di elenco (numerato, puntato e così via), il formato di numerazione (numeri arabi, numeri romani, lettere e così via) e altre opzioni di formattazione della numerazione.

#### D: È possibile aggiungere ulteriori livelli a un elenco numerato in Aspose.Words?

 R: Sì, è possibile aggiungere ulteriori livelli a un elenco numerato in Aspose.Words. IL`ListLevel`La classe consente di impostare le proprietà di formattazione per ogni livello dell'elenco. Puoi impostare opzioni come prefisso, suffisso, allineamento, rientro, ecc. Ciò ti consente di creare elenchi con più livelli di gerarchia.