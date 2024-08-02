---
title: Modifica i controlli del contenuto
linktitle: Modifica i controlli del contenuto
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come modificare i tag dei documenti strutturati in Word utilizzando Aspose.Words per .NET. Aggiorna testo, menu a discesa e immagini passo dopo passo.
type: docs
weight: 10
url: /it/net/programming-with-sdt/modify-content-controls/
---
## introduzione

Se hai mai lavorato con documenti di Word e hai avuto bisogno di modificare controlli di contenuto strutturato, come testo semplice, elenchi a discesa o immagini, utilizzando Aspose.Words per .NET, sei nel posto giusto! I tag di documenti strutturati (SDT) sono strumenti potenti che rendono l'automazione dei documenti più semplice e flessibile. In questo tutorial, approfondiremo come modificare questi SDT per adattarli alle tue esigenze. Che tu stia aggiornando il testo, modificando le selezioni a discesa o scambiando immagini, questa guida ti guiderà attraverso il processo passo dopo passo.

## Prerequisiti

Prima di addentrarci nel nocciolo della questione della modifica dei controlli del contenuto, assicurati di avere quanto segue:

1.  Aspose.Words per .NET installato: assicurati di avere la libreria Aspose.Words installata. In caso contrario, puoi[scaricalo qui](https://releases.aspose.com/words/net/).

2. Conoscenza di base di C#: questa esercitazione presuppone che tu abbia familiarità con i concetti di base della programmazione C#.

3. Un ambiente di sviluppo .NET: dovresti avere un IDE come Visual Studio configurato per l'esecuzione di applicazioni .NET.

4. Un documento di esempio: utilizzeremo un documento Word di esempio con vari tipi di SDT. Puoi usare quello dell'esempio o crearne uno tuo.

5.  Accesso alla documentazione Aspose: per informazioni più dettagliate, consultare il[Documentazione Aspose.Words](https://reference.aspose.com/words/net/).

## Importa spazi dei nomi

Per iniziare a lavorare con Aspose.Words, devi importare gli spazi dei nomi rilevanti nel tuo progetto C#. Ecco come farlo:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Tables;
```

Questi spazi dei nomi ti daranno accesso alle classi e ai metodi necessari per manipolare i tag dei documenti strutturati nei tuoi documenti Word.

## Passaggio 1: imposta il percorso del documento

 Prima di apportare qualsiasi modifica, è necessario specificare il percorso del documento. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo in cui è archiviato il documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Structured document tags.docx");
```

## Passaggio 2: scorrere i tag dei documenti strutturati

 Per modificare gli SDT, devi prima scorrere tutti gli SDT nel documento. Questo viene fatto utilizzando il`GetChildNodes` metodo per ottenere tutti i nodi di tipo`StructuredDocumentTag`.

```csharp
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
    // Modifica gli SDT in base al loro tipo
}
```

## Passaggio 3: modificare gli SDT in testo normale

Se l'SDT è di tipo testo normale, è possibile sostituirne il contenuto. Innanzitutto, cancella il contenuto esistente, quindi aggiungi il nuovo testo.

```csharp
if (sdt.SdtType == SdtType.PlainText)
{
    sdt.RemoveAllChildren();
    Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
    Run run = new Run(doc, "new text goes here");
    para.AppendChild(run);
}
```

 Spiegazione: ecco,`RemoveAllChildren()`cancella il contenuto esistente dell'SDT. Quindi ne creiamo uno nuovo`Paragraph`E`Run` oggetto per inserire il nuovo testo.

## Passaggio 4: modificare gli SDT dell'elenco a discesa

 Per gli SDT con elenco a discesa, è possibile modificare l'elemento selezionato accedendo al file`ListItems` collezione. Qui selezioniamo il terzo elemento nell'elenco.

```csharp
if (sdt.SdtType == SdtType.DropDownList)
{
    SdtListItem secondItem = sdt.ListItems[2];
    sdt.ListItems.SelectedValue = secondItem;
}
```

Spiegazione: questo frammento di codice seleziona l'elemento all'indice 2 (terzo elemento) dall'elenco a discesa. Modifica l'indice in base alle tue esigenze.

## Passaggio 5: modificare gli SDT delle immagini

Per aggiornare un'immagine all'interno di un SDT immagine, è possibile sostituire l'immagine esistente con una nuova.

```csharp
if (sdt.SdtType == SdtType.Picture)
{
    Shape shape = (Shape) sdt.GetChild(NodeType.Shape, 0, true);
    if (shape.HasImage)
    {
        shape.ImageData.SetImage(ImagesDir + "Watermark.png");
    }
}
```

 Spiegazione: questo codice controlla se la forma contiene un'immagine e quindi la sostituisce con una nuova immagine situata in`ImagesDir`.

## Passaggio 6: salva il documento modificato

Dopo aver apportato tutte le modifiche necessarie, salva il documento modificato con un nuovo nome per mantenere intatto il documento originale.

```csharp
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");
```

Spiegazione: Ciò salva il documento con un nuovo nome file in modo da poterlo facilmente differenziare dall'originale.

## Conclusione

La modifica dei controlli del contenuto in un documento Word utilizzando Aspose.Words per .NET è semplice una volta compresi i passaggi coinvolti. Che tu stia aggiornando il testo, modificando le selezioni a discesa o scambiando immagini, Aspose.Words fornisce un'API solida per queste attività. Seguendo questo tutorial, puoi gestire e personalizzare in modo efficace i controlli del contenuto strutturato del tuo documento, rendendo i tuoi documenti più dinamici e adattati alle tue esigenze.

## Domande frequenti

1. Cos'è un tag di documento strutturato (SDT)?

Gli SDT sono elementi nei documenti di Word che aiutano a gestire e formattare il contenuto del documento, come caselle di testo, elenchi a discesa o immagini.

2. Come posso aggiungere un nuovo elemento a discesa a un SDT?

 Per aggiungere un nuovo elemento, utilizzare il file`ListItems` proprietà e aggiungerne una nuova`SdtListItem` alla raccolta.

3. Posso utilizzare Aspose.Words per rimuovere SDT da un documento?

Sì, puoi rimuovere gli SDT accedendo ai nodi del documento ed eliminando l'SDT desiderato.

4. Come gestisco gli SDT nidificati all'interno di altri elementi?

 Usa il`GetChildNodes` metodo con parametri appropriati per accedere agli SDT nidificati.

5. Cosa devo fare se l'SDT che devo modificare non è visibile nel documento?

Assicurarsi che l'SDT non sia nascosto o protetto. Controlla le impostazioni del documento e assicurati che il tuo codice sia indirizzato correttamente al tipo SDT.


### Codice sorgente di esempio per Modifica controlli contenuto utilizzando Aspose.Words per .NET 

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Structured document tags.docx");
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
	switch (sdt.SdtType)
	{
		case SdtType.PlainText:
		{
			sdt.RemoveAllChildren();
			Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
			Run run = new Run(doc, "new text goes here");
			para.AppendChild(run);
			break;
		}
		case SdtType.DropDownList:
		{
			SdtListItem secondItem = sdt.ListItems[2];
			sdt.ListItems.SelectedValue = secondItem;
			break;
		}
		case SdtType.Picture:
		{
			Shape shape = (Shape) sdt.GetChild(NodeType.Shape, 0, true);
			if (shape.HasImage)
			{
				shape.ImageData.SetImage(ImagesDir + "Watermark.png");
			}
			break;
		}
	}
}
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");

```

Questo è tutto! Hai modificato con successo diversi tipi di controlli del contenuto nel tuo documento Word utilizzando Aspose.Words per .NET.