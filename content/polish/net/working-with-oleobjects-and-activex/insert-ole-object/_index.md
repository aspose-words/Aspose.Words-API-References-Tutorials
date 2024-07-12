---
title: Wstaw obiekt Ole do dokumentu programu Word
linktitle: Wstaw obiekt Ole do dokumentu programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wstawić obiekt OLE do dokumentu programu Word przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-oleobjects-and-activex/insert-ole-object/
---

Oto przewodnik krok po kroku wyjaśniający poniższy kod źródłowy C#, który ilustruje, jak wstawić obiekt OLE do dokumentu programu Word przy użyciu Aspose.Words dla .NET.

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

## Krok 3: Wstaw obiekt OLE
 Skorzystaj z Konstruktora Dokumentów`InsertOleObject` metoda wstawiania obiektu OLE do dokumentu. Określ adres URL obiektu OLE, typ obiektu, opcje wyświetlania i inne niezbędne ustawienia.

```csharp
builder. InsertOleObject("http://www.aspose.com”, „plik html”, prawda, prawda, null);
```

## Krok 4: Zapisz dokument
 Skorzystaj z dokumentu`Save` metoda zapisania dokumentu do pliku.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

### Przykładowy kod źródłowy do wstawiania obiektu OLE za pomocą Aspose.Words dla .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com”, „plik html”, prawda, prawda, null);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

To jest kompletny przykładowy kod do wstawiania obiektu OLE za pomocą Aspose.Words dla .NET. Pamiętaj, aby zaimportować niezbędne odniesienia i wykonać kroki opisane wcześniej, aby zintegrować ten kod ze swoim projektem.

## Wniosek

Podsumowując, wstawianie obiektów OLE do dokumentu programu Word to potężna funkcja oferowana przez Aspose.Words dla .NET. Korzystając z tej biblioteki, możesz łatwo osadzać obiekty OLE, takie jak pliki HTML, arkusze kalkulacyjne Excel, prezentacje PowerPoint itp., w dokumentach Word.

W tym artykule przeszliśmy przez przewodnik krok po kroku wyjaśniający kod źródłowy w języku C#, który ilustruje, jak wstawić obiekt OLE do dokumentu Word. Omówiliśmy niezbędne odniesienia, tworzenie nowego dokumentu i generator dokumentów oraz kroki wstawiania obiektu OLE i zapisywania dokumentu.

### Często zadawane pytania dotyczące wstawiania obiektu OLE do dokumentu programu Word

#### P: Jakie poświadczenia muszę zaimportować, aby używać Aspose.Words dla .NET?

Odp.: Aby używać Aspose.Words dla .NET, musisz zaimportować następujące odniesienia:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### P: Jak utworzyć nowy dokument i generator dokumentów?

 Odp.: Możesz utworzyć nowy dokument za pomocą`Document` klasę i narzędzie do tworzenia dokumentów przy użyciu metody`DocumentBuilder` klasę, jak pokazano poniżej:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### P: Jak wstawić obiekt OLE do dokumentu?

 O: Skorzystaj z`InsertOleObject`metoda konstruktora dokumentów (`DocumentBuilder`), aby wstawić obiekt OLE do dokumentu. Określ adres URL obiektu OLE, typ obiektu, opcje wyświetlania i inne niezbędne ustawienia. Oto przykład :

```csharp
builder. InsertOleObject("http://www.aspose.com”, „plik html”, prawda, prawda, null);
```

#### P: Jak zapisać dokument?

 O: Skorzystaj z dokumentu`Save` metoda zapisania dokumentu do pliku. Oto przykład :

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

#### P: Czy możesz podać pełny przykład wstawiania obiektu OLE za pomocą Aspose.Words dla .NET?

O: Oto kompletny przykładowy kod umożliwiający wstawienie obiektu OLE za pomocą Aspose.Words dla .NET. Pamiętaj, aby zaimportować niezbędne odniesienia i wykonać kroki opisane wcześniej, aby zintegrować ten kod ze swoim projektem:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com”, „plik html”, prawda, prawda, null);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```
