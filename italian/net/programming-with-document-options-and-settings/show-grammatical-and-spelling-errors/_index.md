---
title: Mostra errori grammaticali e ortografici
linktitle: Mostra errori grammaticali e ortografici
second_title: Riferimento all'API Aspose.Words per .NET
description: Guida dettagliata per abilitare la visualizzazione di errori grammaticali e ortografici in un documento con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-document-options-and-settings/show-grammatical-and-spelling-errors/
---

In questo tutorial, ti guideremo attraverso il codice sorgente C# per abilitare la visualizzazione di errori grammaticali e ortografici con Aspose.Words per .NET. Questa funzione consente di visualizzare gli errori grammaticali e ortografici in un documento.

## Passaggio 1: impostazione del progetto

Per iniziare, crea un nuovo progetto C# nel tuo IDE preferito. Assicurarsi che nel progetto si faccia riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: caricamento del documento

In questo passaggio, caricheremo il documento Word per il quale vogliamo visualizzare errori grammaticali e ortografici. Utilizzare il seguente codice per caricare il documento:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Sostituire`"YOUR DOCUMENTS DIRECTORY"` con il percorso effettivo della directory in cui si trova il documento.

## Passaggio 3: abilita la visualizzazione degli errori

Ora abiliteremo la visualizzazione degli errori grammaticali e ortografici nel documento. Utilizzare il seguente codice per abilitare la visualizzazione degli errori:

```csharp
doc. ShowGrammaticalErrors = true;
doc. ShowSpellingErrors = true;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");
```

Questo codice abilita la visualizzazione degli errori grammaticali (`ShowGrammaticalErrors`) ed errori di ortografia (`ShowSpellingErrors`) nel documento.

### Codice sorgente di esempio per Mostra errori grammaticali e ortografici utilizzando Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	doc.ShowGrammaticalErrors = true;
	doc.ShowSpellingErrors = true;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");

```

 Assicurarsi di specificare il percorso del documento corretto nel file`dataDir` variabile.

Ora hai imparato come abilitare la visualizzazione degli errori grammaticali e ortografici in un documento utilizzando Aspose.Words per .NET. Seguendo la guida dettagliata fornita in questo tutorial, puoi facilmente abilitare questa funzione nei tuoi documenti.