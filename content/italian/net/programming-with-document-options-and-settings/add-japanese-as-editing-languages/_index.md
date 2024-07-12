---
title: Aggiungi il giapponese come lingua di modifica
linktitle: Aggiungi il giapponese come lingua di modifica
second_title: API di elaborazione dei documenti Aspose.Words
description: Guida passo passo per aggiungere il giapponese come lingua di modifica con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-document-options-and-settings/add-japanese-as-editing-languages/
---

In questo tutorial, ti guideremo passo dopo passo per comprendere e implementare la funzionalità di aggiunta del giapponese come linguaggio di modifica con Aspose.Words per .NET. Questa funzionalità consente di impostare le preferenze della lingua durante il caricamento di un documento e di aggiungere il giapponese come lingua di modifica.

## Passaggio 1: impostazione del progetto

Per iniziare, crea un nuovo progetto C# nel tuo IDE preferito. Assicurati che nel tuo progetto venga fatto riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: caricamento del documento

In questo passaggio caricheremo il documento Word che non contiene una lingua di modifica predefinita e al quale vogliamo aggiungere il giapponese. Utilizzare il seguente codice per caricare il documento:

```csharp
LoadOptions loadOptions = new LoadOptions();

//Imposta le preferenze della lingua che verranno utilizzate durante il caricamento del documento.
loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);

string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

## Passaggio 3: verifica della lingua predefinita

Dopo aver caricato il documento, controlleremo se la lingua di modifica predefinita è stata impostata correttamente sul giapponese. Utilizza il seguente codice per ottenere l'ID della lingua dell'Estremo Oriente:

```csharp
int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
Console.WriteLine(
	localeIdFarEast == (int) EditingLanguage.Japanese
		? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
		: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");
```

Il codice controlla se l'ID della lingua dell'Estremo Oriente corrisponde a quello del giapponese. In base al risultato, viene visualizzato un messaggio corrispondente.

### Codice sorgente di esempio per aggiungere il giapponese come lingue di modifica utilizzando Aspose.Words per .NET

```csharp

	LoadOptions loadOptions = new LoadOptions();
	
	// Imposta le preferenze della lingua che verranno utilizzate durante il caricamento del documento.
	loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);
	
	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
	Console.WriteLine(
		localeIdFarEast == (int) EditingLanguage.Japanese
			? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
			: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");

```

