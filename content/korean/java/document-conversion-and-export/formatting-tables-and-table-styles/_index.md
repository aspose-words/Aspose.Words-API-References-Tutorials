---
title: Aspose.Words for Java의 테이블 및 테이블 스타일 형식 지정
linktitle: 표 및 표 스타일 서식 지정
second_title: Aspose.Words Java 문서 처리 API
description: Aspose.Words for Java에서 테이블 형식을 지정하고 테이블 스타일을 적용하는 방법을 알아보세요. 효과적인 테이블 형식 지정을 위한 소스 코드가 포함된 단계별 가이드를 살펴보세요. Aspose.Words로 문서 레이아웃을 향상하세요.
type: docs
weight: 17
url: /ko/java/document-conversion-and-export/formatting-tables-and-table-styles/
---

## Aspose.Words for Java의 테이블 형식 및 테이블 스타일 소개

표는 문서의 정보를 구조화하고 구성하는 데 중요한 역할을 합니다. Aspose.Words for Java는 테이블 서식을 지정하고 테이블 스타일을 적용하여 문서의 시각적 매력을 향상시키는 강력한 기능을 제공합니다. 이 단계별 가이드에서는 Aspose.Words for Java를 사용하여 테이블 형식 지정 및 테이블 스타일 적용의 다양한 측면을 살펴보겠습니다.

## 전제조건

세부 사항을 살펴보기 전에 Aspose.Words for Java 라이브러리가 프로젝트에 통합되어 있는지 확인하세요. Aspose 웹사이트에서 다운로드할 수 있습니다:[Java용 Aspose.Words 다운로드](https://releases.aspose.com/words/java/).

## 표와 주변 텍스트 사이의 거리 얻기

시작하려면 문서에서 표와 주변 텍스트 사이의 거리를 검색하는 방법을 살펴보겠습니다.

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
System.out.println("Distance Top: " + table.getDistanceTop());
System.out.println("Distance Bottom: " + table.getDistanceBottom());
System.out.println("Distance Right: " + table.getDistanceRight());
System.out.println("Distance Left: " + table.getDistanceLeft());
```

## 표에 윤곽선 테두리 적용

다음 코드를 사용하여 표를 페이지 중앙에 정렬하고, 기존 테두리를 지우고, 사용자 정의 개요 테두리를 설정할 수 있습니다.

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setAlignment(TableAlignment.CENTER);
table.clearBorders();
table.setBorder(BorderType.LEFT, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setBorder(BorderType.RIGHT, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setBorder(BorderType.TOP, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setBorder(BorderType.BOTTOM, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setShading(TextureIndex.TEXTURE_SOLID, Color.lightGray, new Color(0, true));
```

## 테두리가 있는 표 만들기

이 코드 조각은 표를 만들고 표와 해당 셀 모두에 테두리를 설정하는 방법을 보여줍니다.

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.clearBorders();
table.setBorders(LineStyle.SINGLE, 1.5, Color.GREEN);
```

## 행 형식 수정

표 내 특정 행의 형식을 수정하는 방법을 알아보세요.

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Row firstRow = table.getFirstRow();
firstRow.getRowFormat().getBorders().setLineStyle(LineStyle.NONE);
firstRow.getRowFormat().setHeightRule(HeightRule.AUTO);
firstRow.getRowFormat().setAllowBreakAcrossPages(true);
```

## 행 서식 적용

이 예에서는 테이블의 전체 행에 서식을 적용하는 방법을 보여줍니다.

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
builder.insertCell();
RowFormat rowFormat = builder.getRowFormat();
rowFormat.setHeight(100.0);
rowFormat.setHeightRule(HeightRule.EXACTLY);
table.setLeftPadding(30.0);
table.setRightPadding(30.0);
table.setTopPadding(30.0);
table.setBottomPadding(30.0);
builder.writeln("I'm a wonderfully formatted row.");
```

## 셀 패딩 설정

테이블의 개별 셀에 패딩을 설정하는 방법을 살펴보세요.

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.startTable();
builder.insertCell();
builder.getCellFormat().setPaddings(30.0, 50.0, 30.0, 50.0);
builder.writeln("I'm a wonderfully formatted cell.");
```

## 셀 서식 수정

표 내 특정 셀의 서식을 수정하는 방법을 알아보세요.

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
firstCell.getCellFormat().setWidth(30.0);
firstCell.getCellFormat().setOrientation(TextOrientation.DOWNWARD);
firstCell.getCellFormat().getShading().setForegroundPatternColor(Color.GREEN);
```

## 테두리가 다른 테이블과 셀 서식 지정

표의 개별 셀에 서로 다른 테두리를 설정하는 방법을 알아보세요.

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
// 표 테두리 설정
table.setBorders(LineStyle.SINGLE, 2.0, Color.BLACK);
// 개별 셀에 대한 셀 음영 설정
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.RED);
// 셀에 내용 추가
builder.writeln("Cell #1");
builder.insertCell();
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.GREEN);
builder.writeln("Cell #2");
// 다음 행의 셀 서식 지우기
builder.getCellFormat().clearFormatting();
// 이 행의 첫 번째 셀에 대해 더 큰 테두리를 만듭니다.
builder.getCellFormat().getBorders().getLeft().setLineWidth(4.0);
builder.getCellFormat().getBorders().getRight().setLineWidth(4.0);
builder.getCellFormat().getBorders().getTop().setLineWidth(4.0);
builder.getCellFormat().getBorders().getBottom().setLineWidth(4.0);
builder.writeln("Cell #3");
builder.insertCell();
builder.getCellFormat().clearFormatting();
builder.writeln("Cell #4");
```

## 테이블 제목 및 설명 설정

테이블에 제목과 설명을 추가합니다.

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setTitle("Test title");
table.setDescription("Test description");
```

## 10단계: 셀 간격 허용

셀 간격을 허용하고 테이블에 해당 값을 설정합니다.

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setAllowCellSpacing(true);
table.setCellSpacing(2.0);
```

## 11단계: 스타일을 적용한 표 만들기

미리 정의된 스타일로 테이블을 만듭니다.

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
table.setStyleIdentifier(StyleIdentifier.MEDIUM_SHADING_1_ACCENT_1);
table.setStyleOptions(TableStyleOptions.FIRST_COLUMN | TableStyleOptions.ROW_BANDS | TableStyleOptions.FIRST_ROW);
builder.writeln("Item");
builder.getCellFormat().setRightPadding(40.0);
builder.insertCell();
builder.writeln("Quantity (kg)");
```

## 12단계: 스타일에서 셀 및 행의 서식 확장

표 스타일을 확장하여 셀과 행에 서식을 적용하는 방법을 알아보세요.

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
Color cellShadingBefore = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
doc.expandTableStylesToDirectFormatting();
Color cellShadingAfter = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
```

## 13단계: 표 스타일 만들기

특정 형식으로 사용자 정의 표 스타일을 만듭니다.

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
table.setStyleIdentifier(StyleIdentifier.MEDIUM_SHADING_1_ACCENT_1);
table.setStyleOptions(TableStyleOptions.FIRST_COLUMN | TableStyleOptions.ROW_BANDS | TableStyleOptions.FIRST_ROW);
builder.writeln("Item");
builder.getCellFormat().setRightPadding(40.0);
builder.insertCell();
builder.writeln("Quantity (kg)");
```

## 14단계: 조건부 서식 정의

테이블의 행에 조건부 서식을 적용합니다.

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
TableStyle tableStyle = (TableStyle) doc.getStyles().add(StyleType.TABLE, "MyTableStyle1");
tableStyle.getConditionalStyles().getFirstRow().getShading().setBackgroundPatternColor(Color.yellow);
table.setStyle(tableStyle);
```

## 15단계: TableCell 서식 설정

개별 셀에 대한 특정 형식을 설정합니다.

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.startTable();
builder.insertCell();
CellFormat cellFormat = builder.getCellFormat();
cellFormat.setWidth(250.0);
cellFormat.setLeftPadding(30.0);
cellFormat.setRightPadding(30.0);
cellFormat.setTopPadding(30.0);
cellFormat.setBottomPadding(30.0);
builder.writeln("I'm a wonderfully formatted cell.");
```

## 16단계: TableRow 서식 설정

테이블의 전체 행에 서식을 적용합니다.

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
RowFormat rowFormat = builder.getRowFormat();
rowFormat.setHeight(100.0);
rowFormat.setHeightRule(HeightRule.EXACTLY);
table.setLeftPadding(30.0);
table.setRightPadding(30.0);
table.setTopPadding(30.0);
table.setBottomPadding(30.0);
builder.writeln("I'm a wonderfully formatted row.");
```

## 결론

Aspose.Words for Java를 사용하면 테이블 형식을 지정하고 테이블 스타일을 정확하게 적용할 수 있습니다. 개별 셀 서식 수정부터 사용자 정의 표 스타일 생성에 이르기까지 문서를 시각적으로 매력적이고 체계적으로 만드는 도구가 있습니다.

## FAQ

### Java용 Aspose.Words를 어떻게 다운로드하나요?

 Aspose 웹사이트에서 Java용 Aspose.Words를 다운로드할 수 있습니다.[Java용 Aspose.Words 다운로드](https://releases.aspose.com/words/java/).

### 표 내의 개별 셀에 서로 다른 테두리를 적용할 수 있습니까?

예, 이 가이드에 설명된 대로 Aspose.Words for Java를 사용하여 테이블 내의 개별 셀에 대해 서로 다른 테두리를 설정할 수 있습니다.

### 테이블 제목과 설명을 설정하는 목적은 무엇인가요?

표 제목과 설명을 설정하면 문서의 접근성과 구성이 향상되어 독자와 보조 기술이 내용을 더 쉽게 이해할 수 있습니다.

### 테이블의 특정 행에 조건부 서식을 적용하려면 어떻게 해야 합니까?

이 가이드에 표시된 대로 조건부 서식 규칙을 사용하여 사용자 정의 표 스타일을 정의하여 표의 특정 행에 조건부 서식을 적용할 수 있습니다.

### Aspose.Words for Java에 대한 추가 문서와 리소스는 어디에서 찾을 수 있나요?

 포괄적인 문서 및 추가 리소스를 보려면 Aspose.Words for Java 문서를 방문하세요.[Aspose.Words for Java 문서](https://reference.aspose.com/words/java/).