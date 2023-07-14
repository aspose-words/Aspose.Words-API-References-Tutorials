---
title: Non salvare il punto elenco dell'immagine
linktitle: Non salvare il punto elenco dell'immagine
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come disabilitare il salvataggio dei punti elenco delle immagini nei documenti di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-docsaveoptions/do-not-save-picture-bullet/
---

punti elenco con immagini sono una funzionalità comunemente utilizzata nei documenti di Word per aggiungere punti elenco personalizzati. Tuttavia, in alcuni casi potrebbe essere necessario disabilitare la registrazione dei punti elenco dell'immagine quando si manipolano i documenti utilizzando Aspose.Words Library per .NET. In questa guida dettagliata, spiegheremo come utilizzare il codice sorgente Aspose.Words C# per .NET per disabilitare il salvataggio dei punti elenco delle immagini utilizzando le opzioni di salvataggio di DocSaveOptions.

## Comprensione della libreria Aspose.Words

Prima di immergersi nel codice, è importante comprendere la libreria Aspose.Words per .NET. Aspose.Words è una potente libreria per creare, modificare, convertire e proteggere documenti Word in diverse piattaforme, incluso .NET. Offre molte funzionalità per la manipolazione dei documenti, come l'inserimento di testo, la modifica della formattazione, l'aggiunta di sezioni e molto altro.

## Passaggio 1: impostazione della directory dei documenti

Il primo passaggio consiste nel definire la directory in cui si trovano i documenti. È necessario specificare il percorso completo della directory. Per esempio :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Assicurati di sostituire "LA TUA DIRECTORY DEI DOCUMENTI" con il percorso effettivo della tua directory dei documenti.

## Passaggio 2: caricamento del documento con punti elenco immagine

Successivamente, è necessario caricare il documento con punti elenco immagine. Utilizzare la classe Document per caricare il documento da un file. Per esempio :

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

In questo esempio stiamo caricando il documento dal file "Image bullet points.docx"

  situato nella directory dei documenti.

## Passaggio 3: configurare le opzioni di registrazione

Ora configuriamo le opzioni di salvataggio per il nostro documento. Utilizzare la classe DocSaveOptions per specificare le impostazioni di salvataggio. Per esempio :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };
```

In questo esempio creiamo un nuovo oggetto DocSaveOptions e impostiamo la proprietà SavePictureBullet su false per disabilitare il salvataggio dei punti elenco delle immagini.

## Passaggio 4: abilita la funzione "Non salvare il punto elenco dell'immagine".

Per abilitare la funzione "Non salvare l'immagine puntata", abbiamo già configurato le opzioni di salvataggio con SavePictureBullet impostato su false. Ciò garantisce che i punti elenco dell'immagine non vengano salvati nel documento finale.

## Passaggio 5: salvare il documento

Infine, puoi salvare il documento utilizzando il metodo Save della classe Document. Specificare il percorso completo del file e il nome del file desiderato. Per esempio :

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

Assicurati di sostituire "dataDir" con il percorso della directory dei tuoi documenti.

## Esempio di codice sorgente per le opzioni di salvataggio di DocSaveOptions con la funzionalità "Non salvare il punto elenco immagine" utilizzando Aspose.Words per .NET

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carica il documento con punti elenco immagine
Document doc = new Document(dataDir + "Image bullet points.docx");

// Configura le opzioni di salvataggio con la funzione "Non salvare l'immagine puntata".
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };

// Salva il documento con le opzioni specificate
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

## Conclusione

In questa guida, abbiamo spiegato come disabilitare il salvataggio dei punti elenco immagine in un documento utilizzando la libreria Aspose.Words per .NET. Seguendo i passaggi forniti e usando il codice sorgente C# fornito, puoi facilmente applicare questa funzionalità nella tua applicazione C#. La disattivazione del salvataggio dei punti elenco immagine può essere utile in alcune situazioni per preservare la struttura e la formattazione del documento senza salvare i punti elenco immagine.