---
title: Podziel dokument programu Word według nagłówków HTML
linktitle: Według nagłówków HTML
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku wyjaśniający kod źródłowy C# podzielonego dokumentu słownego. Nagłówek Funkcja HTML Aspose.Words dla .NET
type: docs
weight: 10
url: /pl/net/split-document/by-headings-html/
---
W tym samouczku przeprowadzimy Cię przez proces dzielenia dokumentu programu Word na mniejsze części za pomocą funkcji Według nagłówka HTML w Aspose.Words dla .NET. Wykonaj poniższe kroki, aby zrozumieć kod źródłowy i wygenerować osobne dokumenty HTML w oparciu o nagłówek.

## Krok 1: Ładowanie dokumentu

Aby rozpocząć, określ katalog dla swojego dokumentu i załaduj dokument do obiektu Document. Oto jak:

```csharp
//Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## Krok 2: Podzielenie dokumentu według nagłówka w formacie HTML

Teraz ustawimy opcje zapisywania, aby podzielić dokument na mniejsze części w oparciu o nagłówek w formacie HTML. Oto jak:

```csharp
HtmlSaveOptions options = new HtmlSaveOptions
{
// Podziel dokument na mniejsze części, w tym przypadku oddzielając je według tytułu.
DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};

doc.Save(dataDir + "SplitDocument.ParTitresHtml.html", options);
```

### Przykładowy kod źródłowy By Headings HTML przy użyciu Aspose.Words dla .NET

Oto kompletny kod źródłowy funkcji By HTML Heading w Aspose.Words dla .NET:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");

HtmlSaveOptions options = new HtmlSaveOptions
{
	// Podziel dokument na mniejsze części, w tym przypadku według nagłówków.
	DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};


doc.Save(dataDir + "SplitDocument.ByHeadingsHtml.html", options);
```

Dzięki temu kodowi będziesz mógł podzielić dokument Worda na mniejsze części przy użyciu Aspose.Words dla .NET, w oparciu o nagłówki. Następnie możesz wygenerować osobne dokumenty HTML dla każdej części.

## Wniosek

 W tym samouczku nauczyliśmy się dzielić dokument programu Word na mniejsze części za pomocą funkcji Według nagłówka HTML w Aspose.Words dla .NET. Określając`DocumentSplitCriteria` Jak`HeadingParagraph` w`HtmlSaveOptions`, byliśmy w stanie wygenerować osobne dokumenty HTML w oparciu o nagłówki obecne w oryginalnym dokumencie.

Podział dokumentu według nagłówków może być przydatny do organizowania treści i zarządzania nią, szczególnie w przypadku dużych dokumentów zawierających wiele sekcji. Aspose.Words dla .NET zapewnia niezawodne i wydajne rozwiązanie do obsługi dzielenia dokumentów i generowania wyników w różnych formatach.

Zachęcamy do zapoznania się z dodatkowymi funkcjami i opcjami Aspose.Words dla .NET, aby jeszcze bardziej ulepszyć możliwości przetwarzania dokumentów i usprawnić przepływ pracy.

### Często zadawane pytania

#### Jak podzielić dokument programu Word na mniejsze części w oparciu o nagłówki przy użyciu Aspose.Words dla .NET?

 Aby podzielić dokument programu Word na podstawie nagłówków, możesz użyć funkcji Według nagłówka HTML w Aspose.Words dla .NET. Postępuj zgodnie z dostarczonym kodem źródłowym i ustaw`DocumentSplitCriteria` Do`HeadingParagraph` w`HtmlSaveOptions` obiekt. Spowoduje to podzielenie dokumentu na mniejsze części w każdym nagłówku.

#### Na jakie formaty mogę podzielić dokument Word?

 Dostarczony kod źródłowy demonstruje podział dokumentu Word na mniejsze części w formacie HTML. Jednak Aspose.Words dla .NET obsługuje różne formaty wyjściowe, w tym DOCX, PDF, EPUB i inne. Możesz zmodyfikować kod i określić żądany format wyjściowy w pliku`HtmlSaveOptions` odpowiednio sprzeciwić się.

#### Czy mogę wybrać inne kryteria podziału dokumentu?

Tak, możesz wybrać inne kryteria podziału dokumentu w zależności od swoich wymagań. Aspose.Words dla .NET udostępnia kilka opcji kryteriów, takich jak`HeadingParagraph`, `Page`, `Section` , i więcej. Zmodyfikuj`DocumentSplitCriteria` nieruchomość w`HtmlSaveOptions` obiektu, aby wybrać odpowiednie kryteria podziału.

#### Jak mogę dostosować wyjściowy kod HTML dla podzielonych części?

 Aspose.Words dla .NET umożliwia dostosowanie wyjściowego kodu HTML dla podzielonych części poprzez określenie dodatkowych opcji w`HtmlSaveOptions` obiekt. Możesz kontrolować różne aspekty, takie jak style CSS, obrazy, czcionki i inne. Więcej szczegółów na temat dostosowywania wyjścia HTML można znaleźć w dokumentacji Aspose.Words.

#### Czy mogę podzielić dokument na podstawie wielu kryteriów?

 Tak, możesz podzielić dokument na podstawie wielu kryteriów, łącząc odpowiednio opcje kryteriów. Na przykład możesz podzielić dokument według nagłówka i strony, ustawiając opcję`DocumentSplitCriteria`własność do`HeadingParagraph | Page`. Spowoduje to podzielenie dokumentu według każdego nagłówka i każdej strony, tworząc mniejsze części w oparciu o oba kryteria.