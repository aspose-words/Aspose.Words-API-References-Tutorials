---
title: Wstaw obiekt Ole do programu Word z pakietem Ole
linktitle: Wstaw obiekt Ole do programu Word z pakietem Ole
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wstawić obiekt OLE z pakietem OLE do dokumentu za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---

Oto przewodnik krok po kroku wyjaśniający poniższy kod źródłowy C#, który ilustruje, jak wstawić obiekt OLE do słowa z pakietem OLE przy użyciu Aspose.Words dla .NET.

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

## Krok 3: Wstaw obiekt OLE z pakietem OLE
 Skorzystaj z generatora dokumentów`InsertOleObject`metoda wstawiania obiektu OLE z pakietem OLE do dokumentu. Określ strumień danych, typ obiektu, opcje wyświetlania i inne niezbędne ustawienia.

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}
```

## Krok 4: Zapisz dokument
 Skorzystaj z dokumentu`Save` metoda zapisania dokumentu do pliku.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

### Przykładowy kod źródłowy do wstawiania obiektu OLE z pakietem OLE za pomocą Aspose.Words dla .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

To jest kompletny przykładowy kod do wstawiania obiektu OLE z pakietem OLE za pomocą Aspose.Words dla .NET. Pamiętaj, aby zaimportować niezbędne odniesienia i wykonać opisane wcześniej kroki, aby zintegrować ten kod ze swoim projektem.

## Wniosek

Podsumowując, przeszliśmy przez przewodnik krok po kroku, jak wstawić obiekt OLE do dokumentu Word z pakietem OLE przy użyciu Aspose.Words dla .NET.

Wykonując te kroki, będziesz mógł pomyślnie wstawiać obiekty OLE z pakietami OLE do dokumentów Word przy użyciu Aspose.Words dla .NET. Pamiętaj, aby zaimportować niezbędne odniesienia i postępować zgodnie z instrukcjami, aby uzyskać pożądane rezultaty.

### Często zadawane pytania dotyczące wstawiania obiektu ole do słowa za pomocą pakietu ole

#### P: Jakie poświadczenia muszę zaimportować, aby używać Aspose.Words dla .NET?

Odp.: Aby używać Aspose.Words dla .NET, musisz zaimportować następujące odniesienia:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

#### P: Jak utworzyć nowy dokument i generator dokumentów?

 Odp.: Możesz utworzyć nowy dokument za pomocą`Document` klasę i narzędzie do tworzenia dokumentów przy użyciu metody`DocumentBuilder` klasę, jak pokazano poniżej:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### P: Jak wstawić obiekt OLE z pakietem OLE do dokumentu?

 O: Skorzystaj z`InsertOleObject` metoda konstruktora dokumentów (`DocumentBuilder`), aby wstawić do dokumentu obiekt OLE z pakietem OLE. Określ strumień danych, typ obiektu, opcje wyświetlania i inne niezbędne ustawienia. Oto przykład :

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}
```

#### P: Jak zapisać dokument?

 O: Skorzystaj z dokumentu`Save`metoda zapisania dokumentu do pliku. Oto przykład :

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

#### P: Czy możesz podać pełny przykład wstawiania obiektu OLE z pakietem OLE za pomocą Aspose.Words dla .NET?

Odp.: Oto kompletny przykładowy kod umożliwiający wstawienie obiektu OLE do pakietu OLE przy użyciu Aspose.Words dla .NET. Pamiętaj, aby zaimportować niezbędne odniesienia i wykonać kroki opisane wcześniej, aby zintegrować ten kod ze swoim projektem:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

Na tym kończy się nasz samouczek dotyczący wstawiania obiektu OLE z pakietem OLE do dokumentu programu Word przy użyciu Aspose.Words dla .NET. Możesz zaimportować niezbędne odniesienia i wykonać opisane kroki, aby zintegrować ten kod ze swoim projektem. Jeśli masz dodatkowe pytania, nie wahaj się z nami skontaktować.