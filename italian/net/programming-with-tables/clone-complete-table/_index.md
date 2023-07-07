---
title: Clona tabella completa
linktitle: Clona tabella completa
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come clonare un'intera tabella in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-tables/clone-complete-table/
---

In questo tutorial impareremo come utilizzare Aspose.Words per .NET per clonare un'intera tabella in un documento Word. Seguiremo una guida passo passo per comprendere il codice e implementare questa funzione. Alla fine di questo tutorial, sarai in grado di clonare le tabelle nei tuoi documenti Word a livello di programmazione.

## Passaggio 1: impostazione del progetto
1. Avvia Visual Studio e crea un nuovo progetto C#.
2. Aggiungere un riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: caricamento del documento e accesso alla tabella
Per iniziare a lavorare con la tabella, dobbiamo caricare il documento che la contiene e accedervi. Segui questi passi:

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Carica il documento
Document doc = new Document(dataDir + "Tables.docx");

// Accesso all'array
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Assicurati di sostituire "LA TUA DIRECTORY DEI DOCUMENTI" con il percorso effettivo della tua directory dei documenti.

## Passaggio 3: clone dell'array completo
Successivamente, cloneremo l'intera tabella e la inseriremo nel documento dopo l'originale. Usa il seguente codice:

```csharp
// Clonare l'array
Table tableClone = (Table)table.Clone(true);

// Inserisci la tabella clonata nel documento dopo l'originale
table.ParentNode.InsertAfter(tableClone, table);

// Inserisci un paragrafo vuoto tra le due tabelle
// Altrimenti verranno combinati in uno solo al salvataggio (questo è dovuto alla convalida del documento)
table.ParentNode.InsertAfter(new Paragraph(doc), table);
```

 Qui stiamo usando il`Clone` metodo per creare una copia completa dell'array. Quindi usiamo`InsertAfter` per inserire la tabella clonata nel documento, dopo la tabella originale. Aggiungiamo anche un paragrafo vuoto tra le due tabelle per evitare che vengano unite durante il salvataggio.

## Passaggio 4: salvare il documento modificato
Infine, dobbiamo salvare il documento modificato con la tabella clonata. Usa il seguente codice:

```csharp
// Salva il documento modificato
doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

Assicurati di specificare il percorso e il nome file corretti per il documento di output.
  
### Esempio di codice sorgente per Clone Complete Table utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Clona la tabella e inseriscila nel documento dopo l'originale.
	Table tableClone = (Table) table.Clone(true);
	table.ParentNode.InsertAfter(tableClone, table);
	// Inserisci un paragrafo vuoto tra le due tabelle,
	//oppure saranno combinati in uno al momento del salvataggio, questo ha a che fare con la convalida del documento.
	table.ParentNode.InsertAfter(new Paragraph(doc), table);
	doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

## Conclusione
In questo tutorial, abbiamo imparato come clonare un'intera tabella in un documento Word utilizzando Aspose.Words per .NET. Seguendo questa guida dettagliata e implementando il codice C# fornito, è possibile clonare le tabelle nei documenti di Word a livello di programmazione. Questa funzione consente di eseguire manipolazioni avanzate sugli array per soddisfare le proprie esigenze specifiche.