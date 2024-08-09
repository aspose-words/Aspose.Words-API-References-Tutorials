---
title: Utilizzo dei riquadri attività delle estensioni Web
linktitle: Utilizzo dei riquadri attività delle estensioni Web
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come aggiungere e configurare i riquadri attività delle estensioni Web nei documenti di Word utilizzando Aspose.Words per .NET in questo tutorial dettagliato e dettagliato.
type: docs
weight: 10
url: /it/net/programming-with-webextension/using-web-extension-task-panes/
---
## Introduzione

Benvenuti in questo tutorial approfondito sull'utilizzo dei pannelli attività delle estensioni Web in un documento Word utilizzando Aspose.Words per .NET. Se hai sempre desiderato migliorare i tuoi documenti Word con riquadri attività interattivi, sei nel posto giusto. Questa guida ti guiderà attraverso ogni passaggio per raggiungere questo obiettivo senza problemi.

## Prerequisiti

Prima di approfondire, assicuriamoci che tu abbia tutto ciò di cui hai bisogno:

-  Aspose.Words per .NET: puoi scaricarlo[Qui](https://releases.aspose.com/words/net/).
- Ambiente di sviluppo .NET: Visual Studio o qualsiasi altro IDE che preferisci.
- Conoscenza di base di C#: questo ti aiuterà a seguire gli esempi di codice.
-  Licenza per Aspose.Words: puoi acquistarne una[Qui](https://purchase.aspose.com/buy) o ottenere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).

## Importa spazi dei nomi

Prima di iniziare a scrivere il codice, assicurati di aver importato i seguenti spazi dei nomi nel tuo progetto:

```csharp
using Aspose.Words;
using Aspose.Words.WebExtensions;
```

## Guida passo passo

Ora suddividiamo il processo in passaggi facili da seguire.

### Passaggio 1: impostazione della directory dei documenti

Per prima cosa, dobbiamo impostare il percorso della directory dei documenti. Qui è dove verrà salvato il tuo documento Word.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della cartella dei documenti.

### Passaggio 2: creazione di un nuovo documento

Successivamente, creeremo un nuovo documento Word utilizzando Aspose.Words.

```csharp
Document doc = new Document();
```

 Questa riga inizializza una nuova istanza di`Document` classe, che rappresenta un documento Word.

### Passaggio 3: aggiunta di un riquadro attività

Ora aggiungeremo un Task Pane al nostro documento. I riquadri attività sono utili per fornire funzionalità e strumenti aggiuntivi all'interno di un documento Word.

```csharp
TaskPane taskPane = new TaskPane();
doc.WebExtensionTaskPanes.Add(taskPane);
```

 Qui ne creiamo uno nuovo`TaskPane` oggetto e aggiungerlo al documento`WebExtensionTaskPanes` collezione.

### Passaggio 4: configurazione del riquadro attività

Per rendere visibile il nostro Task Pane e impostarne le proprietà, utilizziamo il seguente codice:

```csharp
taskPane.DockState = TaskPaneDockState.Right;
taskPane.IsVisible = true;
taskPane.Width = 300;
```

- `DockState` imposta la posizione in cui verrà visualizzato il Task Pane. In questo caso, è a destra.
- `IsVisible` garantisce che il Task Pane sia visibile.
- `Width` imposta la larghezza del Task Pane.

### Passaggio 5: impostazione del riferimento all'estensione Web

Successivamente, configuriamo il riferimento all'estensione Web che include ID, versione, tipo di negozio e negozio.

```csharp
taskPane.WebExtension.Reference.Id = "wa102923726";
taskPane.WebExtension.Reference.Version = "1.0.0.0";
taskPane.WebExtension.Reference.StoreType = WebExtensionStoreType.OMEX;
taskPane.WebExtension.Reference.Store = "th-TH";
```

- `Id`è un identificatore univoco per l'estensione web.
- `Version` specifica la versione dell'estensione.
- `StoreType` indica la tipologia di negozio (in questo caso OMEX).
- `Store` specifica il codice lingua/cultura del negozio.

### Passaggio 6: aggiunta di proprietà all'estensione Web

Puoi aggiungere proprietà alla tua estensione web per definirne il comportamento o il contenuto.

```csharp
taskPane.WebExtension.Properties.Add(new WebExtensionProperty("mailchimpCampaign", "mailchimpCampaign"));
```

 Qui aggiungiamo una proprietà denominata`mailchimpCampaign`.

### Passaggio 7: associazione dell'estensione Web

Infine, aggiungiamo i collegamenti alla nostra estensione web. Le associazioni consentono di collegare l'estensione a parti specifiche del documento.

```csharp
taskPane.WebExtension.Bindings.Add(new WebExtensionBinding("UnnamedBinding_0_1506535429545", WebExtensionBindingType.Text, "194740422"));
```

- `UnnamedBinding_0_1506535429545` è il nome dell'associazione.
- `WebExtensionBindingType.Text` indica che la rilegatura è di tipo testo.
- `194740422` è l'ID della parte del documento a cui è legata l'estensione.

### Passaggio 8: salvataggio del documento

Dopo aver impostato tutto, salva il documento.

```csharp
doc.Save(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
```

Questa riga salva il documento nella directory specificata con il nome file specificato.

### Passaggio 9: caricamento e visualizzazione delle informazioni del riquadro attività

Per verificare e visualizzare le informazioni del riquadro attività, carichiamo il documento e iteriamo attraverso i riquadri attività.

```csharp
doc = new Document(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");

Console.WriteLine("Task panes sources:\n");

foreach (TaskPane taskPaneInfo in doc.WebExtensionTaskPanes)
{
    WebExtensionReference reference = taskPaneInfo.WebExtension.Reference;
    Console.WriteLine($"Provider: \"{reference.Store}\", version: \"{reference.Version}\", catalog identifier: \"{reference.Id}\";");
}
```

Questo codice carica il documento e stampa il provider, la versione e l'identificatore del catalogo di ciascun riquadro attività nella console.

## Conclusione

E questo è tutto! Hai aggiunto e configurato correttamente un riquadro attività delle estensioni Web in un documento di Word utilizzando Aspose.Words per .NET. Questa potente funzionalità può migliorare in modo significativo i tuoi documenti Word fornendo funzionalità aggiuntive direttamente all'interno del documento. 

## Domande frequenti

### Che cos'è un riquadro attività in Word?
Un Task Pane è un elemento dell'interfaccia che fornisce strumenti e funzionalità aggiuntivi all'interno di un documento Word, migliorando l'interazione e la produttività dell'utente.

### Posso personalizzare l'aspetto del Task Pane?
 Sì, puoi personalizzare l'aspetto del Task Pane impostando proprietà come`DockState`, `IsVisible` , E`Width`.

### Cosa sono le proprietà delle estensioni Web?
Le proprietà dell'estensione Web sono proprietà personalizzate che puoi aggiungere a un'estensione Web per definirne il comportamento o il contenuto.

### Come posso associare un'estensione Web a una parte del documento?
 Puoi associare un'estensione Web a una parte del documento utilizzando il file`WebExtensionBinding` classe, specificando il tipo di associazione e l'ID di destinazione.

### Dove posso trovare ulteriori informazioni su Aspose.Words per .NET?
 Puoi trovare documentazione dettagliata[Qui](https://reference.aspose.com/words/net/).