---
title: Kotwica pionowa
linktitle: Kotwica pionowa
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak ustawić kształt w pionie w dokumencie, korzystając z funkcji zakotwiczenia pionowego w Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-shapes/vertical-anchor/
---

W tym samouczku wyjaśniono, jak używać funkcji zakotwiczenia pionowego w Aspose.Words dla .NET, aby ustawić kształt w pionie w dokumencie. Ustawiając właściwość zakotwiczenia pionowego kształtu, możesz kontrolować jego wyrównanie w pionie względem tekstu lub strony.

## Warunki wstępne
Aby skorzystać z tego samouczka, musisz mieć następujące elementy:

- Zainstalowana biblioteka Aspose.Words dla .NET.
- Podstawowa znajomość języka C# i przetwarzania tekstów w dokumentach Word.

## Krok 1: Skonfiguruj katalog dokumentów
 Zacznij od ustawienia ścieżki do katalogu dokumentów. Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu, w którym chcesz zapisać dokument.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Utwórz nowy dokument i narzędzie DocumentBuider
 Utwórz nową instancję`Document` klasa i A`DocumentBuilder` sprzeciwić się pracy z dokumentem.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Wstaw i skonfiguruj kształt
Wstaw kształt do dokumentu za pomocą`InsertShape` metoda`DocumentBuilder` obiekt. Ustaw żądane wymiary kształtu.

```csharp
Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
```

## Krok 4: Ustaw kotwicę pionową
Ustaw właściwość zakotwiczenia pionowego kształtu, aby kontrolować jego wyrównanie w pionie. W tym przykładzie ustawiliśmy go na „Dół”, aby zakotwiczyć kształt na dole tekstu lub strony.

```csharp
textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
```

## Krok 5: Dodaj zawartość do kształtu
 Użyj`MoveTo` metoda`DocumentBuilder` obiekt, aby przenieść kursor do pierwszego akapitu kształtu. Następnie skorzystaj z`Write` metoda dodawania zawartości do kształtu.

```csharp
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Textbox contents");
```

## Krok 6: Zapisz dokument
 Zapisz dokument w określonym katalogu za pomocą`Save` metoda. Podaj żądaną nazwę pliku z odpowiednim rozszerzeniem. W tym przykładzie zapisujemy dokument jako „WorkingWithShapes.VerticalAnchor.docx”.

```csharp
doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

### Przykładowy kod źródłowy dla Anchor pionowy przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
	textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
	builder.MoveTo(textBox.FirstParagraph);
	builder.Write("Textbox contents");
	doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

Otóż to! Pomyślnie użyłeś funkcji zakotwiczenia pionowego w Aspose.Words dla .NET, aby ustawić kształt w pionie w dokumencie.