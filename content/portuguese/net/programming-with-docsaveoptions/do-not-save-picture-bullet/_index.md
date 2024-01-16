---
title: Não salve o marcador da imagem
linktitle: Não salve o marcador da imagem
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como desabilitar o salvamento de marcadores de imagem em documentos do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-docsaveoptions/do-not-save-picture-bullet/
---

Marcadores de imagem são um recurso comumente usado em documentos do Word para adicionar marcadores personalizados. No entanto, em alguns casos pode ser necessário desabilitar o registro de marcadores de imagem ao manipular documentos usando a Biblioteca Aspose.Words para .NET. Neste guia passo a passo, explicaremos como usar o código-fonte Aspose.Words C# para .NET para desativar o salvamento de marcadores de imagem usando as opções de salvamento DocSaveOptions.

## Compreendendo a biblioteca Aspose.Words

Antes de mergulhar no código, é importante entender a biblioteca Aspose.Words para .NET. Aspose.Words é uma biblioteca poderosa para criar, editar, converter e proteger documentos do Word em diferentes plataformas, incluindo .NET. Oferece diversos recursos para manipulação de documentos, como inserção de texto, alteração de formatação, adição de seções e muito mais.

## Passo 1: Configurando o Diretório de Documentos

O primeiro passo é definir o diretório onde seus documentos estão localizados. Você deve especificar o caminho completo do diretório. Por exemplo :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Certifique-se de substituir "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho real para o diretório de documentos.

## Etapa 2: Carregar o documento com marcadores de imagem

Em seguida, você precisa carregar o documento com marcadores de imagem. Use a classe Document para carregar o documento de um arquivo. Por exemplo :

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

Neste exemplo estamos carregando o documento do arquivo "Image bullet points.docx"

  localizado no diretório de documentos.

## Etapa 3: configurar opções de gravação

Agora vamos configurar as opções de salvamento do nosso documento. Use a classe DocSaveOptions para especificar configurações de salvamento. Por exemplo :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };
```

Neste exemplo, criamos um novo objeto DocSaveOptions e definimos a propriedade SavePictureBullet como false para desabilitar o salvamento de marcadores de imagem.

## Etapa 4: ativar o recurso "Não salvar marcador de imagem"

Para habilitar o recurso "Do Not Save Picture Bullet", já configuramos as opções de salvamento com SavePictureBullet definido como falso. Isso garante que os marcadores da imagem não sejam salvos no documento final.

## Etapa 5: salve o documento

Finalmente, você pode salvar o documento usando o método Save da classe Document. Especifique o caminho completo para o arquivo e o nome do arquivo desejado. Por exemplo :

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

Certifique-se de substituir “dataDir” pelo caminho do diretório para seus documentos.

## Exemplo de código-fonte para opções de salvamento DocSaveOptions com funcionalidade "Do Not Save Picture Bullet" usando Aspose.Words for .NET

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carregue o documento com marcadores de imagem
Document doc = new Document(dataDir + "Image bullet points.docx");

// Configure as opções de salvamento com o recurso "Não salvar marcador de imagem"
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };

// Salve o documento com as opções especificadas
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

## Conclusão

Neste guia, abordamos como desabilitar o salvamento de marcadores de imagem em um documento usando a biblioteca Aspose.Words para .NET. Seguindo as etapas fornecidas e usando o código-fonte C# fornecido, você pode aplicar facilmente essa funcionalidade em seu aplicativo C#. Desativar o salvamento de marcadores de imagem pode ser útil em algumas situações para preservar a estrutura e a formatação do documento sem salvar os marcadores de imagem.