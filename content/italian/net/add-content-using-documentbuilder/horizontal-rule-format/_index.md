---
title: Formato regola orizzontale nel documento Word
linktitle: Formato regola orizzontale nel documento Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come formattare le regole orizzontali nei documenti Word utilizzando Aspose.Words per .NET. Guida passo passo.
type: docs
weight: 10
url: /it/net/add-content-using-documentbuilder/horizontal-rule-format/
---
In questo esempio completo, imparerai come formattare una regola orizzontale in un documento Word utilizzando Aspose.Words per .NET. Ti guideremo attraverso il processo e ti forniremo gli snippet di codice C# necessari. Al termine di questa guida sarai in grado di personalizzare l'allineamento, la larghezza, l'altezza, il colore e altre proprietà di una regola orizzontale.

## Prerequisiti
Prima di iniziare, assicurati di possedere i seguenti prerequisiti:
- Aspose.Words per la libreria .NET installata sul tuo sistema.

## Passaggio 1: crea un DocumentBuilder e inserisci una regola orizzontale
Per iniziare, crea un oggetto DocumentBuilder e utilizza il metodo InsertHorizontalRule per inserire una regola orizzontale:

```csharp
DocumentBuilder builder = new DocumentBuilder();
Shape shape = builder.InsertHorizontalRule();
```

## Passaggio 2: accedi al formato della regola orizzontale
Successivamente, accedi alla proprietà HorizonRuleFormat dell'oggetto Shape per recuperare le opzioni di formattazione:

```csharp
HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
```

## Passaggio 3: personalizza le opzioni di formattazione
Ora puoi personalizzare varie opzioni di formattazione per la regola orizzontale. Ad esempio, puoi regolare l'allineamento, la larghezza, l'altezza, il colore e l'ombreggiatura:

```csharp
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;
```

## Passaggio 4: salva il documento
Dopo aver formattato la regola orizzontale, salva il documento in un file utilizzando il metodo Save dell'oggetto Document:

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

Ricorda di modificare il codice in base alle tue esigenze specifiche e di migliorarlo con funzionalità aggiuntive secondo necessità.

## Conclusione
Congratulazioni! Hai imparato con successo come formattare una regola orizzontale in un documento Word utilizzando Aspose.Words per .NET. Seguendo la guida passo passo e utilizzando il codice sorgente fornito, ora puoi personalizzare l'aspetto delle regole orizzontali per migliorare il layout visivo del tuo documento.

Sperimenta diverse opzioni di formattazione per ottenere lo stile e l'effetto desiderati per le tue regole orizzontali.

### Domande frequenti sul formato delle regole orizzontali nei documenti Word

#### D: Posso applicare colori diversi al filetto orizzontale?

R: Assolutamente! Con Aspose.Words per .NET, puoi facilmente personalizzare il colore della regola orizzontale impostando la proprietà Color sul valore del colore desiderato. Ciò ti consente di abbinare la linea orizzontale al design complessivo del tuo documento.

#### D: È possibile regolare la larghezza e l'altezza della riga orizzontale?

R: Sì, hai il pieno controllo sulla larghezza e sull'altezza della riga orizzontale. Modificando le proprietà LarghezzaPercent e Altezza, è possibile ottenere le dimensioni desiderate per la riga orizzontale.

#### D: Posso modificare l'allineamento della linea orizzontale all'interno del documento?

R: Certamente! Aspose.Words per .NET consente di specificare l'allineamento della regola orizzontale utilizzando la proprietà Alignment. Puoi scegliere tra varie opzioni come Centro, Sinistra, Destra e Giustificato.

#### D: Posso applicare un'ombreggiatura o un colore di sfondo al filetto orizzontale?

R: Sì, puoi aggiungere un'ombreggiatura o un colore di sfondo al filetto orizzontale. Per impostazione predefinita, la proprietà NoShade è impostata su true, ma è possibile impostarla su false e definire l'ombreggiatura utilizzando i metodi appropriati.

#### D: Posso inserire più regole orizzontali in un singolo documento?

R: Assolutamente! È possibile inserire più regole orizzontali in un documento Word utilizzando Aspose.Words per .NET. Ripeti semplicemente i passaggi del tutorial secondo necessità per aggiungere tutte le regole orizzontali di cui hai bisogno.