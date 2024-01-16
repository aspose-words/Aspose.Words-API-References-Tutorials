---
title: Uruchom ponownie listę w każdej sekcji
linktitle: Uruchom ponownie listę w każdej sekcji
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak zresetować listę numerowaną dla każdej sekcji dokumentu programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-list/restart-list-at-each-section/
---

W tym samouczku krok po kroku pokażemy, jak zresetować listę numerowaną dla każdej sekcji dokumentu programu Word przy użyciu Aspose.Words dla .NET. Wyjaśnimy dostarczony kod źródłowy C# i pokażemy, jak zaimplementować go we własnych projektach.

 Aby rozpocząć, upewnij się, że masz zainstalowane i skonfigurowane Aspose.Words for .NET w swoim środowisku programistycznym. Jeśli jeszcze tego nie zrobiłeś, pobierz i zainstaluj bibliotekę z[Aspose.Releases]https://releases.aspose.com/words/net/.

## Krok 1: Tworzenie dokumentu i listy

Najpierw utwórz nowy dokument i dodaj domyślną listę numerowaną:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;
```

## Krok 2: Dodawanie pozycji do listy

 Następnie użyj A`DocumentBuilder` aby dodać pozycje do listy. Możesz użyć pętli, aby dodać wiele elementów do listy:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
     builder.Writeln($"List item {i}");

     if (i == 15)
         builder.InsertBreak(BreakType.SectionBreakNewPage);
}
```

W tym przykładzie wstawiamy podział sekcji po 15. elemencie listy, aby zilustrować zmianę numeracji.

## Krok 3: Zapisz zmodyfikowany dokument

Na koniec zapisz zmodyfikowany dokument:

```csharp
OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);
```

Więc ! Pomyślnie zresetowałeś listę numerowaną dla każdej sekcji dokumentu programu Word przy użyciu Aspose.Words dla .NET.

### Przykładowy kod źródłowy do resetowania listy w każdej sekcji

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;

DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
	 builder.Writeln($"List item {i}");

	 if (i == 15)
		 builder.InsertBreak(BreakType.SectionBreakNewPage);
}

OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);

```

Możesz swobodnie używać tego kodu we własnych projektach i modyfikować go tak, aby odpowiadał Twoim konkretnym potrzebom.

### Często zadawane pytania

#### P: Jak mogę ponownie uruchomić listę w każdej sekcji Aspose.Words?

 O: Aby zrestartować listę w każdej sekcji Aspose.Words, musisz utworzyć instancję`List` class i przypisz do niej listę numerowaną. Następnie możesz użyć`List.IsRestartAtEachSection` aby określić, że numeracja powinna być rozpoczynana od nowa w każdej sekcji. Możesz powiązać tę listę z jedną lub kilkoma sekcjami dokumentu, aby numeracja została poprawnie wznowiona w każdej sekcji.

#### P: Czy mogę dostosować format numeracji list w Aspose.Words?

O: Tak, możesz dostosować format numeracji list w Aspose.Words. The`List` class oferuje do tego kilka właściwości, takich jak`List.ListFormat.ListType`, `List.ListLevels`, `ListLevel.NumberFormat`itp. Możesz użyć tych właściwości, aby ustawić typ listy (numerowana, punktowana itp.), format numeracji (cyfry arabskie, cyfry rzymskie, litery itp.) i inne opcje formatowania numeracji.

#### P: Czy można dodać dodatkowe poziomy do listy numerowanej w Aspose.Words?

 O: Tak, możliwe jest dodanie dodatkowych poziomów do listy numerowanej w Aspose.Words. The`ListLevel` class umożliwia ustawienie właściwości formatowania dla każdego poziomu listy. Możesz ustawić opcje takie jak przedrostek, przyrostek, wyrównanie, wcięcie itp. Umożliwia to tworzenie list o wielu poziomach hierarchii.