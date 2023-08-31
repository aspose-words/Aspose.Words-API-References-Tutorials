---
title: Sezione illimitata nel documento di Word
linktitle: Sezione illimitata nel documento di Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come definire sezioni illimitate in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/document-protection/unrestricted-section/
---
In questo tutorial, ti guideremo attraverso i passaggi per utilizzare la funzionalità di sezione illimitata di Aspose.Words per .NET. Questa funzionalità consente di definire sezioni specifiche in un documento Word che non sono protette, anche se il resto del documento è protetto. Seguire i passaggi seguenti:

## Passaggio 1: creazione del documento e delle sezioni

Inizia creando un'istanza della classe Document e un oggetto DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: aggiungi contenuto al documento
Utilizza l'oggetto DocumentBuilder per aggiungere contenuto al documento e inserire interruzioni di sezione:

```csharp
builder.Writeln("Section 1. Unprotected.");
builder. InsertBreak(BreakType. SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");
```

## Passaggio 3: Proteggi documento e sezioni

La protezione della sezione funziona solo quando la protezione del documento è abilitata ed è consentita solo la modifica nei campi del modulo. Puoi proteggere il documento utilizzando il metodo Protect() dell'oggetto Document:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Assicurati di specificare il tipo corretto di protezione e imposta la password desiderata.

## Passaggio 4: disabilitazione della protezione per una sezione specifica

Per impostazione predefinita, tutte le sezioni sono protette, ma puoi disabilitare selettivamente la protezione per una sezione specifica utilizzando la proprietà ProtectedForForms dell'oggetto Sezione:

```csharp
doc.Sections[0].ProtectedForForms = false;
```

In questo esempio, la protezione è disabilitata per la prima sezione.

## Passaggio 5: salva il documento

Infine, salva il documento modificato:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");
```

Assicurati di specificare il percorso e il nome file corretti per salvare il documento con sezioni illimitate.

### Codice sorgente di esempio per la sezione senza restrizioni utilizzando Aspose.Words per .NET

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

//Per impostazione predefinita, tutte le sezioni sono protette, ma possiamo disattivare selettivamente la protezione.
doc.Sections[0].ProtectedForForms = false;
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");

doc = new Document(dataDir + "DocumentProtection.UnrestrictedSection.docx");

```

Seguendo questi passaggi, sarai in grado di definire facilmente sezioni illimitate nel tuo documento Word con Aspose.Words per .NET.

## Conclusione

In questo tutorial, abbiamo esplorato la funzionalità di sezione illimitata di Aspose.Words per .NET, che consente a sezioni specifiche di un documento Word di rimanere non protette mentre il resto del documento è protetto. Seguendo i passaggi forniti, puoi definire facilmente sezioni all'interno del tuo documento in cui gli utenti possono modificare liberamente il contenuto mantenendo la protezione per le altre sezioni. Aspose.Words per .NET offre potenti funzionalità per la protezione e la personalizzazione dei documenti, dandoti il controllo sulle autorizzazioni di modifica all'interno dei tuoi documenti Word.

### Domande frequenti per la sezione senza restrizioni nel documento Word

#### D: Quali sono le sezioni illimitate in Aspose.Words per .NET?

R: Le sezioni illimitate in Aspose.Words per .NET sono sezioni specifiche all'interno di un documento Word che non sono protette, anche se il resto del documento è protetto. Queste sezioni consentono agli utenti di modificare il contenuto al loro interno mantenendo la protezione per le restanti parti del documento.

#### D: Come posso creare sezioni senza restrizioni utilizzando Aspose.Words per .NET?

R: Per creare sezioni illimitate in un documento Word utilizzando Aspose.Words per .NET, puoi seguire questi passaggi:
1.  Crea un'istanza di`Document` classe e a`DocumentBuilder` oggetto.
2.  Usa il`DocumentBuilder` per aggiungere contenuto al documento e inserire interruzioni di sezione.
3.  Proteggi il documento utilizzando il file`Protect` metodo del`Document` oggetto, specificando il tipo di protezione e la password desiderate.
4.  Disabilita la protezione per una sezione specifica impostando il file`ProtectedForForms` proprietà del corrispondente`Section` opporsi a`false`.
5. Salva il documento modificato.

#### D: Posso avere più sezioni senza restrizioni all'interno di un documento Word?

 R: Sì, puoi avere più sezioni senza restrizioni all'interno di un documento Word. Disabilitando selettivamente la protezione per sezioni specifiche utilizzando il file`ProtectedForForms` proprietà del`Section`oggetto, è possibile definire più sezioni in cui gli utenti possono modificare liberamente il contenuto mantenendo protette le altre sezioni.

#### Q4. Posso rimuovere la protezione da una sezione inizialmente protetta?
 Sì, puoi rimuovere la protezione da una sezione inizialmente protetta impostando il file`ProtectedForForms` proprietà del corrispondente`Section` opporsi a`false`. Ciò consente agli utenti di modificare il contenuto all'interno di quella sezione specifica senza alcuna restrizione.

#### D: Quali tipi di protezione possono essere applicati a un documento Word?

R: Aspose.Words per .NET fornisce vari tipi di protezione che possono essere applicati a un documento Word, tra cui:
- NoProtection: non viene applicata alcuna protezione.
- AllowOnlyRevisions: gli utenti possono solo apportare revisioni al documento.
- ConsentiOnlyComments: gli utenti possono solo aggiungere commenti al documento.
- AllowOnlyFormFields: gli utenti possono modificare solo i campi modulo nel documento.
- Sola lettura: il documento è di sola lettura e non è consentita alcuna modifica.


