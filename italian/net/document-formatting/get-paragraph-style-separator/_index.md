---
title: Ottieni il separatore di stile di paragrafo
linktitle: Ottieni il separatore di stile di paragrafo
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come ottenere il separatore di stile di paragrafo con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/document-formatting/get-paragraph-style-separator/
---

In questo tutorial, ti illustreremo come utilizzare la funzione Ottieni separatore di stile paragrafo con Aspose.Words per .NET. Segui i passaggi seguenti per comprendere il codice sorgente e applicare le modifiche.

## Passaggio 1: caricamento del documento

Per iniziare, specifica la directory per i tuoi documenti e carica il documento in un oggetto Document. Ecco come:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Document.docx");
```

## Passaggio 2: trovare i separatori di stile di paragrafo

Passeremo ora in rassegna tutti i paragrafi del documento e verificheremo se un paragrafo è un separatore di stile. Ecco come:

```csharp
foreach(Paragraph paragraph in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (paragraph.BreakIsStyleSeparator)
     {
         Console.WriteLine("Separator found!");
     }
}
```

### Esempio di codice sorgente per Ottieni separatore di stile di paragrafo utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per la funzione Ottieni separatore di stile paragrafo con Aspose.Words per .NET:

```csharp

            Document doc = new Document(MyDir + "Document.docx");

            foreach (Paragraph paragraph in doc.GetChildNodes(NodeType.Paragraph, true))
            {
                if (paragraph.BreakIsStyleSeparator)
                {
                    Console.WriteLine("Separator Found!");
                }
            }
        
```

Con questo codice sarai in grado di trovare i separatori di stile di paragrafo in un documento utilizzando Aspose.Words per .NET.

