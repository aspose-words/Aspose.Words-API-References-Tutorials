---
title: Uzyskaj pozycję pływającego stołu
linktitle: Uzyskaj pozycję pływającego stołu
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak uzyskać pozycję tabel pływających w dokumencie programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-tables/get-floating-table-position/
---

W tym samouczku dowiemy się, jak uzyskać pozycję tabeli pływającej w dokumencie programu Word za pomocą Aspose.Words dla .NET. Będziemy postępować zgodnie z przewodnikiem krok po kroku, aby zrozumieć kod i wdrożyć tę funkcję. Pod koniec tego samouczka będziesz mógł programowo uzyskać właściwości pozycjonowania tabeli pływającej w dokumentach programu Word.

## Krok 1: Konfiguracja projektu
1. Uruchom program Visual Studio i utwórz nowy projekt C#.
2. Dodaj odwołanie do biblioteki Aspose.Words dla .NET.

## Krok 2: Ładowanie dokumentu i uzyskiwanie dostępu do tabel
Aby rozpocząć przetwarzanie tekstu z tabelami, musimy załadować dokument, który je zawiera i uzyskać do nich dostęp. Wykonaj następujące kroki:

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Załaduj dokument
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Pamiętaj, aby zastąpić „TWOJ KATALOG DOKUMENTÓW” rzeczywistą ścieżką do katalogu dokumentów. Upewnij się także, że dokument zawiera tabele pływające.

## Krok 3: Uzyskanie właściwości pozycjonowania stołu pływającego
Następnie przeszukamy wszystkie tabele w dokumencie i uzyskamy właściwości pozycjonowania tabel ruchomych. Użyj następującego kodu:

```csharp
foreach(Table table in doc.FirstSection.Body.Tables)
{
// Jeśli tablica jest typu zmiennoprzecinkowego, wydrukuj jej właściwości pozycjonowania.
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.HorizontalAnchor);
Console.WriteLine(table.VerticalAnchor);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.AbsoluteVerticalDistance);
Console.WriteLine(table.AllowOverlap);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.RelativeVerticalAlignment);
Console.WriteLine("...............................");
}
}
```

 Tutaj używamy a`foreach` pętla do przeglądania wszystkich tablic w dokumencie. Sprawdzamy, czy tablica jest typu float, sprawdzając`TextWrapping` nieruchomość. Jeśli tak, drukujemy właściwości pozycjonowania tabeli, takie jak kotwica pozioma, kotwica pionowa, bezwzględne odległości poziome i pionowe, zezwolenie na nakładanie się, bezwzględna odległość pozioma i względne wyrównanie w pionie.
 
### Przykładowy kod źródłowy funkcji Get Floating Table Position przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	foreach (Table table in doc.FirstSection.Body.Tables)
	{
		// Jeśli tabela jest typu pływającego, wydrukuj jej właściwości pozycjonowania.
		if (table.TextWrapping == TextWrapping.Around)
		{
			Console.WriteLine(table.HorizontalAnchor);
			Console.WriteLine(table.VerticalAnchor);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.AbsoluteVerticalDistance);
			Console.WriteLine(table.AllowOverlap);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.RelativeVerticalAlignment);
			Console.WriteLine("..............................");
		}
	}
```

## Wniosek
tym samouczku nauczyliśmy się, jak uzyskać pozycję tabeli pływającej w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Postępując zgodnie z tym przewodnikiem krok po kroku i wdrażając dostarczony kod C#, możesz programowo uzyskać właściwości pozycjonowania tabel pływających w dokumentach programu Word. Ta funkcja umożliwia analizowanie tabel pływających i manipulowanie nimi zgodnie z konkretnymi potrzebami.