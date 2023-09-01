---
title: Clona tabella completa
linktitle: Clona tabella completa
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come clonare un'intera tabella in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-tables/clone-complete-table/
---

In questo tutorial impareremo come utilizzare Aspose.Words per .NET per clonare un'intera tabella in un documento Word. Seguiremo una guida passo passo per comprendere il codice e implementare questa funzionalità. Alla fine di questo tutorial, sarai in grado di clonare tabelle nei tuoi documenti Word a livello di codice.

## Passaggio 1: impostazione del progetto
1. Avvia Visual Studio e crea un nuovo progetto C#.
2. Aggiungi un riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: caricamento del documento e accesso alla tabella
Per avviare l'elaborazione testi con la tabella, dobbiamo caricare il documento che la contiene e accedervi. Segui questi passi:

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Caricare il documento
Document doc = new Document(dataDir + "Tables.docx");

// Accesso all'array
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Assicurati di sostituire "LA TUA DIRECTORY DOCUMENTI" con il percorso effettivo della directory dei documenti.

## Passaggio 3: clonazione dell'intero array
Successivamente, cloneremo l'intera tabella e la inseriremo nel documento dopo l'originale. Utilizza il seguente codice:

```csharp
// Clona l'array
Table tableClone = (Table)table.Clone(true);

// Inserisci la tabella clonata nel documento dopo l'originale
table.ParentNode.InsertAfter(tableClone, table);

// Inserisci un paragrafo vuoto tra le due tabelle
// Altrimenti verranno combinati in uno solo al momento del salvataggio (questo è dovuto alla convalida del documento)
table.ParentNode.InsertAfter(new Paragraph(doc), table);
```

 Qui stiamo usando il`Clone` metodo per creare una copia completa dell'array. Quindi usiamo`InsertAfter` per inserire la tabella clonata nel documento, dopo la tabella originale. Aggiungiamo anche un paragrafo vuoto tra le due tabelle per evitare che vengano unite durante il salvataggio.

## Passaggio 4: salvataggio del documento modificato
Infine, dobbiamo salvare il documento modificato con la tabella clonata. Utilizza il seguente codice:

```csharp
// Salva il documento modificato
doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

Assicurati di specificare il percorso e il nome file corretti per il documento di output.
  
### Codice sorgente di esempio per Clone Complete Table utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	//Clona la tabella e inseriscila nel documento dopo l'originale.
	Table tableClone = (Table) table.Clone(true);
	table.ParentNode.InsertAfter(tableClone, table);
	// Inserisci un paragrafo vuoto tra le due tabelle,
	// oppure verranno combinati in uno solo al momento del salvataggio, ciò ha a che fare con la convalida del documento.
	table.ParentNode.InsertAfter(new Paragraph(doc), table);
	doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

## Conclusione
In questo tutorial, abbiamo imparato come clonare un'intera tabella in un documento Word utilizzando Aspose.Words per .NET. Seguendo questa guida passo passo e implementando il codice C# fornito, puoi clonare le tabelle nei tuoi documenti Word a livello di codice. Questa funzionalità consente di eseguire manipolazioni avanzate sugli array per soddisfare le proprie esigenze specifiche.