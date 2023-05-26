---
title: Imposta la posizione orizzontale o verticale relativa
linktitle: Imposta la posizione orizzontale o verticale relativa
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come impostare la posizione orizzontale o verticale relativa di una tabella in un documento di Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-tables/set-relative-horizontal-or-vertical-position/
---

In questo tutorial impareremo come impostare la posizione orizzontale o verticale relativa di una tabella in un documento di Word utilizzando Aspose.Words per .NET. Seguiremo una guida passo passo per comprendere il codice e implementare questa funzione. Alla fine di questo tutorial, sarai in grado di impostare la posizione relativa orizzontale o verticale della tua tabella nei tuoi documenti Word.

## Passaggio 1: impostazione del progetto
1. Avvia Visual Studio e crea un nuovo progetto C#.
2. Aggiungere un riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: caricamento del documento
Per iniziare a lavorare con il documento, attenersi alla seguente procedura:

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Carica il documento
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Assicurati di sostituire "YOUR DOCUMENTS DIRECTORY" con il percorso effettivo della directory dei documenti e fornisci il nome file corretto.

## Passaggio 3: impostazione della posizione relativa del tavolo
Successivamente, imposteremo la posizione orizzontale o verticale relativa della tabella. Usa il seguente codice:

```csharp
// Recupera il tavolo
Table table = doc.FirstSection.Body.Tables[0];

//Definizione della posizione orizzontale relativa del tavolo
table.HorizontalAnchor = RelativeHorizontalPosition.Column;

// Definire la posizione verticale relativa della tabella
table.VerticalAnchor = RelativeVerticalPosition.Page;
```

 Qui usiamo il documento per recuperare la prima tabella dal corpo della prima sezione. Successivamente, impostiamo la posizione orizzontale relativa del tavolo con il`HorizontalAnchor` proprietà utilizzando il`RelativeHorizontalPosition.Column` valore. Allo stesso modo, impostiamo la posizione verticale relativa del tavolo con il`VerticalAnchor` proprietà utilizzando il`RelativeVerticalPosition.Page` valore.

## Passaggio 4: salvare il documento modificato
Infine, occorre salvare il documento modificato con la relativa posizione della tabella definita. Usa il seguente codice:

```csharp
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

Assicurati di specificare il percorso e il nome file corretti per il documento di output.

### Esempio di codice sorgente per Imposta posizione orizzontale o verticale relativa utilizzando Aspose.Words per .NET 

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table wrapped by text.docx");
Table table = doc.FirstSection.Body.Tables[0];
table.HorizontalAnchor = RelativeHorizontalPosition.Column;
table.VerticalAnchor = RelativeVerticalPosition.Page;
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

## Conclusione
In questo tutorial, abbiamo imparato come impostare la posizione orizzontale o verticale relativa di una tabella in un documento di Word utilizzando Aspose.Words per .NET. Seguendo questa guida dettagliata e implementando il codice C# fornito, puoi applicare questa posizione relativa alle tue tabelle nei tuoi documenti Word.