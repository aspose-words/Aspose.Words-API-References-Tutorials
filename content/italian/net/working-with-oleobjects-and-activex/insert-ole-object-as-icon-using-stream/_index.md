---
title: Inserisci oggetto Ole come icona utilizzando Stream
linktitle: Inserisci oggetto Ole come icona utilizzando Stream
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come inserire un oggetto OLE come icona utilizzando un flusso con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon-using-stream/
---

Ecco una guida passo passo per spiegare il codice sorgente C# di seguito che illustra come inserire un oggetto OLE come icona utilizzando un flusso con Aspose.Words per .NET.

## Passaggio 1: importa i riferimenti necessari
Prima di iniziare, assicurati di aver importato i riferimenti necessari per utilizzare Aspose.Words per .NET nel tuo progetto. Ciò include l'importazione della libreria Aspose.Words e l'aggiunta degli spazi dei nomi richiesti al file di origine.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

## Passaggio 2: crea un nuovo documento e un generatore di documenti
 In questo passaggio, creeremo un nuovo documento utilizzando il file`Document` classe e un generatore di documenti che utilizza il file`DocumentBuilder` classe.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 3: inserire un oggetto OLE come icona da un flusso
 Utilizza il Generatore di documenti`InsertOleObjectAsIcon` metodo per inserire un oggetto OLE come icona da un flusso nel documento. Specificare il flusso di dati, il tipo di oggetto, il percorso dell'icona e il nome dell'oggetto incorporato.

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

## Passaggio 4: salva il documento
 Usa quello del documento`Save` metodo per salvare il documento in un file.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

### Esempio di codice sorgente per l'inserimento di un oggetto OLE come icona utilizzando un flusso con Aspose.Words per .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

Questo è un esempio di codice completo per l'inserimento di un oggetto OLE come icona utilizzando un flusso con Aspose.Words per .NET. Assicurati di importare i riferimenti necessari e segui i passaggi precedentemente descritti per integrare questo codice nel tuo progetto.

## Conclusione

La guida passo passo sopra spiega come inserire un oggetto OLE come icona in un documento Word utilizzando un flusso con Aspose.Words per .NET. Seguendo i passaggi descritti, sarai in grado di integrare questa funzionalità nel tuo progetto. Assicurati di importare i riferimenti necessari, crea un nuovo documento e un generatore di documenti, inserisci l'oggetto OLE come icona dallo stream, quindi salva il documento. Utilizza il codice di esempio fornito come punto di partenza e personalizzalo in base alle tue esigenze.

### Domande frequenti

#### D. Come importare i riferimenti necessari per utilizzare Aspose.Words per .NET?

A. Per importare i riferimenti necessari, è necessario seguire questi passaggi:

 Aggiungere quanto segue`using` istruzioni nella parte superiore del file sorgente:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```
Assicurati di aver aggiunto la libreria Aspose.Words al tuo progetto.

#### D. Come creare un nuovo documento e un generatore di documenti utilizzando Aspose.Words per .NET?

A. Per creare un nuovo documento e un generatore di documenti, puoi seguire questi passaggi:

 Usa il`Document` classe per creare un nuovo documento:

```csharp
Document doc = new Document();
```
 Usa il`DocumentBuilder`classe per creare un generatore di documenti associato al documento creato in precedenza:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### D. Come inserire un oggetto OLE come icona da un flusso utilizzando Aspose.Words per .NET?

A. Per inserire un oggetto OLE come icona da uno stream, puoi seguire questi passaggi:

 Usa il`InsertOleObjectAsIcon` metodo del generatore di documenti per inserire l'oggetto OLE:

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
  builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

#### D. Come salvare il documento in un file?

A.  Per salvare il documento in un file, è possibile utilizzare il file`Save` metodo del documento specificando il percorso di destinazione:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

#### D. Come incorporo il codice per inserire un oggetto OLE come icona da un flusso nel mio progetto?

A. Per incorporare il codice per inserire un oggetto OLE come icona da uno stream nel tuo progetto, procedi nel seguente modo:
-  Importa i riferimenti necessari aggiungendo quelli appropriati`using` dichiarazioni.
-  Crea un nuovo documento e un generatore di documenti utilizzando il file`Document`E`DocumentBuilder` classi.
- Utilizzare il codice per inserire l'oggetto OLE come icona da un flusso.
-  Salvare il documento utilizzando il file`Save` metodo con il percorso di destinazione appropriato.

Seguendo questi passaggi, sarai in grado di inserire correttamente un oggetto OLE come icona da un flusso utilizzando Aspose.Words per .NET. Assicurati di seguire le istruzioni e importare i riferimenti necessari per ottenere i risultati desiderati.