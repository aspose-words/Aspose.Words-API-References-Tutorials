---
title: Compare opções em documento do Word
linktitle: Compare opções em documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para explicar o código-fonte C# do recurso Comparar opções no documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/compare-documents/compare-options/
---
Neste tutorial, explicaremos como usar o recurso Comparar opções em documentos do Word com Aspose.Words for .NET. Siga as etapas abaixo para entender o código-fonte e aplicar as alterações.

## Etapa 1: compare documentos com opções personalizadas

 Para começar, carregue dois documentos para comparar. Neste exemplo, usaremos o`Clone()` método para criar uma cópia do documento original. Veja como:

```csharp
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();
```

## Etapa 2: configurar opções de comparação

 Vamos agora configurar as opções de comparação criando um`CompareOptions` objeto e definindo as diversas propriedades conforme necessário. Veja como:

```csharp
CompareOptions options = new CompareOptions
{
IgnoreFormatting = true,
IgnoreHeadersAndFooters = true,
IgnoreCaseChanges = true,
IgnoreTables = true,
IgnoreFields = true,
IgnoreComments = true,
IgnoreTextboxes=true,
IgnoreFootnotes=true
};
```

## Etapa 3: compare documentos com opções personalizadas

 Usaremos agora o`Compare()` método que passa as opções personalizadas para comparar os dois documentos. Este método marcará as alterações no documento original. Veja como:

```csharp
// Compare documentos com opções personalizadas
docA.Compare(docB, "user", DateTime.Now, options);

// Verifique se os documentos são iguais
Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal": "Documents are not equal");
```

### Exemplo de código-fonte para opções de comparação usando Aspose.Words for .NET

Aqui está o código-fonte completo do recurso Comparar opções com Aspose.Words for .NET:

```csharp

	Document docA = new Document(MyDir + "Document.docx");
	Document docB = docA.Clone();

	CompareOptions options = new CompareOptions
	{
		IgnoreFormatting = true,
		IgnoreHeadersAndFooters = true,
		IgnoreCaseChanges = true,
		IgnoreTables = true,
		IgnoreFields = true,
		IgnoreComments = true,
		IgnoreTextboxes = true,
		IgnoreFootnotes = true
	};

	docA.Compare(docB, "user", DateTime.Now, options);

	Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal" : "Documents are not equal");

```

Com este código você pode comparar dois documentos usando opções personalizadas para ignorar elementos específicos ao comparar com Aspose.Words for .NET.

## Conclusão

Neste tutorial, aprendemos como usar Compare Options em Aspose.Words for .NET para personalizar o processo de comparação ao comparar dois documentos. Ao especificar opções diferentes, você pode ignorar elementos específicos e tornar o processo de comparação mais flexível. Este recurso permite que você tenha maior controle sobre o processo de comparação, adaptando-o às suas necessidades específicas. Aspose.Words for .NET fornece recursos poderosos de comparação de documentos, facilitando a identificação de diferenças entre documentos, ignorando certos elementos conforme necessário.

### Perguntas frequentes

#### P: Qual é o propósito de usar opções de comparação no Aspose.Words for .NET?

R: As opções de comparação no Aspose.Words for .NET permitem que você personalize o processo de comparação ao comparar dois documentos. Com essas opções, você pode especificar quais elementos ignorar durante a comparação, como alterações de formatação, cabeçalhos e rodapés, tabelas, campos, comentários, caixas de texto e notas de rodapé.

#### P: Como uso as opções de comparação no Aspose.Words for .NET?

R: Para usar as opções de comparação no Aspose.Words for .NET, siga estas etapas:
1. Carregue os dois documentos que deseja comparar em objetos Document separados.
2.  Use o`Clone()` método para criar uma cópia do documento original.
3.  Criar uma`CompareOptions` objeto e defina suas propriedades para personalizar o processo de comparação. Você pode especificar quais elementos ignorar durante a comparação.
4.  Use o`Compare()` método em um dos documentos e passar o outro documento e o`CompareOptions` objeto como parâmetros. Este método irá comparar os documentos com base nas opções especificadas e marcar as alterações no documento original.
5.  Verifica a`Revisions` propriedade do documento original. Se a contagem for zero, significa que os documentos são idênticos, considerando as opções especificadas.

#### P: Quais são as opções comuns disponíveis em CompareOptions?

R: As opções comuns disponíveis em CompareOptions incluem:
- `IgnoreFormatting`: ignora alterações na formatação.
- `IgnoreHeadersAndFooters`: ignora alterações em cabeçalhos e rodapés.
- `IgnoreCaseChanges`: ignora alterações de maiúsculas e minúsculas (maiúsculas/minúsculas).
- `IgnoreTables`: ignora alterações nas tabelas.
- `IgnoreFields`: ignora alterações nos campos.
- `IgnoreComments`: ignora alterações nos comentários.
- `IgnoreTextboxes`ignora alterações nas caixas de texto.
- `IgnoreFootnotes`: ignora alterações nas notas de rodapé.

#### P: Posso usar opções personalizadas para elementos específicos durante a comparação de documentos?

 R: Sim, você pode usar opções personalizadas para elementos específicos durante a comparação de documentos. Ao definir as propriedades do`CompareOptions` objeto adequadamente, você pode escolher quais elementos ignorar e quais considerar durante a comparação.