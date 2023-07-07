---
title: Campi modulo Ottieni per nome
linktitle: Campi modulo Ottieni per nome
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come recuperare e modificare i campi del modulo per nome nei documenti di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-formfields/form-fields-get-by-name/
---

In questo tutorial passo-passo, ti guideremo su come utilizzare Aspose.Words per .NET per recuperare i campi modulo per nome da un documento Word. Spiegheremo il codice sorgente C# fornito e ti mostreremo come implementarlo nei tuoi progetti.

Per iniziare, assicurati di avere Aspose.Words per .NET installato e configurato nel tuo ambiente di sviluppo. Se non lo hai fatto, scarica e installa la libreria dal sito ufficiale.

## Passaggio 1: inizializzazione dell'oggetto documento

 Per prima cosa, inizializza il file`Document` oggetto fornendo il percorso del documento di origine contenente i campi del modulo:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");
```

## Passaggio 2: recupero dei campi del modulo

 Successivamente, accedi al file`FormFields` proprietà del`Range` oggetto nel documento per recuperare tutti i campi del modulo:

```csharp
FormFieldCollection documentFormFields = doc.Range.FormFields;
```

È possibile recuperare i campi del modulo per indice o per nome. In questo esempio, recuperiamo un campo modulo utilizzando entrambi i metodi:

```csharp
FormField formField1 = documentFormFields[3]; //Recupero per indice
FormField formField2 = documentFormFields["Text2"]; // Recupero per nome
```

## Passaggio 3: modifica delle proprietà del campo del modulo

 Dopo aver recuperato i campi del modulo, è possibile modificarne le proprietà secondo necessità. In questo esempio, cambiamo la dimensione del carattere di`formField1` a 20 e il colore del carattere di`formField2` al rosso:

```csharp
formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;
```

## Passaggio 4: salvare il documento

Infine, salva il documento modificato:

```csharp
doc.Save(dataDir + "ModifiedFormFields.docx");
```

Questo è tutto! Hai recuperato correttamente i campi del modulo per nome e modificato le loro proprietà in un documento di Word utilizzando Aspose.Words per .NET.

### Codice sorgente di esempio per i campi del modulo Get By Name utilizzando Aspose.Words per .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");

FormFieldCollection documentFormFields = doc.Range.FormFields;

FormField formField1 = documentFormFields[3];
FormField formField2 = documentFormFields["Text2"];

formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;

doc.Save(dataDir + "ModifiedFormFields.docx");
```

Sentiti libero di utilizzare questo codice nei tuoi progetti e di modificarlo in base alle tue esigenze specifiche.

### FAQ

#### D: Come posso ottenere un campo modulo per nome in Aspose.Words?

 A: Per ottenere un campo modulo per nome in Aspose.Words, puoi usare il file`Document.Range.FormFields[name]` metodo. Questo metodo restituisce il campo del modulo corrispondente al nome specificato.

#### D: Cosa succede se il campo modulo con il nome specificato non esiste nel documento?

 R: Se il campo modulo con il nome specificato non esiste nel documento, il file`Document.Range.FormFields[name]` metodo tornerà`null`Puoi controllare questo risultato per gestire i casi in cui il campo del modulo non viene trovato.

#### D: Come posso modificare le proprietà di un campo modulo trovato?

R: Una volta ottenuto un campo modulo per nome, puoi accedere alle sue singole proprietà per modificarle. Ad esempio, puoi modificare il valore del campo, abilitare o disabilitare la sua visibilità o modificare altre proprietà secondo necessità.

#### D: Posso ottenere più campi modulo con lo stesso nome in un documento?

 R: Sì, è possibile avere più campi modulo con lo stesso nome in un documento. In questo caso, il`Document.Range.FormFields[name]` Il metodo restituirà il primo campo del modulo trovato con il nome specificato. Se hai più campi modulo con lo stesso nome, dovrai tenerne conto durante la manipolazione dei campi.

#### D: Come posso iterare su tutti i campi del modulo in un documento?

 R: Per eseguire l'iterazione su tutti i campi modulo in un documento, puoi utilizzare a`foreach` loop sul`Document.Range.FormFields` collezione. Ciò ti consentirà di accedere individualmente a ciascun campo del modulo ed eseguire operazioni su ciascuno di essi.