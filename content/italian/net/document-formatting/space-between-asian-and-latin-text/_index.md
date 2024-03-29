---
title: Spazio tra il testo asiatico e quello latino nel documento Word
linktitle: Spazio tra il testo asiatico e quello latino nel documento Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come regolare automaticamente lo spazio tra il testo asiatico e quello latino nel documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/document-formatting/space-between-asian-and-latin-text/
---
In questo tutorial, ti mostreremo come utilizzare la funzione Spazio tra testo asiatico e latino nella funzione documento Word con Aspose.Words per .NET. Segui i passaggi seguenti per comprendere il codice sorgente e applicare le modifiche.

## Passaggio 1: creazione e configurazione del documento

Per iniziare, crea un nuovo documento e un oggetto DocumentBuilder associato. Ecco come:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: impostare lo spazio tra il testo asiatico e quello latino

Configureremo ora lo spazio tra il testo asiatico e quello latino utilizzando le proprietà dell'oggetto ParagraphFormat. Ecco come:

```csharp
ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

builder.Writeln("Auto adjust space between Asian and Latin text");
builder.Writeln("Auto adjust space between Asian text and numbers");
```

## Passaggio 3: salvataggio del documento

 Dopo aver inserito il campo del modulo di immissione del testo, salvare il documento nella posizione desiderata utilizzando il file`Save` metodo. Assicurati di fornire il percorso file appropriato:

```csharp
doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
```

### Codice sorgente di esempio per lo spazio tra testo asiatico e latino utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per la funzione Space Between Asian and Latin Text con Aspose.Words per .NET:


```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

builder.Writeln("Automatically adjust space between Asian and Latin text");
builder.Writeln("Automatically adjust space between Asian text and numbers");

doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
```

Con questo codice sarai in grado di regolare automaticamente lo spazio tra il testo asiatico e quello latino nel tuo documento utilizzando Aspose.Words per .NET.

## Conclusione

In questo tutorial, abbiamo esplorato il processo di utilizzo della funzione Spazio per regolare la spaziatura tra il testo asiatico e quello latino in un documento Word con Aspose.Words per .NET. Seguendo i passaggi descritti, puoi garantire la spaziatura e l'allineamento corretti, particolarmente utili quando si ha a che fare con contenuti misti asiatici e latini.

### Domande frequenti

#### D: Qual è la funzionalità Spazio tra il testo asiatico e quello latino in un documento Word?

R: La funzione Spazio tra testo asiatico e latino in un documento Word si riferisce alla possibilità di regolare automaticamente la spaziatura tra testo scritto in caratteri diversi, come asiatico (ad esempio cinese, giapponese) e latino (ad esempio inglese).

#### D: Perché è importante regolare lo spazio tra il testo asiatico e quello latino?

R: La regolazione dello spazio tra il testo asiatico e quello latino è fondamentale per garantire che le diverse scritture si fondano armoniosamente all'interno del documento. Una spaziatura corretta migliora la leggibilità e l'aspetto visivo generale, evitando che il testo appaia troppo ristretto o disteso.

#### D: Posso personalizzare le regolazioni dello spazio tra diversi script?

 R: Sì, puoi personalizzare le regolazioni dello spazio tra diversi script utilizzando il file`AddSpaceBetweenFarEastAndAlpha` E`AddSpaceBetweenFarEastAndDigit` proprietà. Abilitando o disabilitando queste proprietà, puoi controllare lo spazio tra il testo asiatico e quello latino, nonché tra il testo e i numeri asiatici.

#### D: Aspose.Words per .NET supporta altre funzionalità di formattazione dei documenti?

R: Sì, Aspose.Words per .NET offre ampio supporto per varie funzionalità di formattazione dei documenti. Include funzionalità per stili di carattere, paragrafi, tabelle, immagini e altro. Puoi manipolare e formattare in modo efficace i tuoi documenti Word a livello di codice.

#### D: Dove posso trovare risorse aggiuntive e documentazione per Aspose.Words per .NET?

 R: Per risorse complete e documentazione sull'utilizzo di Aspose.Words per .NET, visitare[Riferimento API Aspose.Words](https://reference.aspose.com/words/net/). Lì troverai guide dettagliate, tutorial, esempi di codice e riferimenti API per aiutarti a utilizzare in modo efficace le potenti funzionalità di Aspose.Words per .NET.