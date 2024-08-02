---
title: Intervallo tag documento strutturato Avvia la mappatura Xml
linktitle: Intervallo tag documento strutturato Avvia la mappatura Xml
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come associare dinamicamente i dati XML ai tag dei documenti strutturati in Word utilizzando Aspose.Words per .NET. Segui la nostra guida passo passo.
type: docs
weight: 10
url: /it/net/programming-with-sdt/structured-document-tag-range-start-xml-mapping/
---
## introduzione

Hai mai desiderato inserire dinamicamente dati XML in un documento Word? Bene, sei fortunato! Aspose.Words per .NET rende questo compito un gioco da ragazzi. In questo tutorial, approfondiremo la mappatura XML degli intervalli di tag dei documenti strutturati. Questa funzionalità ti consente di associare parti XML personalizzate ai controlli del contenuto, garantendo che il contenuto del documento si aggiorni perfettamente con i tuoi dati XML. Pronto a trasformare i tuoi documenti in capolavori dinamici.

## Prerequisiti

Prima di passare alla parte di codifica, assicuriamoci di avere tutto ciò di cui hai bisogno:

1.  Aspose.Words per .NET Library: assicurati di avere la versione più recente. Puoi scaricarlo[Qui](https://releases.aspose.com/words/net/).
2. Ambiente di sviluppo: Visual Studio o qualsiasi altro IDE che supporti C#.
3. Conoscenza di base di C#: la familiarità con la programmazione C# è un must.
4. Documento Word: un documento Word di esempio con cui lavorare.

## Importa spazi dei nomi

Per prima cosa, importiamo gli spazi dei nomi necessari. Ciò garantirà l'accesso a tutte le classi e i metodi richiesti in Aspose.Words per .NET.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Markup;
using System.Text;
```

## Passaggio 1: imposta la directory dei documenti

Ogni progetto ha bisogno di una fondazione, giusto? Qui impostiamo il percorso della directory dei documenti.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: caricare il documento Word

Successivamente, carichiamo il documento Word. Questo è il documento in cui inseriremo i nostri dati XML.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
```

## Passaggio 3: aggiungi una parte XML personalizzata

Dobbiamo costruire una parte XML contenente i dati che vogliamo inserire e aggiungerla alla raccolta CustomXmlPart del documento. Questa parte XML personalizzata fungerà da origine dati per i nostri tag di documenti strutturati.

### Creazione di una parte XML

Innanzitutto, genera un ID univoco per la parte XML e definisci il suo contenuto.

```csharp
// Costruisci una parte XML che contiene dati e aggiungila alla raccolta CustomXmlPart del documento.
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
```

### Verificare il contenuto della parte XML

Per garantire che la parte XML venga aggiunta correttamente, ne stampiamo il contenuto.

```csharp
Console.WriteLine(Encoding.UTF8.GetString(xmlPart.Data));
```

## Passaggio 4: crea un tag per documento strutturato

Un tag di documento strutturato (SDT) è un controllo del contenuto che può essere associato a una parte XML. Qui creiamo un SDT che visualizzerà il contenuto della nostra parte XML personalizzata.

Innanzitutto, individua l'inizio dell'intervallo SDT nel documento.

```csharp
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
```

## Passaggio 5: impostare la mappatura XML per l'SDT

Ora è il momento di associare la nostra parte XML all'SDT. Impostando una mappatura XML, specifichiamo quale parte dei dati XML deve essere visualizzata nell'SDT.

 XPath punta all'elemento specifico nella parte XML che vogliamo visualizzare. Qui indichiamo il secondo`<text>` elemento all'interno di`<root>` elemento.

```csharp
// Imposta una mappatura per il nostro StructuredDocumentTag
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
```

## Passaggio 6: salva il documento

Infine, salva il documento per vedere le modifiche in azione. L'SDT nel documento Word ora visualizzerà il contenuto XML specificato.

```csharp
doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

## Conclusione

il gioco è fatto! Hai mappato con successo una parte XML a un tag di documento strutturato in un documento di Word utilizzando Aspose.Words per .NET. Questa potente funzionalità ti consente di creare documenti dinamici e basati sui dati senza sforzo. Che tu stia generando report, fatture o qualsiasi altro tipo di documento, la mappatura XML può semplificare notevolmente il tuo flusso di lavoro.

## Domande frequenti

### Che cos'è un tag di documento strutturato in Word?
I tag dei documenti strutturati, noti anche come controlli del contenuto, sono contenitori per tipi specifici di contenuto nei documenti di Word. Possono essere utilizzati per associare dati, limitare la modifica o guidare gli utenti nella creazione di documenti.

### Come posso aggiornare dinamicamente il contenuto della parte XML?
 È possibile aggiornare il contenuto della parte XML modificando il file`xmlPartContent` stringa prima di aggiungerla al documento. Aggiorna semplicemente la stringa con i nuovi dati e aggiungila al file`CustomXmlParts` collezione.

### Posso associare più parti XML a diversi SDT nello stesso documento?
Sì, puoi associare più parti XML a diversi SDT nello stesso documento. Ogni SDT può avere la propria parte XML univoca e la propria mappatura XPath.

### È possibile mappare strutture XML complesse su SDT?
Assolutamente! È possibile mappare strutture XML complesse su SDT utilizzando espressioni XPath dettagliate che puntano con precisione agli elementi desiderati all'interno della parte XML.

### Come posso rimuovere una parte XML da un documento?
 Puoi rimuovere una parte XML chiamando il file`Remove` metodo sul`CustomXmlParts` raccolta, passando il`xmlPartId` della parte XML che desideri rimuovere.