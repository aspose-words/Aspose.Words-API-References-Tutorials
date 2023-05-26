---
title: Formato riga orizzontale
linktitle: Formato riga orizzontale
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come formattare le regole orizzontali nei documenti di Word utilizzando Aspose.Words per .NET. Guida passo dopo passo.
type: docs
weight: 10
url: /it/net/add-content-using-documentbuilder/horizontal-rule-format/
---

In questo esempio completo, imparerai come formattare una regola orizzontale in un documento di Word utilizzando Aspose.Words per .NET. Ti guideremo attraverso il processo e ti forniremo i frammenti di codice C# necessari. Alla fine di questa guida, sarai in grado di personalizzare l'allineamento, la larghezza, l'altezza, il colore e altre proprietà di un filetto orizzontale.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
- Aspose.Words per la libreria .NET installata sul tuo sistema.

## Passaggio 1: creare un DocumentBuilder e inserire una regola orizzontale
Per iniziare, crea un oggetto DocumentBuilder e utilizza il metodo InsertHorizontalRule per inserire una regola orizzontale:

```csharp
DocumentBuilder builder = new DocumentBuilder();
Shape shape = builder.InsertHorizontalRule();
```

## Passaggio 2: accedere al formato della regola orizzontale
Successivamente, accedi alla proprietà HorizontalRuleFormat dell'oggetto Shape per recuperare le opzioni di formattazione:

```csharp
HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
```

## Passaggio 3: personalizzare le opzioni di formattazione
Ora puoi personalizzare varie opzioni di formattazione per la regola orizzontale. Ad esempio, puoi regolare l'allineamento, la larghezza, l'altezza, il colore e l'ombreggiatura:

```csharp
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;
```

## Passaggio 4: salvare il documento
Dopo aver formattato il filetto orizzontale, salvare il documento in un file utilizzando il metodo Save dell'oggetto Document:

```csharp
builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

### Esempio di codice sorgente per il formato della regola orizzontale utilizzando Aspose.Words per .NET
Ecco il codice sorgente completo per la formattazione di una regola orizzontale utilizzando Aspose.Words per .NET:

```csharp

	DocumentBuilder builder = new DocumentBuilder();

	Shape shape = builder.InsertHorizontalRule();
	
	HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
	horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
	horizontalRuleFormat.WidthPercent = 70;
	horizontalRuleFormat.Height = 3;
	horizontalRuleFormat.Color = Color.Blue;
	horizontalRuleFormat.NoShade = true;

	builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
			
```

Ricorda di adattare il codice in base alle tue esigenze specifiche e di migliorarlo con funzionalità aggiuntive secondo necessità.

## Conclusione
Congratulazioni! Hai imparato con successo come formattare una regola orizzontale in un documento di Word utilizzando Aspose.Words per .NET. Seguendo la guida dettagliata e utilizzando il codice sorgente fornito, ora puoi personalizzare l'aspetto delle righe orizzontali per migliorare il layout visivo del tuo documento.

Sperimenta con diverse opzioni di formattazione per ottenere lo stile e l'effetto desiderati per i tuoi filetti orizzontali.
