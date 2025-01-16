---
title: Gerar tabela a partir de Datatable
linktitle: Gerar tabela a partir de Datatable
second_title: API de processamento de documentos Java Aspose.Words
description: Aprenda a gerar uma tabela a partir de uma DataTable usando Aspose.Words para Java. Crie documentos profissionais do Word com tabelas formatadas sem esforço.
type: docs
weight: 11
url: /pt/java/table-processing/generate-table-from-datatable/
---
## Introdução

Criar tabelas dinamicamente a partir de fontes de dados é uma tarefa comum em muitos aplicativos. Quer você esteja gerando relatórios, faturas ou resumos de dados, ser capaz de preencher uma tabela com dados programaticamente pode economizar muito tempo e esforço. Neste tutorial, exploraremos como gerar uma tabela a partir de uma DataTable usando Aspose.Words para Java. Dividiremos o processo em etapas gerenciáveis, garantindo que você tenha um entendimento claro de cada parte.

## Pré-requisitos

Antes de mergulhar no código, vamos garantir que você tenha tudo o que precisa para começar:

1.  Java Development Kit (JDK): Certifique-se de ter o JDK instalado em sua máquina. Você pode baixá-lo do[Site da Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
   
2.  Aspose.Words para Java: Você precisará da biblioteca Aspose.Words. Você pode baixar a versão mais recente em[Página de lançamentos da Aspose](https://releases.aspose.com/words/java/).

3. IDE: Um Ambiente de Desenvolvimento Integrado (IDE) como IntelliJ IDEA ou Eclipse tornará a codificação mais fácil.

4. Conhecimento básico de Java: a familiaridade com os conceitos de programação Java ajudará você a entender melhor os trechos de código.

5. Dados de exemplo: Para este tutorial, usaremos um arquivo XML chamado "List of people.xml" para simular uma fonte de dados. Você pode criar este arquivo com dados de exemplo para teste.

## Etapa 1: Crie um novo documento

Primeiro, precisamos criar um novo documento onde nossa tabela residirá. Esta é a tela para nosso trabalho.

```java
Document doc = new Document();
```

 Aqui, instanciamos um novo`Document` objeto. Isso servirá como nosso documento de trabalho onde construiremos nossa tabela.

## Etapa 2: Inicializar o DocumentBuilder

 A seguir, usaremos o`DocumentBuilder` classe, o que nos permite manipular o documento com mais facilidade.

```java
DocumentBuilder builder = new DocumentBuilder(doc);
```

 O`DocumentBuilder` objeto fornece métodos para inserir tabelas, texto e outros elementos no documento.

## Etapa 3: Defina a orientação da página

Como esperamos que nossa tabela seja larga, definiremos a orientação da página como paisagem.

```java
doc.getFirstSection().getPageSetup().setOrientation(Orientation.LANDSCAPE);
```

Esta etapa é crucial porque garante que nossa tabela se encaixe perfeitamente na página sem ser cortada.

## Etapa 4: Carregar dados do XML

 Agora, precisamos carregar nossos dados do arquivo XML em um`DataTable`. É daí que vêm nossos dados.

```java
DataSet ds = new DataSet();
ds.readXml(getMyDir() + "List of people.xml");
DataTable dataTable = ds.getTables().get(0);
```

 Aqui, lemos o arquivo XML e recuperamos a primeira tabela do conjunto de dados. Isto`DataTable` conterá os dados que queremos exibir em nosso documento.

## Etapa 5: Importar a tabela do DataTable

Agora vem a parte emocionante: importar nossos dados para o documento como uma tabela.

```java
Table table = importTableFromDataTable(builder, dataTable, true);
```

 Nós chamamos o método`importTableFromDataTable` , passando o`DocumentBuilder` , nosso`DataTable`, e um booleano para indicar se deve incluir títulos de coluna.

## Etapa 6: estilize a tabela

Depois que tivermos nossa mesa, podemos aplicar algum estilo para deixá-la bonita.

```java
table.setStyleIdentifier(StyleIdentifier.MEDIUM_LIST_2_ACCENT_1);
table.setStyleOptions(TableStyleOptions.FIRST_ROW | TableStyleOptions.ROW_BANDS | TableStyleOptions.LAST_COLUMN);
```

Este código aplica um estilo predefinido à tabela, melhorando seu apelo visual e legibilidade.

## Etapa 7: Remova células indesejadas

Se você tiver alguma coluna que não queira exibir, como uma coluna de imagem, você pode removê-la facilmente.

```java
table.getFirstRow().getLastCell().removeAllChildren();
```

Esta etapa garante que nossa tabela mostre apenas as informações relevantes.

## Etapa 8: Salve o documento

Por fim, salvamos nosso documento com a tabela gerada.

```java
doc.save(getArtifactsDir() + "WorkingWithTables.BuildTableFromDataTable.docx");
```

Esta linha salva o documento no diretório especificado, permitindo que você revise os resultados.

## O método importTableFromDataTable

 Vamos dar uma olhada mais de perto no`importTableFromDataTable` método. Este método é responsável por criar a estrutura da tabela e preenchê-la com dados.

### Etapa 1: Inicie a tabela

Primeiro, precisamos iniciar uma nova tabela no documento.

```java
Table table = builder.startTable();
```

Isso inicializa uma nova tabela em nosso documento.

### Etapa 2: Adicionar títulos de coluna

 Se quisermos incluir títulos de coluna, verificamos o`importColumnHeadings` bandeira.

```java
if (importColumnHeadings) {
    // Armazene a formatação original
    boolean boldValue = builder.getFont().getBold();
    int paragraphAlignmentValue = builder.getParagraphFormat().getAlignment();

    // Definir formatação de título
    builder.getFont().setBold(true);
    builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);

    // Inserir nomes de colunas
    for (DataColumn column : dataTable.getColumns()) {
        builder.insertCell();
        builder.writeln(column.getColumnName());
    }

    builder.endRow();

    // Restaurar formatação original
    builder.getFont().setBold(boldValue);
    builder.getParagraphFormat().setAlignment(paragraphAlignmentValue);
}
```

 Este bloco de código formata a linha de título e insere os nomes das colunas do`DataTable`.

### Etapa 3: preencher a tabela com dados

 Agora, fazemos um loop em cada linha do`DataTable` para inserir dados na tabela.

```java
for (DataRow dataRow : (Iterable<DataRow>) dataTable.getRows()) {
    for (Object item : dataRow.getItemArray()) {
        builder.insertCell();
        switch (item.getClass().getName()) {
            case "DateTime":
                Date dateTime = (Date) item;
                SimpleDateFormat simpleDateFormat = new SimpleDateFormat("MMMM d, yyyy");
                builder.write(simpleDateFormat.format(dateTime));
                break;
            default:
                builder.write(item.toString());
                break;
        }
    }
    builder.endRow();
}
```

Nesta seção, lidamos com diferentes tipos de dados, formatando datas adequadamente e inserindo outros dados como texto.

### Etapa 4: Finalize a mesa

Por fim, finalizamos a tabela quando todos os dados foram inseridos.

```java
builder.endTable();
```

 Esta linha marca o fim da nossa tabela, permitindo que`DocumentBuilder` para saber que terminamos esta seção.

## Conclusão

E aí está! Você aprendeu com sucesso como gerar uma tabela a partir de uma DataTable usando Aspose.Words para Java. Seguindo essas etapas, você pode facilmente criar tabelas dinâmicas em seus documentos com base em várias fontes de dados. Quer você esteja gerando relatórios ou faturas, esse método simplificará seu fluxo de trabalho e aprimorará seu processo de criação de documentos.

## Perguntas frequentes

### O que é Aspose.Words para Java?
Aspose.Words para Java é uma biblioteca poderosa para criar, manipular e converter documentos do Word programaticamente.

### Posso usar o Aspose.Words gratuitamente?
 Sim, o Aspose oferece uma versão de teste gratuita. Você pode baixá-lo em[aqui](https://releases.aspose.com/).

### Como estilizar tabelas no Aspose.Words?
Você pode aplicar estilos usando identificadores de estilo predefinidos e opções fornecidas pela biblioteca.

### Que tipos de dados posso inserir em tabelas?
Você pode inserir vários tipos de dados, incluindo texto, números e datas, que podem ser formatados adequadamente.

### Onde posso obter suporte para o Aspose.Words?
 Você pode encontrar suporte e fazer perguntas no[Fórum Aspose](https://forum.aspose.com/c/words/8/).