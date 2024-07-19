---
title: Verifique o documento do Word criptografado
linktitle: Verifique o documento do Word criptografado
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para verificar se um documento do Word está criptografado com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-fileformat/verify-encrypted-document/
---

Este artigo fornece um guia passo a passo sobre como usar o recurso Verificação de documento criptografado do Word com Aspose.Words for .NET. Explicaremos cada parte do código em detalhes. Ao final deste tutorial você poderá entender como verificar se um documento está criptografado.

Antes de começar, certifique-se de ter instalado e configurado a biblioteca Aspose.Words for .NET em seu projeto. Você pode encontrar a biblioteca e as instruções de instalação no site do Aspose.

## Passo 1: Defina o diretório do documento

 Para começar, você precisa definir o caminho para o diretório onde seus documentos estão localizados. Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório de documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: detectar o formato do arquivo

 A seguir, usamos o`DetectFileFormat` método do`FileFormatUtil` classe para detectar as informações de formato de arquivo. Neste exemplo, presumimos que o documento criptografado se chama "Encrypted.docx" e está localizado no diretório de documentos especificado.

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
```

## Etapa 3: verifique se o documento está criptografado

 Nós usamos o`IsEncrypted` propriedade do`FileFormatInfo` objeto para verificar se o documento está criptografado. Esta propriedade retorna`true` se o documento estiver criptografado, caso contrário ele retornará`false`. Exibimos o resultado no console.

```csharp
Console.WriteLine(info.IsEncrypted);
```

Isso é tudo ! Você verificou com sucesso se um documento está criptografado usando Aspose.Words for .NET.

### Exemplo de código-fonte para verificação de documentos criptografados com Aspose.Words for .NET

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
	Console.WriteLine(info.IsEncrypted);
            
        
```

## perguntas frequentes

### P: Quais são as etapas para verificar um documento criptografado do Word?

As etapas para verificar um documento criptografado do Word são as seguintes:

Defina o diretório do documento.

Detecte o formato do arquivo.

Verifique se o documento está criptografado.

### P: Como posso definir o diretório do documento?
 Para definir o diretório de documentos, você precisa substituir`"YOUR DOCUMENT DIRECTORY"` pelo caminho real do seu diretório de documentos no código a seguir:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

### P: Como detectar o formato do arquivo?
 Você pode usar o`DetectFileFormat` método do`FileFormatUtil` classe para detectar informações de formato de arquivo. No exemplo a seguir, presumimos que o documento criptografado se chama "Encrypted.docx" e está localizado no diretório de documentos especificado:

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
```

### P: Como verificar se o documento está criptografado?
 Você pode usar o`IsEncrypted` propriedade do`FileFormatInfo` objeto para verificar se o documento está criptografado. Esta propriedade retorna`true` se o documento estiver criptografado, caso contrário ele retornará`false`. O resultado é exibido no console:

```csharp
Console.WriteLine(info.IsEncrypted);
```

### P: Como verificar se um documento está criptografado usando Aspose.Words for .NET?
Seguindo as etapas mencionadas neste tutorial e executando o código-fonte fornecido, você pode verificar se um documento está criptografado usando Aspose.Words for .NET.
