---
title: Word 문서에서 서명 공급자 ID 설정
linktitle: Word 문서에서 서명 공급자 ID 설정
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 서명 공급자 ID를 안전하게 설정하세요. 문서에 디지털 서명을 하려면 자세한 2000 단어 가이드를 따르세요.
type: docs
weight: 10
url: /ko/net/programming-with-digital-signatures/set-signature-provider-id/
---
## 소개

안녕하세요! 이제 디지털 서명이 필요한 놀라운 Word 문서가 생겼습니다. 그렇죠? 그러나 단순한 서명이 아니라 특정 서명 제공자 ID를 설정해야 합니다. 법률 문서, 계약서 또는 기타 서류 작업을 처리할 때 안전한 디지털 서명을 추가하는 것이 중요합니다. 이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 Word 문서에서 서명 공급자 ID를 설정하는 전체 과정을 안내하겠습니다. 준비가 된? 뛰어들어보자!

## 전제 조건

시작하기 전에 다음 사항이 있는지 확인하세요.

1. .NET 라이브러리용 Aspose.Words: 아직 작성하지 않으셨다면,[여기에서 다운로드하십시오](https://releases.aspose.com/words/net/).
2. 개발 환경: Visual Studio 또는 C# 호환 IDE.
3. Word 문서: 서명란(`Signature line.docx`).
4.  디지털 인증서: A`.pfx` 인증서 파일(예:`morzal.pfx`).
5. C#에 대한 기본 지식: 기본 사항만 알려드립니다. 걱정하지 마세요. 저희가 도와드리겠습니다!

이제 액션에 뛰어들어 봅시다!

## 네임스페이스 가져오기

먼저, 프로젝트에 필요한 네임스페이스를 포함했는지 확인하세요. 이는 Aspose.Words 라이브러리 및 관련 클래스에 액세스하는 데 필수적입니다.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.DigitalSignatures;
```

좋습니다. 간단하고 이해하기 쉬운 단계로 나누어 보겠습니다.

## 1단계: Word 문서 로드

첫 번째 단계는 서명란이 포함된 Word 문서를 로드하는 것입니다. 이 문서는 지정된 서명 공급자 ID와 함께 디지털 서명을 포함하도록 수정됩니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");
```

 여기서는 문서가 있는 디렉터리를 지정합니다. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서의 실제 경로와 함께.

## 2단계: 서명란에 액세스

다음으로 문서 내의 서명란에 액세스해야 합니다. 서명란은 Word 문서에 도형 개체로 포함됩니다.

```csharp
SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

 이 코드 줄은 문서의 첫 번째 섹션 본문에서 첫 번째 모양을 가져와서`SignatureLine` 물체.

## 3단계: 서명 옵션 설정

이제 액세스한 서명란의 공급자 ID와 서명란 ID를 포함하는 서명 옵션을 만듭니다.

```csharp
SignOptions signOptions = new SignOptions
{
    ProviderId = signatureLine.ProviderId,
    SignatureLineId = signatureLine.Id
};
```

이러한 옵션은 문서에 서명할 때 올바른 서명 공급자 ID가 설정되었는지 확인하는 데 사용됩니다.

## 4단계: 인증서 로드

 문서에 디지털 서명을 하려면 인증서가 필요합니다. 로드하는 방법은 다음과 같습니다.`.pfx` 파일:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

 바꾸다`"aw"` 인증서 파일이 있는 경우 해당 파일의 비밀번호를 사용하세요.

## 5단계: 문서에 서명

 마지막으로, 다음을 사용하여 문서에 서명할 시간입니다.`DigitalSignatureUtil.Sign` 방법.

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
    dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);
```

 그러면 문서에 서명하고 새 파일로 저장됩니다.`Digitally signed.docx`.

## 결론

그리고 거기에 있습니다! .NET용 Aspose.Words를 사용하여 Word 문서에서 서명 공급자 ID를 성공적으로 설정했습니다. 이 프로세스는 문서를 보호할 뿐만 아니라 문서가 디지털 서명 표준을 준수하는지 확인합니다. 이제 문서에 직접 사용해 보세요. 질문이 있으신가요? 아래 FAQ를 확인하거나[Aspose 지원 포럼](https://forum.aspose.com/c/words/8).

## FAQ

### 서명 제공자 ID란 무엇입니까?

서명 제공자 ID는 디지털 서명 제공자를 고유하게 식별하여 신뢰성과 보안을 보장합니다.

### 서명에 .pfx 파일을 사용할 수 있나요?

예, 유효한 디지털 인증서라면 가능합니다. 보호되어 있는 경우 올바른 비밀번호를 가지고 있는지 확인하세요.

### .pfx 파일을 얻으려면 어떻게 해야 합니까?

CA(인증 기관)에서 .pfx 파일을 얻거나 OpenSSL과 같은 도구를 사용하여 파일을 생성할 수 있습니다.

### 한 번에 여러 문서에 서명할 수 있나요?

예, 여러 문서를 반복하여 각 문서에 동일한 서명 프로세스를 적용할 수 있습니다.

### 문서에 서명란이 없으면 어떻게 하나요?

먼저 서명란을 삽입해야 합니다. Aspose.Words는 프로그래밍 방식으로 서명란을 추가하는 방법을 제공합니다.
