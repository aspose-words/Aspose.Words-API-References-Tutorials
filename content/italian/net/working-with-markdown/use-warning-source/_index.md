---
title: Utilizza la sorgente di avviso
linktitle: Utilizza la sorgente di avviso
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come utilizzare l'origine degli avvisi con Aspose.Words per .NET Guida dettagliata.
type: docs
weight: 10
url: /it/net/working-with-markdown/use-warning-source/
---

In questo esempio, ti mostreremo come utilizzare l'origine di avviso con Aspose.Words per .NET. L'origine dell'avviso indica l'origine dell'avviso quando si utilizza la funzione di richiamata.

## Passaggio 1: caricamento del documento

 Caricheremo un documento esistente che contiene avvisi utilizzando il file`Load` metodo del`Document` classe.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");
```

## Passaggio 3: utilizzo della sorgente di avviso

 Utilizzeremo l'origine dell'avviso impostando il documento`WarningCallback` proprietà a una raccolta di`WarningInfo` oggetti.

```csharp
WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;
```

## Passaggio 4: salvataggio del documento

Infine, possiamo salvare il documento nel formato desiderato.

```csharp
doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");
foreach (WarningInfo warningInfo in warnings)
{
if (warningInfo.Source == WarningSource.Markdown)
	Console.WriteLine(warningInfo.Description);
}
```

### Codice sorgente di esempio per l'utilizzo dell'origine avviso con Aspose.Words per .NET

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

Congratulazioni! Ora hai imparato come utilizzare l'origine dell'avviso con Aspose.Words per .NET.

### Domande frequenti

#### D: Possiamo personalizzare l'aspetto del tag "Avvertenza"?

 R: La formattazione del tag "Avviso" dipende dal renderer Markdown utilizzato. Nella maggior parte dei casi, puoi personalizzare l'aspetto utilizzando i CSS per indirizzare il file`blockquote` tag nel tuo documento.

#### D: È possibile aggiungere icone al tag "Avvertenza"?

R: Sì, è possibile aggiungere icone al tag "Avviso" utilizzando il codice HTML nel documento Markdown. Puoi inserire un`span` tag con la classe appropriata per visualizzare un'icona accanto al testo dell'avviso.

#### D: Il tag "Avvertenza" è compatibile con tutti i lettori Markdown?

 R: La compatibilità del tag "Avvertenza" dipende dal rendering Markdown utilizzato. La maggior parte dei lettori di Markdown supporterà il file`blockquote` tag per visualizzare il testo evidenziato, ma l'aspetto esatto può variare.