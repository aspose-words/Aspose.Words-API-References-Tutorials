---
title: Alvo de comparação em documento Word
linktitle: Alvo de comparação em documento Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda a comparar o destino no recurso de documento do Word do Aspose.Words for .NET que permite comparar documentos e gerar um novo documento contendo as alterações feitas.
type: docs
weight: 10
url: /pt/net/compare-documents/comparison-target/
---
Aqui está um guia passo a passo para explicar o código-fonte C# abaixo, que usa o alvo de comparação na funcionalidade de documento do Word do Aspose.Words for .NET.

## Etapa 1: introdução

O recurso de comparação de destino do Aspose.Words for .NET permite comparar dois documentos e gerar um novo documento contendo as alterações feitas no documento de destino. Isso pode ser útil para rastrear alterações feitas entre diferentes versões de um documento.

## Passo 2: Configurando o ambiente

Antes de começar, você precisa configurar seu ambiente de desenvolvimento para funcionar com Aspose.Words for .NET. Certifique-se de ter a biblioteca Aspose.Words instalada e um projeto C# adequado para incorporar o código.

## Etapa 3: adicionar montagens necessárias

Para usar o recurso de destino de comparação do Aspose.Words for .NET, você deve adicionar os assemblies necessários ao seu projeto. Certifique-se de ter as referências adequadas ao Aspose.Words em seu projeto.

```csharp
using Aspose.Words;
```

## Etapa 4: inicialização do documento

Nesta etapa, inicializaremos dois documentos para comparação. Você deve especificar o caminho do diretório onde seus documentos estão localizados, bem como o nome do documento de origem.

```csharp
// Caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Inicialização do documento A para comparar.
Document docA = new Document(dataDir + "DocumentA.docx");

// Clone o documento A para criar uma cópia idêntica do documento B.
Document docB = docA.Clone();
```

## Etapa 5: configurando opções de comparação

Nesta etapa, configuraremos as opções de comparação para especificar o comportamento da comparação. As opções incluem a capacidade de ignorar a formatação, bem como o alvo de comparação, que é a opção “Mostrar alterações em” na caixa de diálogo “Comparar documentos” do Microsoft Word.

```csharp
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };
```

## Etapa 6: comparação de documentos

Agora iremos comparar os documentos e gerar o resultado em um novo documento.

```csharp
docA.Compare(docB, "user", DateTime.Now, options);
```

 O`Compare` método compara o documento A com o documento B e salva as alterações no documento A. Você pode especificar o nome de usuário e a data de comparação para referência.

### Exemplo de código-fonte para Compare Target usando Aspose.Words for .NET


```csharp
            
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();

// Relaciona-se à opção "Mostrar alterações em" do Microsoft Word na caixa de diálogo "Comparar documentos".
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };

docA.Compare(docB, "user", DateTime.Now, options);
            
        
```

## Conclusão

Neste artigo, exploramos o recurso de destino diff do Aspose.Words for .NET. Este recurso permite comparar dois documentos e gerar um novo documento contendo as alterações realizadas. Você pode usar esse conhecimento para rastrear alterações entre diferentes versões dos seus documentos.

### Perguntas frequentes

#### P: Qual é o propósito de usar o Comparison Target no Aspose.Words for .NET?

R: O alvo de comparação no Aspose.Words for .NET permite comparar dois documentos e gerar um novo documento contendo as alterações feitas no documento de destino. Este recurso é útil para rastrear alterações feitas entre diferentes versões de um documento e visualizar as diferenças em um documento separado.

#### P: Como faço para usar o alvo de comparação no Aspose.Words for .NET?

R: Para usar o alvo de comparação no Aspose.Words for .NET, siga estas etapas:
1. Configure seu ambiente de desenvolvimento com a biblioteca Aspose.Words.
2. Adicione os assemblies necessários ao seu projeto referenciando Aspose.Words.
3.  Inicialize os documentos que você deseja comparar usando o`Document` classe ou o`DocumentBuilder` aula.
4.  Configure as opções de comparação criando um`CompareOptions` objeto e configurando propriedades como`IgnoreFormatting` e`Target` (por exemplo.,`ComparisonTargetType.New` para alvo de comparação).
5.  Use o`Compare` método em um documento, passando o outro documento e o`CompareOptions` objeto como parâmetros. Este método irá comparar os documentos e salvar as alterações no primeiro documento.

####  P: Qual é o propósito do`Target` property in the `CompareOptions` class?

 R: O`Target` propriedade no`CompareOptions` classe permite que você especifique o alvo de comparação, que é semelhante à opção "Mostrar alterações em" na caixa de diálogo "Comparar documentos" do Microsoft Word. A meta pode ser definida para`ComparisonTargetType.New` para mostrar alterações em um novo documento,`ComparisonTargetType.Current` para mostrar alterações no documento atual, ou`ComparisonTargetType.Formatting` para mostrar apenas alterações de formatação.