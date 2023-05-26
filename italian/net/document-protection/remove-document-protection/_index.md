---
title: Rimuovi la protezione del documento
linktitle: Rimuovi la protezione del documento
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come rimuovere la protezione da un documento di Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/document-protection/remove-document-protection/
---

In questo tutorial, ti guideremo attraverso i passaggi per utilizzare la funzionalità di rimozione della protezione del documento di Aspose.Words per .NET. Questa funzione consente di rimuovere la protezione da un documento di Word per renderlo accessibile per ulteriori modifiche. Segui i passaggi seguenti:

## Passaggio 1: creazione del documento e aggiunta di contenuto

Inizia creando un'istanza della classe Document e un oggetto DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: aggiungere contenuto al documento

Utilizzare l'oggetto DocumentBuilder per aggiungere contenuto al documento:

```csharp
builder.Writeln("Text added to a document.");
```

## Passaggio 3: rimuovere la protezione del documento

Per rimuovere la protezione del documento, è possibile utilizzare il metodo Unprotect() dell'oggetto Document. Puoi scegliere di rimuovere la protezione senza password o con password corretta. Rimozione della protezione senza password:

```csharp
doc.Unprotect();
doc.Protect(ProtectionType.ReadOnly, "newPassword");
doc.Unprotect("newPassword");
```

Assicurati di sostituire "nuovapassword" con la password del documento corretta.

## Passaggio 4: salvare il documento senza protezione

Infine, salva il documento non protetto utilizzando il metodo Save() dell'oggetto Document:

```csharp
doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");
```

Assicurati di specificare il percorso e il nome file corretti per salvare il documento non protetto.

### Codice sorgente di esempio per rimuovere la protezione dei documenti utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per rimuovere la protezione del documento utilizzando Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("Text added to a document.");

	// È possibile rimuovere la protezione dei documenti senza password o con la password corretta.
	doc.Unprotect();
	doc.Protect(ProtectionType.ReadOnly, "newPassword");
	doc.Unprotect("newPassword");

	doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");

```

Seguendo questi passaggi, puoi rimuovere facilmente la protezione dal documento di Word con Aspose.Words per .NET.
