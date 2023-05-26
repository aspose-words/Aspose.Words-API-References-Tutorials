---
title: Crittografa documento con password
linktitle: Crittografa documento con password
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come crittografare i documenti con una password utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-docsaveoptions/encrypt-document-with-password/
---
La sicurezza dei documenti è essenziale quando si lavora con i file in un'applicazione C#. Con la libreria Aspose.Words per .NET, puoi proteggere facilmente i tuoi documenti crittografandoli con una password. In questa guida dettagliata, ti illustreremo come utilizzare Aspose.Words per il codice sorgente .NET C# per crittografare un documento utilizzando le opzioni di salvataggio di DocSaveOptions.

## Comprensione della libreria Aspose.Words

Prima di immergersi nel codice, è importante comprendere la libreria Aspose.Words per .NET. Aspose.Words è una potente libreria per creare, modificare, convertire e proteggere documenti Word in diverse piattaforme, incluso .NET. Offre molte funzionalità per la manipolazione dei documenti, come l'inserimento di testo, la modifica della formattazione, l'aggiunta di sezioni e molto altro.

## Passaggio 1: definizione della directory dei documenti

Il primo passaggio consiste nell'impostare la directory in cui si desidera salvare il documento crittografato. È necessario specificare il percorso completo della directory. Per esempio :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Assicurati di sostituire "LA TUA DIRECTORY DEI DOCUMENTI" con il percorso effettivo della tua directory dei documenti.

## Passaggio 2: creazione e modifica di un documento

Quindi puoi creare un documento e aggiungervi del contenuto. Usa la classe DocumentBuilder fornita da Aspose.Words per costruire il contenuto del tuo documento. Per esempio :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");
```

In questo esempio, creiamo un nuovo documento vuoto e quindi utilizziamo DocumentBuilder per scrivere il testo "Hello World!".

## Passaggio 3: configurare le opzioni di registrazione

Ora configuriamo le opzioni di salvataggio per il nostro documento. Utilizzare la classe DocSaveOptions per specificare le impostazioni di salvataggio. Per esempio :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };
```

In questo esempio, creiamo un nuovo oggetto DocSaveOptions e impostiamo la proprietà Password su "password" per crittografare il documento con questa password.

## Passaggio 4: abilitazione della funzione "Crittografa documento con password".

Abbiamo già configurato le opzioni per

registrazione con la password specificata, che attiva automaticamente la funzione "Crittografa documento con password". Ciò garantisce che il documento sia crittografato con la password specificata al momento del salvataggio.

## Passaggio 5: salvare il documento

Infine, puoi salvare il documento utilizzando il metodo Save della classe Document. Specificare il percorso completo del file e il nome del file desiderato. Per esempio :

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

Assicurati di sostituire "dataDir" con il percorso della directory dei tuoi documenti.

### Codice sorgente di esempio per DocSaveOptions salva le opzioni con la funzionalità "Crittografa documento con password" utilizzando Aspose.Words per .NET

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creare e modificare un documento
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");

// Configura le opzioni di salvataggio con la funzione "Crittografa documento con password".
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };

// Salva il documento con le opzioni specificate
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

## Conclusione

In questa guida, abbiamo spiegato come utilizzare la libreria Aspose.Words per .NET per crittografare un documento con una password utilizzando le opzioni di salvataggio di DocSaveOptions. Seguendo i passaggi forniti e usando il codice sorgente C# fornito, puoi facilmente applicare questa funzionalità nella tua applicazione C#. La crittografia del documento con una password ne garantisce la riservatezza e la sicurezza durante la sua gestione.