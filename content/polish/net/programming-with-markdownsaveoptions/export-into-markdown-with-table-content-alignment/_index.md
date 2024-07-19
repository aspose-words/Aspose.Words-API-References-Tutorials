---
title: Eksportuj do Markdown z wyrównaniem zawartości tabeli
linktitle: Eksportuj do Markdown z wyrównaniem zawartości tabeli
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak eksportować zawartość tabeli z różnymi wyrównaniami do plików Markdown za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-markdownsaveoptions/export-into-markdown-with-table-content-alignment/
---
Oto przewodnik krok po kroku wyjaśniający następujący kod źródłowy języka C#, który pomaga eksportować zawartość do pliku Markdown z wyrównaniem zawartości tabeli przy użyciu biblioteki Aspose.Words dla platformy .NET. Zanim użyjesz tego kodu, upewnij się, że w swoim projekcie umieściłeś bibliotekę Aspose.Words.

## Krok 1: Ustaw ścieżkę katalogu dokumentów

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Pamiętaj, aby podać poprawną ścieżkę do katalogu dokumentów, w którym zostanie zapisany edytowany dokument.

## Krok 2: Utwórz dokument i generator dokumentów

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Tutaj tworzymy instancję`Document` klasa i instancja`DocumentBuilder` klasa, która pozwoli nam manipulować dokumentem i dodawać elementy.

## Krok 3: Wstaw komórki do tabeli z różnymi wyrównaniami akapitów

```csharp
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Cell1");
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Write("Cell2");
```

Używamy Konstruktora dokumentów, aby wstawiać komórki do tabeli i ustawiać różne wyrównania akapitów dla każdej komórki.

## Krok 4: Ustaw opcje eksportu Markdown i zapisz zmodyfikowany dokument

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
{
     TableContentAlignment = TableContentAlignment.Left
};
doc.Save(dataDir + "Content_table_left_alignment.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Right;
doc.Save(dataDir + "Content_table_right_alignment.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Center;
doc.Save(dataDir + "Content_table_alignment_center.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Auto;
doc.Save(dataDir + "Content_table_auto_alignment.md", saveOptions);
```

Ustawiamy opcje eksportu Markdown z różnymi wyrównaniami zawartości tabeli, a następnie zapisujemy zmodyfikowany dokument, korzystając z każdej opcji wyrównania.

### Przykładowy kod źródłowy do eksportu do Markdown z wyrównaniem zawartości tabeli przy użyciu Aspose.Words dla .NET

```csharp

            
	// Ścieżka do katalogu dokumentów.
    string dataDir = "YOUR DOCUMENT DIRECTORY";
	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
	builder.Write("Cell1");
	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Write("Cell2");

	// Wyrównuje wszystkie akapity wewnątrz tabeli.
	MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
	{
		TableContentAlignment = TableContentAlignment.Left
	};
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.LeftTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Right;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.RightTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Center;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.CenterTableContentAlignment.md", saveOptions);

	// Wyrównanie w tym przypadku zostanie wzięte z pierwszego akapitu w odpowiedniej kolumnie tabeli.
	saveOptions.TableContentAlignment = TableContentAlignment.Auto;
	
	// Zapisz zmodyfikowany dokument
	doc.Save(dataDir + "WorkingWithMarkdownSaveOptions.AutoTableContentAlignment.md", saveOptions);
            
        
```
