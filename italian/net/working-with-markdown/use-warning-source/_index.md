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

### FAQ

#### D: È possibile personalizzare l'aspetto del tag "Avviso"?

R: La formattazione del tag "Warning" dipende dal renderer Markdown utilizzato. Nella maggior parte dei casi, puoi personalizzare l'aspetto utilizzando i CSS per indirizzare il file`blockquote` tag nel tuo documento.

#### D: È possibile aggiungere icone al tag "Avviso"?

 R: Sì, è possibile aggiungere icone al tag "Avviso" utilizzando il codice HTML nel documento Markdown. Puoi inserire un`span` tag con la classe appropriata per visualizzare un'icona accanto al testo di avviso.

#### D: Il tag "Avviso" è compatibile con tutti i lettori Markdown?

 R: La compatibilità del tag "Warning" dipende dal rendering Markdown utilizzato. La maggior parte dei lettori di Markdown supporterà il formato`blockquote` tag per visualizzare il testo evidenziato, ma l'aspetto esatto può variare.