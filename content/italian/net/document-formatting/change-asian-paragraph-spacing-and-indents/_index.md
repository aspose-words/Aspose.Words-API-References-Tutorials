---
title: Modificare la spaziatura dei paragrafi asiatici e i rientri nel documento di Word
linktitle: Modificare la spaziatura dei paragrafi asiatici e i rientri nel documento di Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come modificare la spaziatura e i rientri dei paragrafi asiatici nel documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/document-formatting/change-asian-paragraph-spacing-and-indents/
---
In questo tutorial ti spiegheremo come modificare la spaziatura e i rientri di un paragrafo asiatico utilizzando Aspose.Words per .NET. Segui i passaggi seguenti per comprendere il codice sorgente e applicare le modifiche.

## Passaggio 1: caricamento del documento

Per iniziare, specifica la directory per i tuoi documenti e carica il documento contenente la tipografia asiatica in un oggetto Document. Ecco come:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## Passaggio 2: modifica della spaziatura e dei rientri dei paragrafi

Modificheremo ora la spaziatura e i trattini del primo paragrafo del documento asiatico. Ecco come:

```csharp
ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
format.CharacterUnitLeftIndent = 10; // Aggiorna ParagraphFormat.LeftIndent
format.CharacterUnitRightIndent = 10; // Aggiorna ParagraphFormat.RightIndent
format.CharacterUnitFirstLineIndent = 20; //Aggiorna ParagraphFormat.FirstLineIndent
format.LineUnitBefore = 5; // Aggiorna ParagraphFormat.SpaceBefore
format.LineUnitAfter = 10; // Aggiorna ParagraphFormat.SpaceAfter
```

## Passaggio 3: salvataggio del documento

 Dopo aver inserito il campo del modulo di immissione del testo, salvare il documento nella posizione desiderata utilizzando il file`Save` metodo. Assicurati di fornire il percorso file appropriato:

```csharp
doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");
```

### Codice sorgente di esempio per modificare la spaziatura dei paragrafi e i rientri asiatici utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per la funzione Modifica spaziatura paragrafo e rientri asiatici con Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
	format.CharacterUnitLeftIndent = 10;       // ParagraphFormat.LeftIndent verrà aggiornato
	format.CharacterUnitRightIndent = 10;      // ParagraphFormat.RightIndent verrà aggiornato
	format.CharacterUnitFirstLineIndent = 20;  // ParagraphFormat.FirstLineIndent verrà aggiornato
	format.LineUnitBefore = 5;                 // ParagraphFormat.SpaceBefore verrà aggiornato
	format.LineUnitAfter = 10;                 // ParagraphFormat.SpaceAfter verrà aggiornato

	doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");

```

Con questo codice sarai in grado di modificare la spaziatura e i rientri di un paragrafo asiatico utilizzando Aspose.Words per .NET.

## Conclusione

 In questo tutorial, abbiamo imparato come modificare la spaziatura e i rientri di un paragrafo asiatico utilizzando Aspose.Words per .NET. Modificando le proprietà rilevanti del`ParagraphFormat`possiamo controllare il layout e l'aspetto dei paragrafi asiatici in un documento Word. Questa funzionalità è utile per personalizzare la formattazione del testo con caratteri asiatici e ottenere la presentazione visiva desiderata in documenti con contenuti in lingue miste.

### Domande frequenti

#### D: Cosa fa la funzione "Modifica spaziatura paragrafo e rientri asiatici" in Aspose.Words per .NET?

R: La funzione "Cambia spaziatura e rientri dei paragrafi asiatici" in Aspose.Words per .NET consente di modificare le proprietà di spaziatura e rientro di un paragrafo asiatico in un documento di Word. Puoi regolare i valori del rientro sinistro e destro, del rientro della prima riga, dello spazio prima e dello spazio dopo per controllare il layout e l'aspetto del paragrafo.

#### D: Come posso modificare la spaziatura e i rientri di un paragrafo asiatico utilizzando Aspose.Words per .NET?

 R: Per modificare la spaziatura e i rientri di un paragrafo asiatico, è necessario accedere al file`ParagraphFormat`del paragrafo di destinazione e modificarne le proprietà rilevanti. Nel codice di esempio fornito accediamo al primo paragrafo del documento e impostiamo il file`CharacterUnitLeftIndent`, `CharacterUnitRightIndent`, `CharacterUnitFirstLineIndent`, `LineUnitBefore` , E`LineUnitAfter` proprietà per regolare la spaziatura e i rientri.

#### D: Posso applicare queste modifiche ad altri paragrafi del documento?

 R: Sì, puoi applicare queste modifiche ad altri paragrafi del documento accedendo ai rispettivi`ParagraphFormat` oggetti. Il codice di esempio ha come target il primo paragrafo del documento, ma puoi modificare altri paragrafi regolando l'indice nel file`Paragraphs` raccolta o utilizzando altri criteri per selezionare i paragrafi desiderati.