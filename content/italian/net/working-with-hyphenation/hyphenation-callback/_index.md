---
title: Richiamata con sillabazione
linktitle: Richiamata con sillabazione
second_title: API di elaborazione dei documenti Aspose.Words
description: Impara a implementare la richiamata di sillabazione in Aspose.Words per .NET per migliorare la formattazione dei documenti con questa guida passo passo completa.
type: docs
weight: 10
url: /it/net/working-with-hyphenation/hyphenation-callback/
---

## introduzione

Ehilà! Ti sei mai trovato intrappolato nelle complessità della formattazione del testo, soprattutto quando hai a che fare con lingue che richiedono la sillabazione? Non sei solo. La sillabazione, sebbene cruciale per il corretto layout del testo, può essere un po’ un grattacapo. Ma indovina un po? Aspose.Words per .NET ti copre le spalle. Questa potente libreria ti consente di gestire la formattazione del testo senza problemi, inclusa la gestione della sillabazione attraverso un meccanismo di callback. Incuriosito? Immergiamoci nel nocciolo della questione di come è possibile implementare un callback di sillabazione utilizzando Aspose.Words per .NET.

## Prerequisiti

Prima di sporcarci le mani con il codice, assicuriamoci di avere tutto ciò di cui hai bisogno:

1.  Aspose.Words per .NET: assicurati di avere la libreria. Puoi[scaricalo qui](https://releases.aspose.com/words/net/).
2. IDE: un ambiente di sviluppo come Visual Studio.
3. Conoscenza di base di C#: comprensione di C# e .NET framework.
4. Dizionari di sillabazione: dizionari di sillabazione per le lingue che intendi utilizzare.
5.  Licenza Aspose: una licenza Aspose valida. Puoi ottenere un[licenza temporanea](https://purchase.aspose.com/temporary-license/) se non ne hai uno.

## Importa spazi dei nomi

Per prima cosa, importiamo gli spazi dei nomi necessari. Ciò garantisce che il nostro codice abbia accesso a tutte le classi e i metodi di cui abbiamo bisogno da Aspose.Words.

```csharp
using Aspose.Words;
using System;
using System.IO;
```

## Passaggio 1: registrare la richiamata di sillabazione

Per iniziare, dobbiamo registrare la nostra richiamata di sillabazione. Qui è dove diciamo ad Aspose.Words di utilizzare la nostra logica di sillabazione personalizzata.

```csharp
try
{
    // Registra la richiamata di sillabazione.
    Hyphenation.Callback = new CustomHyphenationCallback();
}
catch (Exception e)
{
    Console.WriteLine($"Error registering hyphenation callback: {e.Message}");
}
```

 Qui creiamo un'istanza del nostro callback personalizzato e lo assegniamo a`Hyphenation.Callback`.

## Passaggio 2: definire il percorso del documento

Successivamente, dobbiamo definire la directory in cui sono archiviati i nostri documenti. Questo è fondamentale poiché caricheremo e salveremo i documenti da questo percorso.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo dei tuoi documenti.

## Passaggio 3: caricare il documento

Ora carichiamo il documento che richiede la sillabazione.

```csharp
Document document = new Document(dataDir + "German text.docx");
```

 Qui stiamo caricando un documento di testo tedesco. Puoi sostituire`"German text.docx"` con il nome file del tuo documento.

## Passaggio 4: salva il documento

Dopo aver caricato il documento, lo salviamo in un nuovo file, applicando il callback di sillabazione nel processo.

```csharp
document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
```

Questa riga salva il documento come PDF con la sillabazione applicata.

## Passaggio 5: gestire l'eccezione del dizionario di sillabazione mancante

A volte, potresti riscontrare un problema in cui manca il dizionario di sillabazione. Gestiamolo.

```csharp
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
    Console.WriteLine(e.Message);
}
finally
{
    Hyphenation.Callback = null;
}
```

In questo blocco catturiamo l'eccezione specifica relativa ai dizionari mancanti e stampiamo il messaggio.

## Passaggio 6: implementare la classe di callback di sillabazione personalizzata

 Ora implementiamo il file`CustomHyphenationCallback` classe che gestisce la richiesta di dizionari di sillabazione.

```csharp
public class CustomHyphenationCallback : IHyphenationCallback
{
    public void RequestDictionary(string language)
    {
        string dictionaryFolder = MyDir;
        string dictionaryFullFileName;
        switch (language)
        {
            case "en-US":
                dictionaryFullFileName = Path.Combine(dictionaryFolder, "hyph_en_US.dic");
                break;
            case "de-CH":
                dictionaryFullFileName = Path.Combine(dictionaryFolder, "hyph_de_CH.dic");
                break;
            default:
                throw new Exception($"Missing hyphenation dictionary for {language}.");
        }
        // Registra il dizionario per la lingua richiesta.
        Hyphenation.RegisterDictionary(language, dictionaryFullFileName);
    }
}
```

 In questa classe, il`RequestDictionary` viene chiamato ogni volta che è necessario un dizionario di sillabazione. Controlla la lingua e registra il dizionario appropriato.

## Conclusione

E il gioco è fatto! Hai appena imparato come implementare un callback di sillabazione in Aspose.Words per .NET. Seguendo questi passaggi, puoi assicurarti che i tuoi documenti siano ben formattati, indipendentemente dalla lingua. Che tu abbia a che fare con l'inglese, il tedesco o qualsiasi altra lingua, questo metodo ti consente di gestire la sillabazione senza sforzo.

## Domande frequenti

### Cos'è Aspose.Words per .NET?
Aspose.Words per .NET è una potente libreria di manipolazione di documenti che consente agli sviluppatori di creare, modificare e convertire documenti a livello di codice.

### Perché la sillabazione è importante nella formattazione dei documenti?
La sillabazione migliora il layout del testo suddividendo le parole nei punti appropriati, garantendo un documento più leggibile e visivamente accattivante.

### Posso usare Aspose.Words gratuitamente?
 Aspose.Words offre una prova gratuita. Puoi prenderlo[Qui](https://releases.aspose.com/).

### Come posso ottenere un dizionario di sillabazione?
Puoi scaricare dizionari di sillabazione da varie risorse online o crearne uno tuo, se necessario.

### Cosa succede se manca un dizionario di sillabazione?
 Se manca un dizionario, il`RequestDictionary` Il metodo genera un'eccezione, che puoi gestire per informare l'utente o fornire un fallback.