---
title: Mantieni il tavolo insieme
linktitle: Mantieni il tavolo insieme
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come tenere insieme un tavolo in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-tables/keep-table-together/
---

In questo tutorial impareremo come tenere insieme una tabella in un documento di Word usando Aspose.Words per .NET. Seguiremo una guida passo passo per comprendere il codice e implementare questa funzione. Alla fine di questo tutorial, sarai in grado di mantenere intatta una tabella senza che si divida su più pagine nei tuoi documenti di Word.

## Passaggio 1: impostazione del progetto
1. Avvia Visual Studio e crea un nuovo progetto C#.
2. Aggiungere un riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: caricamento del documento e recupero della tabella
Per avviare l'elaborazione di parole con la tabella, dobbiamo caricare il documento e recuperare la tabella che vogliamo tenere insieme. Segui questi passi:

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carica il documento
Document doc = new Document(dataDir + "Table spanning two pages.docx");

// Recupera il tavolo
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Assicurati di sostituire "LA TUA DIRECTORY DEI DOCUMENTI" con il percorso effettivo della tua directory dei documenti.

## Passaggio 3: abilita l'opzione "KeepWithNext".
Per mantenere unita la tabella e impedire che si divida su più pagine, è necessario abilitare l'opzione "KeepWithNext" per ogni paragrafo della tabella ad eccezione degli ultimi paragrafi dell'ultima riga della tabella. Usa il seguente codice:

```csharp
foreach(Cell cell in table.GetChildNodes(NodeType.Cell, true))
{
cell.EnsureMinimum();
foreach(Paragraph para in cell.Paragraphs)
if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
para.ParagraphFormat.KeepWithNext = true;
}
```

Qui scorriamo ogni cella della tabella e abilitiamo l'opzione "KeepWithNext" per ogni paragrafo nella cella ad eccezione degli ultimi paragrafi dell'ultima riga della tabella.

## Passaggio 4: salvare il documento modificato
Infine, dobbiamo salvare il documento modificato con la tabella tenuta insieme. Usa il seguente codice:

```csharp
doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

Assicurati di specificare il percorso e il nome file corretti per il documento di output.

### Esempio di codice sorgente per Keep Table Together utilizzando Aspose.Words per .NET 

```csharp
	//Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table spanning two pages.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Dobbiamo abilitare KeepWithNext per ogni paragrafo nella tabella per evitare che si interrompa su una pagina,
	// ad eccezione degli ultimi paragrafi dell'ultima riga della tabella.
	foreach (Cell cell in table.GetChildNodes(NodeType.Cell, true))
	{
		cell.EnsureMinimum();
		foreach (Paragraph para in cell.Paragraphs)
			if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
				para.ParagraphFormat.KeepWithNext = true;
	}
	doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

## Conclusione
In questo tutorial, abbiamo imparato come tenere insieme una tabella in un documento di Word utilizzando Aspose.Words per .NET. Seguendo questa guida dettagliata e implementando il codice C# fornito, puoi mantenere intatta una tabella e impedire che venga suddivisa su più pagine nei tuoi documenti. Questa funzione ti offre un maggiore controllo sull'aspetto e sul layout delle tue tabelle nei tuoi documenti.