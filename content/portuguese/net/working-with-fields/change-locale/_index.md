---
title: Alterar localidade
linktitle: Alterar localidade
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como alterar a localidade para formatação de data e número em documentos do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-fields/change-locale/
---

Neste tutorial, iremos guiá-lo através do processo de alteração da localidade em documentos do Word usando Aspose.Words for .NET. Modificando a localidade, você pode controlar a formatação de datas e números durante operações de mala direta. Forneceremos a você o código-fonte C# necessário e instruções passo a passo para fazer isso.

## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
- Biblioteca Aspose.Words for .NET instalada em seu sistema.

## Etapa 1: crie um documento e o DocumentBuilder
Para começar, crie uma instância da classe Document e um objeto DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 2: inserir um campo
A seguir, insira um campo de mesclagem no documento usando o método InsertField:

```csharp
builder.InsertField("MERGEFIELD Date");
```

No código acima, inserimos um campo de mesclagem denominado “Data” no documento.

## Etapa 3: alterar o local
Para alterar o código do idioma para formatação de data e número, você pode modificar a cultura atual do thread. Neste exemplo, definiremos a localidade como alemão ("de-DE"):

```csharp
CultureInfo currentCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("de-DE");
```

No código acima, armazenamos a cultura atual e depois definimos a cultura do thread atual como alemão.

## Etapa 4: realizar a mala direta
Execute uma operação de mala direta e forneça o valor de data para o campo "Data":

```csharp
doc.MailMerge.Execute(new[] { "Date" }, new object[] { DateTime.Now });
```

Neste trecho de código, executamos a operação de mala direta e fornecemos a data atual como valor para o campo “Data”.

## Etapa 5: restaurar a localidade original
Após a conclusão da mala direta, restaure a cultura original do thread:

```csharp
Thread.CurrentThread.CurrentCulture = currentCulture;
```

No código acima, restauramos a cultura original do thread.

## Etapa 6: salve o documento
Salve o documento modificado em um arquivo usando o método Save da classe Document:

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeLocale.docx");
```

### Exemplo de código-fonte para alteração de localidade usando Aspose.Words para .NET
Aqui está o código-fonte completo para alterar a localidade em documentos do Word usando Aspose.Words for .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField("MERGEFIELD Date");

CultureInfo currentCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("de-DE");

doc.MailMerge.Execute(new[] { "Date" }, new object[] { DateTime.Now });

Thread.CurrentThread.CurrentCulture = currentCulture;

doc.Save(dataDir + "WorkingWithFields.ChangeLocale.docx");
```

## Conclusão
Parabéns! Você aprendeu com sucesso como alterar a localidade em documentos do Word usando Aspose.Words for .NET. Seguindo o guia passo a passo e utilizando o código-fonte fornecido, agora você pode controlar a formatação de datas e números durante operações de mala direta. Personalize a localidade de acordo com seus requisitos para garantir uma formatação precisa e consistente em seus documentos.

### Perguntas frequentes

#### P: O Aspose.Words é compatível com diferentes versões do Microsoft Word?

R: Sim, Aspose.Words é compatível com diferentes versões do Microsoft Word, incluindo Word 2003, Word 2007, Word 2010, Word 2013, Word 2016 e Word 2019.

#### P: O Aspose.Words oferece suporte a estruturas de campo complexas?

R: Absolutamente! Aspose.Words oferece amplo suporte para estruturas de campos complexas, incluindo campos aninhados, cálculos e expressões condicionais. Você pode usar esta API poderosa para trabalhar com qualquer tipo de estrutura de campo.

#### P: O Aspose.Words oferece suporte a operações de atualização de campo?

R: Sim, Aspose.Words permite que você atualize campos de acordo com uma programação. Você pode atualizar facilmente valores de campos, atualizar cálculos e realizar outras operações relacionadas a campos usando a API.

#### P: É possível converter campos em texto simples usando Aspose.Words?

R: Certamente! Aspose.Words fornece métodos para converter campos em texto simples. Isso pode ser útil quando você precisa extrair o conteúdo sem qualquer formatação ou funcionalidade relacionada ao campo.

#### P: É possível gerar documentos Word com campos dinâmicos usando Aspose.Words?

R: Absolutamente! Aspose.Words oferece funcionalidade robusta para gerar documentos Word com campos dinâmicos. Você pode criar modelos com campos predefinidos e preenchê-los com dados dinamicamente, fornecendo uma solução flexível e eficiente para geração de documentos.