---
title: Mantieni la formattazione dell'origine
linktitle: Mantieni la formattazione dell'origine
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come unire documenti Word preservando la formattazione utilizzando Aspose.Words per .NET. Ideale per gli sviluppatori che desiderano automatizzare le attività di assemblaggio dei documenti.
type: docs
weight: 10
url: /it/net/join-and-append-documents/keep-source-formatting/
---
## Introduzione

In questo tutorial esploreremo come unire e aggiungere documenti Word utilizzando Aspose.Words per .NET. Questa potente libreria offre agli sviluppatori funzionalità estese per la manipolazione dei documenti Word a livello di codice. Ci concentreremo sul metodo per mantenere intatta la formattazione originale durante l'unione dei documenti, garantendo che gli stili e i layout originali vengano preservati senza problemi.

## Prerequisiti

Prima di immergerti nel tutorial, assicurati di aver impostato i seguenti prerequisiti:

- Ambiente di sviluppo: Visual Studio o qualsiasi IDE che supporti lo sviluppo .NET.
-  Aspose.Words per .NET Library: scarica e installa la libreria da[Qui](https://releases.aspose.com/words/net/).
- Conoscenza di base della programmazione C#: familiarità con la sintassi C# e i concetti di programmazione orientata agli oggetti.

## Importa spazi dei nomi

Inizia importando gli spazi dei nomi necessari nel tuo progetto C#:

```csharp
using Aspose.Words;
```

## Passaggio 1: imposta il tuo progetto

Creare una nuova applicazione console C# in Visual Studio e installare il pacchetto NuGet Aspose.Words. Questo pacchetto contiene le librerie necessarie per lavorare con i documenti Word nel tuo progetto.

## Passaggio 2: includere lo spazio dei nomi Aspose.Words

Assicurati di includere lo spazio dei nomi Aspose.Words all'inizio del file C# per accedere alle classi e ai metodi Aspose.Words.

## Passaggio 3: inizializzare i percorsi dei documenti

Definire il percorso della directory dei documenti in cui si trovano i documenti di origine e di destinazione.

```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY_PATH";
```

## Passaggio 4: crea il documento di destinazione

Inizializza una nuova istanza della classe Document per creare un documento di destinazione in cui verrà archiviato il contenuto unito.

```csharp
Document dstDoc = new Document();
```

## Passaggio 5: caricare il documento di origine

Allo stesso modo, crea un altro oggetto Document per caricare il documento di origine che desideri aggiungere al documento di destinazione.

```csharp
Document srcDoc = new Document();
```

## Passaggio 6: aggiungi il documento di origine mantenendo la formattazione

Per unire il documento di origine nel documento di destinazione preservandone la formattazione originale, utilizzare il metodo AppendDocument con ImportFormatMode impostato su KeepSourceFormatting.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Passaggio 7: salva il documento unito

Infine, salva il documento unito nella directory specificata utilizzando il metodo Save.

```csharp
dstDoc.Save(dataDir + "MergedDocument.docx");
```

## Conclusione

In questo tutorial, abbiamo spiegato come unire documenti Word mantenendo la formattazione originale utilizzando Aspose.Words per .NET. Questo approccio garantisce che gli stili, i caratteri e i layout dei documenti di origine siano perfettamente integrati nel documento di destinazione, fornendo una soluzione solida per le attività di assemblaggio dei documenti.

## Domande frequenti

### Posso unire più documenti in un'unica operazione utilizzando Aspose.Words per .NET?
Sì, puoi unire più documenti accodando in sequenza ciascun documento al documento di destinazione.

### Aspose.Words conserva tutti gli attributi di formattazione durante l'unione dei documenti?
Aspose.Words supporta varie modalità di importazione; la modalità KeepSourceFormatting garantisce che la maggior parte degli attributi di formattazione vengano mantenuti.

### Aspose.Words è compatibile con le applicazioni .NET Core?
Sì, Aspose.Words supporta .NET Core, consentendoti di utilizzarlo su diverse piattaforme.

### Come posso gestire documenti di grandi dimensioni in modo efficiente utilizzando Aspose.Words?
Aspose.Words fornisce API efficienti per lavorare con documenti di grandi dimensioni, comprese funzionalità per l'impaginazione e la gestione della memoria.

### Dove posso trovare ulteriori risorse e supporto per Aspose.Words?
 Visita il[Aspose.Words per la documentazione .NET](https://reference.aspose.com/words/net/) per riferimenti API dettagliati, esempi e guide.