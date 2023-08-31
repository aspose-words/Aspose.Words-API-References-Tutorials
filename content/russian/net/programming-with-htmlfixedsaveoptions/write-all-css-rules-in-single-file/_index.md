---
title: Запишите все правила CSS в одном файле
linktitle: Запишите все правила CSS в одном файле
second_title: API обработки документов Aspose.Words
description: Узнайте, как преобразовать документ Word в фиксированный HTML, записав все правила CSS в одном файле с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-htmlfixedsaveoptions/write-all-css-rules-in-single-file/
---

При преобразовании документа Word в фиксированный HTML в приложении C# вам может потребоваться объединить все правила CSS в один файл для лучшей организации и переносимости. С помощью библиотеки Aspose.Words для .NET вы можете легко указать эту функциональность, используя параметры сохранения HtmlFixedSaveOptions. В этом пошаговом руководстве мы покажем вам, как использовать исходный код Aspose.Words для .NET C# для преобразования документа Word в фиксированный HTML путем записи всех правил CSS в одном файле с использованием параметров сохранения HtmlFixedSaveOptions.

## Понимание библиотеки Aspose.Words

Прежде чем углубиться в код, важно понять библиотеку Aspose.Words для .NET. Aspose.Words — мощная библиотека для создания, редактирования, преобразования и защиты документов Word на различных платформах, включая .NET. Он предлагает множество функций для управления документами, таких как вставка текста, изменение форматирования, добавление разделов и многое другое.

## Загрузка документа Word

Первый шаг — загрузить документ Word, который вы хотите преобразовать в фиксированный HTML. Используйте класс Document для загрузки документа из исходного файла. Вот пример:

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

В этом примере мы загружаем документ «Document.docx», расположенный в каталоге документов.

## Настройка параметров резервного копирования

Следующим шагом будет настройка параметров сохранения для преобразования в фиксированный HTML. Используйте класс HtmlFixedSaveOptions и задайте для свойства SaveFontFaceCssSeparately значение false, чтобы записать все правила CSS в один файл. Вот как это сделать:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };
```

Мы создаем новый объект HtmlFixedSaveOptions и устанавливаем для свойства SaveFontFaceCssSeparately значение false, чтобы записать все правила CSS в один файл.

## Исправлено преобразование HTML-документа.

Теперь, когда мы настроили параметры сохранения, мы можем приступить к преобразованию документа в фиксированный HTML. Используйте метод Save класса Document, чтобы сохранить преобразованный документ в фиксированном формате HTML, указав параметры сохранения. Вот пример:

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

В этом примере мы сохраняем преобразованный документ как «WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html», используя указанные параметры сохранения.

### Пример исходного кода для HtmlFixedSaveOptions с функцией «Записать все правила CSS в один файл» с использованием Aspose.Words для .NET

```csharp
// Путь доступа к каталогу ваших документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Загрузите документ Word
Document doc = new Document(dataDir + "Document.docx");

// Настройте параметры резервного копирования с помощью функции «Записать все правила CSS в один файл».
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };

// Преобразование документа в фиксированный HTML
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

## Заключение

В этом руководстве мы рассмотрели, как преобразовать документ Word в фиксированный HTML, написав все правила CSS в одном файле с помощью HtmlFixedSaveOptions с библиотекой Aspose.Words для .NET. Следуя предоставленным инструкциям и используя предоставленный исходный код C#, вы можете легко применить эту функцию в своем приложении C#. Запись всех правил CSS в одном файле упрощает организацию HTML-кода, созданного во время преобразования документа, и управление им.