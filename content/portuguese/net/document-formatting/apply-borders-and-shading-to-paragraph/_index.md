---
title: Aplicar bordas e sombreamento ao parágrafo em um documento do Word
linktitle: Aplicar bordas e sombreamento ao parágrafo em um documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como aplicar bordas e sombreamento a um parágrafo em um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/document-formatting/apply-borders-and-shading-to-paragraph/
---
Neste tutorial, mostraremos como aplicar bordas e sombreamento a um parágrafo em um documento do Word usando a funcionalidade do Aspose.Words for .NET. Siga as etapas abaixo para entender o código-fonte e aplicar alterações de formatação.

## Passo 1: Criando e configurando o documento

Para começar, crie um novo documento e um objeto DocumentBuilder associado. Veja como:

```csharp
// Caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passo 2: Configuração da borda

Agora vamos configurar as bordas dos parágrafos especificando o estilo de borda de cada lado. Veja como:

```csharp
BorderCollection borders = builder.ParagraphFormat.Borders;
borders. DistanceFromText = 20;
borders[BorderType.Left].LineStyle = LineStyle.Double;
borders[BorderType.Right].LineStyle = LineStyle.Double;
borders[BorderType.Top].LineStyle = LineStyle.Double;
borders[BorderType.Bottom].LineStyle = LineStyle.Double;
```

## Etapa 3: configuração de preenchimento

Iremos agora configurar o preenchimento do parágrafo especificando a textura e as cores de preenchimento. Veja como:

```csharp
Shading shading = builder.ParagraphFormat.Shading;
shading.Texture = TextureIndex.TextureDiagonalCross;
shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;
```

## Etapa 4: adicionar conteúdo

Vamos adicionar algum conteúdo formatado ao parágrafo. Veja como:

```csharp
builder.Write("I'm a formatted paragraph with a double border and a nice shading.");
```

## Passo 3: Salvando o documento

 Após inserir o campo do formulário de entrada de texto, salve o documento no local desejado usando o`Save` método. Certifique-se de fornecer o caminho de arquivo apropriado:

```csharp
doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");
```

### Exemplo de código-fonte para aplicar bordas e sombreamento ao parágrafo usando Aspose.Words for .NET

Aqui está o código-fonte completo para o recurso Aplicar bordas e sombreamento ao parágrafo com Aspose.Words for .NET:

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	BorderCollection borders = builder.ParagraphFormat.Borders;
	borders.DistanceFromText = 20;
	borders[BorderType.Left].LineStyle = LineStyle.Double;
	borders[BorderType.Right].LineStyle = LineStyle.Double;
	borders[BorderType.Top].LineStyle = LineStyle.Double;
	borders[BorderType.Bottom].LineStyle = LineStyle.Double;

	Shading shading = builder.ParagraphFormat.Shading;
	shading.Texture = TextureIndex.TextureDiagonalCross;
	shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
	shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;

	builder.Write("I'm a formatted paragraph with double border and nice shading.");
	
	doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");

```

## Conclusão

Neste tutorial, aprendemos como aplicar bordas e sombreamento a um parágrafo em um documento do Word usando Aspose.Words for .NET. Ao configurar o parágrafo`Borders` e`Shading` propriedades, pudemos definir o estilo da borda, a cor da linha e a cor de preenchimento do parágrafo. Aspose.Words for .NET fornece recursos de formatação poderosos para personalizar a aparência dos parágrafos e aprimorar a representação visual de seus documentos.

### Perguntas frequentes

#### P: Como aplico bordas e sombreamento a um parágrafo em um documento do Word usando Aspose.Words for .NET?

R: Para aplicar bordas e sombreamento a um parágrafo em um documento do Word usando Aspose.Words for .NET, siga estas etapas:
1.  Crie um novo documento e um`DocumentBuilder` objeto.
2.  Configure as bordas do parágrafo acessando o`Borders` propriedade do`ParagraphFormat` e definir o estilo de borda para cada lado.
3.  Configure o preenchimento do parágrafo acessando o`Shading` propriedade do`ParagraphFormat` e especificando a textura e as cores de preenchimento.
4.  Adicione conteúdo ao parágrafo usando o`Write` método do`DocumentBuilder`.
5.  Salve o documento usando o`Save` método.

#### P: Como defino o estilo da borda para cada lado do parágrafo?

 R: Para definir o estilo da borda para cada lado do parágrafo, você pode acessar o`Borders` propriedade do`ParagraphFormat` e definir o`LineStyle` propriedade para cada`BorderType` (por exemplo,`BorderType.Left`, `BorderType.Right`, `BorderType.Top`, `BorderType.Bottom` ). Você pode especificar diferentes estilos de linha, como`LineStyle.Single`, `LineStyle.Double`, `LineStyle.Dotted`, etc.

#### P: Como especifico a textura e as cores de preenchimento do sombreamento do parágrafo?

 R: Para especificar a textura e as cores de preenchimento do sombreamento do parágrafo, você pode acessar o`Shading` propriedade do`ParagraphFormat` e definir o`Texture` propriedade para um índice de textura desejado (por exemplo,`TextureIndex.TextureDiagonalCross` ). Você também pode definir o`BackgroundPatternColor` e`ForegroundPatternColor` propriedades para as cores desejadas usando o`System.Drawing.Color` aula.