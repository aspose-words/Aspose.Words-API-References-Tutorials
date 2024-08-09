---
title: 취소선
linktitle: 취소선
second_title: Aspose.Words 문서 처리 API
description: 단계별 가이드를 통해 Aspose.Words for .NET을 사용하여 텍스트에 취소선 서식을 적용하는 방법을 알아보세요. 문서 처리 기술을 향상시키세요.
type: docs
weight: 10
url: /ko/net/working-with-markdown/strikethrough/
---
## 소개

.NET용 Aspose.Words를 사용하여 텍스트에 취소선 서식을 적용하는 방법에 대한 자세한 가이드에 오신 것을 환영합니다. 문서 처리 기술을 향상시키고 텍스트에 독특한 느낌을 더하고 싶다면 잘 찾아오셨습니다. 뛰어들어보자!

## 전제 조건

시작하기 전에 다음 사항이 있는지 확인하세요.

-  .NET용 Aspose.Words: 다운로드[여기](https://releases.aspose.com/words/net/).
- .NET Framework: 시스템에 .NET Framework가 설치되어 있는지 확인하십시오.
- 개발 환경: Visual Studio와 같은 IDE.
- C# 기본 지식: C# 프로그래밍에 대한 지식이 필요합니다.

## 네임스페이스 가져오기

시작하려면 필요한 네임스페이스를 가져와야 합니다. 이는 Aspose.Words 라이브러리와 해당 기능에 액세스하는 데 필수적입니다.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## 1단계: DocumentBuilder 초기화

 그만큼`DocumentBuilder` 클래스는 문서에 콘텐츠를 쉽게 추가할 수 있게 해주는 Aspose.Words의 강력한 도구입니다.

```csharp
// DocumentBuilder를 초기화합니다.
DocumentBuilder builder = new DocumentBuilder();
```

## 2단계: 취소선 속성 설정

이제 텍스트에 취소선 속성을 적용해 보겠습니다. 여기에는`StrikeThrough` 의 재산`Font` 반대하다`true`.

```csharp
// 텍스트를 취소선으로 만듭니다.
builder.Font.StrikeThrough = true;
```

## 3단계: 취소선이 있는 텍스트 작성

 취소선 속성을 설정하면 이제 텍스트를 추가할 수 있습니다. 그만큼`Writeln` 메소드는 문서에 텍스트를 추가합니다.

```csharp
// 취소선을 사용하여 텍스트를 작성합니다.
builder.Writeln("This text will be StrikeThrough");
```

## 결론

그리고 거기에 있습니다! Aspose.Words for .NET을 사용하여 텍스트에 취소선 서식을 성공적으로 추가했습니다. 이 강력한 라이브러리는 문서 처리 및 사용자 정의에 대한 가능성의 세계를 열어줍니다. 보고서, 편지 또는 기타 유형의 문서를 작성하든 이러한 기능을 익히면 생산성과 출력 품질이 확실히 향상됩니다.

## FAQ

### .NET용 Aspose.Words란 무엇입니까?
Aspose.Words for .NET은 개발자가 프로그래밍 방식으로 Word 문서를 생성, 조작 및 변환할 수 있는 강력한 문서 처리 라이브러리입니다.

### 상용 프로젝트에서 Aspose.Words for .NET을 사용할 수 있나요?
 예, 상업용 프로젝트에서 .NET용 Aspose.Words를 사용할 수 있습니다. 구매 옵션을 확인하려면 다음을 방문하세요.[구매 페이지](https://purchase.aspose.com/buy).

### .NET용 Aspose.Words에 대한 무료 평가판이 있습니까?
 예, 무료 평가판을 다운로드할 수 있습니다[여기](https://releases.aspose.com/).

### .NET용 Aspose.Words에 대한 지원을 받으려면 어떻게 해야 합니까?
Aspose 커뮤니티와 전문가로부터 지원을 받을 수 있습니다.[지원 포럼](https://forum.aspose.com/c/words/8).

### .NET용 Aspose.Words를 사용하여 다른 텍스트 서식 옵션을 적용할 수 있나요?
전적으로! Aspose.Words for .NET은 굵게, 기울임꼴, 밑줄 등을 포함한 광범위한 텍스트 서식 옵션을 지원합니다.