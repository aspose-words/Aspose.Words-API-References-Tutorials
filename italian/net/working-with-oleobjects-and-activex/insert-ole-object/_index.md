---
title: Inserisci Oggetto Ole
linktitle: Inserisci Oggetto Ole
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come inserire un oggetto OLE in un documento utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-oleobjects-and-activex/insert-ole-object/
---

Ecco una guida passo passo per spiegare il codice sorgente C# di seguito che illustra come inserire un oggetto OLE utilizzando Aspose.Words per .NET.

## Passaggio 1: importare i riferimenti necessari
Prima di iniziare, assicurati di aver importato i riferimenti necessari per utilizzare Aspose.Words per .NET nel tuo progetto. Ciò include l'importazione della libreria Aspose.Words e l'aggiunta degli spazi dei nomi richiesti al file di origine.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Passaggio 2: creare un nuovo documento e un generatore di documenti
 In questo passaggio, creeremo un nuovo documento utilizzando il file`Document` class e un generatore di documenti che utilizza il`DocumentBuilder` classe.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 3: inserire un oggetto OLE
 Usa il Document Builder`InsertOleObject` metodo per inserire un oggetto OLE nel documento. Specificare l'URL dell'oggetto OLE, il tipo di oggetto, le opzioni di visualizzazione e altre impostazioni necessarie.

```csharp
builder. InsertOleObject("http://www.aspose.com", "htmlfile", true, true, null);
```

## Passaggio 4: salvare il documento
 Usa il documento`Save` metodo per salvare il documento in un file.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

### Esempio di codice sorgente per l'inserimento di un oggetto OLE con Aspose.Words per .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com", "htmlfile", true, true, null);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

Questo è un esempio di codice completo per l'inserimento di un oggetto OLE con Aspose.Words per .NET. Assicurati di importare i riferimenti necessari e segui i passaggi precedentemente descritti per integrare questo codice nel tuo progetto.
