---
title: Usa la fonte di avviso
linktitle: Usa la fonte di avviso
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come utilizzare la fonte di avviso con Aspose.Words per .NET Guida dettagliata.
type: docs
weight: 10
url: /it/net/working-with-markdown/use-warning-source/
---

In questo esempio, ti mostreremo come utilizzare la sorgente di avviso con Aspose.Words per .NET. L'origine dell'avviso indica l'origine dell'avviso quando si utilizza la funzione di richiamata.

## Passaggio 1: caricamento del documento

 Caricheremo un documento esistente che contiene avvisi utilizzando l'estensione`Load` metodo del`Document` classe.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");
```

## Passaggio 3: utilizzo della sorgente di avviso

 Useremo la sorgente di avviso impostando il documento`WarningCallback` proprietà a una raccolta di`WarningInfo` oggetti.

```csharp
WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;
```

## Passaggio 4: salvare il documento

Infine, possiamo salvare il documento nel formato desiderato.

```csharp
doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");
foreach (WarningInfo warningInfo in warnings)
{
if (warningInfo.Source == WarningSource.Markdown)
	Console.WriteLine(warningInfo.Description);
}
```

### Esempio di codice sorgente per l'utilizzo di Warning Source con Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");

WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;

doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");

foreach (WarningInfo warningInfo in warnings)
{
	if (warningInfo.Source == WarningSource.Markdown)
		Console.WriteLine(warningInfo.Description);
}
```

Congratulazioni! Ora hai imparato come utilizzare la fonte di avviso con Aspose.Words per .NET.