---
title: Добавить префикс имени класса Css
linktitle: Добавить префикс имени класса Css
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по добавлению префикса имени класса CSS при преобразовании документа в HTML с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-htmlsaveoptions/add-css-class-name-prefix/
---

В этом руководстве мы познакомим вас с исходным кодом C#, чтобы добавить префикс имени класса CSS с помощью Aspose.Words для .NET. Эта функция позволяет добавлять собственный префикс к сгенерированным именам классов CSS при преобразовании документа в HTML.

## Шаг 1: Настройка проекта

Для начала создайте новый проект C# в вашей любимой IDE. Убедитесь, что в вашем проекте есть ссылка на библиотеку Aspose.Words for .NET.

## Шаг 2: Загрузка документа

На этом этапе мы загрузим документ Word, который хотим преобразовать в HTML. Используйте следующий код для загрузки документа:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Заменять`"YOUR DOCUMENTS DIRECTORY"` с фактическим путем к каталогу, в котором находится ваш документ.

## Шаг 3. Установите параметры сохранения HTML

Теперь давайте установим параметры сохранения HTML, включая тип таблицы стилей CSS и префикс имени класса CSS. Используйте следующий код:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
     CssStyleSheetType = CssStyleSheetType.External,
     CssClassNamePrefix = "pfx_"
};
```

 Этот код создает экземпляр`HtmlSaveOptions` и наборы`CssStyleSheetType` к`CssStyleSheetType.External`для создания внешней таблицы стилей CSS и`CssClassNamePrefix` к`"pfx_"` префикс`"pfx_"` для имен классов CSS.

## Шаг 4. Преобразование и сохранение документа в HTML.

Наконец, мы преобразуем документ в HTML, используя параметры сохранения HTML, определенные ранее. Используйте следующий код:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
```

Этот код преобразует документ в HTML и сохраняет его в файл с добавленным префиксом имени класса CSS.

### Пример исходного кода для добавления префикса имени класса Css с использованием Aspose.Words для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External, CssClassNamePrefix = "pfx_"
	};
	
	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);

```

 Обязательно укажите правильный путь к документу в`dataDir` переменная.

Теперь вы узнали, как добавить префикс имени класса CSS при преобразовании документа в HTML с помощью Aspose.Words для .NET. Следуя пошаговому руководству, представленному в этом руководстве, вы можете настроить имена классов CSS в преобразованных HTML-документах.