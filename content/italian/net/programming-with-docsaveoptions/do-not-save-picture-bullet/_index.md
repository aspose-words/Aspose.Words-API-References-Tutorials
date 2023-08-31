---
title: Non salvare l'elenco puntato dell'immagine
linktitle: Non salvare l'elenco puntato dell'immagine
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come disabilitare il salvataggio dei punti elenco immagini nei documenti Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-docsaveoptions/do-not-save-picture-bullet/
---

punti elenco immagini sono una funzionalità comunemente utilizzata nei documenti di Word per aggiungere punti elenco personalizzati. Tuttavia, in alcuni casi potrebbe essere necessario disabilitare la registrazione dei punti elenco delle immagini durante la manipolazione dei documenti utilizzando la libreria Aspose.Words per .NET. In questa guida passo passo, spiegheremo come utilizzare il codice sorgente C# Aspose.Words per .NET per disabilitare il salvataggio dei punti elenco delle immagini utilizzando le opzioni di salvataggio di DocSaveOptions.

## Comprensione della libreria Aspose.Words

Prima di immergersi nel codice, è importante comprendere la libreria Aspose.Words per .NET. Aspose.Words è una potente libreria per creare, modificare, convertire e proteggere documenti Word in diverse piattaforme tra cui .NET. Offre molte funzionalità per la manipolazione dei documenti, come l'inserimento di testo, la modifica della formattazione, l'aggiunta di sezioni e molto altro.

## Passaggio 1: impostazione della directory dei documenti

Il primo passo è definire la directory in cui si trovano i tuoi documenti. È necessario specificare il percorso completo della directory. Per esempio :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Assicurati di sostituire "LA TUA DIRECTORY DOCUMENTI" con il percorso effettivo della directory dei documenti.

## Passaggio 2: caricamento del documento con punti elenco immagini

Successivamente, è necessario caricare il documento con punti elenco immagini. Utilizzare la classe Document per caricare il documento da un file. Per esempio :

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

In questo esempio stiamo caricando il documento dal file "Image bullet points.docx"

  situato nella directory dei documenti.

## Passaggio 3: configura le opzioni di registrazione

Ora configuriamo le opzioni di salvataggio per il nostro documento. Utilizzare la classe DocSaveOptions per specificare le impostazioni di salvataggio. Per esempio :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };
```

In questo esempio creiamo un nuovo oggetto DocSaveOptions e impostiamo la proprietà SavePictureBullet su false per disabilitare il salvataggio dei punti elenco delle immagini.

## Passaggio 4: abilitare la funzione "Non salvare il punto elenco immagini".

Per abilitare la funzione "Non salvare Picture Bullet", abbiamo già configurato le opzioni di salvataggio con SavePictureBullet impostato su false. Ciò garantisce che i punti elenco delle immagini non vengano salvati nel documento finale.

## Passaggio 5: salva il documento

Infine, puoi salvare il documento utilizzando il metodo Save della classe Document. Specificare il percorso completo del file e il nome del file desiderato. Per esempio :

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

Assicurati di sostituire "dataDir" con il percorso della directory dei tuoi documenti.

## Esempio di codice sorgente per le opzioni di salvataggio di DocSaveOptions con la funzionalità "Non salvare Picture Bullet" utilizzando Aspose.Words per .NET

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carica il documento con punti elenco immagini
Document doc = new Document(dataDir + "Image bullet points.docx");

// Configura le opzioni di salvataggio con la funzione "Non salvare Picture Bullet".
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };

// Salvare il documento con le opzioni specificate
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

## Conclusione

In questa guida, abbiamo spiegato come disabilitare il salvataggio dei punti elenco di immagini in un documento utilizzando la libreria Aspose.Words per .NET. Seguendo i passaggi forniti e utilizzando il codice sorgente C# fornito, puoi applicare facilmente questa funzionalità nella tua applicazione C#. Disabilitare il salvataggio dei punti elenco delle immagini può essere utile in alcune situazioni per preservare la struttura e la formattazione del documento senza salvare i punti elenco delle immagini.