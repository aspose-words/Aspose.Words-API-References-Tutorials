---
title: Обнаружение нумерации с пробелами
linktitle: Обнаружение нумерации с пробелами
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как определить номера списка с пробелами в Aspose.Words для .NET. С легкостью улучшайте структуру ваших документов.
type: docs
weight: 10
url: /ru/net/programming-with-txtloadoptions/detect-numbering-with-whitespaces/
---
В этом руководстве мы рассмотрим исходный код C#, предоставленный для функции «Обнаружение нумерации с пробелами» в Aspose.Words для .NET. Эта функция позволяет обнаруживать и создавать списки из текстового документа, содержащего номера списков, за которыми следуют пробелы.

## Шаг 1. Настройка среды

Прежде чем начать, убедитесь, что вы настроили среду разработки с Aspose.Words для .NET. Убедитесь, что вы добавили необходимые ссылки и импортировали соответствующие пространства имен.

## Шаг 2: Создание текстового документа

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";

string textDoc = "Full stop delimiters:\n" +
                  "1. First list item 1\n" +
                  "2. First list item 2\n" +
                  "3. First list item 3\n\n" +
                  "Right bracket delimiters:\n" +
                  "1) Second list item 1\n" +
                  "2) Second list item 2\n" +
                  "3) Second list item 3\n\n" +
                  "Bullet delimiters:\n" +
                  "• Third list item 1\n" +
                  "• Third list item 2\n" +
                  "• Third list item 3\n\n" +
                  "Whitespace delimiters:\n" +
                  "1 Fourth list item 1\n" +
                  "2 Fourth list item 2\n" +
                  "3 Fourth list item 3";
```

На этом шаге мы создаем текстовую строку, имитирующую текстовый документ, содержащий номера списка, за которыми следуют пробелы. Мы используем различные разделители списка, такие как точка, правая скобка, символ маркера и пробелы.

## Шаг 3. Настройка параметров загрузки

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };
```

 На этом этапе мы настраиваем параметры загрузки документа. Мы создаем новый`TxtLoadOptions` объект и установить`DetectNumberingWithWhitespaces` собственность на`true`. Это позволит Aspose.Words обнаруживать номера списка, даже если за ними следуют пробелы.

## Шаг 4: Загрузка документа и сохранение

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

 На этом шаге мы загружаем документ, используя указанную текстовую строку и параметры загрузки. Мы используем`MemoryStream` для преобразования текстовой строки в поток памяти. Затем сохраняем полученный документ в формате .docx.

### Пример исходного кода для функции обнаружения нумерации пробелов в Aspose.Words для .NET.

```csharp

            
// Путь к вашему каталогу документов
string dataDir = "YOUR DOCUMENT DIRECTORY";
			
// Создайте текстовый документ в виде строки с частями, которые можно интерпретировать как списки.
// При загрузке первые три списка всегда будут определяться Aspose.Words,
// и объекты списка будут созданы для них после загрузки.
const string textDoc = "Full stop delimiters:\n" +
					   "1. First list item 1\n" +
					   "2. First list item 2\n" +
					   "3. First list item 3\n\n" +
					   "Right bracket delimiters:\n" +
					   "1) Second list item 1\n" +
					   "2) Second list item 2\n" +
					   "3) Second list item 3\n\n" +
					   "Bullet delimiters:\n" +
					   "• Third list item 1\n" +
					   "• Third list item 2\n" +
					   "• Third list item 3\n\n" +
					   "Whitespace delimiters:\n" +
					   "1 Fourth list item 1\n" +
					   "2 Fourth list item 2\n" +
					   "3 Fourth list item 3";

// Четвертый список с пробелом между номером списка и содержимым элемента списка,
// будет обнаружен как список только в том случае, если для параметра «DetectNumberingWithWhitespaces» в объекте LoadOptions установлено значение true,
// чтобы избежать ошибочного определения абзацев, начинающихся с цифр, как списков.
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };

// Загрузите документ, применяя LoadOptions в качестве параметра, и проверьте результат.
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
            
        
```

Теперь вы можете запустить исходный код, чтобы загрузить текстовый документ, содержащий номера списков с пробелами, а затем создать документ .docx с обнаруженными списками. Выходной файл будет сохранен в указанном каталоге с именем «WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx».

## Заключение
В этом руководстве мы рассмотрели функцию обнаружения нумерации пробелов в Aspose.Words для .NET. Мы научились создавать списки из текстового документа, содержащего номера списков, за которыми следуют пробелы.

Эта функция чрезвычайно полезна для обработки документов, содержащих номера списка, отформатированные по-разному. Используя соответствующие параметры загрузки, Aspose.Words может обнаружить эти номера списка, даже если за ними следуют пробелы, и преобразовать их в структурированные списки в окончательном документе.

Использование этой функции может сэкономить ваше время и повысить эффективность рабочего процесса. Вы можете легко извлекать информацию из текстовых документов и преобразовывать их в хорошо структурированные документы с соответствующими списками.

Не забудьте рассмотреть параметры загрузки, такие как настройка обнаружения набора номера через пробел, для достижения желаемых результатов.

Aspose.Words для .NET предлагает множество расширенных функций для обработки и создания документов. Дальнейшее изучение документации и примеров, предоставленных Aspose.Words, позволит вам в полной мере использовать возможности этой мощной библиотеки.

Поэтому не стесняйтесь интегрировать обнаружение нумерации пробелов в свои проекты Aspose.Words для .NET и воспользоваться его преимуществами для создания хорошо структурированных и удобочитаемых документов.


