---
title: Sposta nella cella della tabella
linktitle: Sposta nella cella della tabella
second_title: Aspose.Words API di elaborazione dei documenti
description: Guida dettagliata all'utilizzo di Sposta nella cella della tabella in Aspose.Words per .NET
type: docs
weight: 10
url: /it/net/add-content-using-documentbuilder/move-to-table-cell/
---

In questo esempio, ti illustreremo come utilizzare la funzione Sposta nella cella della tabella di Aspose.Words per .NET utilizzando passo dopo passo il codice sorgente C# fornito. Questa funzione consente di navigare e manipolare celle specifiche all'interno di una tabella in un documento di Word. Segui i passaggi seguenti per integrare questa funzionalità nella tua applicazione.

## Passaggio 1: caricare il documento contenente la tabella

Innanzitutto, dobbiamo caricare il documento contenente la tabella in cui vogliamo spostare la cella. Utilizzare il codice seguente per eseguire questo passaggio:

```csharp
Document doc = new Document(MyDir + "Tables.docx");
```

Questo codice carica il documento specificato (sostituisci "MyDir + "Tables.docx"" con il percorso effettivo del documento contenente la tabella).

## Passaggio 2: spostare DocumentBuilder in una cella di tabella specifica

Successivamente, sposteremo il DocumentBuilder in una specifica cella della tabella. Utilizzare il codice seguente per eseguire questo passaggio:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToCell(0, 2, 3, 0);
builder.Write("\nCell content added by DocumentBuilder");
```

 Questo codice crea un DocumentBuilder dal documento esistente e quindi sposta il cursore dal DocumentBuilder alla cella della tabella specificata. Infine, aggiunge contenuto a quella cella utilizzando il DocumentBuilder`Write()` metodo.

## Passaggio 3: controlla il risultato

Ora puoi verificare che il passaggio alla cella della tabella sia andato a buon fine. Utilizzare il codice seguente per eseguire questo passaggio:

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

Assert.AreEqual(table.Rows[2].Cells[3], builder.CurrentNode.ParentNode.ParentNode);
Assert.AreEqual("Cell contents added by DocumentBuilderCell 3 contents\a", table.Rows[2].Cells[3].GetText().Trim());
```

Questo codice verifica che la cella specificata sia effettivamente la cella corrente di DocumentBuilder. Verifica inoltre che il contenuto aggiunto da DocumentBuilder sia stato correttamente salvato nella cella della tabella.

È tutto ! Ora hai capito come utilizzare la funzionalità di spostamento nella cella della tabella di Aspose.Words per .NET utilizzando il codice sorgente fornito. Ora puoi integrare questa funzionalità nella tua applicazione e manipolare specifiche celle di tabella nei documenti di Word.


### Esempio di codice sorgente per passare a una cella di tabella utilizzando Aspose.Words per .NET


```csharp
Document doc = new Document(MyDir + "Tables.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

// Sposta il builder alla riga 3, cella 4 della prima tabella.
builder.MoveToCell(0, 2, 3, 0);
builder.Write("\nCell contents added by DocumentBuilder");
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

Assert.AreEqual(table.Rows[2].Cells[3], builder.CurrentNode.ParentNode.ParentNode);
Assert.AreEqual("Cell contents added by DocumentBuilderCell 3 contents\a", table.Rows[2].Cells[3].GetText().Trim());
```
