---
title: 자동링크
linktitle: 자동링크
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words 단계별 가이드를 통해 자동 링크를 삽입하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-markdown/autolink/
---

이 예에서는 Aspose.Words for .NET에서 "자동 링크" 기능을 사용하는 방법을 설명합니다. 이 기능을 사용하면 문서에 하이퍼링크를 자동으로 삽입할 수 있습니다.

## 1단계: 문서 생성기 사용

먼저 문서 생성기를 사용하여 문서에 콘텐츠를 추가하겠습니다.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2단계: 하이퍼링크 삽입

 다음을 사용하여 하이퍼링크를 삽입할 수 있습니다.`InsertHyperlink` 문서 생성기의 방법. 링크에 표시할 URL과 텍스트를 지정합니다.

```csharp
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", 거짓);
```

## 3단계: 이메일 주소를 링크로 삽입

"mailto:" 접두사를 사용하여 이메일 주소를 링크로 삽입할 수도 있습니다. 이렇게 하면 사용자가 링크를 클릭하여 기본 이메일 클라이언트를 열 수 있습니다.

```csharp
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```

## 4단계: 문서 저장

마지막으로 원하는 형식으로 문서를 저장할 수 있습니다.

### .NET용 Aspose.Words를 사용하는 자동 링크의 예제 소스 코드


```csharp
// 문서 빌더를 사용하여 문서에 콘텐츠를 추가합니다.
DocumentBuilder builder = new DocumentBuilder();

// 하이퍼링크를 삽입합니다.
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", 거짓);
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```


축하합니다! 이제 Aspose.Words for .NET에서 "자동 링크" 기능을 사용하는 방법을 배웠습니다.


### FAQ

#### Q: Aspose.Words에서 URL 주소에 대한 자동 링크를 어떻게 만들 수 있나요?

 A: Aspose.Words의 URL 주소에 대한 자동 링크를 생성하려면 다음을 사용할 수 있습니다.`<a>` 태그를 지정하세요.`href` URL 주소가 포함된 속성입니다. 예를 들어 다음을 사용할 수 있습니다.`<a href="https://www.aspose.com">https://www.aspose.com</a>` "https: //www.aspose.com"에 자동으로 연결됩니다.

#### Q: Aspose.Words에서 자동 링크의 표시 텍스트를 사용자 정의할 수 있습니까?

 A: 예, Aspose.Words에서 자동 링크의 표시 텍스트를 사용자 정의할 수 있습니다. URL 주소를 표시 텍스트로 사용하는 대신,`<a>` 태그. 예를 들어 다음을 사용할 수 있습니다.`<a href="https://www.aspose.com">Click here</a>`"여기를 클릭하세요"라는 텍스트를 자동 링크로 표시합니다.

#### Q: Aspose.Words의 자동 링크에 추가 속성을 추가하려면 어떻게 해야 합니까?

 A: Aspose.Words의 자동 링크에 추가 속성을 추가하려면`<a>` 꼬리표. 예를 들어 다음을 사용할 수 있습니다.`<a href="https://www.aspose.com" target="_blank">Link</a>` 새 창이나 탭에서 링크를 열려면` attribute target="_blank"`.