---
title: Aspose.Words for Java에서 문서에 워터마크 사용하기
linktitle: 문서에 워터마크 사용
second_title: Aspose.Words Java 문서 처리 API
description: Aspose.Words for Java에서 문서에 워터마크를 추가하는 방법을 알아보세요. 전문적인 문서에 맞게 텍스트 및 이미지 워터마크를 사용자 정의하세요.
type: docs
weight: 15
url: /ko/java/document-conversion-and-export/using-watermarks-to-documents/
---

## Aspose.Words for Java의 문서에 워터마크 추가 소개

이 튜토리얼에서는 Aspose.Words for Java API를 사용하여 문서에 워터마크를 추가하는 방법을 살펴보겠습니다. 워터마크는 문서의 상태, 기밀성 또는 기타 관련 정보를 나타내기 위해 텍스트나 그래픽으로 문서에 레이블을 지정하는 유용한 방법입니다. 이 가이드에서는 텍스트와 이미지 워터마크를 모두 다룰 것입니다.

## Java용 Aspose.Words 설정

문서에 워터마크를 추가하기 전에 Java용 Aspose.Words를 설정해야 합니다. 시작하려면 다음 단계를 따르세요.

1.  Java용 Aspose.Words를 다음에서 다운로드하세요.[여기](https://releases.aspose.com/words/java/).
2. Java 프로젝트에 Aspose.Words for Java 라이브러리를 추가하세요.
3. Java 코드에서 필요한 클래스를 가져옵니다.

이제 라이브러리가 설정되었으므로 워터마크를 추가해 보겠습니다.

## 텍스트 워터마크 추가

텍스트 워터마크는 문서에 텍스트 정보를 추가하려는 경우 일반적으로 선택됩니다. Aspose.Words for Java를 사용하여 텍스트 워터마크를 추가하는 방법은 다음과 같습니다.

```java
//문서 인스턴스 만들기
Document doc = new Document("Document.docx");

// TextWatermark옵션 정의
TextWatermarkOptions options = new TextWatermarkOptions();
options.setFontFamily("Arial");
options.setFontSize(36f);
options.setColor(Color.BLACK);
options.setLayout(WatermarkLayout.HORIZONTAL);
options.setSemitransparent(false);

// 워터마크 텍스트 및 옵션 설정
doc.getWatermark().setText("Test", options);

// 워터마크가 포함된 문서를 저장하세요.
doc.save("DocumentWithWatermark.docx");
```

## 이미지 워터마크 추가

텍스트 워터마크 외에도 문서에 이미지 워터마크를 추가할 수도 있습니다. 이미지 워터마크를 추가하는 방법은 다음과 같습니다.

```java
//문서 인스턴스 만들기
Document doc = new Document("Document.docx");

// 워터마크용 이미지 로드
byte[] imageBytes = Files.readAllBytes(Paths.get("watermark.png"));
Shape watermark = new Shape(doc, ShapeType.IMAGE);
watermark.getImageData().setImage(imageBytes);

// 워터마크 크기 및 위치 설정
watermark.setWidth(200.0);
watermark.setHeight(100.0);
watermark.setRelativeHorizontalPosition(RelativeHorizontalPosition.CENTER);
watermark.setRelativeVerticalPosition(RelativeVerticalPosition.CENTER);

// 문서에 워터마크 추가
doc.getFirstSection().getBody().getFirstParagraph().appendChild(watermark);

// 워터마크가 포함된 문서를 저장하세요.
doc.save("DocumentWithImageWatermark.docx");
```

## 워터마크 사용자 정의

워터마크의 모양과 위치를 조정하여 워터마크를 사용자 정의할 수 있습니다. 텍스트 워터마크의 경우 글꼴, 크기, 색상, 레이아웃을 변경할 수 있습니다. 이미지 워터마크의 경우 이전 예에서 설명한 대로 크기와 위치를 수정할 수 있습니다.

## 워터마크 제거

문서에서 워터마크를 제거하려면 다음 코드를 사용할 수 있습니다.

```java
//문서 인스턴스 만들기
Document doc = new Document("DocumentWithWatermark.docx");

// 워터마크를 제거하세요
for (Shape shape : doc.getShapes())
{
    if (shape.getName().contains("Watermark"))
    {
        shape.remove();
    }
}

// 워터마크 없이 문서를 저장하세요.
doc.save("DocumentWithoutWatermark.docx");
```


## 결론

이 튜토리얼에서는 Aspose.Words for Java를 사용하여 문서에 워터마크를 추가하는 방법을 배웠습니다. 텍스트 또는 이미지 워터마크를 추가해야 하는지 여부에 관계없이 Aspose.Words는 이를 효율적으로 사용자 정의하고 관리할 수 있는 도구를 제공합니다. 더 이상 필요하지 않은 워터마크를 제거하여 문서를 깨끗하고 전문적으로 유지할 수도 있습니다.

## FAQ

### 텍스트 워터마크의 글꼴을 어떻게 변경할 수 있나요?

 텍스트 워터마크의 글꼴을 변경하려면`setFontFamily` 에 있는 재산`TextWatermarkOptions`. 예를 들어:

```java
options.setFontFamily("Times New Roman");
```

### 단일 문서에 여러 개의 워터마크를 추가할 수 있나요?

 예, 여러 개의 워터마크를 생성하여 문서에 여러 개의 워터마크를 추가할 수 있습니다.`Shape` 다른 설정을 가진 개체를 문서에 추가합니다.

### 워터마크 회전이 가능한가요?

 예, 다음을 설정하여 워터마크를 회전할 수 있습니다.`setRotation` 에 있는 재산`Shape` 물체. 양수 값은 워터마크를 시계 방향으로 회전하고, 음수 값은 시계 반대 방향으로 회전합니다.

### 워터마크를 반투명하게 만들려면 어떻게 해야 합니까?

 워터마크를 반투명하게 만들려면`setSemitransparent`재산`true` 에서`TextWatermarkOptions`.

### 문서의 특정 섹션에 워터마크를 추가할 수 있나요?

예, 섹션을 반복하고 원하는 섹션에 워터마크를 추가하여 문서의 특정 섹션에 워터마크를 추가할 수 있습니다.