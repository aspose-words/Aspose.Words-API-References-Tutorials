---
title: Połączyć
linktitle: Połączyć
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wstawiać linki za pomocą Aspose.Words dla .NET. Przewodnik krok po kroku.
type: docs
weight: 10
url: /pl/net/working-with-markdown/link/
---

W tym przykładzie przeprowadzimy Cię przez proces korzystania z funkcji łączy w Aspose.Words dla .NET. Linki służą do tworzenia klikalnych odnośników do stron internetowych lub innych dokumentów.

## Krok 1: Korzystanie z generatora dokumentów

Najpierw użyjemy generatora dokumentów, aby dodać treść do naszego dokumentu.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Krok 2: Wstawianie linku

 Link możemy wstawić za pomocą`InsertHyperlink` metoda generatora dokumentów. Musimy określić tekst linku, tutaj „Aspose”, a także docelowy adres URL.

```csharp
builder.InsertHyperlink("Aspose", "https://www.aspose.com”, fałsz);
```

### Przykładowy kod źródłowy linków z Aspose.Words dla .NET


```csharp
// Użyj narzędzia do tworzenia dokumentów, aby dodać treść do dokumentu.
DocumentBuilder builder = new DocumentBuilder();

// Wstaw link.
builder.InsertHyperlink("Aspose", "https://www.aspose.com”, fałsz);
```
Gratulacje! Nauczyłeś się teraz, jak korzystać z funkcji łączy w Aspose.Words dla .NET.


### Często zadawane pytania

#### P: Jak mogę utworzyć link do adresu URL w Aspose.Words?

 O: Aby połączyć się z adresem URL w Aspose.Words, możesz użyć metody`<a>` tag z`href` atrybut zawierający adres URL. Możesz na przykład użyć`<a href="https://www.aspose.com">Click Here</a>` do hiperłącza do adresu URL „https://www.example.com” z wyświetlanym tekstem „Kliknij tutaj”.

#### P: Czy możliwe jest utworzenie łącza do wewnętrznej zakładki w Aspose.Words?

 O: Tak, możliwe jest utworzenie łącza do wewnętrznej zakładki w Aspose.Words. Możesz skorzystać z`<a>` tag z`href` atrybut zawierający nazwę zakładki poprzedzoną hashem (#). Na przykład,`<a href="#bookmark1">Go to bookmark 1</a>` spowoduje utworzenie łącza do zakładki o nazwie „zakładka1” w dokumencie.

#### P: Jak mogę dostosować wyświetlany tekst łącza w Aspose.Words?

 Odp.: Aby dostosować wyświetlany tekst łącza w Aspose.Words, możesz modyfikować zawartość między`<a>` tagi. Na przykład,`<a href="https://www.aspose.com">Click here</a>` wyświetli tekst „Kliknij tutaj” jako hiperłącze.

#### P: Czy mogę określić cel łącza w Aspose.Words?

O: Tak, możesz określić cel łącza w Aspose.Words za pomocą`target` atrybut`<a>` etykietka. Na przykład,`<a href="https://www.aspose.com" target="_blank">Open in new window</a>` otworzy link w nowym oknie lub nowej karcie.