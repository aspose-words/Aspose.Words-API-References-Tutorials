---
title: Disposizione nella cella
linktitle: Disposizione nella cella
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come impostare il layout nella cella utilizzando Aspose.Words per .NET con questa guida completa. Perfetto per gli sviluppatori che desiderano personalizzare i documenti Word.
type: docs
weight: 10
url: /it/net/programming-with-shapes/layout-in-cell/
---
## Introduzione

Se hai sempre desiderato ottimizzare a livello di programmazione il layout delle celle della tabella nei documenti di Word, sei nel posto giusto. Oggi approfondiremo come impostare il layout nella cella utilizzando Aspose.Words per .NET. Esamineremo un esempio pratico, analizzandolo passo dopo passo in modo che tu possa seguirlo facilmente.

## Prerequisiti

Prima di addentrarci nel codice, assicuriamoci di avere tutto ciò di cui hai bisogno:

1.  Aspose.Words per .NET: assicurati di avere la libreria Aspose.Words per .NET installata. Se non l'hai fatto, puoi[scaricalo qui](https://releases.aspose.com/words/net/).
2. Ambiente di sviluppo: avrai bisogno di un ambiente di sviluppo configurato con .NET. Visual Studio è un'ottima scelta se stai cercando consigli.
3. Conoscenza di base di C#: mentre spiegherò ogni passaggio, una conoscenza di base di C# ti aiuterà a seguirlo più facilmente.
4.  Directory dei documenti: prepara un percorso di directory in cui salverai i tuoi documenti. Ci riferiremo a questo come`YOUR DOCUMENT DIRECTORY`.

## Importa spazi dei nomi

Per iniziare, assicurati di importare gli spazi dei nomi necessari nel tuo progetto:

```csharp
using System;
using System.Drawing;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Tables;
```

Suddividiamo il processo in passaggi gestibili.

## Passaggio 1: crea un nuovo documento

 Per prima cosa creeremo un nuovo documento Word e inizializzeremo a`DocumentBuilder` oggetto per aiutarci a costruire il nostro contenuto.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: avvia una tabella e imposta il formato della riga

Inizieremo a costruire una tabella e specificheremo l'altezza e la regola dell'altezza per le righe.

```csharp
builder.StartTable();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
```

## Passaggio 3: inserisci celle e compila con contenuto

Successivamente, eseguiamo il loop per inserire le celle nella tabella. Per ogni 7 celle, termineremo la riga per crearne una nuova.

```csharp
for (int i = 0; i < 31; i++)
{
    if (i != 0 && i % 7 == 0) builder.EndRow();
    builder.InsertCell();
    builder.Write("Cell contents");
}
builder.EndTable();
```

## Passaggio 4: aggiungi una forma di filigrana

 Ora aggiungiamo una filigrana al nostro documento. Creeremo un`Shape` oggetto e impostarne le proprietà.

```csharp
Shape watermark = new Shape(doc, ShapeType.TextPlainText)
{
    RelativeHorizontalPosition = RelativeHorizontalPosition.Page,
    RelativeVerticalPosition = RelativeVerticalPosition.Page,
    IsLayoutInCell = true, // Visualizza la forma all'esterno della cella della tabella se verrà inserita in una cella.
    Width = 300,
    Height = 70,
    HorizontalAlignment = HorizontalAlignment.Center,
    VerticalAlignment = VerticalAlignment.Center,
    Rotation = -40
};
```

## Passaggio 5: personalizza l'aspetto della filigrana

Personalizzeremo ulteriormente l'aspetto della filigrana impostandone le proprietà di colore e testo.

```csharp
watermark.FillColor = Color.Gray;
watermark.StrokeColor = Color.Gray;
watermark.TextPath.Text = "watermarkText";
watermark.TextPath.FontFamily = "Arial";
watermark.Name = $"WaterMark_{Guid.NewGuid()}";
watermark.WrapType = WrapType.None;
```

## Passaggio 6: inserire la filigrana nel documento

Troveremo l'ultima esecuzione nel documento e inseriremo la filigrana in quella posizione.

```csharp
Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
builder.MoveTo(run);
builder.InsertNode(watermark);
```

## Passaggio 7: ottimizza il documento per Word 2010

Per garantire la compatibilità, ottimizzeremo il documento per Word 2010.

```csharp
doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
```

## Passaggio 8: salva il documento

Infine, salveremo il nostro documento nella directory specificata.

```csharp
doc.Save(dataDir + "WorkingWithShapes.LayoutInCell.docx");
```

## Conclusione

Ed ecco qua! Hai creato con successo un documento Word con un layout di tabella personalizzato e aggiunto una filigrana utilizzando Aspose.Words per .NET. Questo tutorial mirava a fornire una guida chiara e passo passo per aiutarti a comprendere ogni parte del processo. Con queste competenze, ora puoi creare documenti Word più sofisticati e personalizzati a livello di codice.

## Domande frequenti

### Posso utilizzare un carattere diverso per il testo della filigrana?
 Sì, puoi cambiare il carattere impostando il file`watermark.TextPath.FontFamily` proprietà al carattere desiderato.

### Come posso regolare la posizione della filigrana?
 È possibile modificare il`RelativeHorizontalPosition`, `RelativeVerticalPosition`, `HorizontalAlignment` , E`VerticalAlignment` proprietà per regolare la posizione della filigrana.

### È possibile utilizzare un'immagine invece del testo per la filigrana?
 Assolutamente! Puoi creare un file`Shape` con il tipo`ShapeType.Image` e impostarne l'immagine utilizzando il file`ImageData.SetImage` metodo.

### Posso creare tabelle con altezze di riga variabili?
Sì, puoi impostare altezze diverse per ogni riga modificando il file`RowFormat.Height` proprietà prima di inserire le celle in quella riga.

### Come rimuovo una filigrana dal documento?
 Puoi rimuovere la filigrana individuandola nella raccolta di forme del documento e chiamando il file`Remove` metodo.