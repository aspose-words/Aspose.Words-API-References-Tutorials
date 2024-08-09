---
title: 글머리 기호 목록
linktitle: 글머리 기호 목록
second_title: Aspose.Words 문서 처리 API
description: 이 단계별 가이드를 통해 .NET용 Aspose.Words를 사용하여 Word 문서에서 글머리 기호 목록을 만들고 사용자 정의하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-markdown/bulleted-list/
---
## 소개

.NET용 Aspose.Words의 세계로 뛰어들 준비가 되셨습니까? 오늘은 Word 문서에서 글머리 기호 목록을 만드는 방법을 살펴보겠습니다. 아이디어를 정리하거나 항목을 나열하거나 문서에 약간의 구조를 추가하는 경우 글머리 기호 목록은 매우 편리합니다. 자, 시작해 봅시다!

## 전제 조건

재미있는 코딩을 시작하기 전에 필요한 모든 것이 갖추어져 있는지 확인하세요.

1.  .NET용 Aspose.Words: Aspose.Words 라이브러리가 설치되어 있는지 확인하세요. 아직 갖고 있지 않다면 다음을 수행할 수 있습니다.[여기에서 다운로드하세요](https://releases.aspose.com/words/net/).
2. 개발 환경: Visual Studio와 같은 AC# 개발 환경.
3. 기본 C# 지식: C# 프로그래밍에 대한 기본적인 이해가 있으면 따라가는 데 도움이 됩니다.

## 네임스페이스 가져오기

먼저 필요한 네임스페이스를 가져오겠습니다. 이는 코드가 원활하게 실행될 수 있는 무대를 설정하는 것과 같습니다.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Lists;
```

이제 프로세스를 쉽고 관리하기 쉬운 단계로 나누어 보겠습니다.

## 1단계: 새 문서 만들기

좋습니다. 새 문서를 만드는 것부터 시작해 보겠습니다. 이곳은 모든 마법이 일어날 곳입니다.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2단계: 글머리 기호 목록 형식 적용

다음으로 글머리 기호 목록 형식을 적용하겠습니다. 이는 글머리 기호 목록을 시작하려고 한다는 것을 문서에 알려줍니다.

```csharp
builder.ListFormat.ApplyBulletDefault();
```

## 3단계: 글머리 기호 목록 사용자 정의

여기서는 원하는 대로 글머리 기호 목록을 사용자 정의하겠습니다. 이 예에서는 글머리 기호로 대시(-)를 사용합니다.

```csharp
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";
```

## 4단계: 목록 항목 추가

이제 글머리 기호 목록에 몇 가지 항목을 추가해 보겠습니다. 여기에서 창의력을 발휘하고 필요한 콘텐츠를 추가할 수 있습니다.

```csharp
builder.Writeln("Item 1");
builder.Writeln("Item 2");
```

## 5단계: 하위 항목 추가

좀 더 흥미롭게 만들기 위해 "항목 2" 아래에 몇 가지 하위 항목을 추가해 보겠습니다. 이는 하위 포인트를 구성하는 데 도움이 됩니다.

```csharp
builder.ListFormat.ListIndent();
builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
builder.ListFormat.ListOutdent(); // 기본 목록 수준으로 돌아가기
```

## 결론

그리고 거기에 있습니다! .NET용 Aspose.Words를 사용하여 Word 문서에 글머리 기호 목록을 만들었습니다. 이는 간단한 프로세스이지만 문서를 정리하는 데 매우 강력합니다. 간단한 목록을 만들든 복잡한 중첩 목록을 만들든 Aspose.Words가 도와드립니다.

필요에 따라 다양한 목록 스타일과 형식을 자유롭게 실험해 보세요. 즐거운 코딩하세요!

## FAQ

### 목록에 다른 글머리 기호 기호를 사용할 수 있나요?
    예, 글머리 기호를 변경하여 글머리 기호를 맞춤설정할 수 있습니다.`NumberFormat` 재산.

### 들여쓰기 수준을 더 추가하려면 어떻게 해야 합니까?
    사용`ListIndent` 더 많은 레벨을 추가하는 방법과`ListOutdent` 더 높은 수준으로 돌아가기 위해.

### 글머리 기호 목록과 번호 목록을 혼합할 수 있나요?
   전적으로! 다음을 사용하여 글머리 기호 형식과 숫자 형식 간에 전환할 수 있습니다.`ApplyNumberDefault`그리고`ApplyBulletDefault` 행동 양식.

### 목록 항목의 텍스트 스타일을 지정할 수 있나요?
    예, 다음을 사용하여 목록 항목 내의 텍스트에 다양한 스타일, 글꼴 및 서식을 적용할 수 있습니다.`Font` 의 재산`DocumentBuilder`.

### 다중 열 글머리 기호 목록을 만들려면 어떻게 해야 합니까?
   표 서식을 사용하여 각 셀에 별도의 글머리 기호 목록이 포함된 다중 열 목록을 만들 수 있습니다.