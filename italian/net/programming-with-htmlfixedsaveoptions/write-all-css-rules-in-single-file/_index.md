---
title: Scrivi tutte le regole CSS in un unico file
linktitle: Scrivi tutte le regole CSS in un unico file
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come convertire un documento Word in HTML fisso scrivendo tutte le regole CSS in un singolo file con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-htmlfixedsaveoptions/write-all-css-rules-in-single-file/
---

Quando si converte un documento Word in HTML fisso in un'applicazione C#, è consigliabile consolidare tutte le regole CSS in un unico file per una migliore organizzazione e portabilità. Con la libreria Aspose.Words per .NET, puoi facilmente specificare questa funzionalità utilizzando le opzioni di salvataggio HtmlFixedSaveOptions. In questa guida dettagliata, ti illustreremo come utilizzare Aspose.Words per il codice sorgente .NET C# per convertire un documento Word in HTML fisso scrivendo tutte le regole CSS in un singolo file utilizzando le opzioni di salvataggio HtmlFixedSaveOptions.

## Comprensione della libreria Aspose.Words

Prima di immergersi nel codice, è importante comprendere la libreria Aspose.Words per .NET. Aspose.Words è una potente libreria per creare, modificare, convertire e proteggere documenti Word in diverse piattaforme, incluso .NET. Offre molte funzionalità per la manipolazione dei documenti, come l'inserimento di testo, la modifica della formattazione, l'aggiunta di sezioni e molto altro.

## Caricamento del documento Word

Il primo passo è caricare il documento Word che vuoi convertire in HTML fisso. Utilizzare la classe Document per caricare il documento dal file di origine. Ecco un esempio:

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

In questo esempio, carichiamo il documento "Document.docx" che si trova nella directory dei documenti.

## Configurazione delle opzioni di backup

Il passaggio successivo consiste nel configurare le opzioni di salvataggio per la conversione in HTML fisso. Utilizza la classe HtmlFixedSaveOptions e imposta la proprietà SaveFontFaceCssSeparately su false per scrivere tutte le regole CSS in un unico file. Ecco come farlo:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };
```

Creiamo un nuovo oggetto HtmlFixedSaveOptions e impostiamo la proprietà SaveFontFaceCssSeparately su false per scrivere tutte le regole CSS in un unico file.

## Corretta la conversione del documento HTML

Ora che abbiamo configurato le opzioni di salvataggio, possiamo procedere alla conversione del documento in HTML fisso. Utilizzare il metodo Save della classe Document per salvare il documento convertito in formato HTML fisso specificando le opzioni di salvataggio. Ecco un esempio:

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

In questo esempio, salviamo il documento convertito come "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html" utilizzando le opzioni di salvataggio specificate.

### Codice sorgente di esempio per HtmlFixedSaveOptions con la funzione "Scrivi tutte le regole CSS in un file" utilizzando Aspose.Words per .NET

```csharp
// Percorso di accesso alla directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carica il documento di Word
Document doc = new Document(dataDir + "Document.docx");

// Configura le opzioni di backup con la funzione "Scrivi tutte le regole CSS in un file".
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };

// Converti documento in HTML fisso
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

## Conclusione

In questa guida, abbiamo spiegato come convertire un documento Word in HTML fisso scrivendo tutte le regole CSS in un singolo file utilizzando HtmlFixedSaveOptions con la libreria Aspose.Words per .NET. Seguendo i passaggi forniti e usando il codice sorgente C# fornito, puoi facilmente applicare questa funzionalità nella tua applicazione C#. La scrittura di tutte le regole CSS in un unico file facilita l'organizzazione e la gestione del codice HTML generato durante la conversione del documento.