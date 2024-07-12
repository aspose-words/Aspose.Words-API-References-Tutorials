---
title: 영상
linktitle: 영상
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words 단계별 가이드를 통해 이미지를 삽입하고 사용자 정의하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-markdown/image/
---

이 예에서는 Aspose.Words for .NET에서 이미지 기능을 사용하는 방법을 설명합니다. 그림을 사용하면 그림과 그래픽을 문서에 삽입할 수 있습니다.

## 1단계: 문서 생성기 사용

먼저 문서 생성기를 사용하여 문서에 콘텐츠를 추가하겠습니다.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2단계: 이미지 삽입

 다음을 사용하여 이미지를 삽입할 수 있습니다.`Shape` 클래스를 지정하고 이미지 유형을 지정합니다.`ShapeType.Image` . 또한 이미지의 랩 유형을 다음과 같이 설정했습니다.`WrapType.Inline`.

```csharp
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape. WrapType = WrapType. Inline;
```

## 3단계: 이미지 사용자 정의

 예를 들어 전체 경로를 지정하여 이미지를 사용자 정의합니다.`"/attachment/1456/pic001.png"`, 이미지에 제목을 추가합니다.

```csharp
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "Title";
```

### .NET용 Aspose.Words가 포함된 이미지의 소스 코드 예

```csharp
// 문서 빌더를 사용하여 문서에 콘텐츠를 추가합니다.
DocumentBuilder builder = new DocumentBuilder();

// 이미지를 삽입하세요.
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape.WrapType = WrapType.Inline;
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "title";
builder.InsertNode(shape);
```

축하합니다! 이제 Aspose.Words for .NET에서 이미지 기능을 사용하는 방법을 배웠습니다.


### FAQ

#### Q: 로컬 파일의 이미지를 Aspose.Words에 어떻게 삽입할 수 있나요?

 A: 로컬 파일의 이미지를 Aspose.Words에 삽입하려면 다음을 사용할 수 있습니다.`Shape` 수업과`InsertImage` 방법.

#### Q: Aspose.Words의 URL에서 이미지를 삽입할 수 있나요?

 A: 예, Aspose.Words의 URL에서 이미지를 삽입할 수 있습니다. 당신은 같은 것을 사용할 수 있습니다`InsertImage`메서드를 사용하고 로컬 파일 경로 대신 이미지 URL을 지정하세요.

#### Q: Aspose.Words에서 이미지 크기를 어떻게 조정할 수 있나요?

 A: Aspose.Words에서 이미지 크기를 조정하려면`Width`그리고`Height` 의 속성`Shape` 물체.

#### Q: Aspose.Words의 이미지에 필터를 적용할 수 있나요?

 A: 예, Aspose.Words의 이미지에 필터를 적용할 수 있습니다. 예를 들어 다음을 사용하여 이미지에 흐림 필터를 적용할 수 있습니다.`ApplyGaussianBlur` 의 방법`Shape` 물체.

#### Q: Aspose.Words에서 한 이미지를 다른 이미지로 바꾸려면 어떻게 해야 합니까?

 A: Aspose.Words에서 한 이미지를 다른 이미지로 바꾸려면 다음을 사용할 수 있습니다.`Replace` 의 방법`Shape` 수업. 이 메소드는 매개변수로`Shape` 교체할 이미지의 객체와`Shape` 새로운 이미지의 대상.