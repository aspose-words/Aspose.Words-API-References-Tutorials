---
title: Gruppo di interruzioni di riga di tipografia asiatica nel documento di Word
linktitle: Gruppo di interruzioni di riga di tipografia asiatica nel documento di Word
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come utilizzare il gruppo di interruzioni di riga di tipografia asiatica nel documento di Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/document-formatting/asian-typography-line-break-group/
---
In questo tutorial, ti mostreremo come utilizzare il gruppo di interruzioni di riga di tipografia asiatica nella funzionalità del documento di Word con Aspose.Words per .NET. Segui i passaggi seguenti per comprendere il codice sorgente e applicare le modifiche alla formattazione.

## Passaggio 1: caricamento del documento

Per iniziare, specifica la directory per i tuoi documenti e carica il documento contenente la tipografia asiatica in un oggetto Document. Ecco come:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## Passaggio 2: configurazione della tipografia asiatica

Ora configureremo le impostazioni tipografiche asiatiche per il primo paragrafo del documento. Ecco come:

```csharp
ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
format. FarEastLineBreakControl = false;
format. WordWrap = true;
format. HangingPunctuation = false;
```

## Passaggio 3: salvare il documento

 Dopo aver inserito il campo del modulo di immissione del testo, salvare il documento nella posizione desiderata utilizzando il file`Save` metodo. Assicurati di fornire il percorso file appropriato:

```csharp
doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
```

### Codice sorgente di esempio per Asian Typography Line Break Group utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per la funzione Asian Typography Line Break Group con Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
	format.FarEastLineBreakControl = false;
	format.WordWrap = true;
	format.HangingPunctuation = false;

	doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
	
```
Con questo codice sarai in grado di applicare il gruppo di interruzioni di riga di tipografia asiatica utilizzando Aspose.Words per .NET.

## Conclusione

 In questo tutorial, abbiamo esplorato la funzionalità "Asian Typography Line Break Group" in Aspose.Words per .NET. Configurando il`FarEastLineBreakControl`, `WordWrap` , E`HangingPunctuation` proprietà del`ParagraphFormat`, siamo stati in grado di controllare il comportamento di interruzione di riga per la tipografia asiatica in un documento di Word. Questa funzione è utile per gestire i caratteri asiatici e garantire interruzioni di riga e ritorno a capo corretti nei documenti con contenuti in lingue miste.

### FAQ

#### D: Che cos'è la funzione "Gruppo di interruzioni di riga di tipografia asiatica" in Aspose.Words per .NET?

R: La funzione "Gruppo di interruzioni di riga di tipografia asiatica" in Aspose.Words per .NET consente di controllare il comportamento di interruzione di riga per la tipografia asiatica in un documento di Word. In particolare, influisce sul modo in cui le righe vengono interrotte e avvolte quando si tratta di caratteri asiatici nei paragrafi.

#### D: Come abilito il "Gruppo di interruzione riga di tipografia asiatica" in Aspose.Words per .NET?

 R: Per abilitare il "Gruppo di interruzione di riga di tipografia asiatica", è necessario configurare il file`FarEastLineBreakControl`, `WordWrap` , E`HangingPunctuation` proprietà del`ParagraphFormat` per il paragrafo o i paragrafi pertinenti nel documento. Collocamento`FarEastLineBreakControl` A`false` garantisce che i caratteri asiatici vengano trattati in modo simile ai caratteri latini per quanto riguarda l'interruzione di riga.`WordWrap` impostato`true` abilita il ritorno a capo automatico per la tipografia asiatica e`HangingPunctuation` impostato`false` impedisce la punteggiatura nel testo asiatico.

#### D: Posso applicare il "Gruppo di interruzioni di riga di tipografia asiatica" a paragrafi specifici in un documento?

R: Sì, puoi applicare le impostazioni "Gruppo di interruzioni di riga di tipografia asiatica" a paragrafi specifici in un documento di Word. Nel codice di esempio, le impostazioni vengono applicate al primo paragrafo del documento. È possibile modificare il codice per indirizzare altri paragrafi in base alle esigenze accedendovi tramite il file`Paragraphs` raccolta della/e sezione/i pertinente/i nel documento.