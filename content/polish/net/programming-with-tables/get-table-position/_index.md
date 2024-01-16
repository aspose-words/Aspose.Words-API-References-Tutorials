---
title: Uzyskaj pozycję stołu
linktitle: Uzyskaj pozycję stołu
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak uzyskać pozycję tabeli w dokumencie programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-tables/get-table-position/
---

W tym samouczku nauczymy się, jak uzyskać pozycję tabeli w dokumencie programu Word za pomocą Aspose.Words dla .NET. Będziemy postępować zgodnie z przewodnikiem krok po kroku, aby zrozumieć kod i wdrożyć tę funkcję. Pod koniec tego samouczka będziesz mógł programowo uzyskać właściwości pozycjonowania tabeli w dokumentach programu Word.

## Krok 1: Konfiguracja projektu
1. Uruchom program Visual Studio i utwórz nowy projekt C#.
2. Dodaj odwołanie do biblioteki Aspose.Words dla .NET.

## Krok 2: Załadowanie dokumentu i dostęp do tabeli
Aby rozpocząć przetwarzanie tekstu z tabelą, musimy załadować dokument, który ją zawiera i uzyskać do niej dostęp. Wykonaj następujące kroki:

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Załaduj dokument
Document doc = new Document(dataDir + "Tables.docx");

// Dostęp do tablicy
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Pamiętaj, aby zastąpić „TWOJ KATALOG DOKUMENTÓW” rzeczywistą ścieżką do katalogu dokumentów. Upewnij się także, że dokument zawiera tabelę, której pozycję chcesz uzyskać.

## Krok 3: Uzyskanie właściwości pozycjonowania tablicy
Następnie sprawdzimy typ pozycjonowania tablicy i uzyskamy odpowiednie właściwości pozycjonowania. Użyj następującego kodu:

```csharp
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.RelativeHorizontalAlignment);
Console.WriteLine(table.RelativeVerticalAlignment);
}
else
{
Console.WriteLine(table.Alignment);
}
```

 Tutaj używamy warunku, aby sprawdzić, czy tablica jest typu float. Jeśli tak, drukujemy`RelativeHorizontalAlignment` I`RelativeVerticalAlignment` właściwości, aby uzyskać względne wyrównanie tabeli w poziomie i pionie. W przeciwnym razie drukujemy`Alignment` właściwość, aby uzyskać wyrównanie tablicy.

### Przykładowy kod źródłowy funkcji Get Table Position przy użyciu Aspose.Words dla platformy .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	if (table.TextWrapping == TextWrapping.Around)
	{
		Console.WriteLine(table.RelativeHorizontalAlignment);
		Console.WriteLine(table.RelativeVerticalAlignment);
	}
	else
	{
		Console.WriteLine(table.Alignment);
	}
```

## Wniosek
tym samouczku nauczyliśmy się, jak uzyskać pozycję tabeli w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Postępując zgodnie z tym przewodnikiem krok po kroku i wdrażając dostarczony kod C#, możesz programowo uzyskać właściwości pozycjonowania tabeli w dokumentach programu Word. Ta funkcja umożliwia analizowanie tablic i manipulowanie nimi zgodnie z ich określonymi pozycjami.