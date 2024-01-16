---
title: Converter campos em parágrafo
linktitle: Converter campos em parágrafo
second_title: API de processamento de documentos Aspose.Words
description: Converta campos IF em texto simples em um parágrafo com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-fields/convert-fields-in-paragraph/
---

Aqui está um tutorial que demonstra como usar o recurso Converter campos em parágrafo com Aspose.Words for .NET. Este código converte todos os campos do tipo IF encontrados no último parágrafo de um documento em texto simples. Siga as etapas abaixo para entender e executar este código.

Certifique-se de ter instalado o Aspose.Words for .NET e configurado seu ambiente de desenvolvimento antes de começar.

## Etapa 1: importar referências

Para usar Aspose.Words em seu projeto, você precisa adicionar as referências necessárias. Certifique-se de ter adicionado uma referência à biblioteca Aspose.Words em seu projeto.

## Passo 2: Carregando o documento

Antes de converter campos, você deve carregar o documento que contém os campos a serem convertidos. Certifique-se de especificar o caminho correto para o diretório que contém o documento. Veja como fazer upload do documento:

```csharp
// Caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carregue o documento.
Document doc = new Document(dataDir + "Linked fields.docx");
```

Substitua "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho real para o diretório de documentos.

## Etapa 3: convertendo campos em texto

Agora que o documento foi carregado, podemos prosseguir com a conversão dos campos de tipo em texto simples. Neste exemplo, visamos apenas os campos presentes no último parágrafo do documento. Aqui está o código que realiza esta conversão:

```csharp
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());
```

Este código usa uma combinação de métodos LINQ para filtrar os campos no último parágrafo do documento e depois os converte em texto simples chamando o método`Unlink()` método.

## Passo 4: Salvando o documento modificado

 Depois que os campos forem convertidos, você poderá salvar o documento modificado. Use o`Save()` método para isso. Aqui está um exemplo :

```csharp
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```

Certifique-se de especificar o caminho e o nome de arquivo corretos para o backup.

### Exemplo de código-fonte para converter campos em parágrafo usando Aspose.Words for .NET

```csharp
// Caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carregue o documento.
Document doc = new Document(dataDir + "Linked fields.docx");

// Converta campos IF em texto simples no último parágrafo do documento.
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());

// Salve o documento modificado.
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```

### Perguntas frequentes

#### P: O que é um campo de conversão no Aspose.Words?

R: Um campo de conversão em Aspose.Words é um tipo de campo que converte um valor ou expressão em outro formato ou tipo de dados. Por exemplo, você pode usar um campo de conversão para converter uma data em um formato específico, um número em texto ou realizar outros tipos de conversões.

#### P: Como inserir um campo de conversão em um parágrafo com Aspose.Words?

R: Para inserir um campo de conversão em um parágrafo com Aspose.Words, você pode seguir estas etapas:

1. Importe a classe Document do namespace Aspose.Words.
2. Crie uma instância de Document carregando seu documento existente.
3. Obtenha o parágrafo onde deseja inserir o campo de conversão.
4. Use o método InsertField para inserir o campo de conversão com a sintaxe correta.

#### P: Quais formatos de conversão o Aspose.Words suporta?

R: Aspose.Words oferece suporte a uma ampla variedade de formatos de conversão em campos, incluindo formatos de data, formatos de números, formatos de texto, formatos de moeda, formatos de porcentagem e muito mais. Você pode verificar a documentação do Aspose.Words para obter uma lista completa dos formatos de conversão disponíveis.

#### P: Como atualizar um campo de conversão em um documento do Word com Aspose.Words?

R: Para atualizar um campo de conversão em um documento do Word com Aspose.Words, você pode usar o método UpdateFields. Este método percorre o documento e atualiza todos os campos, incluindo campos de conversão, recalculando valores com base nos dados atuais.