---
title: Sostituisci i collegamenti ipertestuali
linktitle: Sostituisci i collegamenti ipertestuali
second_title: API di elaborazione dei documenti Aspose.Words
description: Sostituisci i collegamenti ipertestuali nei documenti Word utilizzando Aspose.Words per .NET. Istruzioni dettagliate per la sostituzione dei collegamenti ipertestuali.
type: docs
weight: 10
url: /it/net/working-with-fields/replace-hyperlinks/
---

Ecco una guida passo passo per spiegare il seguente codice sorgente C# per sostituire i collegamenti ipertestuali utilizzando la funzionalità Aspose.Words per .NET. Assicurati di aver incluso la libreria Aspose.Words nel tuo progetto prima di utilizzare questo codice.

## Passaggio 1: imposta il percorso della directory del documento

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

 Assicurati di specificare il percorso corretto della directory dei documenti contenente il file`Hyperlinks.docx` file.

## Passaggio 2: caricare il documento contenente i collegamenti ipertestuali

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

 Qui stiamo creando un'istanza di`Document` classe dal file specificato.

## Passaggio 3: sfoglia i campi per trovare i collegamenti ipertestuali

```csharp
foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // Alcuni collegamenti ipertestuali potrebbero essere locali (collegamenti ai segnalibri all'interno del documento), li ignoriamo.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com";
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}
```

 Questo ciclo esamina tutti i campi del documento alla ricerca dei campi di tipo`FieldType.FieldHyperlink` . Una volta trovato un campo di questo tipo, controlliamo se si tratta di un collegamento locale controllando il file`SubAddress` proprietà. In caso contrario, sostituiamo l'indirizzo del collegamento con`"http://www.aspose.com"` e il risultato con`"Aspose - The .NET & Java Component Editor"`.

## Passaggio 4: salva il documento modificato

```csharp
doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

Infine, salviamo il documento modificato con i collegamenti ipertestuali sostituiti in un file specificato.

### Codice sorgente di esempio per sostituire i collegamenti ipertestuali con Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Hyperlinks.docx");

foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // Alcuni collegamenti ipertestuali potrebbero essere locali (collegamenti ai segnalibri all'interno del documento), li ignoriamo.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com";
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}

doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

Questo è un codice sorgente di esempio per sostituire i collegamenti ipertestuali in un documento utilizzando Aspose.Words per .NET.

### Domande frequenti

#### D: Come posso sostituire i collegamenti ipertestuali in un documento di Word utilizzando Aspose.Words per .NET?

 R: Per sostituire i collegamenti ipertestuali in un documento Word utilizzando Aspose.Words per .NET, è possibile utilizzare il file`Document.Range.Replace`metodo che specifica il testo da cercare e il testo sostitutivo. Assicurati di utilizzare le opzioni appropriate per impostare i parametri di ricerca e sostituzione.

#### D: È possibile sostituire solo alcuni collegamenti ipertestuali in un documento di Word con Aspose.Words per .NET?

R: Sì, è possibile sostituire solo alcuni collegamenti ipertestuali in un documento di Word con Aspose.Words per .NET. Puoi filtrare i collegamenti ipertestuali da sostituire utilizzando criteri specifici, come URL del collegamento, testo del collegamento o qualsiasi altra proprietà pertinente. Quindi puoi applicare la sostituzione solo ai collegamenti ipertestuali corrispondenti.

#### D: Come posso ignorare i collegamenti ipertestuali nelle intestazioni, nei piè di pagina o nelle note durante la sostituzione con Aspose.Words per .NET?

R: Per ignorare i collegamenti ipertestuali nelle intestazioni, piè di pagina o note a piè di pagina durante la sostituzione con Aspose.Words per .NET, è possibile utilizzare le opzioni di ricerca avanzata e specificare i limiti di ricerca appropriati. Ad esempio, puoi limitare la ricerca alle sezioni principali del documento ed escludere intestazioni, piè di pagina o note a piè di pagina.

#### D: È possibile sostituire i collegamenti ipertestuali con collegamenti interni ad altre parti del documento?

 R: Sì, è possibile sostituire i collegamenti ipertestuali con collegamenti interni ad altre parti del documento con Aspose.Words per .NET. Puoi utilizzare ancore o ID di testo per creare collegamenti interni e quindi sostituirli utilizzando il file`Document.Range.Replace` metodo con le opzioni appropriate.

#### D: La sostituzione dei collegamenti ipertestuali con Aspose.Words per .NET preserva le proprietà dei collegamenti, come colori o stili?

R: Sì, quando si sostituiscono i collegamenti ipertestuali con Aspose.Words per .NET, le proprietà dei collegamenti come colori o stili vengono mantenute. È possibile specificare le stesse proprietà di formattazione nel testo sostitutivo per ottenere un risultato coerente.