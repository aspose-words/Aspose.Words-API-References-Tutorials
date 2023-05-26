---
title: Inserisci oggetto Ole con pacchetto Ole
linktitle: Inserisci oggetto Ole con pacchetto Ole
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come inserire un oggetto OLE con un pacchetto OLE in un documento utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---

Ecco una guida dettagliata per spiegare il codice sorgente C# di seguito che illustra come inserire un oggetto OLE con un pacchetto OLE utilizzando Aspose.Words per .NET.

## Passaggio 1: importare i riferimenti necessari
Prima di iniziare, assicurati di aver importato i riferimenti necessari per utilizzare Aspose.Words per .NET nel tuo progetto. Ciò include l'importazione della libreria Aspose.Words e l'aggiunta degli spazi dei nomi richiesti al file di origine.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

## Passaggio 2: creare un nuovo documento e un generatore di documenti
 In questo passaggio, creeremo un nuovo documento utilizzando il file`Document` class e un generatore di documenti che utilizza il`DocumentBuilder` classe.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 3: inserire un oggetto OLE con un pacchetto OLE
 Usa il generatore di documenti`InsertOleObject` metodo per inserire un oggetto OLE con un pacchetto OLE nel documento. Specificare il flusso di dati, il tipo di oggetto, le opzioni di visualizzazione e altre impostazioni necessarie.

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}
```

## Passaggio 4: salvare il documento
 Usa il documento`Save` metodo per salvare il documento in un file.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

### Esempio di codice sorgente per l'inserimento di un oggetto OLE con un pacchetto OLE con Aspose.Words per .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

Questo è un esempio di codice completo per l'inserimento di un oggetto OLE con un pacchetto OLE con Aspose.Words per .NET. Assicurati di importare i riferimenti necessari e segui i passaggi precedentemente descritti per integrare questo codice nel tuo progetto.