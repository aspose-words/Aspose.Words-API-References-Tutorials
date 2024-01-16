---
title: Scal dokumenty Worda
linktitle: Połącz dokumenty
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak scalić wiele dokumentów programu Word za pomocą Aspose.Words dla .NET. Ten potężny interfejs API upraszcza proces łączenia dokumentów, czyniąc go wydajnym i prostym.
type: docs
weight: 10
url: /pl/net/split-document/merge-documents/
---

W tym samouczku przeprowadzimy Cię przez proces scalania wielu dokumentów programu Word za pomocą funkcji Scal dokumenty w Aspose.Words dla .NET. Wykonaj poniższe kroki, aby zrozumieć kod źródłowy i uzyskać scalony dokument zawierający wszystkie dokumenty źródłowe.

## Krok 1: Wyszukaj dokumenty do scalania

Przed połączeniem dokumentów musimy zlokalizować dokumenty źródłowe, które mają zostać scalone. Oto jak:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Wyszukaj dokumenty do scalania.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
.GetFileSystemInfos("SplitDocument.PageParPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
Directory.GetFiles(dataDir, "SplitDocument.PageParPage_1.docx", SearchOption.TopDirectoryOnly)[0];
```

## Krok 2: Połącz dokumenty

Teraz połączymy dokumenty jeden po drugim, aby utworzyć ostateczny scalony dokument. Oto jak:

```csharp
// Otwórz pierwszą część powstałego dokumentu.
Document sourceDoc = new Document(sourceDocumentPath);

// Utwórz nowy dokument wynikowy.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// Połącz dokumenty jeden po drugim.
foreach(FileSystemInfo documentPath in documentPaths)
{
if (documentPath.FullName == sourceDocumentPath)
keep on going;

mergedDocBuilder.MoveToDocumentEnd();
mergedDocBuilder.InsertDocument(sourceDoc, ImportFormatMode.KeepSourceFormatting);
sourceDoc = new Document(documentPath.FullName);
}

mergedDoc.Save(dataDir + "SplitDocument.MergeDocuments.docx");
```

### Przykładowy kod źródłowy dla scalania dokumentów przy użyciu Aspose.Words dla .NET

Oto kompletny kod źródłowy funkcji scalania dokumentów w Aspose.Words dla .NET:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Znajdź dokumenty używane do scalania.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
	.GetFileSystemInfos("SplitDocument.PageByPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
	Directory.GetFiles(dataDir, "SplitDocument.PageByPage_1.docx", SearchOption.TopDirectoryOnly)[0];

// Otwórz pierwszą część powstałego dokumentu.
Document sourceDoc = new Document(sourceDocumentPath);

// Utwórz nowy dokument wynikowy.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// Scal części dokumentu jedna po drugiej.
foreach (FileSystemInfo documentPath in documentPaths)
{
	if (documentPath.FullName == sourceDocumentPath)
		continue;

	mergedDocBuilder.MoveToDocumentEnd();
	mergedDocBuilder.InsertDocument(sourceDoc, ImportFormatMode.KeepSourceFormatting);
	sourceDoc = new Document(documentPath.FullName);
}

mergedDoc.Save(dataDir + "SplitDocument.MergeDocuments.docx");
```

## Wniosek

Gratulacje! Nauczyłeś się, jak łączyć wiele dokumentów programu Word za pomocą funkcji Scal dokumenty w Aspose.Words dla .NET. Postępując zgodnie z dostarczonym kodem źródłowym, możesz połączyć oddzielne dokumenty w jeden scalony dokument, zachowując jednocześnie formatowanie każdego dokumentu źródłowego.

Łączenie dokumentów może być przydatne, gdy chcesz skonsolidować informacje z wielu źródeł lub utworzyć jednolity dokument z poszczególnych części. Aspose.Words dla .NET zapewnia potężne API, które upraszcza proces łączenia dokumentów, czyniąc go wydajnym i prostym.

Zachęcamy do zapoznania się z innymi funkcjami oferowanymi przez Aspose.Words dla .NET, aby zwiększyć możliwości przetwarzania dokumentów i usprawnić przepływ pracy.

### Często zadawane pytania

#### Jak scalić dokumenty o różnym formatowaniu?

 Podczas łączenia dokumentów Aspose.Words dla .NET udostępnia opcję zachowania formatowania każdego dokumentu źródłowego. Korzystając z`ImportFormatMode.KeepSourceFormatting` opcji, scalony dokument zachowa formatowanie oryginalnych dokumentów. Jeśli chcesz zastosować spójne formatowanie w całym scalonym dokumencie, możesz zmodyfikować formatowanie za pomocą interfejsu API Aspose.Words po połączeniu dokumentów.

#### Czy mogę łączyć dokumenty w różnych formatach?

Tak, Aspose.Words dla .NET obsługuje łączenie dokumentów w różnych formatach, w tym DOCX, DOC, RTF i innych. Możesz załadować dokumenty w różnych formatach do API Aspose.Words i połączyć je w jeden dokument, niezależnie od ich oryginalnych formatów.

#### Czy mogę łączyć dokumenty o złożonych strukturach, takich jak tabele i obrazy?

Absolutnie! Aspose.Words dla .NET umożliwia łączenie dokumentów o złożonych strukturach, w tym tabelach, obrazach, nagłówkach, stopkach i innych. Interfejs API obsługuje proces łączenia, zachowując integralność i układ treści w każdym dokumencie.

#### Czy możliwe jest łączenie dokumentów o różnych orientacjach i rozmiarach stron?

Tak, Aspose.Words dla .NET obsługuje dokumenty o różnych orientacjach stron i rozmiarach podczas procesu łączenia. Powstały scalony dokument będzie uwzględniał różne orientacje stron i rozmiary dokumentów źródłowych.