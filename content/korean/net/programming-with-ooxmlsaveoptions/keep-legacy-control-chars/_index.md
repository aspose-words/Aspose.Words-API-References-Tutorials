---
title: 레거시 제어 문자 유지
linktitle: 레거시 제어 문자 유지
second_title: Aspose.Words 문서 처리 API
description: 이 단계별 가이드를 통해 .NET용 Aspose.Words를 사용하여 Word 문서에서 레거시 제어 문자를 보존하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-ooxmlsaveoptions/keep-legacy-control-chars/
---
## 소개

Word 문서에 있는 이상하고 보이지 않는 제어 문자 때문에 당황한 적이 있습니까? 형식과 기능을 망칠 수 있는 작고 숨겨진 그렘린과 같습니다. 다행히 .NET용 Aspose.Words는 문서를 저장할 때 이러한 레거시 제어 문자를 그대로 유지하는 편리한 기능을 제공합니다. 이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 이러한 제어 문자를 관리하는 방법에 대해 자세히 알아봅니다. 우리는 단계별로 분석하여 모든 세부 사항을 파악할 수 있도록 할 것입니다. 시작할 준비가 되셨나요? 뛰어들어보자!

## 전제조건

시작하기 전에 다음 사항이 있는지 확인하세요.

1.  .NET용 Aspose.Words: 다음에서 다운로드하고 설치하세요.[여기](https://releases.aspose.com/words/net/).
2.  유효한 Aspose 라이선스: 임시 라이선스를 얻을 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
3. 개발 환경: Visual Studio 또는 .NET을 지원하는 기타 IDE.
4. C#에 대한 기본 지식: C# 프로그래밍 언어에 익숙하면 도움이 됩니다.

## 네임스페이스 가져오기

코드를 작성하기 전에 필요한 네임스페이스를 가져와야 합니다. C# 파일 맨 위에 다음 줄을 추가합니다.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## 1단계: 프로젝트 설정

먼저 Visual Studio(또는 선호하는 IDE)에서 프로젝트를 설정해야 합니다. 

1. 새 C# 프로젝트 만들기: Visual Studio를 열고 새 C# 콘솔 애플리케이션 프로젝트를 만듭니다.
2. .NET용 Aspose.Words 설치: NuGet 패키지 관리자를 사용하여 .NET용 Aspose.Words를 설치합니다. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 버튼으로 클릭하고 "NuGet 패키지 관리"를 선택한 다음 "Aspose.Words"를 검색하여 설치합니다.

## 2단계: 문서 로드

다음으로 레거시 제어 문자가 포함된 Word 문서를 로드합니다.

1. 문서 경로 지정: 문서 디렉터리의 경로를 설정합니다.
   
   ```csharp
   string dataDir = "YOUR DOCUMENT DIRECTORY";
   ```

2.  문서 로드:`Document` 문서를 로드하는 클래스입니다.

   ```csharp
   Document doc = new Document(dataDir + "Legacy control character.doc");
   ```

## 3단계: 저장 옵션 구성

이제 레거시 제어 문자를 그대로 유지하도록 저장 옵션을 구성해 보겠습니다.

1.  저장 옵션 생성: 인스턴스 초기화`OoxmlSaveOptions` 그리고 설정`KeepLegacyControlChars`재산`true`.

   ```csharp
   OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc)
   {
       KeepLegacyControlChars = true
   };
   ```

## 4단계: 문서 저장

마지막으로 구성된 저장 옵션을 사용하여 문서를 저장합니다.

1.  문서 저장:`Save` 의 방법`Document` 지정된 저장 옵션으로 문서를 저장하는 클래스입니다.

   ```csharp
   doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
   ```

## 결론

그리고 거기에 있습니다! 다음 단계를 수행하면 Aspose.Words for .NET에서 Word 문서 작업을 할 때 레거시 제어 문자가 유지되도록 할 수 있습니다. 이 기능은 특히 제어 문자가 중요한 역할을 하는 복잡한 문서를 처리할 때 생명의 은인이 될 수 있습니다. 

## FAQ

### 레거시 제어 문자란 무엇입니까?

레거시 제어 문자는 이전 문서에서 서식과 레이아웃을 제어하는 데 사용되는 인쇄되지 않는 문자입니다.

### 이러한 제어 문자를 유지하는 대신 제거할 수 있나요?

예, 필요한 경우 .NET용 Aspose.Words를 사용하여 이러한 문자를 제거하거나 바꿀 수 있습니다.

### 이 기능은 .NET용 Aspose.Words의 모든 버전에서 사용할 수 있나요?

이 기능은 최신 버전에서 사용할 수 있습니다. 모든 기능에 액세스하려면 최신 버전을 사용하십시오.

### .NET용 Aspose.Words를 사용하려면 라이선스가 필요합니까?

 예, 유효한 라이센스가 필요합니다. 평가 목적으로 임시 라이센스를 얻을 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).

### .NET용 Aspose.Words에 대한 추가 문서는 어디서 찾을 수 있나요?

 자세한 문서를 찾을 수 있습니다[여기](https://reference.aspose.com/words/net/).
 