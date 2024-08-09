---
title: Aspose.Words for Java에서 문서 형태 사용하기
linktitle: 문서 모양 사용
second_title: Aspose.Words Java 문서 처리 API
description: Aspose.Words for Java에서 문서 모양의 강력한 기능을 활용해 보세요. 단계별 예제를 통해 시각적으로 매력적인 문서를 만드는 방법을 알아보세요.
type: docs
weight: 14
url: /ko/java/document-conversion-and-export/using-document-shapes/
---

## Aspose.Words for Java에서 문서 모양 사용 소개

이 포괄적인 가이드에서 우리는 Aspose.Words for Java의 문서 형태의 세계를 탐구할 것입니다. 모양은 시각적으로 매력적이고 대화형 문서를 만드는 데 필수적인 요소입니다. 설명선, 버튼, 이미지 또는 워터마크를 추가해야 하는 경우 Aspose.Words for Java는 이를 효율적으로 수행할 수 있는 도구를 제공합니다. 소스 코드 예제를 통해 이러한 모양을 사용하는 방법을 단계별로 살펴보겠습니다.

## 문서 모양 시작하기

 코드를 시작하기 전에 환경을 설정해 보겠습니다. 프로젝트에 Aspose.Words for Java가 통합되어 있는지 확인하세요. 아직 다운로드하지 않았다면 Aspose 웹사이트에서 다운로드할 수 있습니다.[Java용 Aspose.Words 다운로드](https://releases.aspose.com/words/java/)

## 문서에 도형 추가

### 그룹 모양 삽입

 에이`GroupShape` 여러 모양을 함께 그룹화할 수 있습니다. 다음은`GroupShape`:

```java
Document doc = new Document();
doc.ensureMinimum();

GroupShape groupShape = new GroupShape(doc);
Shape accentBorderShape = new Shape(doc, ShapeType.ACCENT_BORDER_CALLOUT_1);
accentBorderShape.setWidth(100.0);
accentBorderShape.setHeight(100.0);

groupShape.appendChild(accentBorderShape);

Shape actionButtonShape = new Shape(doc, ShapeType.ACTION_BUTTON_BEGINNING);
actionButtonShape.setLeft(100.0);
actionButtonShape.setWidth(100.0);
actionButtonShape.setHeight(200.0);

groupShape.appendChild(actionButtonShape);

groupShape.setWidth(200.0);
groupShape.setHeight(200.0);
groupShape.setCoordSize(new Dimension(200, 200));

DocumentBuilder builder = new DocumentBuilder(doc);
builder.insertNode(groupShape);

doc.save("Your Directory Path" + "WorkingWithShapes.AddGroupShape.docx");
```

### 텍스트 상자 모양 삽입

 텍스트 상자 모양을 삽입하려면`insertShape` 아래 예와 같은 방법을 사용합니다.

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.insertShape(ShapeType.TEXT_BOX, RelativeHorizontalPosition.PAGE, 100.0,
    RelativeVerticalPosition.PAGE, 100.0, 50.0, 50.0, WrapType.NONE);

shape.setRotation(30.0);
builder.writeln();

shape = builder.insertShape(ShapeType.TEXT_BOX, 50.0, 50.0);
shape.setRotation(30.0);

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.DOCX);
saveOptions.setCompliance(OoxmlCompliance.ISO_29500_2008_TRANSITIONAL);

doc.save("Your Directory Path" + "WorkingWithShapes.InsertShape.docx", saveOptions);
```

## 모양 속성 조작

### 종횡비 관리

도형의 가로 세로 비율을 잠글지 여부를 제어할 수 있습니다. 도형의 가로 세로 비율을 잠금 해제하는 방법은 다음과 같습니다.

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.insertImage(getImagesDir() + "Transparent background logo.png");
shape.setAspectRatioLocked(false);

doc.save("Your Directory Path" + "WorkingWithShapes.AspectRatioLocked.docx");
```

### 표 셀에 도형 배치하기

표 셀 내부에 도형을 배치해야 하는 경우 다음 코드를 사용하여 이를 수행할 수 있습니다.

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.startTable();
builder.getRowFormat().setHeight(100.0);
builder.getRowFormat().setHeightRule(HeightRule.EXACTLY);

for (int i = 0; i < 31; i++) {
    if (i != 0 && i % 7 == 0)
        builder.endRow();

    builder.insertCell();
    builder.write("Cell contents");
}

builder.endTable();

Shape watermark = new Shape(doc, ShapeType.TEXT_PLAIN_TEXT);
watermark.setRelativeHorizontalPosition(RelativeHorizontalPosition.PAGE);
watermark.setRelativeVerticalPosition(RelativeVerticalPosition.PAGE);
watermark.isLayoutInCell(true); // 셀에 배치할 경우 표 셀 외부에 모양을 표시합니다.
watermark.setWidth(300.0);
watermark.setHeight(70.0);
watermark.setHorizontalAlignment(HorizontalAlignment.CENTER);
watermark.setVerticalAlignment(VerticalAlignment.CENTER);
watermark.setRotation(-40);
watermark.setFillColor(Color.GRAY);
watermark.setStrokeColor(Color.GRAY);
watermark.getTextPath().setText("watermarkText");
watermark.getTextPath().setFontFamily("Arial");
watermark.setName("WaterMark_{Guid.NewGuid()}");
watermark.setWrapType(WrapType.NONE);

Run run = (Run) doc.getChildNodes(NodeType.RUN, true).get(doc.getChildNodes(NodeType.RUN, true).getCount() - 1);
builder.moveTo(run);
builder.insertNode(watermark);

doc.getCompatibilityOptions().optimizeFor(MsWordVersion.WORD_2010);
doc.save("Your Directory Path" + "WorkingWithShapes.LayoutInCell.docx");
```

## SmartArt 도형 작업

### SmartArt 모양 감지

다음 코드를 사용하여 문서에서 SmartArt 모양을 감지할 수 있습니다.

```java
Document doc = new Document("Your Directory Path" + "SmartArt.docx");
List<Shape> shapes = IterableUtils.toList(doc.getChildNodes(NodeType.SHAPE, true));
int count = (int) shapes.stream().filter(s -> s.hasSmartArt()).count();
System.out.println("The document has " + count + " shapes with SmartArt.");
```

### SmartArt 그림 업데이트

문서 내에서 SmartArt 그림을 업데이트하려면 다음 코드를 사용하세요.

```java
Document doc = new Document("Your Directory Path" + "SmartArt.docx");
for (Shape shape : (Iterable<Shape>) doc.getChildNodes(NodeType.SHAPE, true)) {
    if (shape.hasSmartArt())
        shape.updateSmartArtDrawing();
}
```

## 결론

이 가이드에서는 Aspose.Words for Java의 문서 형태 세계를 탐구했습니다. 문서에 다양한 도형을 추가하고, 해당 속성을 조작하고, SmartArt 도형으로 작업하는 방법을 배웠습니다. 이러한 지식을 활용하면 시각적으로 매력적이고 대화형인 문서를 쉽게 만들 수 있습니다.

## FAQ

### Aspose.Words for Java란 무엇인가요?

Aspose.Words for Java는 개발자가 프로그래밍 방식으로 Word 문서를 생성, 수정 및 변환할 수 있는 Java 라이브러리입니다. 다양한 형식의 문서 작업을 위한 다양한 기능과 도구를 제공합니다.

### Java용 Aspose.Words를 어떻게 다운로드할 수 있나요?

 다음 링크를 따라 Aspose 웹사이트에서 Java용 Aspose.Words를 다운로드할 수 있습니다.[Java용 Aspose.Words 다운로드](https://releases.aspose.com/words/java/)

### 문서 모양을 사용하면 어떤 이점이 있나요?

문서 모양은 문서에 시각적 요소와 상호 작용 기능을 추가하여 문서를 더욱 매력적이고 유익하게 만듭니다. 모양을 사용하면 설명선, 버튼, 이미지, 워터마크 등을 만들어 전반적인 사용자 경험을 향상시킬 수 있습니다.

### 도형의 모양을 사용자 지정할 수 있나요?

예. 크기, 위치, 회전, 채우기 색상 등의 속성을 조정하여 모양의 모양을 맞춤설정할 수 있습니다. Aspose.Words for Java는 모양 사용자 정의를 위한 광범위한 옵션을 제공합니다.

### Aspose.Words for Java는 SmartArt와 호환됩니까?

예, Aspose.Words for Java는 SmartArt 모양을 지원하므로 문서에서 복잡한 다이어그램과 그래픽으로 작업할 수 있습니다.