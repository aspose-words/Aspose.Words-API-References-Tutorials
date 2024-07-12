---
title: Mantieni la numerazione delle fonti
linktitle: Mantieni la numerazione delle fonti
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come importare documenti preservando la formattazione utilizzando Aspose.Words per .NET. Guida passo passo con esempi di codice.
type: docs
weight: 10
url: /it/net/join-and-append-documents/keep-source-numbering/
---
## introduzione

 Quando si lavora con Aspose.Words per .NET, l'importazione di documenti da una fonte a un'altra preservando la formattazione può essere gestita in modo efficiente utilizzando`NodeImporter` classe. Questo tutorial ti guiderà attraverso il processo passo dopo passo.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:
- Visual Studio installato sul tuo computer.
-  Aspose.Words per .NET installato. In caso contrario, scaricalo da[Qui](https://releases.aspose.com/words/net/).
- Conoscenza base di programmazione C# e .NET.

## Importa spazi dei nomi

Innanzitutto, includi gli spazi dei nomi necessari nel tuo progetto:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Tables;
```

## Passaggio 1: imposta il tuo progetto

Inizia creando un nuovo progetto C# in Visual Studio e installa Aspose.Words tramite NuGet Package Manager.

## Passaggio 2: inizializzare i documenti
Creare istanze dell'origine (`srcDoc`) e destinazione (`dstDoc`) documenti.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Passaggio 3: configura le opzioni di importazione
Configura le opzioni di importazione per mantenere la formattazione originale, inclusi i paragrafi numerati.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
	importFormatOptions);
```

## Passaggio 4: importa paragrafi
Scorri i paragrafi nel documento di origine e importali nel documento di destinazione.

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## Passaggio 5: salva il documento
Salva il documento unito nella posizione desiderata.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

## Conclusione

 In conclusione, utilizzare Aspose.Words per .NET per importare documenti preservando la formattazione è semplice con il file`NodeImporter` classe. Questo metodo garantisce che i tuoi documenti mantengano perfettamente l'aspetto e la struttura originali.

## Domande frequenti

### Posso importare documenti con stili di formattazione diversi?
 Sì, il`NodeImporter` La classe supporta l'importazione di documenti con vari stili di formattazione.

### Cosa succede se i miei documenti contengono tabelle e immagini complesse?
Aspose.Words per .NET gestisce strutture complesse come tabelle e immagini durante le operazioni di importazione.

### Aspose.Words è compatibile con tutte le versioni di .NET?
Aspose.Words supporta le versioni .NET Framework e .NET Core per una perfetta integrazione.

### Come posso gestire gli errori durante l'importazione dei documenti?
Utilizza i blocchi try-catch per gestire le eccezioni che possono verificarsi durante il processo di importazione.

### Dove posso trovare una documentazione più dettagliata su Aspose.Words per .NET?
 Visitare il[documentazione](https://reference.aspose.com/words/net/) per guide complete e riferimenti API.
