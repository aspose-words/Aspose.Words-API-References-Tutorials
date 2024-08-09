---
title: Zmień pole Aktualizuj źródło kultury
linktitle: Zmień pole Aktualizuj źródło kultury
second_title: Aspose.Words API do przetwarzania dokumentów
description: Z tego przewodnika dowiesz się, jak zmienić źródło kultury aktualizacji pola w Aspose.Words dla .NET. Z łatwością kontroluj formatowanie daty w oparciu o różne kultury.
type: docs
weight: 10
url: /pl/net/working-with-fields/change-field-update-culture-source/
---
## Wstęp

W tym samouczku zagłębimy się w świat Aspose.Words dla .NET i odkryjemy, jak zmienić źródło kultury aktualizacji pola. Jeśli masz do czynienia z dokumentami programu Word zawierającymi pola daty i chcesz kontrolować sposób formatowania tych dat w zależności od różnych kultur, ten przewodnik jest dla Ciebie. Przeanalizujmy proces krok po kroku, upewniając się, że rozumiesz każdą koncepcję i potrafisz ją skutecznie zastosować w swoich projektach.

## Warunki wstępne

Zanim przejdziemy do kodu, upewnij się, że masz następujące elementy:

-  Aspose.Words dla .NET: Możesz go pobrać z[Tutaj](https://releases.aspose.com/words/net/).
- Środowisko programistyczne: dowolne IDE kompatybilne z .NET (np. Visual Studio).
- Podstawowa znajomość języka C#: W tym samouczku założono, że masz podstawową wiedzę na temat programowania w języku C#.

## Importuj przestrzenie nazw

Najpierw zaimportujmy niezbędne przestrzenie nazw dla naszego projektu. Dzięki temu będziemy mieli dostęp do wszystkich wymaganych klas i metod udostępnianych przez Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

Teraz podzielmy przykład na wiele kroków, które pomogą Ci zrozumieć, jak zmienić źródło kultury aktualizacji pola w Aspose.Words dla .NET.

## Krok 1: Zainicjuj dokument

 Pierwszym krokiem jest utworzenie nowej instancji pliku`Document` klasa i A`DocumentBuilder`. Stanowi to podstawę do tworzenia i manipulowania naszym dokumentem Word.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Wstaw pola z określonymi ustawieniami regionalnymi

Następnie musimy wstawić pola do dokumentu. W tym przykładzie wstawimy dwa pola daty. Ustawimy ustawienia regionalne czcionki na niemieckie (LocaleId = 1031), aby zademonstrować, jak kultura wpływa na format daty.

```csharp
builder.Font.LocaleId = 1031; // niemiecki
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");
```

## Krok 3: Ustaw źródło kultury aktualizacji pola

 Aby kontrolować kulturę używaną podczas aktualizowania pól, ustawiamy`FieldUpdateCultureSource` własność`FieldOptions`klasa. Ta właściwość określa, czy kultura jest pobierana z kodu pola, czy z dokumentu.

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
```

## Krok 4: Wykonaj korespondencję seryjną

Musimy teraz wykonać korespondencję seryjną, aby wypełnić pola rzeczywistymi danymi. W tym przykładzie ustawimy drugie pole daty (`Date2`) do 1 stycznia 2011 r.

```csharp
doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });
```

## Krok 5: Zapisz dokument

Na koniec zapisujemy dokument we wskazanym katalogu. Ten krok kończy proces zmiany źródła kultury aktualizacji pola.

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

## Wniosek

I masz to! Pomyślnie zmieniłeś źródło kultury aktualizacji pola w Aspose.Words dla .NET. Wykonując te kroki, możesz mieć pewność, że w dokumentach programu Word będą wyświetlane daty i inne wartości pól zgodnie z określonymi ustawieniami kultury. Może to być szczególnie przydatne przy generowaniu dokumentów dla odbiorców międzynarodowych.

## Często zadawane pytania

###  Jaki jest cel ustawienia`LocaleId`?
 The`LocaleId` określa ustawienia kultury tekstu, które wpływają na sposób formatowania dat i innych danych wrażliwych na ustawienia regionalne.

### Czy mogę użyć innej lokalizacji niż niemiecka?
 Tak, możesz ustawić`LocaleId`do dowolnego ważnego identyfikatora ustawień regionalnych. Na przykład 1033 dla języka angielskiego (Stany Zjednoczone).

###  Co się stanie, jeśli nie ustawię`FieldUpdateCultureSource` property?
Jeśli ta właściwość nie jest ustawiona, podczas aktualizowania pól zostaną użyte domyślne ustawienia kultury dokumentu.

### Czy można aktualizować pola w oparciu o kulturę dokumentu zamiast kodu pola?
 Tak, możesz ustawić`FieldUpdateCultureSource` Do`FieldUpdateCultureSource.Document` , aby użyć ustawień kultury dokumentu.

### Jak sformatować daty według innego wzoru?
 Możesz zmienić wzór formatu daty w pliku`InsertField` metodę, modyfikując plik`\\@` wartość przełączania.