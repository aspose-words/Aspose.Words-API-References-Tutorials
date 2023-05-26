---
title: Crea e aggiungi nodo paragrafo
linktitle: Crea e aggiungi nodo paragrafo
second_title: Riferimento all'API Aspose.Words per .NET
description: Crea e aggiungi un nodo paragrafo ai tuoi documenti Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-node/create-and-add-paragraph-node/
---

Ecco una guida passo passo per spiegare il codice sorgente C# di seguito che illustra come creare e aggiungere un nodo di paragrafo utilizzando Aspose.Words per .NET.

## Passaggio 1: importare i riferimenti necessari
Prima di iniziare, assicurati di aver importato i riferimenti necessari per utilizzare Aspose.Words per .NET nel tuo progetto. Ciò include l'importazione della libreria Aspose.Words e l'aggiunta degli spazi dei nomi richiesti al file di origine.

```csharp
using Aspose.Words;
```

## Passaggio 2: creare un nuovo documento
 In questo passaggio, creeremo un nuovo documento utilizzando il file`Document` classe.

```csharp
Document doc = new Document();
```

## Passaggio 3: crea un nodo di paragrafo
 Ora creeremo un nodo di paragrafo usando il`Paragraph` class e passando il documento come parametro.

```csharp
Paragraph para = new Paragraph(doc);
```

## Passaggio 4: accedere alla sezione del documento
 Per aggiungere il paragrafo al documento, dobbiamo accedere all'ultima sezione del documento utilizzando il`LastSection` proprietà.

```csharp
Section section = doc.LastSection;
```

## Passaggio 5: aggiungere il nodo del paragrafo al documento
 Ora che abbiamo la sezione del documento, possiamo aggiungere il nodo del paragrafo alla sezione usando il`AppendChild` metodo sulla sezione`Body` proprietà.

```csharp
section.Body.AppendChild(para);
```

## Passaggio 6: salvare il documento
 Infine, per salvare il documento, puoi utilizzare il file`Save` metodo specificando il formato di output desiderato, ad esempio il formato DOCX.

```csharp
doc.Save("output.docx", SaveFormat.Docx);
```

### Esempio di codice sorgente per creare e aggiungere un nodo di paragrafo con Aspose.Words per .NET

```csharp
Document doc = new Document();

Paragraph para = new Paragraph(doc);

Section section = doc.LastSection;
section.Body.AppendChild(para);

```

Questo è un esempio di codice completo per creare e aggiungere un nodo di paragrafo utilizzando Aspose.Words per .NET. Assicurati di importare i riferimenti necessari e segui i passaggi precedentemente descritti per integrare questo codice nel tuo progetto.