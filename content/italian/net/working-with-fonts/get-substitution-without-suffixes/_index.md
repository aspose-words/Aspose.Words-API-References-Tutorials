---
title: Ottieni la sostituzione senza suffissi
linktitle: Ottieni la sostituzione senza suffissi
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come gestire la sostituzione dei caratteri senza suffissi in Aspose.Words per .NET. Segui la nostra guida passo passo per assicurarti che i tuoi documenti siano sempre perfetti.
type: docs
weight: 10
url: /it/net/working-with-fonts/get-substitution-without-suffixes/
---

Benvenuti in questa guida completa sulla gestione della sostituzione dei caratteri utilizzando Aspose.Words per .NET. Se hai mai avuto problemi con i caratteri che non vengono visualizzati correttamente nei tuoi documenti, sei nel posto giusto. Questo tutorial ti guiderà attraverso un processo passo passo per gestire in modo efficiente la sostituzione dei caratteri senza suffissi. Iniziamo!

## Prerequisiti

Prima di immergerti nel tutorial, assicurati di avere quanto segue:

- Conoscenza di base di C#: comprendere la programmazione in C# renderà più semplice seguire e implementare i passaggi.
-  Aspose.Words per .NET Library: scarica e installa la libreria da[Link per scaricare](https://releases.aspose.com/words/net/).
- Ambiente di sviluppo: configura un ambiente di sviluppo come Visual Studio per scrivere ed eseguire il tuo codice.
-  Documento di esempio: un documento di esempio (ad es.`Rendering.docx`) con cui lavorare durante questo tutorial.

## Importa spazi dei nomi

Innanzitutto, dobbiamo importare gli spazi dei nomi necessari per accedere alle classi e ai metodi forniti da Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
using Aspose.Words.WarningInfo;
using System.Collections.Generic;
```

## Passaggio 1: definire la directory dei documenti

Per iniziare, specifica la directory in cui si trova il tuo documento. Questo aiuta a individuare il documento su cui vuoi lavorare.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: impostare il gestore degli avvisi di sostituzione

Successivamente, dobbiamo impostare un gestore di avvisi che ci avviserà ogni volta che si verifica una sostituzione di carattere durante l'elaborazione del documento. Questo è fondamentale per individuare e gestire eventuali problemi relativi ai caratteri.

```csharp
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
Document doc = new Document(dataDir + "Rendering.docx");
doc.WarningCallback = substitutionWarningHandler;
```

## Passaggio 3: aggiungi origini caratteri personalizzate

In questo passaggio, aggiungeremo fonti di caratteri personalizzate per garantire che Aspose.Words possa individuare e utilizzare i caratteri corretti. Ciò è particolarmente utile se hai caratteri specifici memorizzati in directory personalizzate.

```csharp
List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());

FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
```

In questo codice:
-  Recuperiamo le fonti dei caratteri correnti e ne aggiungiamo una nuova`FolderFontSource` puntando alla nostra directory di caratteri personalizzati (`C:\\MyFonts\\`).
- Aggiorniamo quindi le fonti dei caratteri con questo nuovo elenco.

## Passaggio 4: salva il documento

Infine, salva il documento dopo aver applicato le impostazioni di sostituzione dei caratteri. Per questo tutorial, lo salveremo come PDF.

```csharp
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");
```

## Passaggio 5: creare la classe del gestore degli avvisi

 Per gestire gli avvisi in modo efficace, crea una classe personalizzata che implementi il file`IWarningCallback` interfaccia. Questa classe acquisirà e registrerà eventuali avvisi di sostituzione dei caratteri.

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
-  IL`Warning` Il metodo acquisisce avvisi relativi alla sostituzione dei caratteri.
-  IL`FontWarnings` collection memorizza questi avvisi per ulteriori controlli o registrazioni.

## Conclusione

Ora hai imparato il processo di gestione della sostituzione dei caratteri senza suffissi utilizzando Aspose.Words per .NET. Questa conoscenza garantirà che i tuoi documenti mantengano l'aspetto previsto, indipendentemente dai caratteri disponibili nel sistema. Continua a sperimentare diverse impostazioni e fonti per sfruttare appieno la potenza di Aspose.Words.

## Domande frequenti

### Q1: Come posso utilizzare i caratteri da più directory personalizzate?

 Puoi aggiungerne più di uno`FolderFontSource` istanze al`fontSources`elencare e aggiornare le fonti dei caratteri di conseguenza.

### Q2: Dove posso scaricare una versione di prova gratuita di Aspose.Words per .NET?

 È possibile scaricare una versione di prova gratuita da[Aspose la pagina di prova gratuita](https://releases.aspose.com/).

###  Q3: Posso gestire più tipi di avvisi utilizzando`IWarningCallback`?

 Sì, il`IWarningCallback` l'interfaccia consente di gestire vari tipi di avvisi, non solo la sostituzione dei caratteri.

### Q4: Dove posso ottenere supporto per Aspose.Words?

 Per supporto, visitare il[Forum di supporto di Aspose.Words](https://forum.aspose.com/c/words/8).

### Q5: È possibile acquistare una licenza temporanea?

 Sì, puoi ottenere una licenza temporanea da[pagina della licenza temporanea](https://purchase.aspose.com/temporary-license/).