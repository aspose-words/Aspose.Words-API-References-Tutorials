---
title: Zmodyfikuj kontrolę zawartości
linktitle: Zmodyfikuj kontrolę zawartości
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak modyfikować znaczniki dokumentów strukturalnych w programie Word przy użyciu Aspose.Words dla .NET. Aktualizuj tekst, menu rozwijane i obrazy krok po kroku.
type: docs
weight: 10
url: /pl/net/programming-with-sdt/modify-content-controls/
---
## Wstęp

Jeśli kiedykolwiek pracowałeś z dokumentami programu Word i musiałeś modyfikować elementy sterujące zawartością strukturalną – takie jak zwykły tekst, listy rozwijane lub obrazy – używając Aspose.Words dla .NET, jesteś we właściwym miejscu! Tagi dokumentów strukturalnych (SDT) to potężne narzędzia, dzięki którym automatyzacja dokumentów jest łatwiejsza i bardziej elastyczna. W tym samouczku omówimy, w jaki sposób można modyfikować te narzędzia SDT, aby dopasować je do swoich potrzeb. Niezależnie od tego, czy aktualizujesz tekst, zmieniasz opcje menu rozwijanego, czy zamieniasz obrazy, ten przewodnik przeprowadzi Cię przez ten proces krok po kroku.

## Warunki wstępne

Zanim przejdziemy do sedna modyfikowania elementów sterujących zawartością, upewnij się, że masz następujące elementy:

1.  Zainstalowano Aspose.Words dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Words. Jeśli nie, możesz[pobierz go tutaj](https://releases.aspose.com/words/net/).

2. Podstawowa znajomość języka C#: W tym samouczku założono, że znasz podstawowe koncepcje programowania w języku C#.

3. Środowisko programistyczne .NET: Powinieneś mieć skonfigurowane środowisko IDE, takie jak Visual Studio, do uruchamiania aplikacji .NET.

4. Przykładowy dokument: Będziemy używać przykładowego dokumentu programu Word z różnymi typami SDT. Możesz użyć tego z przykładu lub stworzyć własny.

5.  Dostęp do dokumentacji Aspose: Aby uzyskać bardziej szczegółowe informacje, sprawdź[Dokumentacja Aspose.Words](https://reference.aspose.com/words/net/).

## Importuj przestrzenie nazw

Aby rozpocząć pracę z Aspose.Words, musisz zaimportować odpowiednie przestrzenie nazw do swojego projektu C#. Oto jak to zrobić:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Tables;
```

Te przestrzenie nazw zapewniają dostęp do klas i metod niezbędnych do manipulowania znacznikami dokumentów strukturalnych w dokumentach programu Word.

## Krok 1: Skonfiguruj ścieżkę dokumentu

 Przed dokonaniem jakichkolwiek zmian musisz określić ścieżkę do swojego dokumentu. Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką, w której przechowywany jest dokument.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Structured document tags.docx");
```

## Krok 2: Przejrzyj w pętli znaczniki dokumentu strukturalnego

 Aby zmodyfikować zestawy SDT, należy najpierw przejrzeć wszystkie zestawy SDT w dokumencie. Odbywa się to za pomocą`GetChildNodes` metoda pobierania wszystkich węzłów typu`StructuredDocumentTag`.

```csharp
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
    // Modyfikuj SDT w oparciu o ich typ
}
```

## Krok 3: Zmodyfikuj SDTS zwykłego tekstu

Jeśli SDT jest typem zwykłego tekstu, możesz zastąpić jego zawartość. Najpierw usuń istniejącą treść, a następnie dodaj nowy tekst.

```csharp
if (sdt.SdtType == SdtType.PlainText)
{
    sdt.RemoveAllChildren();
    Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
    Run run = new Run(doc, "new text goes here");
    para.AppendChild(run);
}
```

 Wyjaśnienie: Tutaj,`RemoveAllChildren()`czyści istniejącą zawartość SDT. Następnie tworzymy nowy`Paragraph`I`Run` obiekt, aby wstawić nowy tekst.

## Krok 4: Zmodyfikuj SDT listy rozwijanej

 W przypadku list rozwijanych SDT możesz zmienić wybrany element, uzyskując dostęp do`ListItems` kolekcja. Tutaj wybieramy trzecią pozycję na liście.

```csharp
if (sdt.SdtType == SdtType.DropDownList)
{
    SdtListItem secondItem = sdt.ListItems[2];
    sdt.ListItems.SelectedValue = secondItem;
}
```

Objaśnienie: Ten fragment kodu wybiera element o indeksie 2 (trzeci element) z listy rozwijanej. Dostosuj indeks do swoich potrzeb.

## Krok 5: Zmodyfikuj SDT obrazu

Aby zaktualizować obraz w obrazie SDT, możesz zastąpić istniejący obraz nowym.

```csharp
if (sdt.SdtType == SdtType.Picture)
{
    Shape shape = (Shape) sdt.GetChild(NodeType.Shape, 0, true);
    if (shape.HasImage)
    {
        shape.ImageData.SetImage(ImagesDir + "Watermark.png");
    }
}
```

 Objaśnienie: Ten kod sprawdza, czy kształt zawiera obraz, a następnie zastępuje go nowym obrazem znajdującym się pod adresem`ImagesDir`.

## Krok 6: Zapisz zmodyfikowany dokument

Po dokonaniu wszystkich niezbędnych zmian zapisz zmodyfikowany dokument pod nową nazwą, aby zachować oryginalny dokument w stanie nienaruszonym.

```csharp
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");
```

Objaśnienie: Spowoduje to zapisanie dokumentu pod nową nazwą pliku, dzięki czemu będzie można łatwo odróżnić go od oryginału.

## Wniosek

Modyfikowanie kontrolek treści w dokumencie programu Word za pomocą Aspose.Words dla .NET jest proste, jeśli zrozumiesz poszczególne kroki. Niezależnie od tego, czy aktualizujesz tekst, zmieniasz opcje rozwijane, czy zamieniasz obrazy, Aspose.Words zapewnia solidny interfejs API do tych zadań. Postępując zgodnie z tym samouczkiem, możesz skutecznie zarządzać i dostosowywać elementy sterujące treścią strukturalną dokumentu, dzięki czemu dokumenty będą bardziej dynamiczne i dostosowane do Twoich potrzeb.

## Często zadawane pytania

1. Co to jest znacznik dokumentu strukturalnego (SDT)?

SDT to elementy dokumentów programu Word, które pomagają zarządzać zawartością dokumentu i formatować ją, na przykład polami tekstowymi, listami rozwijanymi lub obrazami.

2. Jak mogę dodać nowy element rozwijany do SDT?

 Aby dodać nowy element, użyj opcji`ListItems` właściwość i dołącz nową`SdtListItem` do kolekcji.

3. Czy mogę użyć Aspose.Words do usunięcia SDT z dokumentu?

Tak, możesz usunąć SDT, uzyskując dostęp do węzłów dokumentu i usuwając żądane SDT.

4. Jak obsługiwać SDT zagnieżdżone w innych elementach?

 Skorzystaj z`GetChildNodes` metodę z odpowiednimi parametrami, aby uzyskać dostęp do zagnieżdżonych SDT.

5. Co powinienem zrobić, jeśli SDT, które muszę zmodyfikować, nie jest widoczne w dokumencie?

Upewnij się, że SDT nie jest ukryty ani chroniony. Sprawdź ustawienia dokumentu i upewnij się, że kod jest prawidłowo kierowany na typ SDT.


### Przykładowy kod źródłowy modyfikacji kontroli zawartości przy użyciu Aspose.Words dla .NET 

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Structured document tags.docx");
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
	switch (sdt.SdtType)
	{
		case SdtType.PlainText:
		{
			sdt.RemoveAllChildren();
			Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
			Run run = new Run(doc, "new text goes here");
			para.AppendChild(run);
			break;
		}
		case SdtType.DropDownList:
		{
			SdtListItem secondItem = sdt.ListItems[2];
			sdt.ListItems.SelectedValue = secondItem;
			break;
		}
		case SdtType.Picture:
		{
			Shape shape = (Shape) sdt.GetChild(NodeType.Shape, 0, true);
			if (shape.HasImage)
			{
				shape.ImageData.SetImage(ImagesDir + "Watermark.png");
			}
			break;
		}
	}
}
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");

```

To wszystko! Pomyślnie zmodyfikowałeś różne typy kontroli treści w dokumencie programu Word przy użyciu Aspose.Words dla .NET.