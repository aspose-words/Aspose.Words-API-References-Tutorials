---
title: Wywołanie zwrotne zapisywania strony
linktitle: Wywołanie zwrotne zapisywania strony
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak zapisać każdą stronę dokumentu programu Word jako oddzielny obraz PNG przy użyciu Aspose.Words dla .NET, korzystając z naszego szczegółowego przewodnika krok po kroku.
type: docs
weight: 10
url: /pl/net/programming-with-imagesaveoptions/page-saving-callback/
---
## Wstęp

No hej! Czy kiedykolwiek czułeś potrzebę zapisania każdej strony dokumentu programu Word jako osobnych obrazów? Być może chcesz podzielić duży raport na łatwo przyswajalne wizualizacje, a może chcesz utworzyć miniatury do podglądu. Bez względu na powód, użycie Aspose.Words dla .NET sprawia, że to zadanie jest proste. W tym przewodniku przeprowadzimy Cię przez proces konfigurowania wywołania zwrotnego zapisywania strony, aby zapisać każdą stronę dokumentu jako indywidualny obraz PNG. Zanurkujmy od razu!

## Warunki wstępne

Zanim zaczniemy, upewnij się, że masz następujące elementy:

1.  Aspose.Words dla .NET: Jeśli jeszcze tego nie zrobiłeś, pobierz i zainstaluj z[Tutaj](https://releases.aspose.com/words/net/).
2. Visual Studio: dowolna wersja powinna działać, ale w tym przewodniku będę używać programu Visual Studio 2019.
3. Podstawowa znajomość języka C#: Aby kontynuować naukę, będziesz potrzebować podstawowej znajomości języka C#.

## Importuj przestrzenie nazw

Najpierw musimy zaimportować niezbędne przestrzenie nazw. Pomaga nam to uzyskać dostęp do wymaganych klas i metod bez konieczności wpisywania za każdym razem pełnej przestrzeni nazw.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## Krok 1: Skonfiguruj katalog dokumentów

W porządku, zacznijmy od zdefiniowania ścieżki do katalogu dokumentów. Tutaj znajduje się wejściowy dokument programu Word i miejsce, w którym zostaną zapisane obrazy wyjściowe.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Załaduj swój dokument

Następnie załadujemy dokument, który chcesz przetworzyć. Upewnij się, że dokument („Rendering.docx”) znajduje się w określonym katalogu.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Krok 3: Skonfiguruj opcje zapisywania obrazu

Musimy skonfigurować opcje zapisywania obrazów. W tym przypadku zapisujemy strony jako pliki PNG.

```csharp
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
    PageSavingCallback = new HandlePageSavingCallback()
};
```

 Tutaj,`PageSet` określa zakres stron do zapisania, oraz`PageSavingCallback` wskazuje na naszą niestandardową klasę wywołania zwrotnego.

## Krok 4: Zaimplementuj wywołanie zwrotne zapisywania strony

Teraz zaimplementujmy klasę wywołania zwrotnego, która obsługuje sposób zapisywania każdej strony.

```csharp
private class HandlePageSavingCallback : IPageSavingCallback
{
    public void PageSaving(PageSavingArgs args)
    {
        args.PageFileName = string.Format(dataDir + "Page_{0}.png", args.PageIndex);
    }
}
```

 Ta klasa implementuje`IPageSavingCallback` interfejsie oraz wewnątrz`PageSaving` metodą definiujemy wzór nazewnictwa dla każdej zapisanej strony.

## Krok 5: Zapisz dokument jako obrazy

Na koniec zapisujemy dokument korzystając ze skonfigurowanych opcji.

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

## Wniosek

I masz to! Pomyślnie skonfigurowałeś wywołanie zwrotne zapisywania strony, aby zapisać każdą stronę dokumentu programu Word jako oddzielny obraz PNG przy użyciu Aspose.Words dla .NET. Technika ta jest niezwykle przydatna w różnych zastosowaniach, od tworzenia podglądów stron po generowanie pojedynczych obrazów stron na potrzeby raportów. 

Miłego kodowania!

## Często zadawane pytania

### Czy mogę zapisywać strony w formatach innych niż PNG?  
 Tak, możesz zapisywać strony w różnych formatach, takich jak JPEG, BMP i TIFF, zmieniając plik`SaveFormat` W`ImageSaveOptions`.

### Co jeśli chcę zapisać tylko określone strony?  
 Możesz określić strony, które chcesz zapisać, dostosowując opcję`PageSet` parametr w`ImageSaveOptions`.

### Czy można dostosować jakość obrazu?  
 Absolutnie! Możesz ustawić właściwości takie jak`ImageSaveOptions.JpegQuality` do kontrolowania jakości obrazów wyjściowych.

### Jak efektywnie obsługiwać duże dokumenty?  
W przypadku dużych dokumentów rozważ przetwarzanie stron partiami, aby efektywnie zarządzać wykorzystaniem pamięci.

### Gdzie mogę znaleźć więcej informacji na temat Aspose.Words dla .NET?  
 Sprawdź[dokumentacja](https://reference.aspose.com/words/net/) obszerne przewodniki i przykłady.