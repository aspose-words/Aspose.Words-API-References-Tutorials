---
title: Imposta le cartelle dei caratteri con priorità
linktitle: Imposta le cartelle dei caratteri con priorità
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come impostare le cartelle dei caratteri con priorità nei documenti di Word utilizzando Aspose.Words per .NET. La nostra guida garantisce che i tuoi documenti vengano visualizzati perfettamente ogni volta.
type: docs
weight: 10
url: /it/net/working-with-fonts/set-fonts-folders-with-priority/
---
## Introduzione

Nel mondo della manipolazione dei documenti, l'impostazione di cartelle di caratteri personalizzate può fare un'enorme differenza nel garantire che i tuoi documenti vengano visualizzati perfettamente, indipendentemente da dove vengono visualizzati. Oggi approfondiremo come impostare le cartelle dei caratteri con priorità nei documenti di Word utilizzando Aspose.Words per .NET. Questa guida completa ti guiderà attraverso ogni passaggio, rendendo il processo il più agevole possibile.

## Prerequisiti

Prima di iniziare, assicuriamoci di avere tutto ciò di cui abbiamo bisogno. Ecco una rapida lista di controllo:

-  Aspose.Words per .NET: è necessario che questa libreria sia installata. Se non ce l'hai ancora, puoi[scaricalo qui](https://releases.aspose.com/words/net/).
- Ambiente di sviluppo: assicurati di disporre di un ambiente di sviluppo .NET funzionante, come Visual Studio.
-  Directory dei documenti: assicurati di avere una directory per i tuoi documenti. Per i nostri esempi, useremo`"YOUR DOCUMENT DIRECTORY"` come segnaposto per questo percorso.

## Importa spazi dei nomi

Per prima cosa, dobbiamo importare gli spazi dei nomi necessari. Questi spazi dei nomi sono essenziali per accedere alle classi e ai metodi forniti da Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fonts;
```

Ora analizziamo ogni passaggio per impostare le cartelle dei caratteri con priorità.

## Passaggio 1: imposta le origini dei caratteri

Per iniziare, ti consigliamo di definire le fonti dei caratteri. Qui è dove dici ad Aspose.Words dove cercare i caratteri. Puoi specificare più cartelle di caratteri e persino impostarne la priorità.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
    new SystemFontSource(), 
    new FolderFontSource("C:\\MyFonts\\", true, 1)
});
```

In questo esempio, stiamo impostando due origini di caratteri:
- SystemFontSource: questa è l'origine dei caratteri predefinita che include tutti i caratteri installati sul sistema.
-  FolderFontSource: questa è una cartella di caratteri personalizzati situata in`C:\\MyFonts\\` . IL`true` Il parametro specifica che questa cartella deve essere scansionata in modo ricorsivo e`1` stabilisce la sua priorità.

## Passaggio 2: carica il documento

Successivamente, carica il documento con cui vuoi lavorare. Assicurati che il documento si trovi nella directory specificata.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

 Questa riga di codice carica un documento denominato`Rendering.docx` dalla directory dei documenti.

## Passaggio 3: salva il documento con le nuove impostazioni del carattere

Infine, salva il tuo documento. Quando salvi il documento, Aspose.Words utilizzerà le impostazioni del carattere specificate.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

 Ciò salva il documento come PDF nella directory dei documenti con il nome`WorkingWithFonts.SetFontsFoldersWithPriority.pdf`.

## Conclusione

Ed ecco qua! Hai impostato correttamente le cartelle dei caratteri con priorità utilizzando Aspose.Words per .NET. Specificando cartelle e priorità di caratteri personalizzate, puoi garantire che i tuoi documenti vengano visualizzati in modo coerente, indipendentemente da dove vengono visualizzati. Ciò è particolarmente utile in ambienti in cui i caratteri specifici non sono installati per impostazione predefinita.

## Domande frequenti

### Perché dovrei impostare cartelle di caratteri personalizzate?
L'impostazione di cartelle di caratteri personalizzate garantisce che i tuoi documenti vengano visualizzati correttamente, anche se utilizzano caratteri non installati sul sistema in cui vengono visualizzati.

### Posso impostare più cartelle di caratteri personalizzati?
Sì, puoi specificare più cartelle di caratteri. Aspose.Words ti consente di impostare la priorità per ciascuna cartella, assicurando che i caratteri più importanti vengano trovati per primi.

### Cosa succede se un carattere manca da tutte le fonti specificate?
Se un carattere manca da tutte le fonti specificate, Aspose.Words utilizzerà un carattere di fallback per garantire che il documento sia ancora leggibile.

### Posso modificare la priorità dei caratteri di sistema?
I caratteri di sistema sono sempre inclusi per impostazione predefinita, ma puoi impostare la loro priorità rispetto alle cartelle dei caratteri personalizzati.

### È possibile utilizzare percorsi di rete per cartelle di caratteri personalizzati?
Sì, puoi specificare percorsi di rete come cartelle di caratteri personalizzate, consentendoti di centralizzare le risorse dei caratteri in un percorso di rete.