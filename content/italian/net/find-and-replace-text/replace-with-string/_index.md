---
title: Sostituisci con stringa
linktitle: Sostituisci con stringa
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come sostituire il testo con una stringa in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/find-and-replace-text/replace-with-string/
---
In questo articolo, esploreremo il codice sorgente C# sopra per capire come utilizzare la funzione Sostituisci con stringa nella libreria Aspose.Words per .NET. Questa funzionalità consente di eseguire la sostituzione del testo in base a una stringa di caratteri specifica in un documento di Word.

## Prerequisiti

- Conoscenza base del linguaggio C#.
- Ambiente di sviluppo .NET con libreria Aspose.Words installata.

## Passaggio 1: creazione di un nuovo documento

 Prima di iniziare a utilizzare la sostituzione delle stringhe, dobbiamo creare un nuovo documento utilizzando Aspose.Words per .NET. Questo può essere fatto istanziando a`Document` oggetto:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Passaggio 2: inserisci il testo nel documento

 Una volta che abbiamo un documento, possiamo inserire del testo usando a`DocumentBuilder` oggetto. Nel nostro esempio, utilizziamo il file`Writeln` metodo per inserire la frase "triste pazzesco":

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("sad mad bad");
```

## Passaggio 3: sostituisci con una stringa

 Noi usiamo il`Range.Replace`metodo per sostituire il testo con una stringa. Nel nostro esempio, sostituiamo tutte le occorrenze della parola "triste" con "cattivo" utilizzando il simbolo`FindReplaceOptions` opzione con il`FindReplaceDirection.Forward` direzione della ricerca:

```csharp
doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## Passaggio 4: salvataggio del documento modificato

Infine, salviamo il documento modificato in una directory specificata utilizzando il file`Save` metodo:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
```

### Codice sorgente di esempio per Sostituisci con stringa utilizzando Aspose.Words per .NET

Ecco il codice sorgente di esempio completo per illustrare l'uso della sostituzione con una stringa di caratteri con Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("sad mad bad");

	doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));

	doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
  
```

## Conclusione

In questo articolo, abbiamo esplorato il codice sorgente C# per capire come utilizzare la funzione Sostituisci con stringa di Aspose.Words per .NET. Abbiamo seguito una guida passo passo per creare un documento, inserire testo, sostituirlo con una stringa e salvare il documento modificato.

### Domande frequenti

#### D: Qual è la funzione "Sostituisci con stringa" in Aspose.Words per .NET?

R: La funzione "Sostituisci con stringa" in Aspose.Words per .NET consente di eseguire la sostituzione del testo in base a una stringa di caratteri specifica in un documento di Word. Ti consente di trovare le occorrenze di una stringa particolare e di sostituirle con un'altra stringa specificata.

#### D: Come posso creare un nuovo documento utilizzando Aspose.Words per .NET?

 R: Per creare un nuovo documento utilizzando Aspose.Words per .NET, puoi creare un'istanza di a`Document` oggetto. Ecco un esempio di codice C# per creare un nuovo documento:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

#### D: Come posso inserire testo in un documento utilizzando Aspose.Words per .NET?

 R: Una volta che hai un documento, puoi inserire del testo usando a`DocumentBuilder` oggetto. In Aspose.Words per .NET, puoi utilizzare vari metodi di`DocumentBuilder` classe per inserire testo in posizioni diverse. Ad esempio, puoi utilizzare il file`Writeln` metodo per inserire testo su una nuova riga. Ecco un esempio:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("sad mad bad");
```

#### D: Come posso eseguire la sostituzione del testo con una stringa in Aspose.Words per .NET?

 R: Per eseguire la sostituzione del testo con una stringa in Aspose.Words per .NET, è possibile utilizzare il file`Range.Replace` metodo e specificare la stringa da sostituire e la stringa con cui sostituirla. Questo metodo esegue una semplice corrispondenza di testo e sostituisce tutte le occorrenze della stringa specificata. Ecco un esempio:

```csharp
doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));
```

#### D: Posso eseguire la sostituzione del testo con distinzione tra maiuscole e minuscole con la funzione "Sostituisci con stringa" in Aspose.Words per .NET?

R: Sì, per impostazione predefinita, la funzione "Sostituisci con stringa" in Aspose.Words per .NET fa distinzione tra maiuscole e minuscole. Ciò significa che sostituirà solo il testo che corrisponde esattamente alla stringa specificata in termini di maiuscole e minuscole. Se desideri eseguire una sostituzione senza distinzione tra maiuscole e minuscole, puoi modificare il testo da sostituire e la stringa di sostituzione in modo che abbiano le stesse maiuscole o minuscole oppure puoi utilizzare altre tecniche come le espressioni regolari.

#### D: Posso sostituire più occorrenze di una stringa in un documento utilizzando la funzione "Sostituisci con stringa" in Aspose.Words per .NET?

 R: Sì, puoi sostituire più occorrenze di una stringa in un documento utilizzando la funzione "Sostituisci con stringa" in Aspose.Words per .NET. IL`Range.Replace` Il metodo sostituirà tutte le occorrenze della stringa specificata nel contenuto del documento.

#### D: Esistono limitazioni o considerazioni quando si utilizza la funzione "Sostituisci con stringa" in Aspose.Words per .NET?

R: Quando si utilizza la funzione "Sostituisci con stringa" in Aspose.Words per .NET, è importante essere consapevoli del contesto e assicurarsi che la sostituzione venga applicata solo dove previsto. Assicurati che la stringa di ricerca non venga visualizzata in posizioni indesiderate, ad esempio all'interno di altre parole o come parte di una formattazione speciale. Inoltre, considera le implicazioni sulle prestazioni durante l'elaborazione di parole con documenti di grandi dimensioni o sostituzioni frequenti.

#### D: Posso sostituire stringhe con lunghezze diverse utilizzando la funzione "Sostituisci con stringa" in Aspose.Words per .NET?

R: Sì, puoi sostituire stringhe con lunghezze diverse utilizzando la funzione "Sostituisci con stringa" in Aspose.Words per .NET. La stringa sostitutiva può avere qualsiasi lunghezza e sostituirà la corrispondenza esatta della stringa di ricerca. Il documento verrà modificato di conseguenza per adattarsi alla nuova lunghezza della stringa.