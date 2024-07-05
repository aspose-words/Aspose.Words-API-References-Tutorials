---
title: 링크
linktitle: 링크
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 링크를 삽입하는 방법을 알아보세요. 단계별 가이드.
type: docs
weight: 10
url: /ko/net/working-with-markdown/link/
---

이 예에서는 Aspose.Words for .NET에서 링크 기능을 사용하는 방법을 안내합니다. 링크는 웹사이트나 기타 문서에 대한 클릭 가능한 참조를 만드는 데 사용됩니다.

## 1단계: 문서 생성기 사용

먼저 문서 생성기를 사용하여 문서에 콘텐츠를 추가하겠습니다.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2단계: 링크 삽입

 다음을 사용하여 링크를 삽입할 수 있습니다.`InsertHyperlink` 문서 생성기의 방법. 여기서는 "Aspose"라는 링크 텍스트와 대상 URL을 지정해야 합니다.

```csharp
builder.InsertHyperlink("Aspose", "https://www.aspose.com", 거짓);
```

### .NET용 Aspose.Words와의 링크에 대한 예제 소스 코드


```csharp
// 문서 빌더를 사용하여 문서에 콘텐츠를 추가합니다.
DocumentBuilder builder = new DocumentBuilder();

// 링크를 삽입하세요.
builder.InsertHyperlink("Aspose", "https://www.aspose.com", 거짓);
```
축하합니다! 이제 Aspose.Words for .NET에서 링크 기능을 사용하는 방법을 배웠습니다.


### FAQ

#### Q: Aspose.Words의 URL에 어떻게 연결할 수 있나요?

 A: Aspose.Words의 URL 주소에 연결하려면 다음을 사용할 수 있습니다.`<a>` 태그를 지정하세요.`href` URL 주소가 포함된 속성입니다. 예를 들어 다음을 사용할 수 있습니다.`<a href="https://www.aspose.com">Click Here</a>` 표시 텍스트 "여기를 클릭하세요"를 사용하여 URL "https://www.example.com"에 하이퍼링크합니다.

#### Q: Aspose.Words의 내부 북마크에 연결할 수 있나요?

 A: 예, Aspose.Words의 내부 북마크에 연결하는 것이 가능합니다. 당신은 사용할 수 있습니다`<a>` 태그를 지정하세요.`href` 해시(#) 뒤에 책갈피 이름이 포함된 속성입니다. 예를 들어,`<a href="#bookmark1">Go to bookmark 1</a>` 문서의 "bookmark1"이라는 책갈피에 연결됩니다.

#### Q: Aspose.Words에서 링크의 표시 텍스트를 어떻게 사용자 정의할 수 있나요?

A: Aspose.Words에서 링크의 표시 텍스트를 사용자 정의하려면`<a>` 태그. 예를 들어,`<a href="https://www.aspose.com">Click here</a>` "여기를 클릭하세요"라는 텍스트가 하이퍼링크로 표시됩니다.

#### Q: Aspose.Words에서 링크 대상을 지정할 수 있나요?

 A: 예, Aspose.Words에서 링크 대상을 지정할 수 있습니다.`target` 의 속성`<a>` 꼬리표. 예를 들어,`<a href="https://www.aspose.com" target="_blank">Open in new window</a>` 새 창이나 탭에서 링크가 열립니다.