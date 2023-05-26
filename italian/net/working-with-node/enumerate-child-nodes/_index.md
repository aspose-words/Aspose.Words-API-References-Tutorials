---
title: Enumerare i nodi figlio
linktitle: Enumerare i nodi figlio
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come enumerare i nodi figlio in un paragrafo con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-node/enumerate-child-nodes/
---

Ecco una guida passo passo per spiegare il codice sorgente C# di seguito che illustra come enumerare i nodi figlio utilizzando Aspose.Words per .NET.

## Passaggio 1: importare i riferimenti necessari
Prima di iniziare, assicurati di aver importato i riferimenti necessari per utilizzare Aspose.Words per .NET nel tuo progetto. Ciò include l'importazione della libreria Aspose.Words e l'aggiunta degli spazi dei nomi richiesti al file di origine.

```csharp
using Aspose.Words;
using Aspose.Words.Nodes;
using Aspose.Words.NodeTypes;
```

## Passaggio 2: creare un nuovo documento
 In questo passaggio, creeremo un nuovo documento utilizzando il file`Document` classe.

```csharp
Document doc = new Document();
```

## Passaggio 3: accedi al paragrafo e ai suoi nodi figlio
 Per enumerare i nodi figlio di un paragrafo, dobbiamo prima accedere al paragrafo stesso. Usa il`GetChild` metodo con il`Paragraph` tipo di nodo per ottenere il primo paragrafo del documento.

```csharp
Paragraph paragraph = (Paragraph)doc.GetChild(NodeType.Paragraph, 0, true);
```

Successivamente, recuperiamo la raccolta dei nodi figlio del paragrafo utilizzando il file`ChildNodes` proprietà.

```csharp
NodeCollection children = paragraph. ChildNodes;
```

## Passaggio 4: sfoglia i nodi figlio
 Ora che abbiamo la raccolta di nodi figli, possiamo scorrerli usando a`foreach` ciclo continuo. Controlliamo il tipo di ciascun nodo figlio ed eseguiamo operazioni specifiche in base al tipo.

```csharp
foreach (Node child in children)
{
     // Un paragrafo può contenere elementi secondari di tipi diversi come sequenze, forme e altri.
     if (child. NodeType == NodeType.Run)
     {
         Run run = (Run)child;
         Console.WriteLine(run.Text);
     }
}
```

 In questo esempio, stiamo controllando se il nodo figlio è di tipo`Run` (ad esempio un frammento di testo). In tal caso, convertiamo il nodo in`Run` e visualizzare il testo utilizzando`run.Text`.

## Codice sorgente di esempio per l'enumerazione dei nodi figlio con Aspose.Words per .NET


```csharp
	Document doc = new Document();
	Paragraph paragraph = (Paragraph) doc.GetChild(NodeType.Paragraph, 0, true);

	NodeCollection children = paragraph.ChildNodes;
	foreach (Node child in children)
	{
		// Un paragrafo può contenere figli di vari tipi come sequenze, forme e altri.
		if (child.NodeType == NodeType.Run)
		{
			Run run = (Run) child;
			Console.WriteLine(run.Text);
		}
	}
            
```

Questo è un esempio di codice completo per enumerare i nodi figlio di un paragrafo con Aspose.Words per .NET. Assicurati di importare i riferimenti

