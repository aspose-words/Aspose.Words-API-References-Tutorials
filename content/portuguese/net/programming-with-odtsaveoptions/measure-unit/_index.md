---
title: Unidade de medida
linktitle: Unidade de medida
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como especificar a unidade de medida ao converter um documento Word em ODT com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-odtsaveoptions/measure-unit/
---

Ao converter um documento do Word para o formato OpenDocument Text (ODT) em um aplicativo C#, talvez você queira especificar a unidade de medida usada para formatação mensurável e propriedades de conteúdo. Com a biblioteca Aspose.Words para .NET, você pode especificar facilmente essa funcionalidade usando as opções de salvamento OdtSaveOptions. Neste guia passo a passo, orientaremos você sobre como usar o código-fonte Aspose.Words para .NET C# para converter um documento do Word em ODT, especificando a unidade de medida usando OdtSaveOptions.

## Compreendendo a biblioteca Aspose.Words

Antes de mergulhar no código, é importante entender a biblioteca Aspose.Words para .NET. Aspose.Words é uma biblioteca poderosa para criar, editar, converter e proteger documentos do Word em diferentes plataformas, incluindo .NET. Oferece diversos recursos para manipulação de documentos, como inserção de texto, alteração de formatação, adição de seções e muito mais.

## Carregando o documento do Word

primeira etapa é carregar o documento Word que deseja converter para ODT. Use a classe Document para carregar o documento do arquivo de origem. Aqui está um exemplo :

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

Neste exemplo, carregamos o documento “Document.docx” localizado no diretório de documentos.

## Configurando opções de backup

A próxima etapa é configurar as opções de backup para conversão para ODT. Use a classe OdtSaveOptions e defina a propriedade MeasureUnit com o valor desejado. Por exemplo, se você quiser usar polegadas como unidade de medida, defina MeasureUnit como OdtSaveMeasureUnit.Inches. Veja como fazer isso:

```csharp
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };
```

Criamos um novo objeto OdtSaveOptions e definimos a propriedade MeasureUnit com o valor desejado, em nosso caso, OdtSaveMeasureUnit.Inches para usar polegadas como unidade de medida.

## Converter documento em ODT

Agora que configuramos as opções de salvamento, podemos prosseguir com a conversão do documento para ODT. Use o método Save da classe Document para salvar o documento convertido no formato ODT especificando opções de salvamento. Aqui está um exemplo :

```csharp
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

Neste exemplo, salvamos o documento convertido como "WorkingWithOdtSaveOptions.MeasureUnit.odt" usando as opções de salvamento especificadas.

### Exemplo de código-fonte para OdtSaveOptions com funcionalidade "Unidade de medida" usando Aspose.Words for .NET



```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carregue o documento do Word
Document doc = new Document(dataDir + "Document.docx");

// Configuração de opções de backup com recurso “Unidade de medida”
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };

// Converta o documento para ODT
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

## Conclusão

Neste guia, explicamos como converter um documento do Word em ODT especificando a unidade de medida usando as opções de salvamento OdtSaveOptions com a biblioteca Aspose.Words para .NET. Seguindo as etapas fornecidas e usando o código-fonte C# fornecido, você pode aplicar facilmente essa funcionalidade em seu aplicativo C#. Especificar a unidade de medida ao converter para ODT permite controlar a formatação e as dimensões do documento resultante de acordo com suas necessidades específicas.