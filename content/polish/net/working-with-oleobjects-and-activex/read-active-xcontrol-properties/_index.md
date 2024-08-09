---
title: Przeczytaj właściwości Active XControl z pliku Word
linktitle: Przeczytaj właściwości Active XControl z pliku Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak czytać właściwości kontrolek ActiveX z plików Word przy użyciu Aspose.Words dla .NET w przewodniku krok po kroku. Zwiększ swoje umiejętności automatyzacji dokumentów.
type: docs
weight: 10
url: /pl/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---
## Wstęp

W dzisiejszej erze cyfrowej automatyzacja jest kluczem do zwiększenia produktywności. Jeśli pracujesz z dokumentami programu Word zawierającymi kontrolki ActiveX, może być konieczne przeczytanie ich właściwości w różnych celach. Formanty ActiveX, takie jak pola wyboru i przyciski, mogą przechowywać ważne dane. Używając Aspose.Words dla .NET, możesz efektywnie wyodrębniać i programowo manipulować tymi danymi.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że masz następujące elementy:

1.  Biblioteka Aspose.Words dla .NET: Możesz ją pobrać z[Tutaj](https://releases.aspose.com/words/net/).
2. Visual Studio lub dowolne IDE C#: Aby napisać i wykonać kod.
3. Dokument programu Word z kontrolkami ActiveX: na przykład „Formanty ActiveX.docx”.
4. Podstawowa znajomość języka C#: Znajomość programowania w języku C# jest konieczna do kontynuowania nauki.

## Importuj przestrzenie nazw

Najpierw zaimportujmy niezbędne przestrzenie nazw do pracy z Aspose.Words dla .NET.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Ole;
using System;
```

## Krok 1: Załaduj dokument Word

Aby rozpocząć, musisz załadować dokument Word zawierający kontrolki ActiveX.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ActiveX controls.docx");
```

## Krok 2: Zainicjuj ciąg znaków, aby przechowywać właściwości

Następnie zainicjuj pusty ciąg znaków, w którym będą przechowywane właściwości kontrolek ActiveX.

```csharp
string properties = "";
```

## Krok 3: Iteruj po kształtach w dokumencie

Musimy iterować po wszystkich kształtach w dokumencie, aby znaleźć kontrolki ActiveX.

```csharp
foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
{
    if (shape.OleFormat is null) continue;
    
    OleControl oleControl = shape.OleFormat.OleControl;
    if (oleControl.IsForms2OleControl)
    {
        // Przetwórz formant ActiveX
    }
}
```

## Krok 4: Wyodrębnij właściwości z kontrolek ActiveX

W pętli sprawdź, czy kontrolka to Forms2OleControl. Jeśli tak, rzuć go i wyodrębnij właściwości.

```csharp
Forms2OleControl checkBox = (Forms2OleControl) oleControl;
properties += "\nCaption: " + checkBox.Caption;
properties += "\nValue: " + checkBox.Value;
properties += "\nEnabled: " + checkBox.Enabled;
properties += "\nType: " + checkBox.Type;

if (checkBox.ChildNodes != null)
{
    properties += "\nChildNodes: " + checkBox.ChildNodes;
}

properties += "\n";
```

## Krok 5: Policz całkowitą liczbę kontrolek ActiveX

Po przejrzeniu wszystkich kształtów policz całkowitą liczbę znalezionych kontrolek ActiveX.

```csharp
properties += "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
```

## Krok 6: Wyświetl właściwości

Na koniec wydrukuj wyodrębnione właściwości na konsoli.

```csharp
Console.WriteLine("\n" + properties);
```

## Wniosek

masz to! Pomyślnie nauczyłeś się czytać właściwości kontrolek ActiveX z dokumentu programu Word przy użyciu Aspose.Words dla .NET. W tym samouczku omówiono ładowanie dokumentu, przeglądanie kształtów i wyodrębnianie właściwości z kontrolek ActiveX. Wykonując poniższe kroki, możesz zautomatyzować wyodrębnianie ważnych danych z dokumentów programu Word, zwiększając efektywność przepływu pracy.

## Często zadawane pytania

### Czym są kontrolki ActiveX w dokumentach programu Word?
Formanty ActiveX to interaktywne obiekty osadzone w dokumentach programu Word, takie jak pola wyboru, przyciski i pola tekstowe, używane do tworzenia formularzy i automatyzacji zadań.

### Czy mogę modyfikować właściwości kontrolek ActiveX przy użyciu Aspose.Words dla .NET?
Tak, Aspose.Words dla .NET umożliwia programową modyfikację właściwości formantów ActiveX.

### Czy korzystanie z Aspose.Words dla .NET jest bezpłatne?
 Aspose.Words dla .NET oferuje bezpłatną wersję próbną, ale aby móc dalej korzystać, musisz kupić licencję. Możesz skorzystać z bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/).

### Czy mogę używać Aspose.Words dla .NET z innymi językami .NET oprócz C#?
Tak, Aspose.Words dla .NET może być używany z dowolnym językiem .NET, w tym VB.NET i F#.

### Gdzie mogę znaleźć więcej dokumentacji na temat Aspose.Words dla .NET?
 Można znaleźć szczegółową dokumentację[Tutaj](https://reference.aspose.com/words/net/).