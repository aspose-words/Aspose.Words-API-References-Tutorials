---
title: Użyj znaków kontrolnych
linktitle: Użyj znaków kontrolnych
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący używania znaków kontrolnych w Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-document-properties/use-control-characters/
---

W tym samouczku przeprowadzimy Cię przez kod źródłowy C# dotyczący używania znaków kontrolnych w Aspose.Words dla .NET. Ta funkcja umożliwia manipulowanie znakami kontrolnymi w tekście.

## Krok 1: Konfiguracja projektu

Aby rozpocząć, utwórz nowy projekt C# w swoim ulubionym środowisku IDE. Upewnij się, że w Twoim projekcie znajduje się odwołanie do biblioteki Aspose.Words for .NET.

## Krok 2: Używanie znaków kontrolnych

W tym kroku będziemy używać znaków kontrolnych w tekście. Użyj następującego kodu:

```csharp
const string text = "test\r";
// Zamień znak kontrolny „\r” na „\r\n”.
string replace = text.Replace(ControlChar.Cr, ControlChar.CrLf);
```

 Ten kod definiuje a`text` ciąg zawierający znak kontrolny „\r” (nowa linia) i używa`Replace` metodę zastąpienia go znakiem kontrolnym „\r\n” (nowa linia). wiersz, po którym następuje podział wiersza).

### Przykładowy kod źródłowy użycia znaków kontrolnych przy użyciu Aspose.Words dla .NET

```csharp

	const string text = "test\r";
	// Zamień znak kontrolny „\r” na „\r\n”.
	string replace = text.Replace(ControlChar.Cr, ControlChar.CrLf);

```
 Możesz użyć powyższego kodu we własnym projekcie, zastępując plik`text` string z własnym tekstem zawierającym znaki kontrolne.

Nauczyłeś się teraz, jak używać znaków kontrolnych w Aspose.Words dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem zawartym w tym samouczku, możesz łatwo manipulować znakami kontrolnymi we własnych aplikacjach.