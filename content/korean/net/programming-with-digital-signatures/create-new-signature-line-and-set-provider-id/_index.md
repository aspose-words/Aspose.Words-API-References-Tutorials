---
title: 새 서명란 생성 및 공급자 ID 설정
linktitle: 새 서명란 생성 및 공급자 ID 설정
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 새 서명란을 만들고 공급자 ID를 설정하는 방법을 알아보세요. 단계별 가이드.
type: docs
weight: 10
url: /ko/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---
## 소개

안녕하세요, 기술 매니아 여러분! 프로그래밍 방식으로 Word 문서에 서명란을 추가하는 방법이 궁금하신가요? 자, 오늘 우리는 .NET용 Aspose.Words를 사용하여 이에 대해 자세히 알아볼 것입니다. 이 가이드는 모든 단계를 안내하여 파이처럼 쉽게 새 서명란을 만들고 Word 문서에 공급자 ID를 설정할 수 있도록 해줍니다. 문서 처리를 자동화하려는 경우든 아니면 단순히 작업 흐름을 간소화하려는 경우든 이 튜토리얼에서 모든 내용을 다룰 수 있습니다.

## 전제 조건

손을 더럽히기 전에 필요한 모든 것이 있는지 확인합시다.

1.  .NET용 Aspose.Words: 아직 다운로드하지 않았다면 다운로드하세요.[여기](https://releases.aspose.com/words/net/).
2. 개발 환경: Visual Studio 또는 기타 C# 개발 환경.
3. .NET Framework: .NET Framework가 설치되어 있는지 확인하세요.
4. PFX 인증서: 문서에 서명하려면 PFX 인증서가 필요합니다. 신뢰할 수 있는 인증 기관에서 발급받을 수 있습니다.

## 네임스페이스 가져오기

먼저 C# 프로젝트에 필요한 네임스페이스를 가져오겠습니다.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Signing;
using System;
```

좋아, 핵심으로 들어가 보자. 다음은 새 서명란을 생성하고 공급자 ID를 설정하는 각 단계에 대한 자세한 분석입니다.

## 1단계: 새 문서 만들기

시작하려면 새 Word 문서를 만들어야 합니다. 이것이 우리의 시그니처 라인을 위한 캔버스가 될 것입니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 이 스니펫에서는 새로운`Document` 그리고`DocumentBuilder` . 그만큼`DocumentBuilder` 문서에 요소를 추가하는 데 도움이 됩니다.

## 2단계: 서명란 옵션 정의

다음으로 서명란에 대한 옵션을 정의합니다. 여기에는 서명자의 이름, 직함, 이메일 및 기타 세부 정보가 포함됩니다.

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
    Signer = "vderyushev",
    SignerTitle = "QA",
    Email = "vderyushev@aspose.com",
    ShowDate = true,
    DefaultInstructions = false,
    Instructions = "Please sign here.",
    AllowComments = true
};
```

이러한 옵션은 서명란을 개인화하여 명확하고 전문적으로 만듭니다.

## 3단계: 서명란 삽입

옵션을 설정하면 이제 문서에 서명란을 삽입할 수 있습니다.

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

 여기서는`InsertSignatureLine` 메서드는 서명란을 추가하고 여기에 고유한 공급자 ID를 할당합니다.

## 4단계: 문서 저장

서명란을 삽입한 후 문서를 저장해 봅시다.

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

그러면 새로 추가된 서명란과 함께 문서가 저장됩니다.

## 5단계: 서명 옵션 설정

이제 문서 서명 옵션을 설정해야 합니다. 여기에는 서명란 ID, 공급자 ID, 설명 및 서명 시간이 포함됩니다.

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    ProviderId = signatureLine.ProviderId,
    Comments = "Document was signed by vderyushev",
    SignTime = DateTime.Now
};
```

이러한 옵션을 사용하면 문서가 올바른 세부 정보로 서명되었는지 확인할 수 있습니다.

## 6단계: 인증서 보유자 생성

문서에 서명하기 위해 PFX 인증서를 사용합니다. 이에 대한 인증서 보유자를 만들어 보겠습니다.

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

 꼭 교체하세요`"morzal.pfx"` 실제 인증서 파일과`"aw"` 인증서 비밀번호로.

## 7단계: 문서에 서명

마지막으로 디지털 서명 유틸리티를 사용하여 문서에 서명합니다.

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
    dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);
```

문서에 서명하고 새 파일로 저장합니다.

## 결론

그리고 거기에 있습니다! .NET용 Aspose.Words를 사용하여 Word 문서에 새 서명란을 만들고 공급자 ID를 설정하는 데 성공했습니다. 이 강력한 라이브러리를 사용하면 문서 처리 작업을 매우 쉽게 관리하고 자동화할 수 있습니다. 한번 시도해보고 작업 흐름을 어떻게 간소화할 수 있는지 알아보세요.

## FAQ

### 서명란의 모양을 맞춤 설정할 수 있나요?
전적으로! 다양한 옵션을 조정할 수 있습니다.`SignatureLineOptions` 귀하의 필요에 맞게.

### PFX 인증서가 없으면 어떻게 되나요?
신뢰할 수 있는 인증 기관으로부터 인증서를 받아야 합니다. 이는 문서에 디지털 서명을 하는 데 필수적입니다.

### 문서에 여러 개의 서명란을 추가할 수 있나요?
예, 다양한 옵션을 사용하여 삽입 프로세스를 반복하여 필요한 만큼 서명란을 추가할 수 있습니다.

### .NET용 Aspose.Words는 .NET Core와 호환됩니까?
예, .NET용 Aspose.Words는 .NET Core를 지원하므로 다양한 개발 환경에 다용도로 사용할 수 있습니다.

### 디지털 서명은 얼마나 안전합니까?
Aspose.Words로 생성된 디지털 서명은 유효하고 신뢰할 수 있는 인증서를 사용하는 경우 매우 안전합니다.