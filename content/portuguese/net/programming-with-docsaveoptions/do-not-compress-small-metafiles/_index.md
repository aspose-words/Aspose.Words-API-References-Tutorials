---
title: Não compacte metarquivos pequenos
linktitle: Não compacte metarquivos pequenos
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como usar Aspose.Words for .NET para habilitar o recurso Do Not Compress Small Metafiles ao salvar documentos.
type: docs
weight: 10
url: /pt/net/programming-with-docsaveoptions/do-not-compress-small-metafiles/
---

A compactação de metadados em um documento é um recurso comum no processamento de texto com arquivos em um aplicativo C#. Entretanto, pode ser necessário não compactar os metadados de arquivos pequenos para preservar sua qualidade. Neste guia passo a passo, mostraremos como usar o código-fonte C# do Aspose.Words for .NET para habilitar o recurso "Não compactar metarquivos pequenos" nas opções de salvamento de documentos.

## Compreendendo a biblioteca Aspose.Words

Antes de mergulhar no código, é importante entender a biblioteca Aspose.Words para .NET. Aspose.Words é uma biblioteca poderosa para criar, editar, converter e proteger documentos do Word em diferentes plataformas, incluindo .NET. Oferece diversos recursos para manipulação de documentos, como inserção de texto, alteração de formatação, adição de seções e muito mais.

## Etapa 1: definir diretório de documentos

primeiro passo é definir o diretório onde deseja salvar o documento. Você deve especificar o caminho completo do diretório. Por exemplo :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Certifique-se de substituir "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho real para o diretório de documentos.

## Etapa 2: inserir seções e texto

Então você pode inserir seções e texto em seu documento. Use a classe DocumentBuilder fornecida por Aspose.Words para construir o conteúdo do seu documento. Aqui está um exemplo simples:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

Neste exemplo, criamos um novo documento em branco e usamos o DocumentBuilder para adicionar uma linha de texto.

## Etapa 3: opções de configuração

'cadastro

Agora vamos configurar as opções de salvamento do nosso documento. Use a classe DocSaveOptions para especificar configurações de salvamento. Por exemplo :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions();
```

Neste exemplo, estamos criando um novo objeto DocSaveOptions para definir opções de salvamento.

## Etapa 4: ativar o recurso "Não compactar metarquivos pequenos"

 Para ativar o recurso "Não compactar metarquivos pequenos", você deve definir o`Compliance` propriedade do objeto DocSaveOptions para o valor`PdfCompliance.PdfA1a`. Veja como:

```csharp
saveOptions.Compliance = PdfCompliance.PdfA1a;
```

Essa configuração garante que os metadados de arquivos pequenos não sejam compactados quando o documento for salvo.

## Etapa 5: salve o documento

Finalmente, você pode salvar o documento usando o`Save` método da classe Document. Especifique o caminho completo para o arquivo e o nome do arquivo desejado. Por exemplo :

```csharp
doc.Save(dataDir + "DocumentWithDoNotCompressMetafiles.pdf", saveOptions);
```

Certifique-se de substituir “dataDir” pelo caminho para o diretório do seu documento.

### Exemplo de código-fonte para DocSaveOptions com recurso Do Not Compress Small Metafiles usando Aspose.Words for .NET

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Insira duas seções com algum texto.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

// Configure opções de salvamento com o recurso "Não compactar metarquivos pequenos"
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.Compliance = PdfCompliance.PdfA1a;

// Salve o documento com as opções especificadas
doc.Save(dataDir + "DocumentWithDoNotCompressMetafiles.pdf", saveOptions);
```

## Conclusão

Neste guia, explicamos como usar a biblioteca Aspose.Words para .NET para habilitar o recurso “Não compactar metarquivos pequenos” ao salvar um documento. Seguindo as etapas fornecidas e usando o código-fonte C# fornecido, você pode aplicar facilmente essa funcionalidade em seu aplicativo C#. Preservar metadados de arquivos pequenos não compactados pode ser importante para manter a qualidade e integridade do documento.