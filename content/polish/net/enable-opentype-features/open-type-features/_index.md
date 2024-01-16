---
title: Funkcje typu otwartego
linktitle: Funkcje typu otwartego
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak włączyć i używać funkcji typu otwartego w Aspose.Words dla .NET
type: docs
weight: 10
url: /pl/net/enable-opentype-features/open-type-features/
---

tym kompleksowym samouczku dowiesz się, jak włączyć i wykorzystać funkcje typu otwartego w Aspose.Words dla .NET. Przeprowadzimy Cię przez proces i udostępnimy niezbędne fragmenty kodu C#. Pod koniec tego przewodnika będziesz mógł pracować z funkcjami typu otwartego w dokumentach programu Word.

## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
- Biblioteka Aspose.Words dla .NET zainstalowana w Twoim systemie.

## Krok 1: Załaduj dokument
Na początek załaduj dokument korzystając z klasy Document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");
```

## Krok 2: Włącz funkcje typu otwartego
Aby włączyć funkcje typu otwartego, ustaw właściwość TextShaperFactory klasy LayoutOptions na instancję żądanej fabryki narzędzi do kształtowania tekstu. W tym przykładzie używamy HarfBuzzTextShaperFactory:

```csharp
doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;
```

## Krok 3: Zapisz dokument
Po włączeniu funkcji typu otwartego zapisz dokument w żądanym formacie wyjściowym, takim jak PDF:

```csharp
doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

### Przykładowy kod źródłowy funkcji typu otwartego przy użyciu Aspose.Words dla .NET
Oto kompletny kod źródłowy umożliwiający korzystanie z funkcji Open Type w Aspose.Words dla .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");

doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;

doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

## Wniosek
Gratulacje! Pomyślnie nauczyłeś się, jak włączać i wykorzystywać funkcje typu otwartego w Aspose.Words dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem i korzystając z dostarczonego kodu źródłowego, możesz teraz pracować z funkcjami typu otwartego w dokumentach programu Word.

Funkcje Open Type oferują ulepszone możliwości typografii i kształtowania tekstu, umożliwiając tworzenie atrakcyjnych wizualnie i profesjonalnie wyglądających dokumentów. Eksperymentuj z różnymi fabrykami narzędzi do kształtowania tekstu i odkrywaj możliwości funkcji Open Type w swoich projektach.

### Często zadawane pytania

#### P: Jak włączyć funkcje OpenType w Aspose.Words dla .NET?

Odp.: Aby włączyć funkcje OpenType w Aspose.Words dla .NET, musisz wykonać kroki wymienione w samouczku.

#### P: Jakie funkcje OpenType są obsługiwane w Aspose.Words dla .NET?

O: Aspose.Words dla .NET obsługuje kilka funkcji OpenType, takich jak ligatury, odmiany glifów, podstawienia kontekstowe i inne.

#### P: Jak mogę sprawdzić, czy dana czcionka obsługuje funkcję OpenType?

O: Możesz sprawdzić, czy funkcja OpenType jest obsługiwana w określonej czcionce, korzystając z narzędzia`Font.OpenTypeFeatures` metoda w Aspose.Words dla .NET.

#### P: Jakie inne funkcje formatowania tekstu obsługuje Aspose.Words dla .NET?

Odp.: Oprócz funkcji OpenType, Aspose.Words dla .NET obsługuje także inne funkcje formatowania tekstu, takie jak formatowanie akapitów, tworzenie tabel, dodawanie obrazów itp.

#### P: Czy mogę używać funkcji OpenType we wszystkich wersjach Aspose.Words dla .NET?

O: Funkcje OpenType są obsługiwane w nowszych wersjach Aspose.Words dla .NET. Aby móc korzystać z tych funkcji, upewnij się, że używasz kompatybilnej wersji.