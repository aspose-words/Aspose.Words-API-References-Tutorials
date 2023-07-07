---
title: Inserisci campi modulo
linktitle: Inserisci campi modulo
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come inserire campi modulo a discesa nei documenti di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-formfields/insert-form-fields/
---

In questo tutorial passo-passo, ti guideremo su come inserire campi modulo, in particolare un campo modulo a discesa, in un documento Word utilizzando Aspose.Words per .NET. Spiegheremo il codice sorgente C# fornito e ti mostreremo come implementarlo nei tuoi progetti.

Per iniziare, assicurati di avere Aspose.Words per .NET installato e configurato nel tuo ambiente di sviluppo. Se non lo hai fatto, scarica e installa la libreria dal sito ufficiale.

## Passaggio 1: inizializzazione degli oggetti Document e DocumentBuilder

 Per prima cosa, inizializza il file`Document` E`DocumentBuilder` oggetti:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: inserimento di un campo modulo a discesa

 Quindi, specifica le opzioni per il campo del modulo a discesa e inseriscilo nel documento utilizzando il`InsertComboBox` metodo del`DocumentBuilder` oggetto. In questo esempio, inseriamo un campo modulo a discesa denominato "DropDown" con tre opzioni: "Uno", "Due" e "Tre":

```csharp
string[] items = { "One", "Two", "Three" };
builder.InsertComboBox("DropDown", items, 0);
```

## Passaggio 3: salvare il documento

Infine, salva il documento:

```csharp
doc.Save("OutputDocument.docx");
```

Questo è tutto! Hai inserito correttamente un campo modulo a discesa in un documento Word utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per Inserisci campi modulo utilizzando Aspose.Words per .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

string[] items = { "One", "Two", "Three" };
builder.InsertComboBox("DropDown", items, 0);

doc.Save("OutputDocument.docx");
```

Sentiti libero di utilizzare questo codice nei tuoi progetti e di modificarlo in base alle tue esigenze specifiche.

### FAQ

#### D: Come posso inserire un campo modulo di tipo testo in Aspose.Words?

 R: Per inserire un campo modulo di tipo testo in Aspose.Words, puoi utilizzare il`FormField` class e impostare il suo`Type` proprietà a`FormFieldType.Text`. Puoi anche personalizzare altre proprietà come nome, etichetta e opzioni.

#### D: È possibile creare un campo modulo di tipo checkbox in un documento?

 R: Sì, è possibile creare un campo modulo di tipo checkbox in un documento Aspose.Words. Puoi usare il`FormField` class e impostare il suo`Type` proprietà a`FormFieldType.CheckBox` per creare una casella di controllo. È quindi possibile personalizzare le proprietà della casella di controllo secondo necessità.

#### D: Come posso aggiungere un campo modulo di tipo a discesa a un documento?

 R: Per aggiungere un campo modulo di tipo a discesa in un documento Aspose.Words, utilizzare il`FormField` class e impostare il suo`Type` proprietà a`FormFieldType.DropDown` . È quindi possibile impostare le opzioni del menu a discesa utilizzando il`DropDownItems` proprietà.

#### D: Posso impostare un valore predefinito per un campo modulo in Aspose.Words?

R: Sì, puoi impostare un valore predefinito per un campo modulo in Aspose.Words. Usa il`FormField.Result` proprietà per specificare il valore iniziale del campo del modulo.

#### D: Come posso recuperare i dati inseriti nei campi del modulo in Aspose.Words?

 A: Per recuperare i dati inseriti nei campi del modulo in Aspose.Words, è possibile utilizzare il file`FormField.Result` proprietà che contiene il valore immesso dall'utente. Puoi accedere a questa proprietà per ogni campo del modulo nel tuo documento.