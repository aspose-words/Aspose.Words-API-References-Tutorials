---
title: Unità di misura
linktitle: Unità di misura
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come specificare l'unità di misura durante la conversione di un documento Word in ODT con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-odtsaveoptions/measure-unit/
---

Quando si converte un documento Word in formato OpenDocument Text (ODT) in un'applicazione C#, è possibile specificare l'unità di misura utilizzata per la formattazione misurabile e le proprietà del contenuto. Con la libreria Aspose.Words per .NET, puoi facilmente specificare questa funzionalità utilizzando le opzioni di salvataggio OdtSaveOptions. In questa guida dettagliata, ti illustreremo come utilizzare Aspose.Words per il codice sorgente .NET C# per convertire un documento Word in ODT specificando l'unità di misura utilizzando OdtSaveOptions.

## Comprensione della libreria Aspose.Words

Prima di immergersi nel codice, è importante comprendere la libreria Aspose.Words per .NET. Aspose.Words è una potente libreria per creare, modificare, convertire e proteggere documenti Word in diverse piattaforme, incluso .NET. Offre molte funzionalità per la manipolazione dei documenti, come l'inserimento di testo, la modifica della formattazione, l'aggiunta di sezioni e molto altro.

## Caricamento del documento Word

Il primo passo è caricare il documento Word che vuoi convertire in ODT. Utilizzare la classe Document per caricare il documento dal file di origine. Ecco un esempio:

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

In questo esempio, carichiamo il documento "Document.docx" che si trova nella directory dei documenti.

## Configurazione delle opzioni di backup

Il passaggio successivo consiste nel configurare le opzioni di backup per la conversione in ODT. Utilizzare la classe OdtSaveOptions e impostare la proprietà MeasureUnit sul valore desiderato. Ad esempio, se si desidera utilizzare i pollici come unità di misura, impostare MeasureUnit su OdtSaveMeasureUnit.Inches. Ecco come farlo:

```csharp
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };
```

Creiamo un nuovo oggetto OdtSaveOptions e impostiamo la proprietà MeasureUnit al valore desiderato, nel nostro caso OdtSaveMeasureUnit.Inches per utilizzare i pollici come unità di misura.

## Converti documento in ODT

Ora che abbiamo configurato le opzioni di salvataggio, possiamo procedere alla conversione del documento in ODT. Utilizzare il metodo Save della classe Document per salvare il documento convertito in formato ODT specificando le opzioni di salvataggio. Ecco un esempio:

```csharp
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

In questo esempio, salviamo il documento convertito come "WorkingWithOdtSaveOptions.MeasureUnit.odt" utilizzando le opzioni di salvataggio specificate.

### Codice sorgente di esempio per OdtSaveOptions con funzionalità "Unità di misura" utilizzando Aspose.Words per .NET



```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carica il documento di Word
Document doc = new Document(dataDir + "Document.docx");

// Configurazione delle opzioni di backup con la funzione "Unità di misura".
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };

// Converti il documento in ODT
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

## Conclusione

In questa guida abbiamo spiegato come convertire un documento Word in ODT specificando l'unità di misura utilizzando le opzioni di salvataggio OdtSaveOptions con la libreria Aspose.Words per .NET. Seguendo i passaggi forniti e usando il codice sorgente C# fornito, puoi facilmente applicare questa funzionalità nella tua applicazione C#. Specificare l'unità di misura durante la conversione in ODT consente di controllare la formattazione e le dimensioni del documento risultante in base alle proprie esigenze specifiche.