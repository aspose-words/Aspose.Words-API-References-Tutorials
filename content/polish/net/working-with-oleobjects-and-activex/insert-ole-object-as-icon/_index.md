---
title: Wstaw obiekt Ole do dokumentu programu Word jako ikonę
linktitle: Wstaw obiekt Ole do dokumentu programu Word jako ikonę
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wstawić obiekt OLE do dokumentu programu Word jako ikonę za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon/
---

Oto przewodnik krok po kroku wyjaśniający poniższy kod źródłowy C#, który ilustruje, jak wstawić obiekt OLE do dokumentu programu Word jako ikonę przy użyciu Aspose.Words dla .NET.

## Krok 1: Zaimportuj niezbędne referencje
Zanim zaczniesz, upewnij się, że zaimportowałeś do swojego projektu niezbędne odniesienia do korzystania z Aspose.Words dla .NET. Obejmuje to importowanie biblioteki Aspose.Words i dodanie wymaganych przestrzeni nazw do pliku źródłowego.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Krok 2: Utwórz nowy dokument i generator dokumentów
 Na tym etapie utworzymy nowy dokument za pomocą pliku`Document` klasę i narzędzie do tworzenia dokumentów przy użyciu metody`DocumentBuilder` klasa.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Wstaw obiekt OLE jako ikonę
 Skorzystaj z Konstruktora Dokumentów`InsertOleObjectAsIcon`metoda wstawiania obiektu OLE jako ikony do dokumentu. Określ ścieżkę pliku OLE, flagę wyświetlania, ścieżkę ikony i nazwę osadzonego obiektu.

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

## Krok 4: Zapisz dokument
 Skorzystaj z dokumentu`Save` metoda zapisania dokumentu do pliku.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

### Przykładowy kod źródłowy do wstawiania obiektu OLE jako ikony za pomocą Aspose.Words dla .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

To jest kompletny przykładowy kod do wstawiania obiektu OLE jako ikony za pomocą Aspose.Words dla .NET. Pamiętaj, aby zaimportować niezbędne odniesienia i wykonać kroki opisane wcześniej, aby zintegrować ten kod ze swoim projektem.

## Wniosek

Podsumowując, zapoznaliśmy się z przewodnikiem krok po kroku dotyczącym wstawiania obiektu OLE jako ikony w dokumencie programu Word przy użyciu Aspose.Words dla .NET.

Wykonując te kroki, będziesz mógł pomyślnie wstawić obiekt OLE jako ikonę w dokumentach Word przy użyciu Aspose.Words dla .NET. Pamiętaj, aby zaimportować niezbędne odniesienia i postępować zgodnie z instrukcjami, aby uzyskać pożądane rezultaty.

### Często zadawane pytania dotyczące wstawiania obiektu ole w dokumencie programu Word jako ikony

#### P. Jakie odniesienia są potrzebne, aby wstawić obiekt OLE jako ikonę w dokumencie programu Word przy użyciu Aspose.Words dla .NET?

O: Aby używać Aspose.Words dla .NET, musisz zaimportować do swojego projektu następujące odniesienia:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### P. Jak utworzyć nowy dokument i generator dokumentów w Aspose.Words dla .NET?

 Odp.: Możesz utworzyć nowy dokument za pomocą`Document` klasę i narzędzie do tworzenia dokumentów przy użyciu metody`DocumentBuilder` klasa. Oto przykład :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### P. Jak wstawić obiekt OLE jako ikonę w dokumencie?

 O: Skorzystaj z Konstruktora Dokumentów`InsertOleObjectAsIcon` metoda wstawiania obiektu OLE jako ikony. Określ ścieżkę pliku OLE, flagę wyświetlania, ścieżkę ikony i nazwę osadzonego obiektu. Oto przykład :

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

#### P. Jak zapisać dokument z wstawionym obiektem OLE jako ikoną?

 O: Skorzystaj z dokumentu`Save` metoda zapisania dokumentu do pliku. Oto przykład :

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```