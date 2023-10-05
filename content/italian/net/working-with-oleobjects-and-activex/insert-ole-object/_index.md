---
title: Inserisci oggetto Ole nel documento di Word
linktitle: Inserisci oggetto Ole nel documento di Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come inserire un oggetto OLE nel documento Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-oleobjects-and-activex/insert-ole-object/
---

Ecco una guida passo passo per spiegare il codice sorgente C# di seguito che illustra come inserire un oggetto OLE nel documento Word utilizzando Aspose.Words per .NET.

## Passaggio 1: importa i riferimenti necessari
Prima di iniziare, assicurati di aver importato i riferimenti necessari per utilizzare Aspose.Words per .NET nel tuo progetto. Ciò include l'importazione della libreria Aspose.Words e l'aggiunta degli spazi dei nomi richiesti al file di origine.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Passaggio 2: crea un nuovo documento e un generatore di documenti
 In questo passaggio, creeremo un nuovo documento utilizzando il file`Document` classe e un generatore di documenti che utilizza il file`DocumentBuilder` classe.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 3: inserire un oggetto OLE
 Utilizza il Generatore di documenti`InsertOleObject` metodo per inserire un oggetto OLE nel documento. Specificare l'URL dell'oggetto OLE, il tipo di oggetto, le opzioni di visualizzazione e altre impostazioni necessarie.

```csharp
builder. InsertOleObject("http://www.aspose.com", "htmlfile", vero, vero, null);
```

## Passaggio 4: salva il documento
 Usa quello del documento`Save` metodo per salvare il documento in un file.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

### Esempio di codice sorgente per l'inserimento di un oggetto OLE con Aspose.Words per .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com", "htmlfile", vero, vero, null);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

Questo è un esempio di codice completo per l'inserimento di un oggetto OLE con Aspose.Words per .NET. Assicurati di importare i riferimenti necessari e segui i passaggi precedentemente descritti per integrare questo codice nel tuo progetto.

## Conclusione

In conclusione, l'inserimento di oggetti OLE in un documento Word è una potente funzionalità offerta da Aspose.Words per .NET. Utilizzando questa libreria, puoi incorporare facilmente oggetti OLE come file HTML, fogli di calcolo Excel, presentazioni PowerPoint, ecc. nei tuoi documenti Word.

In questo articolo abbiamo seguito una guida passo passo per spiegare il codice sorgente in C# che illustra come inserire un oggetto OLE in un documento Word. Abbiamo trattato i riferimenti necessari, la creazione di un nuovo documento e un generatore di documenti e i passaggi per inserire un oggetto OLE e salvare il documento.

### Domande frequenti sull'inserimento di un oggetto OLE in un documento Word

#### D: Quali credenziali devo importare per utilizzare Aspose.Words per .NET?

R: Per utilizzare Aspose.Words per .NET, è necessario importare i seguenti riferimenti:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### D: Come creare un nuovo documento e un generatore di documenti?

 R: Puoi creare un nuovo documento utilizzando il file`Document` classe e un generatore di documenti che utilizza il file`DocumentBuilder` classe, come mostrato di seguito:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### D: Come inserire un oggetto OLE nel documento?

 R: Usa il`InsertOleObject`metodo del generatore di documenti (`DocumentBuilder`) per inserire un oggetto OLE nel documento. Specificare l'URL dell'oggetto OLE, il tipo di oggetto, le opzioni di visualizzazione e altre impostazioni necessarie. Ecco un esempio:

```csharp
builder. InsertOleObject("http://www.aspose.com", "htmlfile", vero, vero, null);
```

#### D: Come salvare il documento?

 R: Usa il documento`Save` metodo per salvare il documento in un file. Ecco un esempio:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

#### D: Puoi fornire un esempio completo di inserimento di un oggetto OLE con Aspose.Words per .NET?

R: Ecco un codice di esempio completo per inserire un oggetto OLE con Aspose.Words per .NET. Assicurati di importare i riferimenti necessari e segui i passaggi precedentemente descritti per integrare questo codice nel tuo progetto:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com", "htmlfile", vero, vero, null);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```
