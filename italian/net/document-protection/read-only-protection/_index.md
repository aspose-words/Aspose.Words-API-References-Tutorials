---
title: Protezione di sola lettura
linktitle: Protezione di sola lettura
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come proteggere i tuoi documenti Word di sola lettura con Aspose.Words per .NET.
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

