---
title: Definir versão do Ms Word
linktitle: Definir versão do Ms Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como carregar um documento com uma versão específica do MS Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-loadoptions/set-ms-word-version/
---
Ao processar palavras com documentos do Word em um aplicativo C#, pode ser necessário especificar a versão do Microsoft Word a ser usada ao carregar o documento. Com a biblioteca Aspose.Words para .NET, você pode definir facilmente qual versão do MS Word usar usando LoadOptions. Neste guia passo a passo, orientaremos você sobre como usar o código-fonte Aspose.Words for .NET C# para carregar um documento com uma versão especificada do MS Word usando as opções de carregamento LoadOptions.

## Compreendendo a biblioteca Aspose.Words

Antes de mergulhar no código, é importante entender a biblioteca Aspose.Words para .NET. Aspose.Words é uma biblioteca poderosa para criar, editar, converter e proteger documentos do Word em diferentes plataformas, incluindo .NET. Oferece diversos recursos para manipulação de documentos, como inserção de texto, alteração de formatação, adição de seções e muito mais.

## Configurando opções de carregamento

O primeiro passo é configurar as opções de carregamento do nosso documento. Use a classe LoadOptions para especificar parâmetros de carregamento. No nosso caso, precisamos definir a propriedade MswVersion para a versão desejada do MS Word. Por exemplo, estamos usando a versão Microsoft Word 2010. Aqui está como fazer isso:

```csharp
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };
```

Criamos um novo objeto LoadOptions e definimos a propriedade MswVersion como MsWordVersion.Word2010 para especificar a versão do MS Word 2010.

## Carregamento de documentos com versão especificada do MS Word

Agora que configuramos as opções de carregamento, podemos carregar o documento usando a classe Document e especificar as opções de carregamento. Aqui está um exemplo :

```csharp
Document doc = new Document(dataDir + "Document.docx", loadOptions);
```

Neste exemplo, carregamos o documento "Document.docx" localizado no diretório de documentos usando as opções de carregamento especificadas.

### Exemplo de código-fonte para LoadOptions com funcionalidade "Definir versão do MS Word" usando Aspose.Words for .NET

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Configure opções de carregamento com o recurso "Definir versão do MS Word"
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };

// Carregue o documento com a versão especificada do MS Word
Document doc = new Document(dataDir + "Document.docx", loadOptions);

// Salve o documento
doc.Save(dataDir + "WorkingWithLoadOptions.SetMsWordVersion.docx");
```

## Conclusão

Neste guia, explicamos como fazer upload de um documento especificando uma versão específica do MS Word usando a biblioteca Aspose.Words para .NET. Seguindo as etapas fornecidas e usando o código-fonte C# fornecido, você pode aplicar facilmente essa funcionalidade em seu aplicativo C#. Carregar um documento com uma versão específica do MS Word permite garantir a compatibilidade e o processamento adequados do documento em seu aplicativo.


### Perguntas frequentes

#### P: Por que eu precisaria especificar a versão do MS Word ao carregar um documento em um aplicativo C#?

Especificar a versão do MS Word garante que o documento seja carregado e processado corretamente, especialmente quando se trata de formatação ou recursos específicos que podem variar entre as diferentes versões.

#### P: Quais versões do MS Word o Aspose.Words suporta?

R: Aspose.Words for .NET oferece suporte a várias versões do MS Word, incluindo Word 97, Word 2003, Word 2007, Word 2010, Word 2013, Word 2016, Word 2019 e muito mais.

#### P: Posso carregar um documento com uma versão do MS Word diferente daquela instalada no meu sistema?

R: Sim, Aspose.Words permite que você especifique uma versão diferente do MS Word ao carregar o documento, garantindo compatibilidade mesmo se o sistema de destino tiver uma versão diferente do MS Word.

#### P: Como a configuração da versão do MS Word beneficia meu aplicativo C#?

R: Definir a versão do MS Word garante que o documento seja processado de acordo com a formatação e os recursos pretendidos dessa versão específica, fornecendo resultados consistentes.

#### P: O Aspose.Words está limitado a lidar apenas com documentos DOCX?

R: Não, o Aspose.Words oferece suporte a vários formatos de documentos, incluindo DOC, RTF, HTML, PDF e muito mais, tornando-o uma ferramenta versátil para lidar com diferentes tipos de documentos.