---
title: Rimuovi informazioni personali
linktitle: Rimuovi informazioni personali
second_title: Riferimento all'API Aspose.Words per .NET
description: Guida dettagliata alla rimozione di informazioni personali da un documento con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-document-properties/remove-personal-information/
---

In questo tutorial, ti guideremo attraverso il codice sorgente C# per rimuovere le informazioni personali da un documento con Aspose.Words per .NET. Questa funzione consente di rimuovere informazioni personali riservate da un documento, come i dati di identificazione dell'autore.

## Passaggio 1: impostazione del progetto

Per iniziare, crea un nuovo progetto C# nel tuo IDE preferito. Assicurarsi che nel progetto si faccia riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: caricamento del documento

In questo passaggio, caricheremo il documento Word da cui vogliamo rimuovere le informazioni personali. Utilizzare il seguente codice per caricare il documento:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };
```

 Sostituire`"YOUR DOCUMENTS DIRECTORY"` con il percorso effettivo della directory in cui si trova il documento.

## Passaggio 3: eliminare le informazioni personali

 Ora abiliteremo la rimozione delle informazioni personali impostando il file`RemovePersonalInformation` proprietà a`true`. Usa il seguente codice:

```csharp
doc.RemovePersonalInformation = true;
```

Questo codice attiva la cancellazione delle informazioni personali nel documento.

## Passaggio 4: salvare il documento

Infine, salveremo il documento con le informazioni personali rimosse. Usa il seguente codice:

```csharp
doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
```

Questo codice salva il documento con le informazioni personali rimosse in un nuovo file.

### Codice sorgente di esempio per rimuovere le informazioni personali utilizzando Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };

	doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
	
```

 Assicurarsi di specificare il percorso del documento corretto nel file`dataDir` variabile.

Ora hai imparato come rimuovere le informazioni personali da un documento utilizzando Aspose.Words per .NET. Seguendo la guida dettagliata fornita in questo tutorial, puoi rimuovere facilmente le informazioni riservate dai tuoi documenti.