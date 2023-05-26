---
title: Удалить личную информацию
linktitle: Удалить личную информацию
second_title: Справочник по API Aspose.Words для .NET
description: Пошаговое руководство по удалению личной информации из документа с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-document-properties/remove-personal-information/
---

В этом руководстве мы познакомим вас с исходным кодом C#, чтобы удалить личную информацию из документа с помощью Aspose.Words для .NET. Эта функция позволяет удалить из документа конфиденциальную личную информацию, например идентификационные данные автора.

## Шаг 1: Настройка проекта

Для начала создайте новый проект C# в своей любимой среде IDE. Убедитесь, что в вашем проекте есть ссылка на библиотеку Aspose.Words for .NET.

## Шаг 2: Загрузка документа

На этом этапе мы загрузим документ Word, из которого мы хотим удалить личную информацию. Используйте следующий код для загрузки документа:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };
```

 Заменять`"YOUR DOCUMENTS DIRECTORY"` с фактическим путем к каталогу, в котором находится ваш документ.

## Шаг 3. Удалите личную информацию

 Теперь мы включим удаление личной информации, установив`RemovePersonalInformation` собственность на`true`. Используйте следующий код:

```csharp
doc.RemovePersonalInformation = true;
```

Этот код активирует удаление личной информации в документе.

## Шаг 4: Сохранение документа

Наконец, мы сохраним документ с удаленной личной информацией. Используйте следующий код:

```csharp
doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
```

Этот код сохраняет документ с удаленной личной информацией в новый файл.

### Пример исходного кода для удаления личной информации с помощью Aspose.Words для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };

	doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
	
```

 Не забудьте указать правильный путь к документу в`dataDir` переменная.

Теперь вы узнали, как удалить личную информацию из документа с помощью Aspose.Words для .NET. Следуя пошаговому руководству, приведенному в этом руководстве, вы сможете легко удалить конфиденциальную информацию из своих документов.