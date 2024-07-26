---
title: Mhtml 리소스에 대한 CID URL 내보내기
linktitle: Mhtml 리소스에 대한 CID URL 내보내기
second_title: Aspose.Words 문서 처리 API
description: 이 단계별 튜토리얼에서 .NET용 Aspose.Words를 사용하여 MHTML 리소스에 대한 Cid URL을 내보내는 방법을 알아보세요. 모든 수준의 개발자에게 적합합니다.
type: docs
weight: 10
url: /ko/net/programming-with-htmlsaveoptions/export-cid-urls-for-mhtml-resources/
---
## 소개

.NET용 Aspose.Words를 사용하여 MHTML 리소스에 대한 Cid URL을 내보내는 기술을 마스터할 준비가 되셨습니까? 숙련된 개발자이든 이제 막 시작하는 개발자이든 이 포괄적인 가이드는 모든 단계를 안내합니다. 이 기사를 마치면 Word 문서에서 MHTML 리소스를 효율적으로 처리하는 방법을 명확하게 이해하게 될 것입니다. 뛰어들어보자!

## 전제조건

시작하기 전에 필요한 모든 것이 갖추어져 있는지 확인하십시오.

-  .NET용 Aspose.Words: 최신 버전의 .NET용 Aspose.Words가 설치되어 있는지 확인하세요. 그렇지 않은 경우 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/words/net/).
- 개발 환경: Visual Studio와 같은 개발 환경입니다.
- C#에 대한 기본 지식: 모든 단계를 안내하겠지만 C#에 대한 기본적인 이해가 도움이 될 것입니다.

## 네임스페이스 가져오기

먼저 필요한 네임스페이스를 가져오겠습니다. 이 단계는 튜토리얼의 단계를 설정합니다.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

이제 프로세스를 간단하고 관리 가능한 단계로 나누어 보겠습니다. 각 단계에는 쉽게 따라할 수 있도록 자세한 설명이 포함되어 있습니다.

## 1단계: 프로젝트 설정

### 1.1단계: 새 프로젝트 생성
Visual Studio를 열고 새 C# 프로젝트를 만듭니다. 작업을 단순하게 유지하려면 콘솔 앱 템플릿을 선택하세요.

### 1.2단계: .NET 참조용 Aspose.Words 추가
.NET용 Aspose.Words를 사용하려면 Aspose.Words 라이브러리에 대한 참조를 추가해야 합니다. NuGet 패키지 관리자를 통해 이 작업을 수행할 수 있습니다.

1. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 버튼으로 클릭합니다.
2. "NuGet 패키지 관리"를 선택하십시오.
3. "Aspose.Words"를 검색하여 설치하세요.

## 2단계: Word 문서 로드

### 2.1단계: 문서 디렉터리 지정
문서 디렉터리의 경로를 정의합니다. 여기에 Word 문서가 있는 곳입니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 바꾸다`"YOUR DOCUMENT DIRECTORY"` 디렉터리의 실제 경로를 사용합니다.

### 2.2단계: 문서 로드
Word 문서를 프로젝트에 로드합니다.

```csharp
Document doc = new Document(dataDir + "Content-ID.docx");
```

## 3단계: HTML 저장 옵션 구성

 인스턴스 만들기`HtmlSaveOptions` 문서를 MHTML로 저장하는 방법을 사용자 정의합니다.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
{
    PrettyFormat = true,
    ExportCidUrlsForMhtmlResources = true
};
```

- `SaveFormat.Mhtml` 출력 형식이 MHTML임을 지정합니다.
- `PrettyFormat = true` 출력이 깔끔하게 형식화되었는지 확인합니다.
- `ExportCidUrlsForMhtmlResources = true` MHTML 리소스에 대한 Cid URL을 내보낼 수 있습니다.

### 4단계: 문서를 MHTML로 저장

4.1단계: 문서 저장
구성된 옵션을 사용하여 문서를 MHTML 파일로 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);
```

## 결론

축하해요! .NET용 Aspose.Words를 사용하여 MHTML 리소스에 대한 Cid URL을 성공적으로 내보냈습니다. 이 튜토리얼에서는 프로젝트 설정, Word 문서 로드, HTML 저장 옵션 구성 및 문서를 MHTML로 저장하는 과정을 안내했습니다. 이제 이러한 단계를 자신의 프로젝트에 적용하고 문서 관리 작업을 향상시킬 수 있습니다.

## FAQ

### MHTML 리소스에 대한 Cid URL을 내보내는 목적은 무엇입니까?
MHTML 리소스에 대한 CID URL을 내보내면 MHTML 파일에 포함된 리소스가 올바르게 참조되어 문서 이식성과 무결성이 향상됩니다.

### 출력 형식을 추가로 사용자 정의할 수 있나요?
 예, Aspose.Words for .NET은 문서 저장을 위한 광범위한 사용자 정의 옵션을 제공합니다. 다음을 참조하세요.[선적 서류 비치](https://reference.aspose.com/words/net/) 상세 사항은.

### .NET용 Aspose.Words를 사용하려면 라이선스가 필요합니까?
 예, Aspose.Words for .NET을 사용하려면 라이선스가 필요합니다. 무료 평가판을 받을 수 있습니다.[여기](https://releases.aspose.com/) 또는 라이센스를 구매하세요[여기](https://purchase.aspose.com/buy).

### 여러 문서에 대해 이 프로세스를 자동화할 수 있나요?
전적으로! 배치 작업을 효율적으로 처리하기 위해 Aspose.Words for .NET의 강력한 기능을 활용하여 여러 문서의 프로세스를 자동화하는 스크립트를 만들 수 있습니다.

### 문제가 발생하면 어디서 지원을 받을 수 있나요?
지원이 필요하면 Aspose 지원 포럼을 방문하세요.[여기](https://forum.aspose.com/c/words/8) 커뮤니티와 Aspose 개발자의 도움을 받으세요.