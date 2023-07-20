---
title: Protezione di sola lettura nel documento di Word
linktitle: Protezione di sola lettura nel documento di Word
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come proteggere i tuoi documenti di sola lettura in Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/document-protection/read-only-protection/
---
In questo tutorial, ti guideremo attraverso i passaggi per utilizzare la funzione di protezione di sola lettura di Aspose.Words per .NET. Questa funzione consente di rendere un documento Word di sola lettura per impedire modifiche non autorizzate. Segui i passaggi seguenti:

## Passaggio 1: creazione del documento e applicazione della protezione

Inizia creando un'istanza della classe Document e un oggetto DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: scrivere il contenuto del documento
Utilizzare l'oggetto DocumentBuilder per scrivere contenuto nel documento:

```csharp
builder.Write("Open document as read-only");
```

## Passaggio 3: impostare la password e rendere il documento di sola lettura

Impostare una password per il documento utilizzando la proprietà SetPassword() dell'oggetto WriteProtection:

```csharp
doc.WriteProtection.SetPassword("MyPassword");
```

Assicurati di sostituire "MyPassword" con la password effettiva che desideri utilizzare.

## Passaggio 4: applicare il documento di sola lettura

Rendi il documento di sola lettura impostando la proprietà ReadOnlyRecommended su true:

```csharp
doc.WriteProtection.ReadOnlyRecommended = true;
```

## Passaggio 5: applicare la protezione di sola lettura e salvare il documento

Infine, applica la protezione in sola lettura utilizzando il metodo Protect() dell'oggetto Document:

```csharp
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");
```

Assicurarsi di specificare il percorso e il nome file corretti per salvare il documento protetto.

### Esempio di codice sorgente per Read Only Protection utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per la protezione in sola lettura utilizzando Aspose.Words per .NET:

```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Open document as read-only");

// Inserisci una password di massimo 15 caratteri.
doc.WriteProtection.SetPassword("MyPassword");

// Rendere il documento di sola lettura.
doc.WriteProtection.ReadOnlyRecommended = true;

// Applica la protezione da scrittura in sola lettura.
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");

```

Seguendo questi passaggi, puoi proteggere facilmente i tuoi documenti

## Conclusione

In questo tutorial, abbiamo esplorato la funzione di protezione di sola lettura di Aspose.Words per .NET, che consente di rendere i documenti di Word di sola lettura per impedire modifiche non autorizzate. Seguendo i passaggi forniti, puoi facilmente applicare la protezione di sola lettura ai tuoi documenti e migliorarne la sicurezza. La protezione di sola lettura aiuta a garantire l'integrità e l'accuratezza del contenuto del documento limitando le capacità di modifica. Aspose.Words per .NET fornisce un'API potente e flessibile per gestire la protezione dei documenti e supporta varie altre funzionalità per personalizzare e proteggere i tuoi documenti Word.

### Domande frequenti sulla protezione di sola lettura nel documento di Word

#### D: Cos'è la protezione di sola lettura in Aspose.Words per .NET?

R: La protezione di sola lettura in Aspose.Words per .NET è una funzionalità che consente di rendere un documento Word di sola lettura, impedendo modifiche non autorizzate. Quando un documento è impostato per la sola lettura, gli utenti possono aprire e visualizzare il documento, ma non possono apportare modifiche al suo contenuto.

#### D: Come posso applicare la protezione di sola lettura a un documento di Word utilizzando Aspose.Words per .NET?

R: Per applicare la protezione di sola lettura a un documento Word utilizzando Aspose.Words per .NET, puoi seguire questi passaggi:
1.  Crea un'istanza di`Document` classe e a`DocumentBuilder` oggetto.
2.  Usa il`DocumentBuilder` per scrivere il contenuto del documento.
3.  Impostare una password per il documento utilizzando il file`SetPassword` metodo del`WriteProtection` oggetto.
4.  Impostare il`ReadOnlyRecommended` proprietà del`WriteProtection` opporsi a`true` per consigliare di aprire il documento in sola lettura.
5.  Applicare la protezione di sola lettura utilizzando il`Protect` metodo del`Document` oggetto, specificando l'`ProtectionType` COME`ReadOnly`.
6.  Salvare il documento protetto utilizzando il file`Save` metodo del`Document` oggetto.

#### D: Posso rimuovere la protezione di sola lettura da un documento Word utilizzando Aspose.Words per .NET?

R: Sì, puoi rimuovere la protezione di sola lettura da un documento Word utilizzando Aspose.Words per .NET. Per fare questo, puoi usare il`Unprotect` metodo del`Document` class, che rimuove qualsiasi protezione esistente dal documento.

#### D: Posso impostare una password diversa per la protezione di sola lettura in un documento di Word?

 R: No, la protezione di sola lettura in Aspose.Words per .NET non consente di impostare una password separata specificatamente per la protezione di sola lettura. La password impostata utilizzando il`SetPassword` metodo del`WriteProtection` object si applica alla protezione complessiva del documento, inclusa la protezione sia in sola lettura che in lettura-scrittura.

#### D: Gli utenti possono ignorare la protezione di sola lettura in un documento di Word?

R: La protezione di sola lettura in un documento Word ha lo scopo di scoraggiare e impedire modifiche accidentali o non autorizzate. Sebbene fornisca un livello di protezione, può essere aggirato dagli utenti con conoscenze tecniche sufficienti o autorizzazioni di modifica. Tuttavia, la protezione di sola lettura funge da deterrente e aiuta a mantenere l'integrità del documento.