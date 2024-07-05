---
title: Imposta cartelle di caratteri Cartelle multiple
linktitle: Imposta cartelle di caratteri Cartelle multiple
second_title: API di elaborazione dei documenti Aspose.Words
description: Guida passo passo per impostare più cartelle di caratteri durante il rendering di un documento utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fonts/set-fonts-folders-multiple-folders/
---

In questo tutorial ti guideremo attraverso il processo passo passo per impostare più cartelle di caratteri durante il rendering di un documento utilizzando Aspose.Words per .NET. Spiegheremo il codice sorgente C# in bundle e ti forniremo una guida completa per aiutarti a comprendere e implementare questa funzionalità nei tuoi progetti. Alla fine di questo tutorial, saprai come specificare più cartelle di caratteri da utilizzare durante il rendering dei tuoi documenti utilizzando Aspose.Words per .NET.

## Passaggio 1: definire la directory dei documenti
Innanzitutto, devi impostare il percorso della directory dei documenti. Questa è la posizione in cui desideri salvare il documento renderizzato modificato. Sostituisci "DIRECTORY DOCUMENTI" con il percorso appropriato.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: caricare il documento da renderizzare
 Quindi puoi caricare il documento da renderizzare utilizzando il file`Document` classe. Assicurati di specificare il percorso corretto del documento.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Passaggio 3: imposta le cartelle dei caratteri
 Ora puoi impostare più cartelle di caratteri utilizzando il file`FontSettings` classe e il`SetFontsFolders()` metodo. È possibile specificare i percorsi delle cartelle di caratteri che si desidera utilizzare in un array. In questo esempio abbiamo specificato due cartelle di caratteri: "C:\MyFonts\" e "D:\Varie\Fonts\".

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
```

## Passaggio 4: applica le impostazioni dei caratteri
 Successivamente, devi applicare le impostazioni del carattere al tuo documento utilizzando il file`FontSettings` proprietà del`Document` classe.

```csharp
doc.FontSettings = fontSettings;
```

## Passaggio 5: salva il documento renderizzato
 Infine, puoi salvare il documento renderizzato in un file utilizzando il file`Save()` metodo del`Document` classe. Assicurati di specificare il percorso e il nome file corretti.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

### Codice sorgente di esempio per Imposta cartelle di caratteri Cartelle multiple utilizzando Aspose.Words per .NET 

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Tieni presente che questa impostazione sovrascriverà qualsiasi origine di caratteri predefinita ricercata per impostazione predefinita. Ora verranno cercate solo queste cartelle
// caratteri durante il rendering o l'incorporamento di caratteri. Per aggiungere un'origine di caratteri aggiuntiva mantenendo le origini di caratteri di sistema, utilizzare sia FontSettings.GetFontSources che
// FontSettings.SetFontSources invece.
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

## Conclusione
In questo tutorial, abbiamo imparato come impostare più cartelle di caratteri durante il rendering di un documento utilizzando Aspose.Words per .NET. Seguendo questa guida passo passo, puoi facilmente specificare più cartelle di caratteri da utilizzare durante il rendering dei tuoi documenti. Aspose.Words offre un'API potente e flessibile per l'elaborazione delle parole con i caratteri nei tuoi documenti. Con questa conoscenza, puoi controllare e personalizzare le origini dei caratteri utilizzate durante il rendering dei tuoi documenti in base alle tue esigenze specifiche.

### Domande frequenti

#### D: Come posso impostare più cartelle di caratteri in Aspose.Words?

 R: Per impostare più cartelle di caratteri in Aspose.Words, puoi utilizzare il file`SetFontsFolders` metodo del`Fonts` classe che fornisce un elenco di posizioni delle cartelle di caratteri personalizzati.

#### D: L'impostazione di più cartelle di caratteri influisce su tutti i documenti elaborati con Aspose.Words?

R: Sì, l'impostazione di più cartelle di caratteri influisce su tutti i documenti elaborati con Aspose.Words. Dopo aver definito le cartelle dei caratteri, Aspose.Words utilizzerà queste posizioni per cercare i caratteri in tutti i documenti.

#### D: Quante cartelle di caratteri posso definire in Aspose.Words?

R: È possibile definire tutte le cartelle di caratteri necessarie in Aspose.Words. Non esiste un limite specifico al numero di cartelle di caratteri che è possibile definire.

#### D: Come posso controllare le cartelle dei caratteri definite in Aspose.Words?

 R: Per controllare le cartelle dei caratteri definite in Aspose.Words, puoi utilizzare il file`GetFolders` metodo del`Fonts` class per ottenere le posizioni delle cartelle dei caratteri configurate.

#### D: Le cartelle dei font devono contenere font specifici?

R: Sì, le cartelle dei caratteri dovrebbero contenere i caratteri che desideri utilizzare nei tuoi documenti Word. Aspose.Words cercherà i caratteri nelle cartelle specificate durante l'elaborazione dei documenti.