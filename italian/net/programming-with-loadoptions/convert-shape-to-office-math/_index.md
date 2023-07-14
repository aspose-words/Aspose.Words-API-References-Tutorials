---
title: Converti forma in Office Math
linktitle: Converti forma in Office Math
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come convertire le forme in formule matematiche di Office durante il caricamento di documenti con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-loadoptions/convert-shape-to-office-math/
---

Durante l'elaborazione di testi con documenti contenenti forme matematiche in un'applicazione C#, potrebbe essere necessario convertirli in formule matematiche di Office per una migliore compatibilità e presentazione. Con la libreria Aspose.Words per .NET, puoi convertire facilmente le forme in formule matematiche di Office durante il caricamento di un documento. In questa guida dettagliata, ti illustreremo come usare Aspose.Words per il codice sorgente .NET C# per caricare un documento con la conversione di forme in formule matematiche di Office usando LoadOptions.

## Comprensione della libreria Aspose.Words

Prima di immergersi nel codice, è importante comprendere la libreria Aspose.Words per .NET. Aspose.Words è una potente libreria per creare, modificare, convertire e proteggere documenti Word in diverse piattaforme, incluso .NET. Offre molte funzionalità per la manipolazione dei documenti, come l'inserimento di testo, la modifica della formattazione, l'aggiunta di sezioni e molto altro.

## Configurazione delle opzioni di caricamento

Il primo passo è configurare le opzioni di caricamento per il nostro documento. Utilizzare la classe LoadOptions per specificare i parametri di caricamento. Nel nostro caso, vogliamo convertire le forme in formule matematiche di Office, quindi dobbiamo impostare la proprietà ConvertShapeToOfficeMath su true. Ecco come farlo:

```csharp
LoadOptions loadOptions = new LoadOptions { ConvertShapeToOfficeMath = true };
```

Creiamo un nuovo oggetto LoadOptions e impostiamo la proprietà ConvertShapeToOfficeMath su true per abilitare la conversione delle forme in formule matematiche di Office durante il caricamento del documento.

## Caricamento del documento con conversione delle forme in formule matematiche di Office

Ora che abbiamo configurato le opzioni di caricamento, possiamo caricare il documento utilizzando la classe Document e specificare le opzioni di caricamento. Ecco un esempio:

```csharp
Document doc = new Document(dataDir + "Office math.docx", loadOptions);
```

In questo esempio, carichiamo il documento "Office math.docx" situato nella directory dei documenti utilizzando le opzioni di caricamento specificate.

## Registrazione del documento

Dopo aver caricato il documento con la conversione delle forme in formule matematiche di Office, è possibile salvarlo nel formato desiderato utilizzando il metodo Save della classe Document. Ad esempio, per salvare il documento in formato .docx:

```csharp
doc.Save(dataDir + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.Docx);
```

Assicurati di sostituire "dataDir" con il percorso della directory dei tuoi documenti.

### Codice sorgente di esempio per LoadOptions con la funzionalità "Converti forma in Office Math" utilizzando Aspose.Words per .NET

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Configurazione delle opzioni di caricamento con la funzionalità "Converti Forma".

  To Office Math"
LoadOptions loadOptions = new LoadOptions { ConvertShapeToOfficeMath = true };

// Carica il documento con le opzioni specificate
Document doc = new Document(dataDir + "Office math.docx", loadOptions);

//Salva il documento nel formato desiderato
doc.Save(dataDir + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.Docx);
```

## Conclusione

In questa guida, abbiamo spiegato come caricare un documento con la conversione di forme in formule matematiche di Office utilizzando la libreria Aspose.Words per .NET. Seguendo i passaggi forniti e usando il codice sorgente C# fornito, puoi facilmente applicare questa funzionalità nella tua applicazione C#. La conversione di forme in formule matematiche di Office offre una migliore compatibilità e presentazione dei documenti che contengono elementi matematici.
