---
title: Ricevi notifiche di caratteri
linktitle: Ricevi notifiche di caratteri
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come ricevere notifiche di caratteri mancanti o sostituiti quando usi Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fonts/receive-notifications-of-fonts/
---

In questo tutorial, ti illustreremo come ricevere notifiche sui font durante l'utilizzo di Aspose.Words per .NET. Le notifiche dei font ti consentono di rilevare e gestire i font mancanti o sostituiti nei tuoi documenti. Ti guideremo passo dopo passo per aiutarti a comprendere e implementare il codice nel tuo progetto .NET.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti elementi:
- Conoscenza operativa del linguaggio di programmazione C#
- La libreria Aspose.Words per .NET installata nel tuo progetto

## Passaggio 1: definire la directory dei documenti
 Innanzitutto, devi impostare il percorso della directory nella posizione del documento di Word. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel codice con il percorso appropriato.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: caricare il documento e configurare le impostazioni del carattere
 Successivamente, caricheremo il documento utilizzando il file`Document` class e configurare le impostazioni del carattere utilizzando il file`FontSettings` classe. Imposteremo il carattere predefinito da utilizzare in caso di caratteri mancanti.

```csharp
//Caricare il documento e configurare le impostazioni del carattere
Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
```

## Passaggio 3: imposta il gestore delle notifiche
 Successivamente, definiremo un gestore di notifica implementando il`IWarningCallback` interfaccia. Questo ci consentirà di raccogliere avvisi sui caratteri durante il salvataggio del documento.

```csharp
// Definire il gestore delle notifiche
HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc. WarningCallback = callback;
```

## Passaggio 4: applica le impostazioni dei caratteri e salva il documento
Infine, applicheremo le impostazioni del carattere al documento e lo salveremo. Eventuali avvisi relativi ai caratteri verranno acquisiti dal gestore delle notifiche definito in precedenza.

```csharp
// Applicare le impostazioni dei caratteri e salvare il documento
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.ReceiveNotificationsOfFonts.pdf");
```

### Esempio di codice sorgente per ricevere notifiche di caratteri utilizzando Aspose.Words per .NET 
```csharp

// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Possiamo scegliere il font predefinito da utilizzare in caso di font mancanti.
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
// Per il test imposteremo Aspose.Words per cercare i caratteri solo in una cartella che non esiste. Poiché Aspose.Words non lo farà
// trova tutti i caratteri nella directory specificata, quindi durante il rendering i caratteri nel documento verranno adattati con il valore predefinito
//carattere specificato in FontSettings.DefaultFontName. Possiamo rispondere a questa richiesta tramite la nostra richiamata.
fontSettings.SetFontsFolder(string.Empty, false);
// Crea una nuova classe che implementa IWarningCallback che raccoglie eventuali avvisi prodotti durante il salvataggio del documento.
HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc.WarningCallback = callback;
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.ReceiveNotificationsOfFonts.pdf");

```

## Conclusione
In questo tutorial, abbiamo visto come ricevere notifiche sui font durante l'utilizzo di Aspose.Words per .NET. Le notifiche dei font ti consentono di rilevare e gestire i font mancanti o sostituiti nei tuoi documenti. Usa questa funzione per garantire la coerenza dei caratteri nei tuoi documenti e intraprendere le azioni appropriate in caso di caratteri mancanti.
