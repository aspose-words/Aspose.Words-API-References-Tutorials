---
title: Consenti solo protezione campi modulo
linktitle: Consenti solo protezione campi modulo
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come utilizzare Aspose.Words per .NET per proteggere i documenti e consentire solo la modifica dei campi del modulo.
type: docs
weight: 10
url: /it/net/document-protection/allow-only-form-fields-protect/
---

La protezione dei documenti è una funzionalità essenziale quando si lavora con i file all'interno dell'applicazione C#. Con la libreria Aspose.Words per .NET, puoi proteggere facilmente i tuoi documenti e consentire solo la modifica dei campi del modulo. In questa guida dettagliata, ti illustreremo come utilizzare il codice sorgente C# per consentire solo la modifica dei campi del modulo utilizzando la funzione Consenti solo protezione dei campi del modulo di Aspose.Words per .NET.

## Passaggio 1: impostazione della directory dei documenti

Il primo passo è definire la directory del tuo documento. È necessario specificare il percorso in cui si desidera salvare il documento protetto. Per esempio :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Assicurati di sostituire "LA TUA DIRECTORY DEI DOCUMENTI" con il percorso effettivo della tua directory dei documenti.

## Passaggio 2: Inserimento di sezioni e testo

Successivamente, è necessario inserire sezioni e testo nel documento. Usa la classe DocumentBuilder fornita da Aspose.Words per costruire il contenuto del tuo documento. Qui c'è un semplice esempio:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

In questo esempio, creiamo un nuovo documento vuoto e quindi utilizziamo DocumentBuilder per aggiungere una riga di testo.

## Passaggio 3: abilitazione della protezione dei documenti

 La protezione dei documenti funziona solo quando la protezione dei documenti è abilitata. È possibile abilitare la protezione dei documenti utilizzando il file`Protect` metodo della classe Document. Ecco come:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

In questo esempio, abilitiamo la protezione del documento specificando il tipo di protezione `

AllowOnlyFormFields` e impostando una password.

## Passaggio 4: consentire solo i campi del modulo

Ora che la protezione del documento è abilitata, dobbiamo specificare che è consentita solo la modifica dei campi del modulo. Ciò garantisce che gli utenti possano modificare solo parti del documento che sono campi modulo. Ecco come:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Assicurati di sostituire "password" con la password che hai impostato in precedenza.

## Passaggio 5: salvare il documento protetto

Infine, puoi salvare il documento protetto utilizzando il file`Save` metodo della classe Document. Specificare il percorso file completo e il nome file desiderato. Per esempio :

```csharp
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

Assicurati di sostituire "dataDir" con il percorso della directory dei documenti.

### Codice sorgente di esempio per la funzione Consenti solo protezione campi modulo utilizzando Aspose.Words per .NET

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Inserisci due sezioni con del testo.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

// Una protezione del documento funziona solo quando la protezione del documento è attivata ed è consentita solo la modifica nei campi del modulo.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

// Salva il documento protetto.
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

## Conclusione

In questa guida, abbiamo esplorato come utilizzare la libreria Aspose.Words per .NET per proteggere un documento e consentire solo la modifica dei campi del modulo. Seguendo i passaggi forniti, puoi facilmente implementare questa funzionalità nella tua applicazione C#. La protezione dei documenti è essenziale per garantire la sicurezza e la riservatezza dei tuoi documenti.
