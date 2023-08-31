---
title: Usa carattere dalla macchina di destinazione
linktitle: Usa carattere dalla macchina di destinazione
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come convertire un documento Word in HTML fisso utilizzando i caratteri della macchina di destinazione con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-htmlfixedsaveoptions/use-font-from-target-machine/
---

Quando si converte un documento Word in HTML fisso in un'applicazione C#, è possibile utilizzare i caratteri del computer di destinazione per garantire che l'HTML sottoposto a rendering mantenga l'aspetto e lo stile originali del documento. Con la libreria Aspose.Words per .NET, puoi facilmente specificare questa funzionalità utilizzando le opzioni di salvataggio HtmlFixedSaveOptions. In questa guida dettagliata, ti illustreremo come utilizzare il codice sorgente C# di Aspose.Words per .NET per convertire un documento Word in HTML fisso utilizzando i caratteri della macchina di destinazione utilizzando HtmlFixedSaveOptions.

## Comprensione della libreria Aspose.Words

Prima di immergersi nel codice, è importante comprendere la libreria Aspose.Words per .NET. Aspose.Words è una potente libreria per creare, modificare, convertire e proteggere documenti Word in diverse piattaforme, incluso .NET. Offre molte funzionalità per la manipolazione dei documenti, come l'inserimento di testo, la modifica della formattazione, l'aggiunta di sezioni e molto altro.

## Caricamento del documento Word

Il primo passo è caricare il documento Word che vuoi convertire in HTML fisso. Utilizzare la classe Document per caricare il documento dal file di origine. Ecco un esempio:

```csharp
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");
```

In questo esempio, carichiamo il documento "Punti elenco con font.docx alternativo" che si trova nella directory dei documenti.

## Configurazione delle opzioni di backup

Il passaggio successivo consiste nel configurare le opzioni di salvataggio per la conversione in HTML fisso. Utilizzare la classe HtmlFixedSaveOptions e impostare la proprietà UseTargetMachineFonts su true per indicare ad Aspose.Words di utilizzare i caratteri dal computer di destinazione. Ecco come farlo:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };
```

Creiamo un nuovo oggetto HtmlFixedSaveOptions e impostiamo la proprietà UseTargetMachineFonts su true per utilizzare i caratteri della macchina di destinazione durante la conversione.

## Corretta la conversione del documento HTML

Ora che abbiamo configurato le opzioni di salvataggio, possiamo procedere alla conversione del documento in HTML fisso. Utilizzare il metodo Save della classe Document per salvare il documento convertito in formato HTML fisso specificando le opzioni di salvataggio. Ecco un esempio:

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

In questo esempio, salviamo il documento convertito come "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html" utilizzando le opzioni di salvataggio specificate.

### Esempio di codice sorgente per HtmlFixedSaveOptions con la funzione "Usa caratteri dal computer di destinazione" utilizzando Aspose.Words per .NET

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carica il documento di Word
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");

//Configura le opzioni di backup con la funzione "Usa i caratteri dalla macchina di destinazione".
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };

// Converti documento in HTML fisso
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

## Conclusione

In questa guida, abbiamo spiegato come convertire un documento Word in HTML fisso utilizzando i caratteri della macchina di destinazione con la libreria Aspose.Words per .NET. Seguendo i passaggi forniti e usando il codice sorgente C# fornito, puoi facilmente applicare questa funzionalità nella tua applicazione C#. La conversione in HTML fisso con i font della macchina di destinazione garantisce una resa fedele e coerente del documento in formato HTML.
