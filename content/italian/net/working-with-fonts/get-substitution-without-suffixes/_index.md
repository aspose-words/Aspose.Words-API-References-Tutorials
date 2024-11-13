---
title: Ottieni la sostituzione senza suffissi
linktitle: Ottieni la sostituzione senza suffissi
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come gestire la sostituzione dei font senza suffissi in Aspose.Words per .NET. Segui la nostra guida passo passo per assicurarti che i tuoi documenti siano sempre perfetti.
type: docs
weight: 10
url: /it/net/working-with-fonts/get-substitution-without-suffixes/
---
## Introduzione

Benvenuti a questa guida completa sulla gestione della sostituzione dei font tramite Aspose.Words per .NET. Se avete mai avuto problemi con i font che non apparivano correttamente nei vostri documenti, siete arrivati nel posto giusto. Questo tutorial vi guiderà passo dopo passo attraverso un processo per gestire in modo efficiente la sostituzione dei font senza suffissi.

## Prerequisiti

Prima di immergerti nel tutorial, assicurati di avere quanto segue:

- Conoscenza di base di C#: comprendere la programmazione C# renderà più semplice seguire e implementare i passaggi.
-  Aspose.Words per la libreria .NET: Scarica e installa la libreria da[collegamento per il download](https://releases.aspose.com/words/net/).
- Ambiente di sviluppo: configura un ambiente di sviluppo come Visual Studio per scrivere ed eseguire il codice.
-  Documento di esempio: un documento di esempio (ad esempio,`Rendering.docx`) con cui lavorare durante questo tutorial.

## Importazione degli spazi dei nomi

Per prima cosa, dobbiamo importare gli spazi dei nomi necessari per accedere alle classi e ai metodi forniti da Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
using System.Collections.Generic;
```

## Passaggio 1: definire la directory dei documenti

Per iniziare, specifica la directory in cui si trova il tuo documento. Questo ti aiuterà a localizzare il documento su cui vuoi lavorare.

```csharp
// Percorso alla directory del documento
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: impostare il gestore degli avvisi di sostituzione

Successivamente, dobbiamo impostare un gestore di avvisi che ci notificherà ogni volta che si verifica una sostituzione di font durante l'elaborazione del documento. Questo è fondamentale per rilevare e gestire eventuali problemi di font.

```csharp
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
Document doc = new Document(dataDir + "Rendering.docx");
doc.WarningCallback = substitutionWarningHandler;
```

## Passaggio 3: aggiungere origini font personalizzate

In questo passaggio, aggiungeremo fonti di font personalizzate per garantire che Aspose.Words possa individuare e utilizzare i font corretti. Ciò è particolarmente utile se hai font specifici archiviati in directory personalizzate.

```csharp
List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());

FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
```

In questo codice:
-  Recuperiamo le fonti dei font correnti e ne aggiungiamo una nuova`FolderFontSource` che punta alla nostra directory di font personalizzati (`C:\\MyFonts\\`).
- Aggiorniamo quindi le fonti dei font con questo nuovo elenco.

## Passaggio 4: Salvare il documento

Infine, salva il documento dopo aver applicato le impostazioni di sostituzione font. Per questo tutorial, lo salveremo come PDF.

```csharp
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");
```

## Passaggio 5: creare la classe del gestore degli avvisi

 Per gestire efficacemente gli avvisi, creare una classe personalizzata che implementi l'`IWarningCallback` interfaccia. Questa classe catturerà e registrerà tutti gli avvisi di sostituzione dei font.

```csharp
public class DocumentSubstitutionWarnings : IWarningCallback
{
    public void Warning(WarningInfo info)
    {
        if (info.WarningType == WarningType.FontSubstitution)
            FontWarnings.Warning(info);
    }

    public WarningInfoCollection FontWarnings = new WarningInfoCollection();
}
```

In questa classe:
- IL`Warning`Il metodo cattura gli avvisi relativi alla sostituzione dei font.
- IL`FontWarnings` la raccolta memorizza questi avvisi per ulteriori controlli o registrazioni.

## Conclusione

Ora hai padroneggiato il processo di gestione della sostituzione dei font senza suffissi usando Aspose.Words per .NET. Questa conoscenza garantirà che i tuoi documenti mantengano l'aspetto desiderato, indipendentemente dai font disponibili sul sistema. Continua a sperimentare con diverse impostazioni e fonti per sfruttare appieno la potenza di Aspose.Words.

## Domande frequenti

### Come posso utilizzare i font da più directory personalizzate?

 Puoi aggiungerne più di uno`FolderFontSource` istanze al`fontSources` elencare e aggiornare di conseguenza le fonti dei font.

### Dove posso scaricare una versione di prova gratuita di Aspose.Words per .NET?

 Puoi scaricare una versione di prova gratuita da[Pagina di prova gratuita di Aspose](https://releases.aspose.com/).

###  Posso gestire più tipi di avvisi utilizzando`IWarningCallback`?

 Sì, il`IWarningCallback` L'interfaccia consente di gestire vari tipi di avvisi, non solo la sostituzione dei font.

### Dove posso ottenere supporto per Aspose.Words?

 Per supporto, visita il[Forum di supporto di Aspose.Words](https://forum.aspose.com/c/words/8).

### È possibile acquistare una licenza temporanea?

 Sì, puoi ottenere una licenza temporanea dall'[pagina della licenza temporanea](https://purchase.aspose.com/temporary-license/).