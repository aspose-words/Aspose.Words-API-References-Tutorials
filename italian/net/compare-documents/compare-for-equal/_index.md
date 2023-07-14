---
title: Confronta per uguale
linktitle: Confronta per uguale
second_title: Aspose.Words API di elaborazione dei documenti
description: Guida dettagliata per spiegare il codice sorgente C# della funzione Compare for Equals con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/compare-documents/compare-for-equal/
---

In questo tutorial, ti illustreremo come utilizzare la funzione Compare for Equal con Aspose.Words per .NET. Segui i passaggi seguenti per comprendere il codice sorgente e applicare le modifiche.

## Passaggio 1: confronto dei documenti

 Per iniziare, carica due documenti da confrontare. In questo esempio, useremo il`Clone()` metodo per creare una copia del documento originale. Ecco come:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document docA = new Document(dataDir + "Document.docx");
Document docB = docA.Clone();
```

## Passaggio 2: confronto dei documenti

 Useremo ora il`Compare()` metodo per confrontare i due documenti. Questo metodo segnerà le modifiche nel documento originale. Ecco come:

```csharp
// Confronta i documenti
docA.Compare(docB, "user", DateTime.Now);

// Controlla se i documenti sono uguali
Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are identical": "Documents are not identical");
```

### Esempio di codice sorgente per Compare For Equal utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per la funzione Compare for Equals con Aspose.Words per .NET:

```csharp

	Document docA = new Document(MyDir + "Document.docx");
	Document docB = docA.Clone();
	
	// DocA ora contiene le modifiche come revisioni.
	docA.Compare(docB, "user", DateTime.Now);

	Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal" : "Documents are not equal");

```

Con questo codice, sarai in grado di confrontare due documenti e determinare se sono uguali utilizzando Aspose.Words per .NET.

