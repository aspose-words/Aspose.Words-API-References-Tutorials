---
title: Gruppo di interruzione di riga di tipografia asiatica nel documento di Word
linktitle: Gruppo di interruzione di riga di tipografia asiatica nel documento di Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come utilizzare il gruppo di interruzioni di riga della tipografia asiatica nel documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/document-formatting/asian-typography-line-break-group/
---
In questo tutorial, ti mostreremo come utilizzare il gruppo di interruzioni di riga della tipografia asiatica nella funzionalità dei documenti Word con Aspose.Words per .NET. Segui i passaggi seguenti per comprendere il codice sorgente e applicare le modifiche alla formattazione.

## Passaggio 1: caricamento del documento

Per iniziare, specifica la directory per i tuoi documenti e carica il documento contenente la tipografia asiatica in un oggetto Document. Ecco come:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## Passaggio 2: impostazione della tipografia asiatica

Configureremo ora le impostazioni della tipografia asiatica per il primo paragrafo del documento. Ecco come:

```csharp
ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
format. FarEastLineBreakControl = false;
format. WordWrap = true;
format. HangingPunctuation = false;
```

## Passaggio 3: salvataggio del documento

 Dopo aver inserito il campo del modulo di immissione del testo, salvare il documento nella posizione desiderata utilizzando il file`Save` metodo. Assicurati di fornire il percorso file appropriato:

```csharp
doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
```

### Esempio di codice sorgente per il gruppo di interruzioni di riga di tipografia asiatica utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per la funzione Line Break Group di tipografia asiatica con Aspose.Words per .NET:

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
Con questo codice sarai in grado di applicare il gruppo di interruzioni di riga della tipografia asiatica utilizzando Aspose.Words per .NET.

## Conclusione

 In questo tutorial, abbiamo esplorato la funzionalità "Gruppo di interruzione della linea di tipografia asiatica" in Aspose.Words per .NET. Configurando il`FarEastLineBreakControl`, `WordWrap` , E`HangingPunctuation` proprietà del`ParagraphFormat`, siamo riusciti a controllare il comportamento dell'interruzione di riga per la tipografia asiatica in un documento Word. Questa funzionalità è utile per gestire i caratteri asiatici e garantire interruzioni di riga e a capo automatico corretti nei documenti con contenuti in lingue miste.

### Domande frequenti

#### D: Qual è la funzionalità "Gruppo di interruzione riga di tipografia asiatica" in Aspose.Words per .NET?

A: La funzione "Gruppo di interruzione di riga di tipografia asiatica" in Aspose.Words per .NET consente di controllare il comportamento di interruzione di riga per la tipografia asiatica in un documento di Word. Nello specifico, influisce sul modo in cui le righe vengono interrotte e mandate a capo quando si tratta di caratteri asiatici nei paragrafi.

#### D: Come posso abilitare il "Gruppo di interruzione della linea di tipografia asiatica" in Aspose.Words per .NET?

 R: Per abilitare il "Gruppo interruzioni di riga tipografia asiatica", è necessario configurare il file`FarEastLineBreakControl`, `WordWrap` , E`HangingPunctuation` proprietà del`ParagraphFormat` per i paragrafi pertinenti nel documento. Collocamento`FarEastLineBreakControl` A`false` garantisce che i caratteri asiatici vengano trattati in modo simile ai caratteri latini per quanto riguarda l'interruzione di riga.`WordWrap` impostato`true` abilita il ritorno a capo per la tipografia asiatica e`HangingPunctuation` impostato`false` impedisce alla punteggiatura di rimanere bloccata nel testo asiatico.

#### D: Posso applicare il "Gruppo di interruzioni di riga di tipografia asiatica" a paragrafi specifici di un documento?

R: Sì, puoi applicare le impostazioni del "Gruppo interruzioni di riga tipografia asiatica" a paragrafi specifici in un documento Word. Nel codice di esempio le impostazioni vengono applicate al primo paragrafo del documento. Puoi modificare il codice per indirizzare altri paragrafi secondo necessità accedendovi tramite il file`Paragraphs` raccolta delle sezioni pertinenti del documento.