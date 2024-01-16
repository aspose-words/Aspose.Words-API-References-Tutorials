---
title: Word 문서에 인라인 이미지 삽입
linktitle: Word 문서에 인라인 이미지 삽입
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에 인라인 이미지를 삽입하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/add-content-using-documentbuilder/insert-inline-image/
---
이 포괄적인 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에 인라인 이미지를 삽입하는 방법을 배웁니다. 우리는 프로세스를 안내하고 필요한 C# 코드 조각을 제공할 것입니다. 이 가이드가 끝나면 문서 텍스트에 이미지를 직접 추가할 수 있게 됩니다.

## 전제조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
- 시스템에 설치된 .NET 라이브러리용 Aspose.Words.

## 1단계: 새 문서 및 DocumentBuilder 만들기
시작하려면 Document 클래스를 사용하여 새 문서를 만들고 DocumentBuilder 객체를 초기화합니다.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2단계: 인라인 이미지 삽입
그런 다음 DocumentBuilder 클래스의 InsertImage 메서드를 사용하여 인라인 이미지를 문서에 삽입합니다. 이미지 파일 경로를 매개변수로 제공합니다.

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## 3단계: 문서 저장
인라인 이미지를 삽입한 후 Document 클래스의 Save 메서드를 사용하여 문서를 파일에 저장합니다.

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

### .NET용 Aspose.Words를 사용하여 인라인 이미지 삽입을 위한 예제 소스 코드
다음은 .NET용 Aspose.Words를 사용하여 인라인 이미지를 삽입하기 위한 전체 소스 코드입니다.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(ImagesDir + "Transparent background logo.png");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

## 결론
축하해요! Aspose.Words for .NET을 사용하여 Word 문서에 인라인 이미지를 삽입하는 방법을 성공적으로 배웠습니다. 단계별 가이드를 따르고 제공된 소스 코드를 활용하면 이제 문서 텍스트 내에 이미지를 원활하게 추가할 수 있습니다.

인라인 이미지는 그림, 로고 또는 기타 시각적 요소를 문서 흐름에 직접 추가하는 등 다양한 시나리오에 유용합니다.

### Word 문서에 인라인 이미지 삽입에 대한 FAQ

#### Q: Word 문서 내의 인라인 이미지 크기를 조정할 수 있나요?

A: 예, .NET용 Aspose.Words를 사용하여 인라인 이미지의 크기를 조정할 수 있습니다. 이미지를 삽입한 후 이미지를 나타내는 Shape 개체의 너비 및 높이 속성을 조정하여 크기를 조작할 수 있습니다.

#### Q: 접근성을 위해 인라인 이미지에 대체 텍스트를 추가할 수 있나요?

A: 예. 인라인 이미지에 대체 텍스트를 추가하여 접근성을 높일 수 있습니다. Aspose.Words for .NET은 이미지에 대체 텍스트를 추가하여 화면 판독기와 기타 보조 기술이 시각 장애가 있는 사용자에게 이미지 콘텐츠를 설명할 수 있도록 지원합니다.

#### Q: 인라인 이미지에 서식이나 스타일을 적용할 수 있나요?

답: 물론이죠! Aspose.Words for .NET은 인라인 이미지에 대한 광범위한 형식 지정 옵션을 제공합니다. 문서의 시각적 디자인에 맞게 다양한 스타일, 테두리, 효과 및 기타 서식 특성을 이미지에 적용할 수 있습니다.

#### Q: .NET용 Aspose.Words는 스트림 또는 바이트 배열에서 이미지 삽입을 지원합니까?

A: 예, .NET용 Aspose.Words를 사용하여 스트림이나 바이트 배열에서 인라인 이미지를 삽입할 수 있습니다. 이를 통해 외부 소스에서 로드된 이미지나 동적으로 생성된 이미지로 작업할 수 있습니다.

#### Q: 텍스트 콘텐츠 내 특정 위치에 이미지를 삽입할 수 있나요?

A: 예, Aspose.Words for .NET의 DocumentBuilder 클래스는 인라인 이미지의 삽입 위치에 대한 정확한 제어를 제공합니다. 이미지가 삽입되어야 하는 텍스트 내의 정확한 위치를 지정할 수 있습니다.