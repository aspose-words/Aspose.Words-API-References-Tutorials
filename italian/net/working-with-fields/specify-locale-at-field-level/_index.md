---
title: Specifica la lingua a livello di campo
linktitle: Specifica la lingua a livello di campo
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come specificare la localizzazione a livello di campo nei documenti di Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fields/specify-locale-at-field-level/
---

Ecco una guida dettagliata per spiegare il seguente codice sorgente C# che consente di specificare la localizzazione a livello di campo utilizzando la funzionalità Aspose.Words per .NET. Assicurati di aver incluso la libreria Aspose.Words nel tuo progetto prima di utilizzare questo codice.

## Passaggio 1: impostare il percorso della directory del documento

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Assicurati di specificare il percorso corretto della directory dei documenti in cui verrà salvato il documento modificato.

## Passaggio 2: creare un generatore di documenti

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

 Qui stiamo creando un'istanza di`DocumentBuilder` class che ci permetterà di aggiungere campi al documento.

## Passaggio 3: inserire un campo data con una posizione specifica

```csharp
Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;
```

 Usiamo il generatore di documenti per inserire un campo di tipo`FieldType.FieldDate` nel documento. Impostando il`LocaleId` proprietà a`1049`, specifichiamo la localizzazione russa per questo campo.

## Passaggio 4: salvare il documento modificato

```csharp
builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

Infine, salviamo il documento modificato con la posizione specificata in un file specificato.

### Esempio di codice sorgente per specificare la localizzazione a livello di campo con Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

DocumentBuilder builder = new DocumentBuilder();

Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;

builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

Questo era un esempio di codice sorgente per specificare la localizzazione a livello di campo in un documento utilizzando Aspose.Words per .NET. È possibile utilizzare questo codice per inserire campi data con posizioni specifiche nei documenti di Word.
