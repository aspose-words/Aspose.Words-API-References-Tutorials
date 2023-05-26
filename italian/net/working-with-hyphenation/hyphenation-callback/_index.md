---
title: Richiamata di sillabazione
linktitle: Richiamata di sillabazione
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come utilizzare il callback della sillabazione in Aspose.Words per .NET per gestire la sillabazione delle parole.
type: docs
weight: 10
url: /it/net/working-with-hyphenation/hyphenation-callback/
---

In questo tutorial passo-passo, ti mostreremo come utilizzare la funzione di callback della sillabazione in Aspose.Words per .NET. Spiegheremo il codice sorgente C# fornito e ti mostreremo come implementarlo nei tuoi progetti.

Per iniziare, assicurati di avere Aspose.Words per .NET installato e configurato nel tuo ambiente di sviluppo. Se non l'hai già fatto, scarica e installa la libreria dal sito ufficiale.

## Passaggio 1: salva il promemoria di sillabazione

 Per prima cosa, registreremo il callback della sillabazione usando un custom`CustomHyphenationCallback` classe. Questo ci permetterà di gestire la sillabazione delle parole secondo le nostre regole:

```csharp
Hyphenation.Callback = new CustomHyphenationCallback();
```

 Assicurati di aver implementato il`CustomHyphenationCallback`classe in base alle vostre specifiche esigenze.

## Passaggio 2: caricamento del documento e applicazione della sillabazione

Quindi, carica il tuo documento dalla directory specificata e sillaba le parole usando Aspose.Words:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "German text.docx");
document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
```

## Passaggio 3: gestione degli errori di dizionario mancanti

Nel caso in cui manchi un dizionario di sillabazione, rileveremo l'eccezione corrispondente e visualizzeremo un messaggio di errore:

```csharp
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
     Console.WriteLine(e.Message);
}
```

## Passaggio 4: pulizia e disabilitazione del promemoria di sillabazione

Infine, per la pulizia e per disattivare il promemoria di sillabazione, eseguire i seguenti passaggi:

```csharp
finally
{
     Hyphenation. Callback = null;
}
```

Questo pulisce e disabilita il promemoria di sillabazione dopo aver terminato l'elaborazione.

COSÌ ! Hai utilizzato correttamente il callback di sillabazione in Aspose.Words per .NET.

### Esempio di codice sorgente per la richiamata di sillabazione con Aspose.Words per .NET

```csharp
try
{
	 // Registra callback di sillabazione.
	 Hyphenation.Callback = new CustomHyphenationCallback();
	 string dataDir = "YOUR DOCUMENT DIRECTORY";
	 Document document = new Document(dataDir + "German text.docx");
	 document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
}
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
	 Console.WriteLine(e.Message);
}
finally
{
	 Hyphenation. Callback = null;
}

```

Sentiti libero di utilizzare questo codice nei tuoi progetti e di modificarlo in base alle tue esigenze specifiche.