---
title: Protezione della password
linktitle: Protezione della password
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come proteggere con password i tuoi documenti Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/document-protection/password-protection/
---

In questo tutorial, ti guideremo attraverso i passaggi per utilizzare la funzione di protezione tramite password di Aspose.Words per .NET. Questa funzione consente di proteggere un documento Word con una password per garantirne la riservatezza. Segui i passaggi seguenti:

## Passaggio 1: creazione del documento e applicazione della protezione

Inizia creando un'istanza della classe Document:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## Passaggio 2: applicare la protezione tramite password

Quindi puoi applicare la protezione tramite password utilizzando il metodo Protect() dell'oggetto Document:

```csharp
doc.Protect(ProtectionType.NoProtection, "password");
```

Assicurati di sostituire "password" con la password effettiva che desideri utilizzare per proteggere il documento.

## Passaggio 3: salvare il documento protetto

Infine, puoi salvare il documento protetto utilizzando il metodo Save() dell'oggetto Document:

```csharp
doc.Save(dataDir + "DocumentProtection.PasswordProtection.docx");
```

Assicurarsi di specificare il percorso e il nome file corretti per salvare il documento protetto.

### Codice sorgente di esempio per la protezione con password utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per la protezione con password utilizzando Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();

	//Applicare la protezione del documento.
	doc.Protect(ProtectionType.NoProtection, "password");

	doc.Save(dataDir + "DocumentProtection.PasswordProtection.docx");

```

Ricordati di sostituire "RUBRICA DEI TUOI DOCUMENTI" con la directory dei tuoi documenti e "password" con la password effettiva che desideri utilizzare.

