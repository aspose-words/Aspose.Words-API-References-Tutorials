---
title: Funzionalità di tipo aperto
linktitle: Funzionalità di tipo aperto
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come abilitare e utilizzare le funzionalità Open Type in Aspose.Words per .NET
type: docs
weight: 10
url: /it/net/enable-opentype-features/open-type-features/
---

In questo tutorial completo, imparerai come abilitare e utilizzare le funzionalità Open Type in Aspose.Words per .NET. Ti guideremo attraverso il processo e ti forniremo i frammenti di codice C# necessari. Alla fine di questa guida, sarai in grado di lavorare con le funzionalità Open Type nei tuoi documenti Word.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
- Aspose.Words per la libreria .NET installata sul tuo sistema.

## Passaggio 1: caricare il documento
Per iniziare, carica il documento utilizzando la classe Document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");
```

## Passaggio 2: abilitare le funzionalità di tipo aperto
Per abilitare le funzionalità Open Type, imposta la proprietà TextShaperFactory della classe LayoutOptions su un'istanza della factory di text shaper desiderata. In questo esempio, utilizziamo HarfBuzzTextShaperFactory:

```csharp
doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;
```

## Passaggio 3: salvare il documento
Dopo aver abilitato le funzionalità Open Type, salvare il documento nel formato di output desiderato, ad esempio PDF:

```csharp
doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

### Esempio di codice sorgente per funzionalità di tipo aperto utilizzando Aspose.Words per .NET
Ecco il codice sorgente completo per l'utilizzo delle funzionalità Open Type in Aspose.Words per .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");

doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;

doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

## Conclusione
Congratulazioni! Hai imparato con successo come abilitare e utilizzare le funzionalità Open Type in Aspose.Words per .NET. Seguendo la guida passo passo e utilizzando il codice sorgente fornito, ora puoi lavorare con le funzionalità Open Type nei tuoi documenti Word.

Le funzionalità Open Type offrono capacità tipografiche e di modellazione del testo migliorate, consentendo di creare documenti visivamente accattivanti e dall'aspetto professionale. Sperimenta con diversi text shaper factory ed esplora le possibilità delle funzionalità Open Type nei tuoi progetti.

### FAQ

#### D: Come abilito le funzionalità OpenType in Aspose.Words per .NET?

R: Per abilitare le funzionalità OpenType in Aspose.Words per .NET, è necessario seguire i passaggi indicati nel tutorial.

#### D: Quali funzionalità OpenType sono supportate in Aspose.Words per .NET?

R: Aspose.Words per .NET supporta diverse funzionalità OpenType, come legature, variazioni di glifi, sostituzioni contestuali e altro.

#### D: Come posso verificare se una funzione OpenType è supportata in un font specifico?

R: Puoi verificare se una funzione OpenType è supportata in un font specifico utilizzando il file`Font.OpenTypeFeatures` metodo in Aspose.Words per .NET.

#### D: Quali altre funzionalità di formattazione del testo supporta Aspose.Words per .NET?

R: Oltre alle funzionalità OpenType, Aspose.Words per .NET supporta anche altre funzionalità di formattazione del testo come la formattazione di paragrafi, la creazione di tabelle, l'aggiunta di immagini, ecc.

#### D: Posso utilizzare le funzionalità OpenType in tutte le versioni di Aspose.Words per .NET?

R: Le funzionalità OpenType sono supportate nelle versioni più recenti di Aspose.Words per .NET. Assicurati di utilizzare una versione compatibile per beneficiare di queste funzionalità.