---
title: Converter campos no corpo
linktitle: Converter campos no corpo
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como usar Aspose.Words for .NET para converter campos de página em texto no corpo de um documento do Word.
type: docs
weight: 10
url: /pt/net/working-with-fields/convert-fields-in-body/
---

Neste tutorial passo a passo, orientaremos você sobre como usar o recurso ConvertFieldsInBody do Aspose.Words for .NET usando o código-fonte C# fornecido. Este recurso permite converter campos específicos no corpo do seu documento em texto simples, facilitando o processamento dos seus documentos. Siga as etapas abaixo para usar esse recurso de maneira eficaz.

## Etapa 1: Pré-requisitos

Antes de começar, certifique-se de ter instalado o Aspose.Words for .NET e de ter um documento pronto para processamento. Certifique-se também de ter o caminho do diretório para seus documentos.

## Passo 2: Carregue o documento

Comece declarando uma variável para o caminho do diretório de documentos e, em seguida, use essa variável para inicializar um objeto Document do documento especificado. Em nosso exemplo, o documento é denominado "Campos vinculados.docx".

```csharp
// O caminho para o seu diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carregue o documento
Document doc = new Document(dataDir + "Linked fields.docx");
```

## Etapa 3: converter campos de página em texto simples

 Agora que o documento está carregado, podemos prosseguir para as etapas de conversão. Para converter os campos da página em texto simples no corpo da primeira seção, você pode usar o`Range.Fields` método para obter todos os campos no intervalo especificado e, em seguida, filtrar os campos do tipo`FieldType.FieldPage` . Então você pode usar o`ForEach` método para percorrer cada campo e chamar o`Unlink()` método para convertê-lo em texto simples.

```csharp
// Passe os parâmetros apropriados para converter os campos da página em texto simples no corpo da primeira seção.
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.Unlink());
```

## Etapa 4: salve o documento modificado

Depois de converter os campos da página em texto simples, você poderá salvar o documento modificado usando o`Save()` método e especificando o caminho e o nome do arquivo de saída. Em nosso exemplo, salvamos como "WorkingWithFields.ConvertFieldsInBody.docx".

```csharp
// Salve o documento modificado
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```

### Exemplo de código-fonte para conversão de campos no corpo com Aspose.Words for .NET

Aqui está o exemplo de código-fonte completo para converter campos no corpo usando Aspose.Words for .NET:

```csharp
// O caminho para o seu diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carregue o documento
Document doc = new Document(dataDir + "Linked fields.docx");

// Passe os parâmetros apropriados para converter os campos da página em texto simples no corpo da primeira seção.
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.A
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```

### Perguntas frequentes

#### P: O Aspose.Words é compatível com diferentes versões do Microsoft Word?

R: Sim, Aspose.Words é compatível com várias versões do Microsoft Word, incluindo Word 2003, Word 2007, Word 2010, Word 2013, Word 2016 e Word 2019.

#### P: O Aspose.Words pode lidar com estruturas de campo complexas?

R: Absolutamente! Aspose.Words fornece amplo suporte para estruturas de campos complexas, incluindo campos aninhados, cálculos e expressões condicionais. Você pode aproveitar a API poderosa para trabalhar com qualquer tipo de estrutura de campo.

#### P: O Aspose.Words oferece suporte a operações de atualização de campo?

R: Sim, Aspose.Words permite atualizar campos programaticamente. Você pode atualizar facilmente valores de campos, atualizar cálculos e realizar outras operações relacionadas a campos usando a API.

#### P: Posso converter campos em texto simples usando Aspose.Words?

R: Certamente! Aspose.Words fornece métodos para converter campos em texto simples. Isso pode ser útil quando você precisa extrair o conteúdo sem qualquer formatação ou funcionalidade relacionada ao campo.

#### P: É possível gerar documentos Word com campos dinâmicos usando Aspose.Words?

R: Absolutamente! Aspose.Words oferece recursos robustos para gerar documentos Word com campos dinâmicos. Você pode criar modelos com campos predefinidos e preenchê-los com dados dinamicamente, fornecendo uma solução flexível e eficiente de geração de documentos.