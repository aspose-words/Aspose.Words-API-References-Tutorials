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

### FAQ

#### D: Cos'è un promemoria di sillabazione in Aspose.Words?

A: Un promemoria di sillabazione in Aspose.Words è una funzione che ti consente di personalizzare il modo in cui le parole vengono sillabizzate nei tuoi documenti. Utilizzando un promemoria di sillabazione, è possibile specificare regole personalizzate per la sillabazione delle parole, che possono essere utili per lingue specifiche o scenari particolari in cui la sillabazione predefinita non produce i risultati desiderati.

#### D: Come impostare un promemoria di sillabazione in Aspose.Words?

 R: Per definire un callback di sillabazione in Aspose.Words, è necessario creare una classe che implementi il`HyphenationCallback` interfaccia e implementare il`HandleWord()` metodo. Questo metodo verrà chiamato per ogni parola incontrata durante la sillabazione. Puoi applicare regole di sillabazione personalizzate e restituire la parola sillabata. Quindi puoi associare la tua richiamata di sillabazione usando il`Document.HyphenationCallback` proprietà del tuo documento.

#### D: Qual è il vantaggio di utilizzare un promemoria di sillabazione in Aspose.Words?

A: Il vantaggio dell'utilizzo di un promemoria di sillabazione in Aspose.Words è la possibilità di personalizzare il modo in cui le parole vengono sillabizzate nei tuoi documenti. Questo ti dà un maggiore controllo sulla sillabazione, specialmente per lingue o scenari specifici in cui la sillabazione predefinita non dà i risultati desiderati. Puoi applicare regole specifiche ad ogni parola per ottenere una sillabazione precisa in base alle tue esigenze.

#### D: Quali sono alcuni scenari comuni in cui l'utilizzo di un promemoria per la sillabazione può essere utile?

R: L'uso di un booster di sillabazione può essere utile in diversi scenari, come ad esempio:
- Sillabazione di parole in lingue specifiche che hanno particolari regole di sillabazione.
- L'applicazione di regole di sillabazione personalizzate per acronimi o parole tecniche.
- Adattamento della sillabazione secondo preferenze stilistiche o standard tipografici.

#### D: Come posso testare la sillabazione personalizzata con un promemoria di sillabazione in Aspose.Words?

R: Per testare la sillabazione personalizzata con un promemoria di sillabazione in Aspose.Words, puoi creare un documento di prova contenente parole per le quali desideri applicare regole di sillabazione personalizzate. Quindi puoi impostare il tuo callback di sillabazione personalizzato, chiama il file`Document.Range.Replace()` metodo per sostituire le parole nel documento e utilizzare il`Hyphenate()` metodo del`Hyphenation` class per ottenere la sillabazione delle parole . È quindi possibile formattare le parole sillabizzate secondo necessità, ad esempio aggiungendo trattini tra le sillabe.