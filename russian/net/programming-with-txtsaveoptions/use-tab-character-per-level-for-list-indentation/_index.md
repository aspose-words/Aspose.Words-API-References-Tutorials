---
title: Используйте символ табуляции на уровень для отступа списка
linktitle: Используйте символ табуляции на уровень для отступа списка
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как использовать списки отступов с функцией символов табуляции в Aspose.Words для .NET. Сэкономьте время и улучшите рабочий процесс с помощью этой мощной функции.
type: docs
weight: 10
url: /ru/net/programming-with-txtsaveoptions/use-tab-character-per-level-for-list-indentation/
---

В этом руководстве мы рассмотрим исходный код C#, предоставленный для функции «Использовать один символ табуляции на уровне для отступа списка» с Aspose.Words для .NET. Эта функция позволяет применять символы табуляции для отступов списков на каждом уровне, обеспечивая большую гибкость и контроль над внешним видом ваших документов.

## Шаг 1. Настройка среды

Прежде чем начать, убедитесь, что вы настроили среду разработки с Aspose.Words для .NET. Убедитесь, что вы добавили необходимые ссылки и импортировали соответствующие пространства имен.

## Шаг 2: Создание документа и генератора

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 На этом этапе мы создаем новый`Document` объект и связанный с ним`DocumentBuilder` объект. Эти объекты позволят нам манипулировать и генерировать наш документ.

## Шаг 3: Создание списка с тремя уровнями отступов

```csharp
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder.ListFormat.ListIndent();
builder. Writen("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");
```

 На этом шаге мы применяем формат номеров списка по умолчанию, используя`ApplyNumberDefault()` метод форматирования списка. Затем мы добавляем три элемента в наш список с помощью конструктора документов.`Writeln()` и`Write()` методы. Мы используем`ListIndent()` метод увеличения отступа на каждом уровне.

## Шаг 4. Настройте параметры записи

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 1;
saveOptions.ListIndentation.Character = '\t';
```

 На этом этапе мы настраиваем параметры сохранения документа. Мы создаем новый`TxtSaveOptions` объект и установить`ListIndentation.Count`значение 1, чтобы указать количество символов табуляции на уровень отступа. Мы также установили`ListIndentation.Character` свойство на '\t', чтобы указать, что мы хотим использовать символы табуляции.

## Шаг 5: Сохраните документ

```csharp
doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt", saveOptions);
```

 На этом последнем шаге мы сохраняем документ с указанными параметрами сохранения. Мы используем`Save()` метод передачи документа полного пути к выходному файлу и параметры сохранения.


Теперь вы можете запустить исходный код для создания документа с отступом списка с использованием символов табуляции. Выходной файл будет сохранен в указанном каталоге с именем «WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt».

### Пример исходного кода для использования одного символа табуляции на уровне для функции отступа списка с Aspose.Words для .NET:

```csharp

// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Создайте список с тремя уровнями отступа
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder.ListFormat.ListIndent();
builder. Writen("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");

TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 1;
saveOptions.ListIndentation.Character = '\t';

doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt", saveOptions);

```

Теперь, когда вы закончили создание документа с отступом списка с использованием символов табуляции, вы можете использовать Markdown для форматирования содержимого статьи. Обязательно используйте соответствующие теги форматирования, чтобы выделить заголовки, субтитры и включенный исходный код.