---
title: Imposta il russo come lingua di modifica predefinita
linktitle: Imposta il russo come lingua di modifica predefinita
second_title: Aspose.Words API di elaborazione dei documenti
description: Guida passo-passo per impostare il russo come lingua di modifica predefinita di un documento con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-document-options-and-settings/set-russian-as-default-editing-language/
---

In questo tutorial, ti guideremo attraverso il codice sorgente C# per impostare il russo come lingua di modifica predefinita con Aspose.Words per .NET. Questa funzione consente di impostare la lingua predefinita durante il caricamento di un documento.

## Passaggio 1: impostazione del progetto

Per iniziare, crea un nuovo progetto C# nel tuo IDE preferito. Assicurarsi che nel progetto si faccia riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: caricamento del documento

In questo passaggio, caricheremo il documento Word per il quale vogliamo impostare il russo come lingua di modifica predefinita. Utilizzare il seguente codice per caricare il documento:

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;

// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

 Sostituire`"YOUR DOCUMENTS DIRECTORY"` con il percorso effettivo della directory in cui si trova il documento.

## Passaggio 3: verifica della lingua predefinita

Dopo aver caricato il documento, verificheremo se la lingua predefinita è stata impostata correttamente sul russo. Utilizzare il codice seguente per ottenere l'ID lingua predefinito:

```csharp
int localeId = doc.Styles.DefaultFont.LocaleId;
Console.WriteLine(
	localeId == (int) EditingLanguage.Russian
		? "The document either has no any language set in defaults or it was set to Russian originally."
		: "The document default language was set to another than Russian language originally, so it is not overridden.");
```

Il codice controlla se l'ID della lingua corrisponde a quello del russo. In base al risultato, visualizza un messaggio corrispondente.

### Codice sorgente di esempio per Imposta il russo come lingua di modifica predefinita utilizzando Aspose.Words per .NET

```csharp

	LoadOptions loadOptions = new LoadOptions();
	loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;
	
	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeId = doc.Styles.DefaultFont.LocaleId;
	Console.WriteLine(
		localeId == (int) EditingLanguage.Russian
			? "The document either has no any language set in defaults or it was set to Russian originally."
			: "The document default language was set to another than Russian language originally, so it is not overridden.");

```

 Assicurarsi di specificare il percorso del documento corretto nel file`dataDir` variabile.

Ora hai imparato come impostare il russo come lingua di modifica predefinita per un documento utilizzando Aspose.Words per .NET. Seguendo la guida passo