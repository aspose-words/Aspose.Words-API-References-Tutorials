---
title: Use caracteres de controle
linktitle: Use caracteres de controle
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para usar caracteres de controle com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-document-properties/use-control-characters/
---

Neste tutorial, orientaremos você no código-fonte C# para usar caracteres de controle com Aspose.Words for .NET. Este recurso permite manipular caracteres de controle no texto.

## Etapa 1: configuração do projeto

Para começar, crie um novo projeto C# em seu IDE favorito. Certifique-se de que a biblioteca Aspose.Words for .NET seja referenciada em seu projeto.

## Etapa 2: usando caracteres de controle

Nesta etapa, usaremos caracteres de controle em um texto. Use o seguinte código:

```csharp
const string text = "test\r";
// Substitua o caractere de controle "\r" por "\r\n".
string replace = text.Replace(ControlChar.Cr, ControlChar.CrLf);
```

 Este código define um`text` string contendo o caractere de controle "\r" (nova linha) e usa o`Replace` método para substituí-lo pelo caractere de controle "\r\n" (nova linha). linha seguida por uma quebra de linha).

### Exemplo de código-fonte para usar caracteres de controle usando Aspose.Words for .NET

```csharp

	const string text = "test\r";
	// Substitua o caractere de controle "\r" por "\r\n".
	string replace = text.Replace(ControlChar.Cr, ControlChar.CrLf);

```
 Você pode usar o código acima em seu próprio projeto, substituindo o`text` string com seu próprio texto contendo caracteres de controle.

Agora você aprendeu como usar caracteres de controle com Aspose.Words for .NET. Seguindo o guia passo a passo fornecido neste tutorial, você pode manipular facilmente caracteres de controle em seus próprios aplicativos.