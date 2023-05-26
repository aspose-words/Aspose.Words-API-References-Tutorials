---
title: Modifica la spaziatura e i rientri dei paragrafi asiatici
linktitle: Modifica la spaziatura e i rientri dei paragrafi asiatici
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come modificare la spaziatura e i rientri dei paragrafi asiatici con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/document-formatting/change-asian-paragraph-spacing-and-indents/
---

In questo tutorial, ti illustreremo come modificare la spaziatura e i rientri di un paragrafo asiatico utilizzando Aspose.Words per .NET. Segui i passaggi seguenti per comprendere il codice sorgente e applicare le modifiche.

## Passaggio 1: caricamento del documento

Per iniziare, specifica la directory per i tuoi documenti e carica il documento contenente la tipografia asiatica in un oggetto Document. Ecco come:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## Passaggio 2: modifica della spaziatura dei paragrafi e dei rientri

Modificheremo ora la spaziatura ei rientri del primo paragrafo del documento asiatico. Ecco come:

```csharp
ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
format.CharacterUnitLeftIndent = 10; // Aggiorna ParagraphFormat.LeftIndent
format.CharacterUnitRightIndent = 10; // Aggiorna ParagraphFormat.RightIndent
format.CharacterUnitFirstLineIndent = 20; // Aggiorna ParagraphFormat.FirstLineIndent
format.LineUnitBefore = 5; // Aggiorna ParagraphFormat.SpaceBefore
format.LineUnitAfter = 10; // Aggiorna ParagraphFormat.SpaceAfter
```

## Passaggio 3: salvare il documento

 Dopo aver inserito il campo del modulo di immissione del testo, salvare il documento nella posizione desiderata utilizzando il file`Save` metodo. Assicurati di fornire il percorso file appropriato:

```csharp
doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");
```

### Codice sorgente di esempio per modificare la spaziatura e i rientri dei paragrafi asiatici utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per la funzione Modifica la spaziatura e i rientri dei paragrafi asiatici con Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
	format.CharacterUnitLeftIndent = 10;       // ParagraphFormat.LeftIndent verrà aggiornato
	format.CharacterUnitRightIndent = 10;      // ParagraphFormat.RightIndent verrà aggiornato
	format.CharacterUnitFirstLineIndent = 20;  //ParagraphFormat.FirstLineIndent verrà aggiornato
	format.LineUnitBefore = 5;                 // ParagraphFormat.SpaceBefore verrà aggiornato
	format.LineUnitAfter = 10;                 // ParagraphFormat.SpaceAfter verrà aggiornato

	doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");

```

Con questo codice sarai in grado di modificare la spaziatura e i rientri di un paragrafo asiatico utilizzando Aspose.Words per .NET.

