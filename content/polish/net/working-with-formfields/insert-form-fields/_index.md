---
title: Wstaw pola formularza
linktitle: Wstaw pola formularza
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wstawiać rozwijane pola formularzy do dokumentów programu Word przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-formfields/insert-form-fields/
---

W tym samouczku krok po kroku poprowadzimy Cię, jak wstawić pola formularza, w szczególności pole formularza rozwijanego, do dokumentu programu Word za pomocą Aspose.Words dla .NET. Wyjaśnimy dostarczony kod źródłowy C# i pokażemy, jak zaimplementować go we własnych projektach.

 Aby rozpocząć, upewnij się, że masz zainstalowany i skonfigurowany Aspose.Words for .NET w swoim środowisku programistycznym. Jeśli jeszcze tego nie zrobiłeś, pobierz i zainstaluj bibliotekę z[Aspose.Releases]https://releases.aspose.com/words/net/.

## Krok 1: Inicjowanie obiektów Document i DocumentBuilder

 Najpierw zainicjuj`Document`I`DocumentBuilder` obiekty:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Wstawianie pola formularza rozwijanego

 Następnie określ opcje rozwijanego pola formularza i wstaw go do dokumentu za pomocą`InsertComboBox` metoda`DocumentBuilder` obiekt. W tym przykładzie wstawimy rozwijane pole formularza o nazwie „DropDown” z trzema opcjami: „Jeden”, „Dwa” i „Trzy”:

```csharp
string[] items = { "One", "Two", "Three" };
builder.InsertComboBox("DropDown", items, 0);
```

## Krok 3: Zapisywanie dokumentu

Na koniec zapisz dokument:

```csharp
doc.Save("OutputDocument.docx");
```

Otóż to! Pomyślnie wstawiłeś rozwijane pole formularza do dokumentu Word przy użyciu Aspose.Words dla .NET.

### Przykładowy kod źródłowy dla wstawiania pól formularza przy użyciu Aspose.Words dla .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

string[] items = { "One", "Two", "Three" };
builder.InsertComboBox("DropDown", items, 0);

doc.Save("OutputDocument.docx");
```

Możesz swobodnie używać tego kodu we własnych projektach i modyfikować go zgodnie ze swoimi specyficznymi wymaganiami.

### Często zadawane pytania

#### P: Jak mogę wstawić pole formularza tekstowego w Aspose.Words?

 Odp.: Aby wstawić pole formularza tekstowego w Aspose.Words, możesz użyć`FormField` klasę i ustaw ją`Type`własność do`FormFieldType.Text`. Można także dostosować inne właściwości, takie jak nazwa, etykieta i opcje.

#### P: Czy można utworzyć w dokumencie pole formularza typu checkbox?

 O: Tak, możliwe jest utworzenie pola formularza typu checkbox w dokumencie Aspose.Words. Możesz skorzystać z`FormField` klasę i ustaw ją`Type`własność do`FormFieldType.CheckBox` aby utworzyć pole wyboru. Następnie możesz dostosować właściwości pola wyboru według potrzeb.

#### P: Jak mogę dodać pole formularza rozwijanego do dokumentu?

 O: Aby dodać pole formularza rozwijanego w dokumencie Aspose.Words, użyj opcji`FormField` klasę i ustaw ją`Type`własność do`FormFieldType.DropDown` . Następnie możesz ustawić opcje rozwijane za pomocą`DropDownItems` nieruchomość.

#### P: Czy mogę ustawić domyślną wartość pola formularza w Aspose.Words?

O: Tak, możesz ustawić domyślną wartość pola formularza w Aspose.Words. Użyj`FormField.Result` właściwość określająca wartość początkową pola formularza.

#### P: Jak mogę odzyskać dane wprowadzone w polach formularza w Aspose.Words?

 Odp.: Aby odzyskać dane wprowadzone w polach formularza w Aspose.Words, możesz użyć`FormField.Result` właściwość zawierająca wartość wprowadzoną przez użytkownika. Dostęp do tej właściwości można uzyskać dla każdego pola formularza w dokumencie.