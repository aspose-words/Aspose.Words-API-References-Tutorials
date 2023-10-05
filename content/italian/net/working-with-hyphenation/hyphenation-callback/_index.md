---
title: Richiamata con sillabazione
linktitle: Richiamata con sillabazione
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come utilizzare il callback di sillabazione in Aspose.Words per .NET per gestire la sillabazione delle parole.
type: docs
weight: 10
url: /it/net/working-with-hyphenation/hyphenation-callback/
---

In questo tutorial passo passo, ti mostreremo come utilizzare la funzione di callback di sillabazione in Aspose.Words per .NET. Spiegheremo il codice sorgente C# fornito e ti mostreremo come implementarlo nei tuoi progetti.

 Per iniziare, assicurati di avere Aspose.Words per .NET installato e configurato nel tuo ambiente di sviluppo. Se non l'hai già fatto, scarica e installa la libreria da[Aspose.Releases]https://releases.aspose.com/words/net/.

## Passaggio 1: salva il promemoria di sillabazione

 Innanzitutto, registreremo la richiamata di sillabazione utilizzando un file custom`CustomHyphenationCallback` classe. Ciò ci consentirà di gestire la sillabazione delle parole secondo le nostre regole:

```csharp
Hyphenation.Callback = new CustomHyphenationCallback();
```

 Assicurati di aver implementato il file`CustomHyphenationCallback` lezione in base alle tue esigenze specifiche.

## Passaggio 2: caricare il documento e applicare la sillabazione

Successivamente, carica il documento dalla directory specificata e sillaba le parole utilizzando Aspose.Words:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "German text.docx");
document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
```

## Passaggio 3: gestione degli errori del dizionario mancanti

Nel caso in cui manchi un dizionario di sillabazione, cattureremo l'eccezione corrispondente e visualizzeremo un messaggio di errore:

```csharp
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
     Console.WriteLine(e.Message);
}
```

## Passaggio 4: pulizia e disattivazione del promemoria di sillabazione

Infine, per motivi di pulizia e per disattivare il promemoria di sillabazione, eseguire i seguenti passaggi:

```csharp
finally
{
     Hyphenation. Callback = null;
}
```

Ciò pulisce e disabilita il promemoria di sillabazione al termine dell'elaborazione.

COSÌ ! Hai utilizzato con successo la richiamata di sillabazione in Aspose.Words per .NET.

### Codice sorgente di esempio per la richiamata di sillabazione con Aspose.Words per .NET

```csharp
try
{
	 // Registra la richiamata di sillabazione.
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

Sentiti libero di utilizzare questo codice nei tuoi progetti e modificarlo per adattarlo alle tue esigenze specifiche.

### Domande frequenti

#### D: Che cos'è un promemoria di sillabazione in Aspose.Words?

A: Un promemoria di sillabizzazione in Aspose.Words è una funzionalità che ti consente di personalizzare il modo in cui le parole vengono sillabizzate nei tuoi documenti. Utilizzando un promemoria di sillabazione, è possibile specificare regole personalizzate per la sillabazione delle parole, che possono essere utili per lingue specifiche o scenari particolari in cui la sillabazione predefinita non produce i risultati desiderati.

#### Q: Come impostare un promemoria di sillabazione in Aspose.Words?

 R: Per definire un callback di sillabazione in Aspose.Words, è necessario creare una classe che implementi il`HyphenationCallback` interfaccia e implementare il`HandleWord()` metodo. Questo metodo verrà chiamato per ogni parola incontrata durante la sillabazione. Puoi applicare regole di sillabazione personalizzate e restituire la parola sillabata. Quindi puoi associare la richiamata di sillabazione utilizzando il file`Document.HyphenationCallback` proprietà del tuo documento

#### D: Qual è il vantaggio di utilizzare un promemoria di sillabazione in Aspose.Words?

R: Il vantaggio di utilizzare un promemoria di sillabazione in Aspose.Words è la possibilità di personalizzare il modo in cui le parole vengono sillabate nei documenti. Ciò ti offre un maggiore controllo sulla sillabazione, soprattutto per lingue specifiche o scenari in cui la sillabazione predefinita non fornisce i risultati desiderati. Puoi applicare regole specifiche ad ogni parola per ottenere una sillabazione precisa in base alle tue esigenze.

#### D: Quali sono alcuni scenari comuni in cui l'utilizzo di un promemoria per la sillabazione può essere utile?

R: L'uso di un booster di sillabazione può essere utile in diversi scenari, come ad esempio:
- Sillabizzazione di parole in lingue specifiche che hanno particolari regole di sillabazione.
- L'applicazione di regole di sillabazione personalizzate per acronimi o parole tecniche.
- Adattamento della sillabazione in base alle preferenze stilistiche o agli standard tipografici.

#### D: Come posso testare la sillabazione personalizzata con un promemoria di sillabazione in Aspose.Words?

 A: Per testare la sillabazione personalizzata con un promemoria di sillabazione in Aspose.Words, è possibile creare un documento di prova contenente parole per le quali si desidera applicare regole di sillabazione personalizzate. Quindi puoi impostare la richiamata di sillabazione personalizzata, chiamare il file`Document.Range.Replace()` metodo per sostituire le parole nel documento e utilizzare il metodo`Hyphenate()` metodo del`Hyphenation` class per ottenere la sillabazione delle parole. È quindi possibile formattare le parole sillabate secondo necessità, ad esempio aggiungendo trattini tra le sillabe.