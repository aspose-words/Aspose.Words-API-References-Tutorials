---
title: Verifica documento Word crittografato
linktitle: Verifica documento Word crittografato
second_title: Aspose.Words API di elaborazione dei documenti
description: Guida dettagliata per verificare che un documento word sia crittografato con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-fileformat/verify-encrypted-document/
---

Questo articolo fornisce una guida dettagliata su come utilizzare la funzione di verifica del documento di Word crittografato con Aspose.Words per .NET. Spiegheremo ogni parte del codice in dettaglio. Alla fine di questo tutorial, sarai in grado di capire come verificare se un documento è crittografato.

Prima di iniziare, assicurati di aver installato e configurato la libreria Aspose.Words per .NET nel tuo progetto. Puoi trovare la libreria e le istruzioni di installazione sul sito web di Aspose.

## Passaggio 1: definire la directory dei documenti

 Per iniziare, devi definire il percorso della directory in cui si trovano i tuoi documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: rileva il formato del file

 Successivamente, usiamo il`DetectFileFormat` metodo del`FileFormatUtil` class per rilevare le informazioni sul formato del file. In questo esempio, supponiamo che il documento crittografato si chiami "Encrypted.docx" e si trovi nella directory dei documenti specificata.

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
```

## Passaggio 3: controlla se il documento è crittografato

 Noi usiamo il`IsEncrypted` proprietà del`FileFormatInfo`oggetto per verificare se il documento è crittografato. Questa proprietà ritorna`true` se il documento è cifrato, altrimenti ritorna`false`. Mostriamo il risultato nella console.

```csharp
Console.WriteLine(info.IsEncrypted);
```

È tutto ! Hai verificato con successo se un documento è crittografato utilizzando Aspose.Words per .NET.

### Codice sorgente di esempio per la verifica di documenti crittografati con Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
	Console.WriteLine(info.IsEncrypted);
            
        
```

## Domande frequenti

### D: Quali sono i passaggi per verificare un documento Word crittografato?

I passaggi per verificare un documento Word crittografato sono i seguenti:

Definire la directory del documento.

Rileva il formato del file.

Controlla se il documento è crittografato.

### D: Come posso impostare la directory dei documenti?
 Per impostare la directory dei documenti, è necessario sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti nel seguente codice:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

### D: Come rilevare il formato del file?
 Puoi usare il`DetectFileFormat` metodo del`FileFormatUtil`class per rilevare le informazioni sul formato del file. Nell'esempio seguente, assumiamo che il documento crittografato si chiami "Encrypted.docx" e si trovi nella directory dei documenti specificata:

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
```

### D: Come verificare se il documento è crittografato?
 Puoi usare il`IsEncrypted` proprietà del`FileFormatInfo`oggetto per verificare se il documento è crittografato. Questa proprietà ritorna`true` se il documento è cifrato, altrimenti ritorna`false`. Il risultato viene visualizzato nella console:

```csharp
Console.WriteLine(info.IsEncrypted);
```

### D: Come verificare se un documento è crittografato utilizzando Aspose.Words per .NET?
Seguendo i passaggi menzionati in questo tutorial ed eseguendo il codice sorgente fornito, è possibile verificare se un documento è crittografato utilizzando Aspose.Words per .NET.
