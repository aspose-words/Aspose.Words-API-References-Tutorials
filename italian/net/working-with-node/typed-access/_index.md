---
title: Accesso digitato
linktitle: Accesso digitato
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come utilizzare l'accesso digitato per manipolare le tabelle in Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-node/typed-access/
---

Ecco una guida passo passo per spiegare il codice sorgente C# di seguito che illustra come utilizzare la funzionalità di accesso tipizzato con Aspose.Words per .NET.

## Passaggio 1: importare i riferimenti necessari
Prima di iniziare, assicurati di aver importato i riferimenti necessari per utilizzare Aspose.Words per .NET nel tuo progetto. Ciò include l'importazione della libreria Aspose.Words e l'aggiunta degli spazi dei nomi richiesti al file di origine.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

## Passaggio 2: creare un nuovo documento
 In questo passaggio, creeremo un nuovo documento utilizzando il file`Document` classe.

```csharp
Document doc = new Document();
```

## Passaggio 3: accedi alla sezione e al corpo
Per accedere alle tabelle contenute nel documento, dobbiamo prima accedere alla sezione e al corpo del documento.

```csharp
Section section = doc.FirstSection;
Body body = section.Body;
```

## Passaggio 4: accesso rapido e digitato alle tabelle
Ora che abbiamo il corpo del documento, possiamo utilizzare l'accesso rapido e digitato per accedere a tutte le tabelle contenute nel corpo.

```csharp
TableCollection tables = body.Tables;
```

## Passaggio 5: sfoglia le tabelle
 Utilizzando un`foreach` loop, possiamo scorrere tutte le tabelle ed eseguire operazioni specifiche su ogni tabella.

```csharp
foreach(Table table in tables)
{
     // Accesso rapido e digitato alla prima riga della tabella.
     table.FirstRow?.Remove();

     // Accesso rapido e digitato all'ultima riga della tabella.
     table.LastRow?.Remove();
}
```

In questo esempio, eliminiamo la prima e l'ultima riga di ogni tabella utilizzando l'accesso rapido e digitato fornito da Aspose.Words.

### Esempio di codice sorgente per l'accesso tipizzato con Aspose.Words per .NET

```csharp
	Document doc = new Document();

	Section section = doc.FirstSection;
	Body body = section.Body;
	
	// Accesso digitato rapido a tutti i nodi figlio della tabella contenuti nel corpo.
	TableCollection tables = body.Tables;

	foreach (Table table in tables)
	{
		// Accesso digitato rapido alla prima riga della tabella.
		table.FirstRow?.Remove();

		// Accesso digitato rapido all'ultima riga della tabella.
		table.LastRow?.Remove();
	}
            
```

Questo è un codice di esempio completo per l'accesso digitato alle tabelle con Aspose.Words per .NET. Assicurati di importare i riferimenti necessari e segui i passaggi precedentemente descritti per integrare questo codice nel tuo progetto.

---
