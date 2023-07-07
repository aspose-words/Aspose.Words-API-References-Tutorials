---
title: Sostituisci collegamenti ipertestuali
linktitle: Sostituisci collegamenti ipertestuali
second_title: Riferimento all'API Aspose.Words per .NET
description: Sostituisci i collegamenti ipertestuali nei documenti di Word utilizzando Aspose.Words per .NET. Istruzioni dettagliate per la sostituzione dei collegamenti ipertestuali.
type: docs
weight: 10
url: /it/net/working-with-fields/replace-hyperlinks/
---

Ecco una guida dettagliata per spiegare il seguente codice sorgente C# per sostituire i collegamenti ipertestuali utilizzando Aspose.Words per la funzionalità .NET. Assicurati di aver incluso la libreria Aspose.Words nel tuo progetto prima di utilizzare questo codice.

## Passaggio 1: impostare il percorso della directory del documento

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

 Assicurati di specificare il percorso corretto della directory dei documenti che contiene il file`Hyperlinks.docx` file.

## Passaggio 2: caricare il documento contenente i collegamenti ipertestuali

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

 Qui stiamo creando un'istanza di`Document` class dal file specificato.

## Passaggio 3: sfoglia i campi per trovare i collegamenti ipertestuali

```csharp
foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // Alcuni collegamenti ipertestuali possono essere locali (collegamenti a segnalibri all'interno del documento), li ignoriamo.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com";
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}
```

 Questo ciclo passa attraverso tutti i campi nel documento alla ricerca di campi di tipo`FieldType.FieldHyperlink` . Una volta trovato un campo di questo tipo, verifichiamo se si tratta di un link locale controllando il`SubAddress` proprietà. In caso contrario, sostituiamo l'indirizzo del link con`"http://www.aspose.com"` e il risultato con`"Aspose - The .NET & Java Component Editor"`.

## Passaggio 4: salvare il documento modificato

```csharp
doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

Infine, salviamo il documento modificato con i collegamenti ipertestuali sostituiti in un file specificato.

### Esempio di codice sorgente per sostituire i collegamenti ipertestuali con Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Hyperlinks.docx");

foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // Alcuni collegamenti ipertestuali possono essere locali (collegamenti a segnalibri all'interno del documento), li ignoriamo.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com";
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}

doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

Questo è un codice sorgente di esempio per sostituire i collegamenti ipertestuali in un documento utilizzando Aspose.Words per .NET.

### FAQ

#### D: Come posso sostituire i collegamenti ipertestuali in un documento di Word utilizzando Aspose.Words per .NET?

 A: Per sostituire i collegamenti ipertestuali in un documento di Word utilizzando Aspose.Words per .NET, è possibile utilizzare il`Document.Range.Replace`metodo che specifica il testo da cercare e il testo sostitutivo. Assicurati di utilizzare le opzioni appropriate per impostare i parametri di ricerca e sostituzione.

#### D: È possibile sostituire solo alcuni collegamenti ipertestuali in un documento di Word con Aspose.Words per .NET?

R: Sì, è possibile sostituire solo alcuni collegamenti ipertestuali in un documento di Word con Aspose.Words per .NET. È possibile filtrare i collegamenti ipertestuali da sostituire utilizzando criteri specifici, come l'URL del collegamento, il testo del collegamento o qualsiasi altra proprietà pertinente. Quindi puoi applicare la sostituzione solo ai collegamenti ipertestuali corrispondenti.

#### D: Come posso ignorare i collegamenti ipertestuali in intestazioni, piè di pagina o note a piè di pagina durante la sostituzione con Aspose.Words per .NET?

R: Per ignorare i collegamenti ipertestuali in intestazioni, piè di pagina o note a piè di pagina durante la sostituzione con Aspose.Words per .NET, è possibile utilizzare le opzioni di ricerca avanzate e specificare i limiti di ricerca appropriati. Ad esempio, puoi limitare la ricerca alle sezioni principali del documento ed escludere intestazioni, piè di pagina o note a piè di pagina.

#### D: È possibile sostituire i collegamenti ipertestuali con collegamenti interni ad altre parti del documento?

 R: Sì, è possibile sostituire i collegamenti ipertestuali con collegamenti interni ad altre parti del documento con Aspose.Words per .NET. Puoi utilizzare ancore o ID di testo per creare collegamenti interni e quindi sostituirli utilizzando il file`Document.Range.Replace` metodo con le opzioni appropriate.

#### D: La sostituzione dei collegamenti ipertestuali con Aspose.Words per .NET preserva le proprietà dei collegamenti, come colori o stili?

R: Sì, quando si sostituiscono i collegamenti ipertestuali con Aspose.Words per .NET, le proprietà dei collegamenti come i colori o gli stili vengono mantenute. È possibile specificare le stesse proprietà di formattazione nel testo sostitutivo per ottenere un risultato coerente.