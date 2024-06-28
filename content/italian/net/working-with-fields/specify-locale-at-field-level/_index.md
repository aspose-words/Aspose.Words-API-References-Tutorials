---
title: Specificare la lingua a livello di campo
linktitle: Specificare la lingua a livello di campo
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come specificare la localizzazione a livello di campo nei documenti Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fields/specify-locale-at-field-level/
---

Ecco una guida passo passo per spiegare il seguente codice sorgente C# che consente di specificare la localizzazione a livello di campo utilizzando la funzionalità Aspose.Words per .NET. Assicurati di aver incluso la libreria Aspose.Words nel tuo progetto prima di utilizzare questo codice.

## Passaggio 1: imposta il percorso della directory del documento

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Assicurati di specificare il percorso corretto della directory dei documenti in cui verrà salvato il documento modificato.

## Passaggio 2: crea un generatore di documenti

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

 Qui stiamo creando un'istanza di`DocumentBuilder` classe che ci permetterà di aggiungere campi al documento.

## Passaggio 3: inserisci un campo data con una posizione specifica

```csharp
Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;
```

 Utilizziamo il generatore di documenti per inserire un campo di tipo`FieldType.FieldDate` nel documento. Impostando il`LocaleId`proprietà a`1049`, specifichiamo la localizzazione russa per questo campo.

## Passaggio 4: salva il documento modificato

```csharp
builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

Infine, salviamo il documento modificato con la posizione specificata in un file specificato.

### Codice sorgente di esempio per specificare la localizzazione a livello di campo con Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

DocumentBuilder builder = new DocumentBuilder();

Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;

builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

Questo era un codice sorgente di esempio per specificare la localizzazione a livello di campo in un documento utilizzando Aspose.Words per .NET. Puoi utilizzare questo codice per inserire campi data con posizioni specifiche nei tuoi documenti Word.

### Domande frequenti

#### D: Come posso specificare le impostazioni locali a livello di campo in Aspose.Words per .NET?

 R: Per specificare la locale a livello di campo in Aspose.Words per .NET, è possibile utilizzare il file`FieldOptions` classe e il suo`FieldLocale` proprietà per impostare la locale desiderata. Ad esempio, puoi usare`FieldOptions.FieldLocale = new CultureInfo("fr-FR")` per specificare la locale francese (Francia).

#### D: È possibile specificare una locale diversa per ciascun campo in Aspose.Words per .NET?

 R: Sì, è possibile specificare una locale diversa per ciascun campo in Aspose.Words per .NET. Puoi usare il`FieldOptions.FieldLocale` proprietà prima di creare o aggiornare un campo specifico per assegnargli una lingua diversa.

#### D: Come posso ottenere le impostazioni locali attualmente utilizzate per un campo in Aspose.Words per .NET?

 R: Per ottenere la locale attualmente utilizzata per un campo in Aspose.Words per .NET, è possibile utilizzare il campo`Field.LocaleId`proprietà. Ciò ti consentirà di ottenere l'identificatore locale associato al campo.