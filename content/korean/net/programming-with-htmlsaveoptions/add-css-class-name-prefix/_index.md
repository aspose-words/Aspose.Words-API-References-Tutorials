---
title: CSS 클래스 이름 접두사 추가
linktitle: CSS 클래스 이름 접두사 추가
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서를 HTML로 저장할 때 CSS 클래스 이름 접두사를 추가하는 방법을 알아보세요. 단계별 가이드, 코드 조각, FAQ가 포함되어 있습니다.
type: docs
weight: 10
url: /ko/net/programming-with-htmlsaveoptions/add-css-class-name-prefix/
---
## 소개

환영! .NET용 Aspose.Words의 세계에 뛰어들고 계시다면 정말 좋은 경험이 될 것입니다. 오늘은 Aspose.Words for .NET을 사용하여 Word 문서를 HTML로 저장할 때 CSS 클래스 이름 접두사를 추가하는 방법을 살펴보겠습니다. 이 기능은 HTML 파일에서 클래스 이름 충돌을 피하고 싶을 때 매우 편리합니다.

## 전제 조건

시작하기 전에 다음 사항이 있는지 확인하세요.

-  Aspose.Words for .NET: 아직 설치하지 않으셨다면,[여기에서 다운로드하세요](https://releases.aspose.com/words/net/).
- 개발 환경: Visual Studio 또는 기타 C# IDE.
-  Word 문서: 다음과 같은 문서를 사용하겠습니다.`Rendering.docx`. 프로젝트 디렉토리에 넣으세요.

## 네임스페이스 가져오기

먼저 C# 프로젝트로 필요한 네임스페이스를 가져왔는지 확인하세요. 코드 파일 상단에 다음을 추가하세요.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

이제 단계별 가이드를 살펴보겠습니다.

## 1단계: 프로젝트 설정

CSS 클래스 이름 접두사 추가를 시작하기 전에 프로젝트를 설정해 보겠습니다.

### 1.1단계: 새 프로젝트 생성

 Visual Studio를 실행하고 새 콘솔 앱 프로젝트를 만듭니다. 다음과 같이 눈에 띄는 이름을 지정하십시오.`AsposeCssPrefixExample`.

### 1.2단계: .NET용 Aspose.Words 추가

아직 추가하지 않았다면 NuGet을 통해 프로젝트에 .NET용 Aspose.Words를 추가하세요. NuGet 패키지 관리자 콘솔을 열고 다음을 실행하기만 하면 됩니다.

```bash
Install-Package Aspose.Words
```

엄청난! 이제 코딩을 시작할 준비가 되었습니다.

## 2단계: 문서 로드

가장 먼저 해야 할 일은 HTML로 변환하려는 Word 문서를 로드하는 것입니다.

### 2.1단계: 문서 경로 정의

 문서 디렉터리의 경로를 설정합니다. 이 튜토리얼에서는 문서가`Documents` 프로젝트 디렉토리 내에서.

```csharp
string dataDir = @"C:\YourProject\Documents\";
```

### 2.2단계: 문서 로드

이제 Aspose.Words를 사용하여 문서를 로드해 보겠습니다.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 3단계: HTML 저장 옵션 구성

다음으로 CSS 클래스 이름 접두사를 포함하도록 HTML 저장 옵션을 구성해야 합니다.

### 3.1단계: HTML 저장 옵션 생성

 인스턴스화`HtmlSaveOptions` 개체를 선택하고 CSS 스타일 시트 유형을 다음으로 설정합니다.`External`.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
    CssStyleSheetType = CssStyleSheetType.External
};
```

### 3.2단계: CSS 클래스 이름 접두사 설정

 이제`CssClassNamePrefix` 원하는 접두사에 속성을 추가합니다. 이 예에서는 다음을 사용합니다.`"pfx_"`.

```csharp
saveOptions.CssClassNamePrefix = "pfx_";
```

## 4단계: 문서를 HTML로 저장

마지막으로 구성된 옵션을 사용하여 문서를 HTML 파일로 저장해 보겠습니다.


출력 HTML 파일 경로를 지정하고 문서를 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
```

## 5단계: 출력 확인

 프로젝트를 실행한 후`Documents` 접는 사람. 다음과 같은 HTML 파일을 찾아야 합니다.`WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html` . 텍스트 편집기나 브라우저에서 이 파일을 열어 CSS 클래스에 접두사가 있는지 확인하세요.`pfx_`.

## 결론

그리고 거기에 있습니다! 다음 단계를 수행하면 Aspose.Words for .NET을 사용하여 HTML 출력에 CSS 클래스 이름 접두사를 성공적으로 추가했습니다. 이 간단하면서도 강력한 기능은 HTML 문서에서 깔끔하고 충돌 없는 스타일을 유지하는 데 도움이 됩니다.

## FAQ

### 각 저장 작업에 대해 다른 접두사를 사용할 수 있습니까?
 예, 문서를 저장할 때마다 접두어를 변경하여 사용자 정의할 수 있습니다.`CssClassNamePrefix` 재산.

### 이 방법은 인라인 CSS를 지원합니까?
 그만큼`CssClassNamePrefix`속성은 외부 CSS와 함께 작동합니다. 인라인 CSS의 경우 다른 접근 방식이 필요합니다.

### 다른 HTML 저장 옵션을 어떻게 포함할 수 있나요?
 다양한 속성을 구성할 수 있습니다.`HtmlSaveOptions` HTML 출력을 사용자 정의합니다. 확인해보세요[선적 서류 비치](https://reference.aspose.com/words/net/) 자세한 내용은

### HTML을 스트림에 저장할 수 있습니까?
 전적으로! 스트림 객체를 스트림에 전달하여 문서를 스트림에 저장할 수 있습니다.`Save` 방법.

### 문제가 발생할 경우 어떻게 지원을 받을 수 있나요?
 에서 지원을 받으실 수 있습니다.[포럼을 Aspose](https://forum.aspose.com/c/words/8).