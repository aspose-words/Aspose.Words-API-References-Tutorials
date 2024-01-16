---
title: Criptografar documento com senha
linktitle: Criptografar documento com senha
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como criptografar documentos com senha usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-docsaveoptions/encrypt-document-with-password/
---
A segurança do documento é essencial ao processar palavras com arquivos em um aplicativo C#. Com a biblioteca Aspose.Words para .NET, você pode proteger facilmente seus documentos criptografando-os com uma senha. Neste guia passo a passo, orientaremos você sobre como usar o código-fonte Aspose.Words for .NET C# para criptografar um documento usando as opções de salvamento DocSaveOptions.

## Compreendendo a biblioteca Aspose.Words

Antes de mergulhar no código, é importante entender a biblioteca Aspose.Words para .NET. Aspose.Words é uma biblioteca poderosa para criar, editar, converter e proteger documentos do Word em diferentes plataformas, incluindo .NET. Oferece diversos recursos para manipulação de documentos, como inserção de texto, alteração de formatação, adição de seções e muito mais.

## Passo 1: Definindo o diretório do documento

primeiro passo é definir o diretório onde deseja salvar o documento criptografado. Você deve especificar o caminho completo do diretório. Por exemplo :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Certifique-se de substituir "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho real para o diretório de documentos.

## Passo 2: Criando e editando um documento

Então você pode criar um documento e adicionar conteúdo a ele. Use a classe DocumentBuilder fornecida por Aspose.Words para construir o conteúdo do seu documento. Por exemplo :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");
```

Neste exemplo, criamos um novo documento em branco e depois usamos o DocumentBuilder para escrever o texto "Hello World!".

## Etapa 3: configurar opções de gravação

Agora vamos configurar as opções de salvamento do nosso documento. Use a classe DocSaveOptions para especificar configurações de salvamento. Por exemplo :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };
```

Neste exemplo, criamos um novo objeto DocSaveOptions e definimos a propriedade Password como “password” para criptografar o documento com esta senha.

## Etapa 4: ativar o recurso "Criptografar documento com senha"

Já configuramos as opções para

registro com a senha especificada, que ativa automaticamente o recurso "Criptografar documento com senha". Isso garante que o documento seja criptografado com a senha especificada quando foi salvo.

## Passo 5: Salvando o documento

Finalmente, você pode salvar o documento usando o método Save da classe Document. Especifique o caminho completo para o arquivo e o nome do arquivo desejado. Por exemplo :

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

Certifique-se de substituir “dataDir” pelo caminho do diretório para seus documentos.

### Exemplo de código-fonte para opções de salvamento DocSaveOptions com funcionalidade "Criptografar documento com senha" usando Aspose.Words for .NET

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Criar e editar um documento
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");

// Configure as opções de salvamento com o recurso "Criptografar documento com senha"
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };

// Salve o documento com as opções especificadas
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

## Conclusão

Neste guia, explicamos como usar a biblioteca Aspose.Words para .NET para criptografar um documento com uma senha usando as opções de salvamento DocSaveOptions. Seguindo as etapas fornecidas e usando o código-fonte C# fornecido, você pode aplicar facilmente essa funcionalidade em seu aplicativo C#. Criptografar o documento com senha garante sua confidencialidade e segurança no manuseio.