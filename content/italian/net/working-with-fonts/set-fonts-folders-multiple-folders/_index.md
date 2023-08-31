---
title: Imposta cartelle di caratteri Cartelle multiple
linktitle: Imposta cartelle di caratteri Cartelle multiple
second_title: Aspose.Words API di elaborazione dei documenti
description: Guida passo passo per impostare più cartelle di caratteri durante il rendering di un documento utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fonts/set-fonts-folders-multiple-folders/
---

In questo tutorial, ti guideremo attraverso il processo passo-passo per impostare più cartelle di font durante il rendering di un documento utilizzando Aspose.Words per .NET. Spiegheremo il codice sorgente C# in bundle e ti forniremo una guida completa per aiutarti a comprendere e implementare questa funzionalità nei tuoi progetti. Alla fine di questo tutorial, saprai come specificare più cartelle di font da utilizzare durante il rendering dei tuoi documenti utilizzando Aspose.Words per .NET.

## Passaggio 1: definire la directory dei documenti
Innanzitutto, devi impostare il percorso della directory dei documenti. Questa è la posizione in cui vuoi salvare il documento renderizzato modificato. Sostituisci "LA TUA CARTELLA DEI DOCUMENTI" con il percorso appropriato.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passo 2: carica il documento da renderizzare
 Quindi puoi caricare il documento di cui eseguire il rendering utilizzando il file`Document` classe. Assicurati di specificare il percorso del documento corretto.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Passaggio 3: impostare le cartelle dei caratteri
 Ora puoi impostare più cartelle di font usando il file`FontSettings` classe e il`SetFontsFolders()` metodo. È possibile specificare i percorsi delle cartelle dei caratteri che si desidera utilizzare in un array. In questo esempio, abbiamo specificato due cartelle di font: "C:\MyFonts\" e "D:\Varie\Fonts\".

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
```

## Passaggio 4: applica le impostazioni dei caratteri
 Successivamente, è necessario applicare le impostazioni del carattere al documento utilizzando il file`FontSettings` proprietà del`Document` classe.

```csharp
doc.FontSettings = fontSettings;
```

## Passaggio 5: salvare il documento renderizzato
 Infine, puoi salvare il documento renderizzato in un file usando l'estensione`Save()` metodo del`Document` classe. Assicurarsi di specificare il percorso e il nome file corretti.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

### Esempio di codice sorgente per Set Fonts Folders Multiple Folders utilizzando Aspose.Words per .NET 

```csharp
//Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Tieni presente che questa impostazione sovrascriverà qualsiasi origine di font predefinita che viene cercata per impostazione predefinita. Ora verranno cercate solo queste cartelle
// font durante il rendering o l'incorporamento di font. Per aggiungere una fonte di carattere aggiuntiva mantenendo le fonti di carattere di sistema, utilizzare sia FontSettings.GetFontSources che
// FontSettings.SetFontSources invece.
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

## Conclusione
In questo tutorial, abbiamo imparato come impostare più cartelle di font durante il rendering di un documento utilizzando Aspose.Words per .NET. Seguendo questa guida dettagliata, puoi facilmente specificare più cartelle di font da utilizzare durante il rendering dei tuoi documenti. Aspose.Words offre un'API potente e flessibile per l'elaborazione di testi con caratteri nei tuoi documenti. Con questa conoscenza, puoi controllare e personalizzare le origini dei caratteri utilizzate durante il rendering dei tuoi documenti in base alle tue esigenze specifiche.

### FAQ

#### Q: Come posso impostare più cartelle di font in Aspose.Words?

 A: Per impostare più cartelle di font in Aspose.Words, puoi usare il`SetFontsFolders` metodo del`Fonts` class che fornisce un elenco di percorsi di cartelle di caratteri personalizzati.

#### D: L'impostazione di più cartelle di font influisce su tutti i documenti elaborati con Aspose.Words?

A: Sì, l'impostazione di più cartelle di font influisce su tutti i documenti elaborati con Aspose.Words. Dopo aver definito le cartelle dei caratteri, Aspose.Words utilizzerà queste posizioni per cercare i caratteri in tutti i documenti.

#### D: Quante cartelle di font posso definire in Aspose.Words?

R: Puoi definire tutte le cartelle di font necessarie in Aspose.Words. Non esiste un limite specifico al numero di cartelle di font che è possibile definire.

#### D: Come posso controllare le cartelle dei font definite in Aspose.Words?

 A: Per controllare le cartelle dei font definite in Aspose.Words, puoi usare il`GetFolders` metodo del`Fonts` class per ottenere le posizioni delle cartelle dei caratteri configurate.

#### D: Le cartelle dei font devono contenere font specifici?

R: Sì, le cartelle dei caratteri devono contenere i caratteri che desideri utilizzare nei documenti di Word. Aspose.Words cercherà i caratteri nelle cartelle specificate durante l'elaborazione dei documenti.