---
title: Pola formularza pobierane według nazwy
linktitle: Pola formularza pobierane według nazwy
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak pobierać i modyfikować pola formularzy według nazw w dokumentach programu Word przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-formfields/form-fields-get-by-name/
---

W tym samouczku krok po kroku poprowadzimy Cię, jak używać Aspose.Words dla .NET do pobierania pól formularzy według nazwy z dokumentu Word. Wyjaśnimy dostarczony kod źródłowy C# i pokażemy, jak zaimplementować go we własnych projektach.

 Aby rozpocząć, upewnij się, że masz zainstalowany i skonfigurowany Aspose.Words for .NET w swoim środowisku programistycznym. Jeśli jeszcze tego nie zrobiłeś, pobierz i zainstaluj bibliotekę z[Aspose.Releases]https://releases.aspose.com/words/net/.

## Krok 1: Inicjowanie obiektu dokumentu

 Najpierw zainicjuj`Document` obiekt podając ścieżkę do dokumentu źródłowego zawierającego pola formularza:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");
```

## Krok 2: Pobieranie pól formularza

 Następnie uzyskaj dostęp do`FormFields` własność`Range` obiekt w dokumencie, aby pobrać wszystkie pola formularza:

```csharp
FormFieldCollection documentFormFields = doc.Range.FormFields;
```

Pola formularza można wyszukiwać według indeksu lub nazwy. W tym przykładzie pobieramy pole formularza za pomocą obu metod:

```csharp
FormField formField1 = documentFormFields[3]; // Pobieranie według indeksu
FormField formField2 = documentFormFields["Text2"]; // Pobieranie po imieniu
```

## Krok 3: Modyfikowanie właściwości pól formularza

Po pobraniu pól formularza możesz w razie potrzeby zmodyfikować ich właściwości. W tym przykładzie zmieniamy rozmiar czcionki`formField1` do 20 i kolor czcionki`formField2` na czerwono:

```csharp
formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;
```

## Krok 4: Zapisywanie dokumentu

Na koniec zapisz zmodyfikowany dokument:

```csharp
doc.Save(dataDir + "ModifiedFormFields.docx");
```

Otóż to! Pomyślnie pobrałeś pola formularza według nazwy i zmodyfikowałeś ich właściwości w dokumencie programu Word przy użyciu Aspose.Words dla .NET.

### Przykładowy kod źródłowy dla pól formularza Get By Name przy użyciu Aspose.Words dla .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");

FormFieldCollection documentFormFields = doc.Range.FormFields;

FormField formField1 = documentFormFields[3];
FormField formField2 = documentFormFields["Text2"];

formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;

doc.Save(dataDir + "ModifiedFormFields.docx");
```

Możesz swobodnie używać tego kodu we własnych projektach i modyfikować go zgodnie ze swoimi specyficznymi wymaganiami.

### Często zadawane pytania

#### P: Jak mogę uzyskać pole formularza według nazwy w Aspose.Words?

 O: Aby uzyskać pole formularza według nazwy w Aspose.Words, możesz użyć metody`Document.Range.FormFields[name]` metoda. Metoda ta zwraca pole formularza odpowiadające podanej nazwie.

#### P: Co się stanie, jeżeli pole formularza o podanej nazwie nie istnieje w dokumencie?

 Odp.: Jeżeli pole formularza o podanej nazwie nie istnieje w dokumencie, plik`Document.Range.FormFields[name]` metoda powróci`null`. Możesz sprawdzić ten wynik, aby obsłużyć przypadki, w których nie znaleziono pola formularza.

#### P: Jak mogę zmodyfikować właściwości znalezionego pola formularza?

O: Po otrzymaniu nazwy pola formularza możesz uzyskać dostęp do jego indywidualnych właściwości i je edytować. Na przykład możesz zmienić wartość pola, włączyć lub wyłączyć jego widoczność lub zmodyfikować inne właściwości, stosownie do potrzeb.

#### P: Czy mogę umieścić w dokumencie wiele pól formularza o tej samej nazwie?

 O: Tak, w dokumencie może znajdować się wiele pól formularza o tej samej nazwie. W tym przypadku`Document.Range.FormFields[name]` metoda zwróci pierwsze znalezione pole formularza o podanej nazwie. Jeśli masz wiele pól formularza o tej samej nazwie, musisz wziąć to pod uwagę podczas manipulowania polami.

#### P: Jak mogę iterować po wszystkich polach formularza w dokumencie?

 O: Aby iterować po wszystkich polach formularza w dokumencie, możesz użyć a`foreach` pętla na`Document.Range.FormFields` kolekcja. Umożliwi to dostęp do każdego pola formularza z osobna i wykonanie operacji na każdym z nich.