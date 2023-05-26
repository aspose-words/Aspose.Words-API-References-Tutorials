---
title: Inserisci Oggetto Ole Come Icona
linktitle: Inserisci Oggetto Ole Come Icona
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come inserire un oggetto OLE come icona con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon/
---

Ecco una guida passo passo per spiegare il codice sorgente C# di seguito che illustra come inserire un oggetto OLE come icona utilizzando Aspose.Words per .NET.

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

## Passaggio 3: inserire un oggetto OLE come icona
 Usa il Document Builder`InsertOleObjectAsIcon` metodo per inserire un oggetto OLE come icona nel documento. Specificare il percorso del file OLE, il flag di visualizzazione, il percorso dell'icona e il nome dell'oggetto incorporato.

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

## Passaggio 4: salvare il documento
 Usa il documento`Save` metodo per salvare il documento in un file.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

### Esempio di codice sorgente per l'inserimento di un oggetto OLE come icona con Aspose.Words per .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

Questo è un esempio di codice completo per l'inserimento di un oggetto OLE come icona con Aspose.Words per .NET. Assicurati di importare i riferimenti necessari e segui i passaggi precedentemente descritti per integrare questo codice nel tuo progetto.
