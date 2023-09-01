---
title: Tieni il tavolo unito
linktitle: Tieni il tavolo unito
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come tenere insieme una tabella in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-tables/keep-table-together/
---

In questo tutorial impareremo come tenere insieme una tabella in un documento Word utilizzando Aspose.Words per .NET. Seguiremo una guida passo passo per comprendere il codice e implementare questa funzionalità. Alla fine di questo tutorial, sarai in grado di mantenere intatta una tabella senza che si divida su più pagine nei tuoi documenti Word.

## Passaggio 1: impostazione del progetto
1. Avvia Visual Studio e crea un nuovo progetto C#.
2. Aggiungi un riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: caricamento del documento e recupero della tabella
Per avviare l'elaborazione delle parole con la tabella, dobbiamo caricare il documento e recuperare la tabella che vogliamo tenere insieme. Segui questi passi:

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Caricare il documento
Document doc = new Document(dataDir + "Table spanning two pages.docx");

// Recupera la tabella
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Assicurati di sostituire "LA TUA DIRECTORY DOCUMENTI" con il percorso effettivo della directory dei documenti.

## Passaggio 3: attiva l'opzione "KeepWithNext".
Per mantenere unita la tabella ed evitare che si divida su più pagine, dobbiamo abilitare l'opzione "KeepWithNext" per ogni paragrafo della tabella tranne gli ultimi paragrafi dell'ultima riga della tabella. Utilizza il seguente codice:

```csharp
foreach(Cell cell in table.GetChildNodes(NodeType.Cell, true))
{
cell.EnsureMinimum();
foreach(Paragraph para in cell.Paragraphs)
if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
para.ParagraphFormat.KeepWithNext = true;
}
```

Qui passiamo in rassegna ogni cella della tabella e abilitiamo l'opzione "KeepWithNext" per ogni paragrafo nella cella tranne gli ultimi paragrafi dell'ultima riga nella tabella.

## Passaggio 4: salvataggio del documento modificato
Infine, dobbiamo salvare il documento modificato con la tabella tenuta insieme. Utilizza il seguente codice:

```csharp
doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

Assicurati di specificare il percorso e il nome file corretti per il documento di output.

### Codice sorgente di esempio per Keep Table Together utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table spanning two pages.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Dobbiamo abilitare KeepWithNext per ogni paragrafo nella tabella per evitare che si spezzi su una pagina,
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
In questo tutorial, abbiamo imparato come tenere insieme una tabella in un documento Word utilizzando Aspose.Words per .NET. Seguendo questa guida passo passo e implementando il codice C# fornito, puoi mantenere intatta una tabella ed evitare che venga suddivisa su più pagine nei tuoi documenti. Questa funzionalità ti offre un maggiore controllo sull'aspetto e sul layout delle tabelle nei tuoi documenti.