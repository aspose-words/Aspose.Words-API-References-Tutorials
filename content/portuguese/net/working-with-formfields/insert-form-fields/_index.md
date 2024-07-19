---
title: Inserir campos de formulário
linktitle: Inserir campos de formulário
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir campos de formulário suspensos em documentos do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-formfields/insert-form-fields/
---

Neste tutorial passo a passo, iremos orientá-lo sobre como inserir campos de formulário, especificamente um campo de formulário suspenso, em um documento do Word usando Aspose.Words for .NET. Explicaremos o código-fonte C# fornecido e mostraremos como implementá-lo em seus próprios projetos.

 Para começar, certifique-se de ter o Aspose.Words for .NET instalado e configurado em seu ambiente de desenvolvimento. Caso ainda não tenha feito isso, baixe e instale a biblioteca em[Aspose.Releases]https://releases.aspose.com/words/net/.

## Etapa 1: inicializando os objetos Document e DocumentBuilder

 Primeiro, inicialize o`Document`e`DocumentBuilder` objetos:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 2: Inserindo um campo de formulário suspenso

 A seguir, especifique as opções para o campo suspenso do formulário e insira-o no documento usando o`InsertComboBox` método do`DocumentBuilder` objeto. Neste exemplo, inserimos um campo de formulário suspenso chamado "DropDown" com três opções: "Um", "Dois" e "Três":

```csharp
string[] items = { "One", "Two", "Three" };
builder.InsertComboBox("DropDown", items, 0);
```

## Etapa 3: salvando o documento

Por fim, salve o documento:

```csharp
doc.Save("OutputDocument.docx");
```

É isso! Você inseriu com sucesso um campo de formulário suspenso em um documento do Word usando Aspose.Words for .NET.

### Exemplo de código-fonte para inserir campos de formulário usando Aspose.Words for .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

string[] items = { "One", "Two", "Three" };
builder.InsertComboBox("DropDown", items, 0);

doc.Save("OutputDocument.docx");
```

Sinta-se à vontade para usar este código em seus próprios projetos e modificá-lo de acordo com suas necessidades específicas.

### Perguntas frequentes

#### P: Como posso inserir um campo de formulário de tipo de texto no Aspose.Words?

 R: Para inserir um campo de formulário de tipo de texto no Aspose.Words, você pode usar o`FormField` classe e definir seu`Type`propriedade para`FormFieldType.Text`. Você também pode personalizar outras propriedades, como nome, rótulo e opções.

#### P: É possível criar um campo de formulário do tipo caixa de seleção em um documento?

 R: Sim, é possível criar um campo de formulário do tipo caixa de seleção em um documento Aspose.Words. Você pode usar o`FormField` classe e definir seu`Type`propriedade para`FormFieldType.CheckBox` para criar uma caixa de seleção. Você pode então personalizar as propriedades da caixa de seleção conforme necessário.

#### P: Como posso adicionar um campo de formulário do tipo suspenso a um documento?

 R: Para adicionar um campo de formulário do tipo suspenso em um documento Aspose.Words, use o`FormField` classe e definir seu`Type`propriedade para`FormFieldType.DropDown` . Você pode então definir as opções suspensas usando o`DropDownItems` propriedade.

#### P: Posso definir um valor padrão para um campo de formulário no Aspose.Words?

R: Sim, você pode definir um valor padrão para um campo de formulário no Aspose.Words. Use o`FormField.Result` propriedade para especificar o valor inicial do campo do formulário.

#### P: Como posso recuperar os dados inseridos nos campos do formulário no Aspose.Words?

 R: Para recuperar dados inseridos em campos de formulário no Aspose.Words, você pode usar o`FormField.Result` propriedade que contém o valor inserido pelo usuário. Você pode acessar essa propriedade para cada campo do formulário no seu documento.