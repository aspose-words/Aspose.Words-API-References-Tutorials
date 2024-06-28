---
title: Word 문서에 서명
linktitle: Word 문서에 서명
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에 디지털 서명하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-digital-signatures/sign-document/
---
이 튜토리얼에서는 Aspose.Words for .NET에서 문서 서명 기능을 사용하는 단계를 안내합니다. 이 기능을 사용하면 인증서를 사용하여 Word 문서에 디지털 서명을 할 수 있습니다. 아래 단계를 따르십시오.

## 1단계: 인증서 로드

CertificateHolder 클래스를 사용하여 서명 인증서를 로드하는 것부터 시작하세요.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

인증서 및 관련 비밀번호의 올바른 경로를 지정하십시오.

## 2단계: 문서에 서명하기

DigitalSignatureUtil 클래스를 사용하여 문서에 서명합니다.

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
	certHolder);
```

원본 문서와 서명된 문서의 올바른 경로를 지정해야 합니다.

### .NET용 Aspose.Words를 사용하는 서명 문서의 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용하여 문서에 서명하는 전체 소스 코드입니다.

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
		certHolder);

```

다음 단계를 따르면 Aspose.Words for .NET을 사용하여 Word 문서에 쉽게 서명할 수 있습니다.

## 결론

 이 튜토리얼에서는 .NET용 Aspose.Words의 문서 서명 기능을 살펴보았습니다. 서명 인증서를 로드하고`DigitalSignatureUtil.Sign` 방법을 사용하면 Word 문서에 디지털 서명을 할 수 있습니다. 문서 서명은 인증을 제공하고 문서 내용의 무결성을 보장하므로 안전하고 신뢰할 수 있는 문서 관리에 중요한 기능입니다.

### 수화 문서에 대한 FAQ

#### Q: .NET용 Aspose.Words의 문서 서명이란 무엇입니까?

A: Aspose.Words for .NET의 문서 서명은 인증서를 사용하여 Word 문서에 디지털 서명하는 프로세스를 의미합니다. 이 기능은 문서에 디지털 서명을 추가하여 문서 내용의 신뢰성, 무결성 및 부인 방지 기능을 제공합니다.

#### Q: .NET용 Aspose.Words에서 서명 인증서를 어떻게 로드할 수 있나요?

 A: .NET용 Aspose.Words에서 서명 인증서를 로드하려면 다음을 사용할 수 있습니다.`CertificateHolder` 수업. 인스턴스 만들기`CertificateHolder` 인증서 파일의 경로와 관련 비밀번호를 제공합니다. 예는 다음과 같습니다.

```csharp
CertificateHolder certHolder = CertificateHolder.Create("path/to/certificate.pfx", "password");
```

인증서 및 관련 비밀번호에 대한 올바른 경로를 제공하십시오.

#### Q: .NET용 Aspose.Words를 사용하여 Word 문서에 어떻게 서명합니까?

 A: .NET용 Aspose.Words를 사용하여 Word 문서에 서명하려면 다음을 사용할 수 있습니다.`DigitalSignatureUtil` 수업. 를 불러`Sign` 소스 문서의 경로, 서명된 문서(출력)의 경로 및`CertificateHolder` 물체. 예는 다음과 같습니다.

```csharp
DigitalSignatureUtil.Sign("path/to/source/document.docx", "path/to/signed/document.docx", certHolder);
```

소스 문서와 서명된 문서(출력)에 대한 올바른 경로를 제공하는지 확인하십시오.

#### Q: 문서 서명의 목적은 무엇입니까?

답변: 문서 서명은 문서의 신뢰성과 무결성을 보장하는 방법입니다. 문서에 디지털 서명을 하면 원본에 대한 증거를 제공하고, 내용이 변경되지 않았는지 확인하고, 부인 방지를 설정할 수 있습니다. 문서 서명은 일반적으로 법률, 재무 및 민감한 문서에 사용됩니다.

#### Q: .NET용 Aspose.Words에서 문서 서명에 어떤 인증서든 사용할 수 있나요?

A: .NET용 Aspose.Words에서 문서 서명을 위해서는 유효한 X.509 인증서를 사용해야 합니다. 이 인증서는 신뢰할 수 있는 인증 기관(CA)에서 얻거나 자체 서명된 인증서를 테스트 목적으로 사용할 수 있습니다.

#### Q: Aspose.Words for .NET은 문서 서명을 위해 어떤 파일 형식을 지원합니까?

 A: Aspose.Words for .NET은 DOCX 파일 형식의 Word 문서에 대한 문서 서명을 지원합니다. 다음을 사용하여 DOCX 파일에 서명할 수 있습니다.`DigitalSignatureUtil` 수업과 그에 맞는 자격증을 취득하세요.

#### Q: 동일한 인증서를 사용하여 여러 Word 문서에 서명할 수 있습니까?

A: 예, 동일한 인증서를 사용하여 여러 Word 문서에 서명할 수 있습니다. 다음을 사용하여 인증서를 로드한 후`CertificateHolder` 클래스를 호출하면 이를 재사용하여 여러 문서에 서명할 수 있습니다.`DigitalSignatureUtil.Sign` 소스 및 서명된 문서 경로가 다른 방법입니다.

#### Q: 문서 서명이 원본 문서를 수정합니까?

A: Aspose.Words for .NET을 사용한 문서 서명은 원본 문서를 수정하지 않습니다. 대신 원본 문서는 그대로 유지하면서 디지털 서명된 문서 복사본을 만듭니다. 디지털 서명된 사본에는 추가된 디지털 서명이 포함되어 문서 내용의 무결성을 보장합니다.

#### Q: Aspose.Words for .NET을 사용하여 서명된 문서의 디지털 서명을 확인할 수 있습니까?

 A: 예, Aspose.Words for .NET은 서명된 문서의 디지털 서명을 확인하는 기능을 제공합니다. 당신은 사용할 수 있습니다`DigitalSignatureUtil.Verify` 디지털 서명의 유효성과 진위 여부를 확인하는 방법.