---
title: Mostra Nascondi segnalibri nel documento di Word
linktitle: Mostra Nascondi segnalibri nel documento di Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come mostrare o nascondere un segnalibro specifico nel documento Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-bookmarks/show-hide-bookmarks/
---

In questo articolo, esploreremo il codice sorgente C# sopra per capire come utilizzare la funzione Mostra Nascondi Segnalibri nella libreria Aspose.Words per .NET. Questa funzione ti consente di mostrare o nascondere un segnalibro specifico nel documento Word.

## Prerequisiti

- Conoscenza base del linguaggio C#.
- Ambiente di sviluppo .NET con libreria Aspose.Words installata.

## Passaggio 1: caricamento del documento

 Noi usiamo il`Document` classe per caricare il documento esistente da un file:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## Passaggio 2: mostra o nascondi un segnalibro specifico

 Noi usiamo il`ShowHideBookmarkedContent` funzione per mostrare o nascondere un segnalibro specifico nel documento. Questa funzione prende come parametri il documento, il nome del segnalibro e un valore booleano per indicare se mostrare o nascondere il segnalibro:

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", false);
```

## Passaggio 3: salvataggio del documento modificato

 Noi usiamo il`Save` metodo per salvare il documento modificato in un file:

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

### Codice sorgente di esempio per Mostra Nascondi segnalibri utilizzando Aspose.Words per .NET

Ecco il codice sorgente di esempio completo per dimostrare come mostrare o nascondere un segnalibro specifico utilizzando Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");

	ShowHideBookmarkedContent(doc, "MyBookmark1", false);
	
	doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");

```

#### Codice sorgente ShowHideBookmarkedContent

```csharp

public void ShowHideBookmarkedContent(Document doc, string bookmarkName, bool showHide)
        {
            Bookmark bm = doc.Range.Bookmarks[bookmarkName];

            DocumentBuilder builder = new DocumentBuilder(doc);
            builder.MoveToDocumentEnd();

            // {IF "{MERGEFIELD segnalibro}" = "true" "" ""}
            Field field = builder.InsertField("IF \"", null);
            builder.MoveTo(field.Start.NextSibling);
            builder.InsertField("MERGEFIELD " + bookmarkName + "", null);
            builder.Write("\" = \"true\" ");
            builder.Write("\"");
            builder.Write("\"");
            builder.Write(" \"\"");

            Node currentNode = field.Start;
            bool flag = true;
            while (currentNode != null && flag)
            {
                if (currentNode.NodeType == NodeType.Run)
                    if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
                        flag = false;

                Node nextNode = currentNode.NextSibling;

                bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
                currentNode = nextNode;
            }

            Node endNode = bm.BookmarkEnd;
            flag = true;
            while (currentNode != null && flag)
            {
                if (currentNode.NodeType == NodeType.FieldEnd)
                    flag = false;

                Node nextNode = currentNode.NextSibling;

                bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
                endNode = currentNode;
                currentNode = nextNode;
            }

            doc.MailMerge.Execute(new[] { bookmarkName }, new object[] { showHide });
        }
		
```
## Conclusione

In questo articolo, abbiamo esplorato il codice sorgente C# per capire come utilizzare la funzionalità Mostra Nascondi Segnalibri di Aspose.Words per .NET. Abbiamo seguito una guida passo passo per mostrare o nascondere un segnalibro specifico in un documento.

### Domande frequenti per mostrare nascondere i segnalibri nel documento Word

#### D: Posso mostrare o nascondere più segnalibri nello stesso documento?

R: Sì, puoi mostrare o nascondere più segnalibri nello stesso documento ripetendo i passaggi 2 e 3 per ciascun segnalibro che desideri elaborare.

#### D: Il codice fornito funziona con altri formati di documenti Word, come .doc o .docm?

R: Sì, il codice fornito funziona con vari formati di documenti Word supportati da Aspose.Words, come .doc e .docm. Assicurati solo di utilizzare il nome file e il percorso corretti durante il caricamento e il salvataggio del documento.

#### D: Come posso mostrare nuovamente un segnalibro nascosto?

 A: Per mostrare nuovamente un segnalibro nascosto, devi utilizzare lo stesso`ShowHideBookmarkedContent` funzione che passa il valore`true` per il parametro booleano che indica se mostrare o nascondere il segnalibro.

#### D: Posso utilizzare le condizioni per mostrare o nascondere i segnalibri in base ai valori dei campi di unione nel documento?

 R: Sì, puoi utilizzare le condizioni e unire i valori dei campi per determinare se un segnalibro deve essere mostrato o nascosto. È possibile personalizzare il codice del`ShowHideBookmarkedContent` funzione per tenere conto delle condizioni e dei valori appropriati.

#### D: Come posso eliminare un segnalibro in un documento Word utilizzando Aspose.Words per .NET?

 R: Per rimuovere un segnalibro in un documento Word utilizzando Aspose.Words per .NET, è possibile utilizzare il file`RemoveBookmarks` metodo del`Document` classe. Ecco un codice di esempio:

```csharp
doc.RemoveBookmarks("BookmarkName");
```