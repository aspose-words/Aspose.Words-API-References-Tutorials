---
title: Rimuovi la restrizione di sola lettura
linktitle: Rimuovi la restrizione di sola lettura
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come rimuovere la restrizione di sola lettura da un documento di Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/document-protection/remove-read-only-restriction/
---
In questo tutorial, ti guideremo attraverso i passaggi per utilizzare Aspose.Words per la funzionalità di rimozione delle restrizioni di sola lettura .NET. Questa funzione consente di rimuovere la restrizione di sola lettura da un documento di Word per renderlo modificabile. Segui i passaggi seguenti:

## Passaggio 1: creazione del documento e impostazione della protezione

Inizia creando un'istanza della classe Document:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
doc.WriteProtection.SetPassword("MyPassword");
```

Impostare una password per il documento utilizzando la proprietà SetPassword() dell'oggetto WriteProtection:

Assicurati di sostituire "MyPassword" con la password effettiva che hai utilizzato per proteggere il documento.

## Passaggio 2: rimuovere la restrizione di sola lettura

Per rimuovere la restrizione di sola lettura, imposta la proprietà ReadOnlyRecommended su false:

```csharp
doc.WriteProtection.ReadOnlyRecommended = false;
```

## Passaggio 3: applica la protezione illimitata

Infine, applica la protezione illimitata utilizzando il metodo Protect() dell'oggetto Document:

```csharp
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

Assicurati di specificare il percorso e il nome file corretti per salvare il documento senza la restrizione di sola lettura.

### Codice sorgente di esempio per rimuovere la restrizione di sola lettura utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per rimuovere la restrizione di sola lettura utilizzando Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	
	// Inserisci una password di massimo 15 caratteri.
	doc.WriteProtection.SetPassword("MyPassword");

	// Rimuovi l'opzione di sola lettura.
	doc.WriteProtection.ReadOnlyRecommended = false;

	// Applicare la protezione da scrittura senza alcuna protezione.
	doc.Protect(ProtectionType.NoProtection);
	doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");

```

Seguendo questi passaggi, puoi rimuovere facilmente la restrizione di sola lettura da un documento di Word con Aspose.Words per .NET.

