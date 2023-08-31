---
title: Consenti solo la protezione dei campi del modulo nel documento Word
linktitle: Consenti solo la protezione dei campi del modulo nel documento Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come utilizzare Aspose.Words per .NET per proteggere i documenti Word e consentire solo la modifica dei campi del modulo.
type: docs
weight: 10
url: /it/net/document-protection/allow-only-form-fields-protect/
---
La protezione dei documenti è una funzionalità essenziale durante l'elaborazione di testi con file all'interno dell'applicazione C#. Con la libreria Aspose.Words per .NET, puoi facilmente proteggere i tuoi documenti e consentire solo la modifica dei campi del modulo. In questa guida passo passo, ti spiegheremo come utilizzare il codice sorgente C# per consentire solo la modifica dei campi modulo utilizzando la funzionalità Consenti solo protezione campi modulo di Aspose.Words per .NET.

## Passaggio 1: impostazione della directory dei documenti

Il primo passo è definire la directory del documento. È necessario specificare il percorso in cui si desidera salvare il documento protetto. Per esempio :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Assicurati di sostituire "LA TUA DIRECTORY DOCUMENTI" con il percorso effettivo della directory dei documenti.

## Passaggio 2: inserimento di sezioni e testo

Successivamente, devi inserire sezioni e testo nel tuo documento. Utilizza la classe DocumentBuilder fornita da Aspose.Words per creare il contenuto del tuo documento. Qui c'è un semplice esempio:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

In questo esempio creiamo un nuovo documento vuoto e quindi utilizziamo DocumentBuilder per aggiungere una riga di testo.

## Passaggio 3: abilitazione della protezione dei documenti

 La protezione dei documenti funziona solo quando la protezione dei documenti è abilitata. È possibile abilitare la protezione dei documenti utilizzando il file`Protect` metodo della classe Document. Ecco come:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

In questo esempio, abilitiamo la protezione del documento specificando il tipo di protezione `

AllowOnlyFormFields` e impostando una password.

## Passaggio 4: consentire solo i campi del modulo

Ora che la protezione dei documenti è abilitata, dobbiamo specificare che è consentita solo la modifica dei campi del modulo. Ciò garantisce che gli utenti possano modificare solo le parti del documento che sono campi modulo. Ecco come:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Assicurati di sostituire "password" con la password impostata in precedenza.

## Passaggio 5: salvataggio del documento protetto

 Infine, puoi salvare il documento protetto utilizzando il file`Save` metodo della classe Document. Specificare il percorso completo del file e il nome del file desiderato. Per esempio :

```csharp
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

Assicurati di sostituire "dataDir" con il percorso della directory dei documenti.

### Codice sorgente di esempio per la funzionalità Consenti solo protezione campi modulo utilizzando Aspose.Words per .NET

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Inserisci due sezioni con del testo.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

// La protezione del documento funziona solo quando la protezione del documento è attivata ed è consentita solo la modifica nei campi del modulo.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

// Salva il documento protetto.
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

## Conclusione

In questa guida, abbiamo esplorato come utilizzare la libreria Aspose.Words per .NET per proteggere un documento e consentire solo la modifica dei campi del modulo. Seguendo i passaggi forniti, puoi implementare facilmente questa funzionalità nella tua applicazione C#. La protezione dei documenti è essenziale per garantire la sicurezza e la riservatezza dei tuoi documenti.

### Domande frequenti per consentire solo la protezione dei campi modulo nel documento Word

#### D: Cos'è la protezione dei documenti in Aspose.Words per .NET?

R: La protezione dei documenti in Aspose.Words per .NET è una funzionalità che ti consente di proteggere i tuoi documenti limitando determinate azioni, come la modifica, la formattazione o la modifica del contenuto. Aiuta a mantenere l'integrità e la riservatezza dei tuoi documenti impedendo modifiche non autorizzate.

#### D: Come posso proteggere un documento e consentire la modifica solo dei campi del modulo utilizzando Aspose.Words per .NET?

R: Per proteggere un documento e consentire la modifica solo dei campi del modulo utilizzando Aspose.Words per .NET, è possibile seguire questi passaggi:
1. Definisci il percorso della directory per il tuo documento.
2.  Inserisci sezioni e testo nel tuo documento utilizzando il file`DocumentBuilder` classe.
3.  Abilita la protezione dei documenti utilizzando il file`Protect` metodo del`Document` class, specificando il tipo di protezione come`AllowOnlyFormFields` e fornendo una password.
4.  Salvare il documento protetto utilizzando il file`Save` metodo del`Document` classe.

#### D: Posso inserire campi modulo in un documento protetto utilizzando Aspose.Words per .NET?

R: Sì, puoi inserire campi modulo in un documento protetto utilizzando Aspose.Words per .NET. La protezione dei documenti con il`AllowOnlyFormFields` type consente agli utenti di modificare solo i campi del modulo proteggendo il resto del contenuto del documento. Puoi usare il`DocumentBuilder` classe per inserire campi modulo nel documento prima di abilitare la protezione.

#### D: Posso rimuovere la protezione dei documenti da un documento protetto?

 R: Sì, puoi rimuovere la protezione del documento da un documento protetto utilizzando Aspose.Words per .NET. Per rimuovere la protezione è possibile utilizzare il file`Unprotect` metodo del`Document` classe e fornire la password corretta. Ciò rimuoverà la protezione e consentirà la modifica senza restrizioni del documento.

#### D: È possibile proteggere un documento con più tipi di protezione?

 R: No, Aspose.Words per .NET consente di applicare un solo tipo di protezione alla volta a un documento. comunque, il`AllowOnlyFormFields` il tipo di protezione può limitare efficacemente la modifica ai campi del modulo consentendo altri tipi di protezione, ad esempio`AllowOnlyComments` O`AllowOnlyRevisions`da abbinare alla protezione del campo modulo.

#### D: Posso impostare password diverse per diversi tipi di protezione in un documento?

R: No, Aspose.Words per .NET ti consente di impostare un'unica password per la protezione del documento, indipendentemente dal tipo di protezione. La stessa password verrà utilizzata per abilitare e disabilitare la protezione dei documenti.