---
title: Sezione illimitata
linktitle: Sezione illimitata
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come definire sezioni senza restrizioni in un documento di Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/document-protection/unrestricted-section/
---

In questo tutorial, ti guideremo attraverso i passaggi per utilizzare la funzionalità di sezione illimitata di Aspose.Words per .NET. Questa funzione consente di definire sezioni specifiche in un documento Word che non sono protette, anche se il resto del documento è protetto. Segui i passaggi seguenti:

## Passaggio 1: creazione del documento e delle sezioni

Inizia creando un'istanza della classe Document e un oggetto DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: aggiungere contenuto al documento
Utilizzare l'oggetto DocumentBuilder per aggiungere contenuto al documento e inserire interruzioni di sezione:

```csharp
builder.Writeln("Section 1. Unprotected.");
builder. InsertBreak(BreakType. SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");
```

## Passaggio 3: proteggere il documento e le sezioni

La protezione della sezione funziona solo quando la protezione del documento è abilitata ed è consentita solo la modifica nei campi del modulo. È possibile proteggere il documento utilizzando il metodo Protect() dell'oggetto Document:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Assicurarsi di specificare il tipo corretto di protezione e impostare la password desiderata.

## Passaggio 4: disabilitazione della protezione per una sezione specifica

Per impostazione predefinita, tutte le sezioni sono protette, ma è possibile disabilitare in modo selettivo la protezione per una sezione specifica utilizzando la proprietà ProtectedForForms dell'oggetto Section:

```csharp
doc.Sections[0].ProtectedForForms = false;
```

In questo esempio, la protezione è disabilitata per la prima sezione.

## Passaggio 5: salvare il documento

Infine, salva il documento modificato:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");
```

Assicurati di specificare il percorso e il nome file corretti per salvare il documento con sezioni senza restrizioni.

### Esempio di codice sorgente per sezione senza restrizioni utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per la sezione senza restrizioni utilizzando Aspose.Words per .NET:


```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Inserisci due sezioni con del testo.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Section 1. Unprotected.");
builder.InsertBreak(BreakType.SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");

// La protezione della sezione funziona solo quando la protezione del documento è attivata ed è consentita solo la modifica nei campi del modulo.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

// Per impostazione predefinita, tutte le sezioni sono protette, ma possiamo disattivare la protezione in modo selettivo.
doc.Sections[0].ProtectedForForms = false;
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");

doc = new Document(dataDir + "DocumentProtection.UnrestrictedSection.docx");

```

Seguendo questi passaggi, sarai in grado di definire facilmente sezioni senza restrizioni nel tuo documento Word con Aspose.Words per .NET.

