---
title: Usar fonte da máquina de destino
linktitle: Usar fonte da máquina de destino
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como converter um documento do Word em HTML fixo usando as fontes da máquina de destino com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-htmlfixedsaveoptions/use-font-from-target-machine/
---

Ao converter um documento do Word em HTML fixo em um aplicativo C#, você pode querer usar as fontes da máquina de destino para garantir que o HTML renderizado retenha a aparência e o estilo originais do documento. Com a biblioteca Aspose.Words para .NET, você pode especificar facilmente essa funcionalidade usando as opções de salvamento HtmlFixedSaveOptions. Neste guia passo a passo, orientaremos você sobre como usar o código-fonte C# do Aspose.Words for .NET para converter um documento do Word em HTML fixo usando as fontes da máquina de destino usando HtmlFixedSaveOptions.

## Compreendendo a biblioteca Aspose.Words

Antes de mergulhar no código, é importante entender a biblioteca Aspose.Words para .NET. Aspose.Words é uma biblioteca poderosa para criar, editar, converter e proteger documentos do Word em diferentes plataformas, incluindo .NET. Oferece diversos recursos para manipulação de documentos, como inserção de texto, alteração de formatação, adição de seções e muito mais.

## Carregando o documento do Word

O primeiro passo é carregar o documento Word que deseja converter para HTML fixo. Use a classe Document para carregar o documento do arquivo de origem. Aqui está um exemplo :

```csharp
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");
```

Neste exemplo, carregamos o documento "Marcadores com fonte alternativa.docx" localizado no diretório de documentos.

## Configurando opções de backup

próxima etapa é configurar as opções de salvamento para conversão para HTML fixo. Use a classe HtmlFixedSaveOptions e defina a propriedade UseTargetMachineFonts como true para informar ao Aspose.Words para usar fontes da máquina de destino. Veja como fazer isso:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };
```

Criamos um novo objeto HtmlFixedSaveOptions e definimos a propriedade UseTargetMachineFonts como true para usar as fontes da máquina de destino durante a conversão.

## Conversão de documento HTML corrigida

Agora que configuramos as opções de salvamento, podemos prosseguir com a conversão do documento para HTML fixo. Use o método Save da classe Document para salvar o documento convertido em formato HTML fixo especificando opções de salvamento. Aqui está um exemplo :

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

Neste exemplo, salvamos o documento convertido como "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html" usando as opções de salvamento especificadas.

### Exemplo de código-fonte para HtmlFixedSaveOptions com recurso "Usar fontes da máquina de destino" usando Aspose.Words for .NET

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carregue o documento do Word
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");

//Configure opções de backup com o recurso "Usar fontes da máquina de destino"
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };

// Converter documento em HTML fixo
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

## Conclusão

Neste guia, explicamos como converter um documento do Word em HTML fixo usando as fontes da máquina de destino com a biblioteca Aspose.Words para .NET. Seguindo as etapas fornecidas e usando o código-fonte C# fornecido, você pode aplicar facilmente essa funcionalidade em seu aplicativo C#. A conversão para HTML fixo com as fontes da máquina de destino garante uma renderização fiel e consistente do documento em formato HTML.
