---
title: Добавить японский в качестве языков редактирования
linktitle: Добавить японский в качестве языков редактирования
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по добавлению японского в качестве языка редактирования с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-document-options-and-settings/add-japanese-as-editing-languages/
---

В этом руководстве мы шаг за шагом проведем вас, чтобы понять и реализовать функциональность добавления японского языка в качестве языка редактирования с помощью Aspose.Words для .NET. Эта функция позволяет установить языковые настройки при загрузке документа и добавить японский язык в качестве языка редактирования.

## Шаг 1: Настройка проекта

Для начала создайте новый проект C# в своей любимой среде IDE. Убедитесь, что в вашем проекте есть ссылка на библиотеку Aspose.Words for .NET.

## Шаг 2: Загрузка документа

На этом шаге мы загрузим документ Word, который не содержит языка редактирования по умолчанию и к которому мы хотим добавить японский. Используйте следующий код для загрузки документа:

```csharp
LoadOptions loadOptions = new LoadOptions();

// Установите языковые настройки, которые будут использоваться при загрузке документа.
loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);

string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

## Шаг 3. Проверка языка по умолчанию

После загрузки документа мы проверим, правильно ли установлен японский язык редактирования по умолчанию. Используйте следующий код, чтобы получить идентификатор дальневосточного языка:

```csharp
int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
Console.WriteLine(
	localeIdFarEast == (int) EditingLanguage.Japanese
		? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
		: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");
```

Код проверяет, совпадает ли идентификатор дальневосточного языка с идентификатором японского. По результату выводит соответствующее сообщение.

### Пример исходного кода для добавления японского языка в качестве языков редактирования с использованием Aspose.Words для .NET

```csharp

	LoadOptions loadOptions = new LoadOptions();
	
	// Установите языковые настройки, которые будут использоваться при загрузке документа.
	loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);
	
	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
	Console.WriteLine(
		localeIdFarEast == (int) EditingLanguage.Japanese
			? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
			: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");

```

