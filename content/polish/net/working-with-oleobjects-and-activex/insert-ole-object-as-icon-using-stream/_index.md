---
title: Wstaw obiekt Ole jako ikonę za pomocą strumienia
linktitle: Wstaw obiekt Ole jako ikonę za pomocą strumienia
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wstawić obiekt OLE jako ikonę za pomocą strumienia z Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon-using-stream/
---

Oto przewodnik krok po kroku wyjaśniający poniższy kod źródłowy C#, który ilustruje, jak wstawić obiekt OLE jako ikonę przy użyciu strumienia z Aspose.Words dla .NET.

## Krok 1: Zaimportuj niezbędne referencje
Zanim zaczniesz, upewnij się, że zaimportowałeś do swojego projektu niezbędne odniesienia do korzystania z Aspose.Words dla .NET. Obejmuje to importowanie biblioteki Aspose.Words i dodanie wymaganych przestrzeni nazw do pliku źródłowego.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

## Krok 2: Utwórz nowy dokument i generator dokumentów
 Na tym etapie utworzymy nowy dokument za pomocą pliku`Document` klasę i narzędzie do tworzenia dokumentów przy użyciu metody`DocumentBuilder` klasa.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Wstaw obiekt OLE jako ikonę ze strumienia
 Skorzystaj z Konstruktora Dokumentów`InsertOleObjectAsIcon` metoda wstawiania obiektu OLE jako ikony ze strumienia do dokumentu. Określ strumień danych, typ obiektu, ścieżkę ikony i nazwę osadzonego obiektu.

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

## Krok 4: Zapisz dokument
 Skorzystaj z dokumentu`Save` metoda zapisania dokumentu do pliku.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

### Przykładowy kod źródłowy do wstawiania obiektu OLE jako ikony przy użyciu strumienia z Aspose.Words dla .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

To jest kompletny przykładowy kod do wstawiania obiektu OLE jako ikony przy użyciu strumienia z Aspose.Words dla .NET. Pamiętaj, aby zaimportować niezbędne odniesienia i wykonać opisane wcześniej kroki, aby zintegrować ten kod ze swoim projektem.

## Wniosek

Powyższy przewodnik krok po kroku wyjaśnia, jak wstawić obiekt OLE jako ikonę w dokumencie programu Word przy użyciu przepływu z Aspose.Words dla .NET. Wykonując opisane kroki, będziesz mógł zintegrować tę funkcjonalność ze swoim projektem. Pamiętaj, aby zaimportować niezbędne odniesienia, utworzyć nowy dokument i generator dokumentów, wstawić obiekt OLE jako ikonę ze strumienia, a następnie zapisać dokument. Skorzystaj z dostarczonego przykładowego kodu jako punktu wyjścia i dostosuj go do swoich potrzeb.

### Często zadawane pytania

#### P. Jak zaimportować niezbędne odniesienia, aby używać Aspose.Words dla .NET?

A. Aby zaimportować niezbędne referencje, wykonaj następujące kroki:

 Dodaj poniższe`using` instrukcje na górze pliku źródłowego:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```
Upewnij się, że dodałeś bibliotekę Aspose.Words do swojego projektu.

#### P. Jak utworzyć nowy dokument i narzędzie do tworzenia dokumentów przy użyciu Aspose.Words dla .NET?

A. Aby utworzyć nowy dokument i generator dokumentów, możesz wykonać następujące kroki:

 Użyj`Document` class, aby utworzyć nowy dokument:

```csharp
Document doc = new Document();
```
 Użyj`DocumentBuilder` class, aby utworzyć narzędzie do tworzenia dokumentów powiązane z wcześniej utworzonym dokumentem:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### P. Jak wstawić obiekt OLE jako ikonę ze strumienia przy użyciu Aspose.Words dla .NET?

A. Aby wstawić obiekt OLE jako ikonę ze strumienia, wykonaj następujące kroki:

 Użyj`InsertOleObjectAsIcon` metoda generatora dokumentów w celu wstawienia obiektu OLE:

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
  builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

#### P. Jak zapisać dokument w pliku?

A.  Aby zapisać dokument do pliku, możesz użyć metody`Save` metoda dokumentu określająca ścieżkę docelową:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

#### P. Jak osadzić kod umożliwiający wstawienie obiektu OLE jako ikony ze strumienia do mojego projektu?

A. Aby osadzić kod umożliwiający wstawienie obiektu OLE jako ikony ze strumienia do projektu, wykonaj następujące kroki:
- Zaimportuj niezbędne referencje, dodając odpowiednie`using` sprawozdania.
-  Utwórz nowy dokument i narzędzie do tworzenia dokumentów za pomocą`Document`I`DocumentBuilder` zajęcia.
- Użyj kodu do wstawienia obiektu OLE jako ikony ze strumienia.
-  Zapisz dokument za pomocą`Save` metodę z odpowiednią ścieżką docelową.

Wykonując te kroki, będziesz mógł pomyślnie wstawić obiekt OLE jako ikonę ze strumienia przy użyciu Aspose.Words dla .NET. Postępuj zgodnie z instrukcjami i zaimportuj niezbędne odniesienia, aby uzyskać pożądane rezultaty.