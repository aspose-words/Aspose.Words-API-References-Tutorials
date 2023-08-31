---
title: Imposta la posizione relativa orizzontale o verticale
linktitle: Imposta la posizione relativa orizzontale o verticale
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come impostare la posizione relativa orizzontale o verticale di una tabella in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-tables/set-relative-horizontal-or-vertical-position/
---

In questo tutorial impareremo come impostare la posizione relativa orizzontale o verticale di una tabella in un documento Word utilizzando Aspose.Words per .NET. Seguiremo una guida passo passo per comprendere il codice e implementare questa funzionalità. Alla fine di questo tutorial sarai in grado di impostare la posizione relativa orizzontale o verticale della tua tabella nei tuoi documenti Word.

## Passaggio 1: impostazione del progetto
1. Avvia Visual Studio e crea un nuovo progetto C#.
2. Aggiungi un riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: caricamento del documento
Per avviare l'elaborazione parole con il documento, attenersi alla seguente procedura:

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Caricare il documento
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Assicurati di sostituire "LA TUA DIRECTORY DOCUMENTI" con il percorso effettivo della directory dei documenti e fornisci il nome file corretto.

## Passaggio 3: impostazione della posizione relativa della tabella
Successivamente, imposteremo la relativa posizione orizzontale o verticale della tabella. Utilizza il seguente codice:

```csharp
// Recupera la tabella
Table table = doc.FirstSection.Body.Tables[0];

//Definizione della posizione orizzontale relativa del tavolo
table.HorizontalAnchor = RelativeHorizontalPosition.Column;

// Definire la posizione verticale relativa della tabella
table.VerticalAnchor = RelativeVerticalPosition.Page;
```

 Qui utilizziamo il documento per recuperare la prima tabella dal corpo della prima sezione. Successivamente, impostiamo la posizione orizzontale relativa della tabella con`HorizontalAnchor` proprietà utilizzando il`RelativeHorizontalPosition.Column` valore. Allo stesso modo, impostiamo la posizione verticale relativa della tabella con`VerticalAnchor` proprietà utilizzando il`RelativeVerticalPosition.Page` valore.

## Passaggio 4: salvataggio del documento modificato
Infine, dobbiamo salvare il documento modificato con la relativa posizione della tabella definita. Utilizza il seguente codice:

```csharp
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

Assicurati di specificare il percorso e il nome file corretti per il documento di output.

### Codice sorgente di esempio per impostare la posizione relativa orizzontale o verticale utilizzando Aspose.Words per .NET 

```csharp
//Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table wrapped by text.docx");
Table table = doc.FirstSection.Body.Tables[0];
table.HorizontalAnchor = RelativeHorizontalPosition.Column;
table.VerticalAnchor = RelativeVerticalPosition.Page;
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

## Conclusione
In questo tutorial, abbiamo imparato come impostare la posizione relativa orizzontale o verticale di una tabella in un documento Word utilizzando Aspose.Words per .NET. Seguendo questa guida passo passo e implementando il codice C# fornito, puoi applicare questa posizione relativa alle tabelle nei tuoi documenti Word.