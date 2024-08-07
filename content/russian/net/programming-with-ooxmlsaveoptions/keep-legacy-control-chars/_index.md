---
title: Сохраните устаревшие управляющие символы
linktitle: Сохраните устаревшие управляющие символы
second_title: API обработки документов Aspose.Words
description: Узнайте, как сохранить устаревшие управляющие символы в документах Word с помощью Aspose.Words для .NET, с помощью этого пошагового руководства.
type: docs
weight: 10
url: /ru/net/programming-with-ooxmlsaveoptions/keep-legacy-control-chars/
---
## Введение

Вы когда-нибудь были озадачены этими странными невидимыми управляющими символами в документах Word? Они похожи на крошечных скрытых гремлинов, которые могут испортить форматирование и функциональность. К счастью, Aspose.Words для .NET предоставляет удобную функцию, позволяющую сохранить эти устаревшие управляющие символы нетронутыми при сохранении документов. В этом уроке мы углубимся в то, как управлять этими управляющими символами с помощью Aspose.Words для .NET. Мы разберем его шаг за шагом, гарантируя, что вы поймете каждую деталь на этом пути. Готовы начать? Давайте погрузимся!

## Предварительные условия

Прежде чем мы начнем, убедитесь, что у вас есть следующее:

1.  Aspose.Words для .NET: загрузите и установите с[здесь](https://releases.aspose.com/words/net/).
2.  Действующая лицензия Aspose: вы можете получить временную лицензию.[здесь](https://purchase.aspose.com/temporary-license/).
3. Среда разработки: Visual Studio или любая другая IDE, поддерживающая .NET.
4. Базовые знания C#: Знакомство с языком программирования C# будет полезным.

## Импортировать пространства имен

Прежде чем писать код, вам необходимо импортировать необходимые пространства имен. Добавьте следующие строки в начало вашего файла C#:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Шаг 1: Настройка вашего проекта

Сначала вам нужно настроить проект в Visual Studio (или предпочитаемой вами IDE). 

1. Создайте новый проект C#. Откройте Visual Studio и создайте новый проект консольного приложения C#.
2. Установите Aspose.Words для .NET: используйте диспетчер пакетов NuGet для установки Aspose.Words для .NET. Щелкните правой кнопкой мыши свой проект в обозревателе решений, выберите «Управление пакетами NuGet», найдите «Aspose.Words» и установите его.

## Шаг 2. Загрузите документ

Далее вы загрузите документ Word, содержащий устаревшие управляющие символы.

1. Укажите путь к документу: укажите путь к каталогу вашего документа.
   
   ```csharp
   string dataDir = "YOUR DOCUMENT DIRECTORY";
   ```

2.  Загрузите документ: используйте`Document` class для загрузки вашего документа.

   ```csharp
   Document doc = new Document(dataDir + "Legacy control character.doc");
   ```

## Шаг 3. Настройте параметры сохранения

Теперь давайте настроим параметры сохранения, чтобы сохранить устаревшие управляющие символы нетронутыми.

1.  Создать параметры сохранения: инициализировать экземпляр`OoxmlSaveOptions` и установите`KeepLegacyControlChars`собственность`true`.

   ```csharp
   OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc)
   {
       KeepLegacyControlChars = true
   };
   ```

## Шаг 4. Сохраните документ

Наконец, сохраните документ с настроенными параметрами сохранения.

1.  Сохраните документ: используйте`Save` метод`Document` class для сохранения документа с указанными параметрами сохранения.

   ```csharp
   doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
   ```

## Заключение

И вот оно! Выполнив эти шаги, вы можете гарантировать, что ваши устаревшие управляющие символы будут сохранены при работе с документами Word в Aspose.Words для .NET. Эта функция может оказаться спасением, особенно при работе со сложными документами, где управляющие символы играют решающую роль. 

## Часто задаваемые вопросы

### Что такое устаревшие управляющие символы?

Устаревшие управляющие символы — это непечатаемые символы, используемые в старых документах для управления форматированием и макетом.

### Могу ли я удалить эти управляющие символы вместо того, чтобы оставить их?

Да, вы можете использовать Aspose.Words для .NET, чтобы удалить или заменить эти символы, если это необходимо.

### Доступна ли эта функция во всех версиях Aspose.Words для .NET?

Эта функция доступна в последних версиях. Обязательно используйте последнюю версию для доступа ко всем функциям.

### Нужна ли мне лицензия для использования Aspose.Words для .NET?

 Да, вам нужна действующая лицензия. Вы можете получить временную лицензию для ознакомительных целей.[здесь](https://purchase.aspose.com/temporary-license/).

### Где я могу найти дополнительную документацию по Aspose.Words для .NET?

 Вы можете найти подробную документацию[здесь](https://reference.aspose.com/words/net/).
 