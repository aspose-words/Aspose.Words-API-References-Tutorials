---
title: Elenco Usa stili di destinazione
linktitle: Elenco Usa stili di destinazione
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come unire e aggiungere documenti di Word preservando gli stili di elenco del documento di destinazione utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/join-and-append-documents/list-use-destination-styles/
---

Questo tutorial ti guiderà attraverso il processo di utilizzo della funzione List Use Destination Styles di Aspose.Words per .NET. Questa funzione consente di unire e aggiungere documenti di Word mentre si utilizzano gli stili di elenco del documento di destinazione.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

1. Aspose.Words per .NET installato. Puoi scaricarlo dal sito Web di Aspose o installarlo tramite NuGet.
2. Visual Studio o qualsiasi altro ambiente di sviluppo C#.

## Passaggio 1: inizializzare le directory dei documenti

 Innanzitutto, devi impostare il percorso della directory dei documenti. Modificare il valore di`dataDir` variabile al percorso in cui si trovano i documenti.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: caricare i documenti di origine e di destinazione

 Successivamente, è necessario caricare i documenti di origine e destinazione utilizzando Aspose.Words`Document` classe. Aggiorna i nomi dei file nel file`Document` costruttore in base ai nomi dei documenti.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Passaggio 3: imposta il documento di origine su Continua dopo il documento di destinazione

 Per garantire che il contenuto del documento di origine continui dopo la fine del documento di destinazione, è necessario impostare il file`SectionStart` proprietà della prima sezione nel documento di origine to`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Passaggio 4: gestire la formattazione dell'elenco

Per gestire la formattazione dell'elenco, ripeterai ogni paragrafo nel documento di origine e controllerai se si tratta di un elemento dell'elenco. Se lo è, confronterai l'ID elenco con gli elenchi esistenti nel documento di destinazione. Se esiste un elenco con lo stesso ID, creerai una copia dell'elenco nel documento di origine e aggiornerai il formato dell'elenco del paragrafo per utilizzare l'elenco copiato.

```csharp
Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();

foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    if (para.IsListItem)
    {
        int listId = para.ListFormat.List.ListId;
        if (dstDoc.Lists.GetListByListId(listId) != null)
        {
            Aspose.Words.Lists.List currentList;
            if (newLists.ContainsKey(listId))
            {
                currentList = newLists[listId];
            }
            else
            {
                currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
                newLists.Add(listId, currentList);
            }
            para.ListFormat.List = currentList;
        }
    }
}
```

## Passaggio 5: aggiungere il documento di origine al documento di destinazione

 Ora puoi aggiungere il documento di origine al documento di destinazione utilizzando il file`AppendDocument` metodo del`Document` classe. IL`ImportFormatMode.UseDestinationStyles` Il parametro assicura che gli stili di elenco del documento di destinazione vengano utilizzati durante l'operazione di accodamento.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## Passaggio 6: salvare il documento finale

Infine, salva il documento unito con la funzione Elenco Usa stili di destinazione abilitata utilizzando il file`Save` metodo del`Document` classe.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

### Esempio di codice sorgente per List Usa stili di destinazione utilizzando Aspose.Words per .NET 

Ecco il codice sorgente completo per la funzionalità "Elenco stili destinazione uso" in C# utilizzando Aspose.Words per .NET:


```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Impostare il documento di origine in modo che continui subito dopo la fine del documento di destinazione.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Tieni traccia degli elenchi che vengono creati.
	Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		if (para.IsListItem)
		{
			int listId = para.ListFormat.List.ListId;
			// Controlla se il documento di destinazione contiene già un elenco con questo ID. Se lo fa, allora questo potrebbe
			// fare in modo che i due elenchi vengano eseguiti insieme. Crea invece una copia dell'elenco nel documento di origine.
			if (dstDoc.Lists.GetListByListId(listId) != null)
			{
				Aspose.Words.Lists.List currentList;
				// Esiste già un elenco appena copiato per questo ID, recuperare l'elenco memorizzato,
				// e usalo sul paragrafo corrente.
				if (newLists.ContainsKey(listId))
				{
					currentList = newLists[listId];
				}
				else
				{
					// Aggiungi una copia di questo elenco al documento e conservalo per riferimento futuro.
					currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
					newLists.Add(listId, currentList);
				}
				// Imposta l'elenco di questo paragrafo sull'elenco copiato.
				para.ListFormat.List = currentList;
			}
		}
	}
	// Aggiungi il documento di origine alla fine del documento di destinazione.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

Questo è tutto! Hai implementato correttamente la funzione List Use Destination Styles utilizzando Aspose.Words per .NET. Il documento finale conterrà il contenuto unito con gli stili di elenco del documento di destinazione.