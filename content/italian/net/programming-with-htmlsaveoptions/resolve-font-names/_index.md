---
title: Risolvi i nomi dei caratteri
linktitle: Risolvi i nomi dei caratteri
second_title: API di elaborazione dei documenti Aspose.Words
description: Guida passo passo per risolvere i nomi dei caratteri mancanti durante la conversione in HTML con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-htmlsaveoptions/resolve-font-names/
---

In questo tutorial ti guideremo attraverso il codice sorgente C# per risolvere i nomi dei caratteri mancanti con Aspose.Words per .NET. Questa funzione ti consente di risolvere automaticamente i nomi dei caratteri mancanti durante la conversione di un documento in HTML.

## Passaggio 1: impostazione del progetto

Per iniziare, crea un nuovo progetto C# nel tuo IDE preferito. Assicurati che nel tuo progetto venga fatto riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: caricamento del documento

In questo passaggio caricheremo il documento da elaborare. Utilizzare il codice seguente per caricare il documento da una directory specificata:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Missing font.docx");
```

 Questo codice crea un'istanza di`Document` caricando il documento dalla directory specificata.

## Passaggio 3: configurazione delle opzioni di backup HTML

Ora configureremo le opzioni di salvataggio HTML per risolvere i nomi dei caratteri mancanti durante la conversione. Utilizza il seguente codice:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
PrettyFormat = true,
ResolveFontNames=true
};
```

 Questo codice crea un'istanza di`HtmlSaveOptions` imposta il`ResolveFontNames` opzione a`true` per risolvere i nomi dei caratteri mancanti durante la conversione in HTML. Anche il`PrettyFormat` l'opzione è impostata su`true` per ottenere un codice HTML ben formattato.

## Passaggio 4: convertire e salvare il documento in HTML

Infine, convertiremo il documento in HTML utilizzando le opzioni di salvataggio HTML configurate in precedenza. Utilizza il seguente codice:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);
```

Questo codice converte il documento in HTML risolvendo automaticamente i nomi dei caratteri mancanti e salva il file HTML convertito nella directory specificata.

### Codice sorgente di esempio per risolvere i nomi dei caratteri utilizzando Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Missing font.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		PrettyFormat = true, ResolveFontNames = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);

```

 Assicurati di specificare il percorso corretto della directory dei documenti nel file`dataDir` variabile.