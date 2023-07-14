---
title: Inserisci l'oggetto Ole in Word con il pacchetto Ole
linktitle: Inserisci l'oggetto Ole in Word con il pacchetto Ole
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come inserire un oggetto OLE con un pacchetto OLE in un documento utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---

Ecco una guida dettagliata per spiegare il codice sorgente C# di seguito che illustra come inserire un oggetto OLE in Word con un pacchetto OLE utilizzando Aspose.Words per .NET.

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
 Usa il generatore di documenti`InsertOleObject`metodo per inserire un oggetto OLE con un pacchetto OLE nel documento. Specificare il flusso di dati, il tipo di oggetto, le opzioni di visualizzazione e altre impostazioni necessarie.

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

## Conclusione

In conclusione, abbiamo seguito una guida passo passo per inserire un oggetto OLE in un documento Word con un pacchetto OLE utilizzando Aspose.Words per .NET.

Seguendo questi passaggi, sarai in grado di inserire correttamente oggetti OLE con pacchetti OLE nei tuoi documenti Word utilizzando Aspose.Words per .NET. Assicurati di importare i riferimenti necessari e segui attentamente le istruzioni per ottenere i risultati desiderati.

### Domande frequenti per inserire un oggetto ole in Word con un pacchetto ole

#### D: Quali credenziali devo importare per utilizzare Aspose.Words per .NET?

R: Per utilizzare Aspose.Words per .NET, è necessario importare i seguenti riferimenti:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

#### D: Come creare un nuovo documento e un generatore di documenti?

 R: Puoi creare un nuovo documento usando il file`Document` class e un generatore di documenti che utilizza il`DocumentBuilder` classe, come mostrato di seguito:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### D: Come inserire un oggetto OLE con un pacchetto OLE nel documento?

 R: Usa il`InsertOleObject` metodo del generatore di documenti (`DocumentBuilder`) per inserire un oggetto OLE con un pacchetto OLE nel documento. Specificare il flusso di dati, il tipo di oggetto, le opzioni di visualizzazione e altre impostazioni necessarie. Ecco un esempio:

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}
```

#### D: Come salvare il documento?

 R: Usa il documento`Save`metodo per salvare il documento in un file. Ecco un esempio:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

#### D: Puoi fornire un esempio completo di inserimento di un oggetto OLE con un pacchetto OLE con Aspose.Words per .NET?

A: Ecco un codice di esempio completo per inserire un oggetto OLE con un pacchetto OLE utilizzando Aspose.Words per .NET. Assicurati di importare i riferimenti necessari e segui i passaggi precedentemente descritti per integrare questo codice nel tuo progetto:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

Questo conclude il nostro tutorial sull'inserimento di un oggetto OLE con un pacchetto OLE in un documento Word utilizzando Aspose.Words per .NET. Sentiti libero di importare i riferimenti necessari e segui i passaggi descritti per integrare questo codice nel tuo progetto. Se hai ulteriori domande, non esitare a contattarci.