---
title: Per Sezioni
linktitle: Per Sezioni
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come dividere un documento di Word in sezioni separate utilizzando Aspose.Words per .NET con un esempio di codice completo.
type: docs
weight: 10
url: /it/net/split-document/by-sections/
---

In questo esempio, ti mostreremo come dividere un documento Word in sezioni separate utilizzando la funzione Per sezioni di Aspose.Words per .NET. Segui i passaggi seguenti per comprendere il codice sorgente e ottenere documenti separati per ogni sezione.

## Passaggio 1: caricamento del documento

Per iniziare, dobbiamo specificare la directory del tuo documento e caricare il documento in un oggetto Document. Ecco come:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Large document.docx");
```

## Passaggio 2: dividere il documento in sezioni

Ora ripeteremo ogni sezione del documento e suddivideremo il documento in parti più piccole, sezione per sezione. Ecco come farlo:

```csharp
for (int i = 0; i < doc. Sections. Count; i++)
{
// Dividi il documento in parti più piccole, in questo caso, separandolo per sezione.
Section section = doc.Sections[i].Clone();

Document newDoc = new Document();
newDoc.Sections.Clear();

Section newSection = (Section) newDoc.ImportNode(section, true);
newDoc.Sections.Add(newSection);

// Salva ogni sezione come documento separato.
newDoc.Save(dataDir + $"SplitDocument.ParSections_{i}.docx");
}
```

### Esempio di codice sorgente per Sezioni utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per la funzione By Sections di Aspose.Words per .NET:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Big document.docx");

for (int i = 0; i < doc.Sections.Count; i++)
{
	// Dividi un documento in parti più piccole, in questo caso, diviso per sezione.
	Section section = doc.Sections[i].Clone();

	Document newDoc = new Document();
	newDoc.Sections.Clear();

	Section newSection = (Section) newDoc.ImportNode(section, true);
	newDoc.Sections.Add(newSection);

	// Salva ogni sezione come documento separato.
	newDoc.Save(dataDir + $"SplitDocument.BySections_{i}.docx");
}
```

Con questo codice sarai in grado di dividere un documento Word in sezioni separate usando Aspose.Words per .NET.

Ora puoi facilmente lavorare con sezioni specifiche.

