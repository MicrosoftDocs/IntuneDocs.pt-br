---
title: Como configurar certificados com o Intune | Microsoft Docs
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: aprenda a usar o Intune para criar e atribuir certificados que ajudarão a proteger Wi-Fi, VPN e outras conexões."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 05/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 81c7e04d4b4cc7599b63917e5507775b38b65ba7
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---

# <a name="how-to-configure-certificates-in-microsoft-intune"></a>Como configurar certificados no Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Ao conceder aos usuários acesso a recursos corporativos por meio de VPN, Wi-Fi ou perfis de email, você pode autenticar essas conexões usando certificados. Eles eliminam a necessidade para inserir nomes de usuário e senhas para autenticar conexões.

Use o Intune para atribuir esses certificados aos dispositivos gerenciados. O Intune dá suporte à atribuição e gerenciamento desses tipos de certificados:

- Protocolo SCEP
- PKCS#12 (ou PFX)

Cada um desses tipos de certificado tem seus próprios pré-requisitos e requisitos de infraestrutura.

## <a name="general-workflow"></a>Fluxo de trabalho geral

1. Verifique se você tem a infraestrutura de certificado correta em vigor. Você pode usar os [Certificados SCEP](certificates-scep-configure.md) e os [Certificados PKCS](certficates-pfx-configure.md).
2. Instale um certificado raiz ou um certificado de CA (Autoridade de Certificação) intermediário em cada dispositivo para que o dispositivo reconheça a legitimidade da autoridade de certificação. Para fazer isso, crie e atribua um **perfil de certificado confiável**. Quando você atribui esse perfil, os dispositivos que você gerencia com o Intune solicitarão e receberão o certificado raiz. Você precisa criar um perfil separado para cada plataforma. Perfis de certificado confiável estão disponíveis para as seguintes plataformas:
    - iOS 8.0 e posterior
    - macOS 10.9 e posterior
    - Android 4.0 e posterior
    - Android for Work
    - Windows 8.1 e posterior
    - Windows Phone 8.1 e posterior
    - Windows 10 e posterior
3. Crie perfis de certificado para que os dispositivos solicitem um certificado a ser usado para autenticação de VPN, Wi-Fi e acesso por email. Você pode criar e atribuir um perfil de certificado **PKCS** ou **SCEP** para dispositivos em execução nestas plataformas:
    - iOS 8.0 e posterior
    - Android 4.0 e posterior
    - Android for Work
    - Windows 10 (Desktop e Mobile) e posterior

    Somente é possível usar um perfil de certificado SCEP nestas plataformas:

-     macOS 10.9 e posterior
-     Windows Phone 8.1 e posterior

Você deve criar um perfil separado para cada plataforma de dispositivo. Ao criar o perfil, associe-o ao perfil de certificado raiz confiável já criado.

### <a name="further-considerations"></a>Considerações adicionais

- Se não tiver uma Autoridade de Certificação Corporativa, você precisará criar uma.
- Com base em suas plataformas de dispositivo, se decidir usar o perfil de SCEP (Protocolo de Registro de Certificado Simplificado), você também precisará configurar um NDES (Serviço de Registro de Dispositivo de Rede).
- Se você planeja usar perfis SCEP ou PKCS, precisará baixar e configurar o Microsoft Intune Certificate Connector.


## <a name="step-1--configure-your-certificate-infrastructure"></a>Etapa 1 - configurar a infraestrutura de certificado

Consulte um dos tópicos a seguir para ajudar a configurar a infraestrutura para cada tipo de perfil de certificado:

- [Configurar e gerenciar certificados SCEP com o Intune](certificates-scep-configure.md)
- [Configurar e gerenciar certificados PKCS com o Intune](certficates-pfx-configure.md)


## <a name="step-2---export-your-trusted-root-ca-certificate"></a>Etapa 2 - exportar o certificado de AC raiz confiável

Exporte o certificado de AC (Autoridade de Certificação) Raiz Confiável como um arquivo **.cer** da autoridade de certificação emissora ou de qualquer dispositivo que confie em sua autoridade de certificação emissora. Não exporte a chave privada.

Ao configurar um perfil de certificado confiável, você importará esse certificado.

## <a name="step-3-create-trusted-certificate-profiles"></a>Etapa 3: criar perfis de certificado confiável
Você deverá criar um perfil de certificado confiável antes de criar um perfil de certificado SCEP ou PKCS. Você precisa de um perfil de certificado confiável e um perfil SCEP ou PKCS para cada plataforma de dispositivo. O fluxo para a criação de certificados confiáveis é semelhante para cada plataforma de dispositivo.

### <a name="to-create-a-trusted-certificate-profile"></a>Para criar um perfil de certificado confiável

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Outros** > **Intune**.
3. Na folha **Intune**, escolha **Configuração do dispositivo**.
2. Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.
3. Na folha de perfis, escolha **Criar Perfil**.
4. Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil de certificado confiável.
5. Na lista suspensa **Plataforma**, selecione a plataforma de dispositivo para esse certificado confiável. No momento, é possível escolher uma das seguintes plataformas para as configurações de certificado:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 e posterior**
    - **Windows 10 e posterior**
6. Na lista suspensa de **Tipo de perfil**, escolha **Certificado confiável**.
7. Navegue até o certificado salvo na tarefa 1 e clique em **OK**.
8. Somente para dispositivos Windows 8.1 e Windows 10, selecione o **Repositório de Destino** para o certificado confiável de:
    - **Repositório de certificados do computador – Raiz**
    - **Repositório de certificados do computador – Intermediário**
    - **Repositório de certificados do usuário – Intermediário**
8. Após terminar, escolha **OK**, volte para a folha **Criar Perfil** e selecione **Criar**.

O perfil será criado e aparecerá na folha da lista de perfis.

Se você desejar atribuir esse perfil aos grupos, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).


> [!Note]
> Dispositivos Android exibirão um aviso de que terceiros instalaram um certificado confiável.

## <a name="step-4-create-scep-or-pkcs-certificate-profiles"></a>Etapa 4: criar perfis de certificado SCEP ou PKCS

Consulte um dos tópicos a seguir para ajudar a configurar e atribuir cada tipo de perfil de certificado:

- [Configurar e gerenciar certificados SCEP com o Intune](certificates-scep-configure.md)
- [Configurar e gerenciar certificados PKCS com o Intune](certficates-pfx-configure.md)

Depois de criar um perfil de certificado confiável, crie perfis de certificado SCEP ou PKCS para cada plataforma que você deseja usar. Quando você cria um perfil de certificado SCEP, deverá especificar um perfil de certificado confiável para essa mesma plataforma. Isso vincula os dois perfis de certificado, mas você ainda deve atribuir cada perfil separadamente.


## <a name="next-steps"></a>Próximas etapas
Consulte [Como atribuir perfis de dispositivo](device-profile-assign.md) para obter informações gerais sobre como atribuir perfis de dispositivo.
