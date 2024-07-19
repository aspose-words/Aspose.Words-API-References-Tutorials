---
title: Automatyczne połączenie
linktitle: Automatyczne połączenie
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wstawić autolink za pomocą Aspose.Words dla .NET Przewodnik krok po kroku.
type: docs
weight: 10
url: /pl/net/working-with-markdown/autolink/
---

W tym przykładzie wyjaśnimy, jak używać funkcji „Autolink” w Aspose.Words dla .NET. Ta funkcja umożliwia automatyczne wstawianie hiperłączy do dokumentu.

## Krok 1: Korzystanie z generatora dokumentów

Najpierw użyjemy generatora dokumentów, aby dodać treść do naszego dokumentu.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Krok 2: Wstawianie hiperłącza

 Hiperłącze możemy wstawić za pomocą`InsertHyperlink` metoda generatora dokumentów. Podajemy adres URL i tekst, który będzie wyświetlany dla linku.

```csharp
builder.InsertHyperlink("https://www.aspose.com”, „https://www.aspose.com”, fałsz);
```

## Krok 3: Wstawianie adresu e-mail jako linku

Jako link możemy także wstawić adres e-mail, korzystając z przedrostka „mailto:”. Umożliwi to użytkownikom kliknięcie łącza w celu otwarcia domyślnego klienta poczty e-mail.

```csharp
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```

## Krok 4: Zapisanie dokumentu

Wreszcie możemy zapisać dokument w żądanym formacie.

### Przykładowy kod źródłowy dla Autolink przy użyciu Aspose.Words dla .NET


```csharp
// Użyj narzędzia do tworzenia dokumentów, aby dodać treść do dokumentu.
DocumentBuilder builder = new DocumentBuilder();

//Wstaw łącze.
builder.InsertHyperlink("https://www.aspose.com”, „https://www.aspose.com”, fałsz);
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```


Gratulacje! Nauczyłeś się teraz, jak korzystać z funkcji „Autolink” w Aspose.Words dla .NET.


### Często zadawane pytania

#### P: Jak mogę utworzyć automatyczne łącze do adresu URL w Aspose.Words?

 O: Aby utworzyć automatyczne łącze do adresu URL w Aspose.Words, możesz użyć metody`<a>` tag z`href` atrybut zawierający adres URL. Możesz na przykład użyć`<a href="https://www.aspose.com">https://www.aspose.com</a>` aby automatycznie połączyć się z „https: //www.aspose.com”.

#### P: Czy można dostosować tekst wyświetlany w automatycznym łączu w Aspose.Words?

 Odp.: Tak, możesz dostosować wyświetlany tekst automatycznego łącza w Aspose.Words. Zamiast używać adresu URL jako wyświetlanego tekstu, możesz użyć dowolnego innego tekstu, zastępując treść pomiędzy`<a>` tagi. Możesz na przykład użyć`<a href="https://www.aspose.com">Click here</a>` aby wyświetlić tekst „Kliknij tutaj” jako automatyczny link.

#### P: Jak mogę dodać dodatkowe atrybuty do autolinku w Aspose.Words?

O: Aby dodać dodatkowe atrybuty do automatycznego łącza w Aspose.Words, możesz użyć dodatkowych atrybutów HTML wewnątrz`<a>` etykietka. Możesz na przykład użyć`<a href="https://www.aspose.com" target="_blank">Link</a>` aby otworzyć łącze w nowym oknie lub nowej karcie za pomocą przycisku` attribute target="_blank"`.