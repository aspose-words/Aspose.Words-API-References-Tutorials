---
title: Wstaw pływający obraz do dokumentu programu Word
linktitle: Wstaw pływający obraz do dokumentu programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wstawiać pływające obrazy w dokumentach programu Word przy użyciu Aspose.Words dla .NET. Przewodnik krok po kroku.
type: docs
weight: 10
url: /pl/net/add-content-using-documentbuilder/insert-floating-image/
---
tym kompleksowym przykładzie dowiesz się, jak wstawić pływający obraz do dokumentu programu Word przy użyciu Aspose.Words dla .NET. Przeprowadzimy Cię przez proces i udostępnimy niezbędne fragmenty kodu C#. Pod koniec tego przewodnika będziesz mógł dodawać do swoich dokumentów obrazy z dostosowywalnymi opcjami pozycjonowania i zawijania.

## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
- Biblioteka Aspose.Words dla .NET zainstalowana w Twoim systemie.

## Krok 1: Utwórz nowy dokument i narzędzie DocumentBuider
Aby rozpocząć, utwórz nowy dokument za pomocą klasy Document i zainicjuj obiekt DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Wstaw pływający obraz
Następnie użyj metody InsertImage klasy DocumentBuilder, aby wstawić pływający obraz. Podaj ścieżkę pliku obrazu, względną pozycję w poziomie i pionie, szerokość, wysokość i opcje zawijania jako parametry:

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png",
	RelativeHorizontalPosition.Margin,
	100,
	RelativeVerticalPosition.Margin,
	100,
	200,
	100,
	WrapType.Square);
```

## Krok 3: Zapisz dokument
Po wstawieniu obrazu pływającego należy zapisać dokument do pliku korzystając z metody Save klasy Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
```

## Przykładowy kod źródłowy dla wstawiania pływającego obrazu przy użyciu Aspose.Words dla .NET
Oto kompletny kod źródłowy do wstawiania pływającego obrazu przy użyciu Aspose.Words dla .NET:
Pływające obrazy są przydatne w różnych scenariuszach, takich jak dodawanie logo, ilustracji lub elementów dekoracyjnych, które można umieszczać niezależnie od tekstu dokumentu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(ImagesDir + "Transparent background logo.png",
	RelativeHorizontalPosition.Margin,
	100,
	RelativeVerticalPosition.Margin,
	100,
	200,
	100,
	WrapType.Square);

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
```

Pamiętaj, aby dostosować kod do swoich konkretnych wymagań, w tym ścieżki pliku obrazu oraz żądanych opcji pozycjonowania i zawijania.

## Wniosek
Gratulacje! Pomyślnie nauczyłeś się, jak wstawić pływający obraz do dokumentu programu Word przy użyciu Aspose.Words dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem i korzystając z dostarczonego kodu źródłowego, możesz teraz wzbogacić swoje dokumenty o atrakcyjne wizualnie i konfigurowalne pływające obrazy.

### Często zadawane pytania dotyczące wstawiania pływającego obrazu w dokumencie programu Word

#### P: Czy mogę wstawić wiele ruchomych obrazów w jednym dokumencie?

Odp.: Oczywiście! Możesz wstawić dowolną liczbę pływających obrazów do dokumentu programu Word za pomocą Aspose.Words dla .NET. Po prostu powtórz proces wstawiania, aby dodać wiele atrakcyjnych wizualnie obrazów.

#### P: Jakie opcje zawijania są dostępne dla pływającego obrazu?

Odp.: Aspose.Words dla .NET udostępnia różne opcje zawijania pływających obrazów, w tym Kwadrat, Ciasno, Przez, TopBottom i Brak. Opcje te określają sposób interakcji tekstu z pływającym obrazem.

#### P: Czy mogę dostosować rozmiar pływającego obrazu?

Odp.: Absolutnie! Możesz określić szerokość i wysokość pływającego obrazu za pomocą odpowiednich parametrów w metodzie InsertImage. Dzięki temu możesz kontrolować wymiary obrazu zgodnie z preferencjami projektowymi.

#### P: Czy mogę ustawić pływający obraz względem określonego elementu w dokumencie?

O: Tak, Aspose.Words dla .NET umożliwia położenie pływającego obrazu względem określonych elementów, takich jak margines, strona, akapit lub tabela. Możesz wybrać odpowiednie względne parametry pozycji poziomej i pionowej, aby osiągnąć żądane położenie.

#### P: Czy Aspose.Words dla .NET jest odpowiedni zarówno dla aplikacji stacjonarnych, jak i internetowych?

O: Tak, Aspose.Words dla .NET to wszechstronna biblioteka odpowiednia zarówno dla aplikacji komputerowych, jak i internetowych. Niezależnie od tego, czy tworzysz aplikację Windows, czy system internetowy, możesz bez wysiłku zintegrować bibliotekę.
