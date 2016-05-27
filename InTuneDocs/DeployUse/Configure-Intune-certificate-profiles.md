---
# required metadata

title: Configurar perfis de certificado | Microsoft Intune
description:
keywords:
author: nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 679a20a1-e66f-4b6b-bd8f-896daf1f8175

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Configurar perfis de certificado do Intune
Depois de configurar a infraestrutura e os certificados conforme descrito em [Configure certificate infrastructure](configure-certificate-infrastructure.md) (Configurar infraestrutura de certificado), você pode configurar perfis de certificado:

**Tarefa 1**: Exportar o Certificado de AC raiz confiável
**Tarefa 2**: Criar perfis de Certificado de Autoridade de Certificação confiável
**Tarefa 3**: uma das seguintes tarefas:

Criar perfis de certificado SCEP

Criar perfis de certificado .PFX

### Tarefa 1: Exportar o certificado de raiz confiável
Exporte o certificado de AC raiz confiável como um arquivo **.cer** da CA emissora ou de qualquer dispositivo que confie em sua AC emissora. Você não exportar a chave privada.

Quando configurar um perfil de certificado confiável, você importará esse certificado.

### Tarefa 2: Criar perfis de certificado confiável
Você deve criar um **Perfil de certificado confiável** antes de ser possível criar um perfil de certificado SCEP ou .PFX. Você precisa de um perfil de certificado confiável e um perfil SCEP ou .PFS para cada plataforma de dispositivo móvel.

##### Para criar um perfil de certificado confiável

1.  Abra o [Console de administração do Intune](https://manage.microsoft.com) e clique em **Política** &gt; **Adicionar Política**.

2.  Configure um dos seguintes tipos de política:

    **Android &gt; Perfil de certificado confiável (Android 4 e posterior)**

    **iOS &gt; Perfil de certificado confiável (iOS 7.1 e posterior)**

    **Mac OS X &gt; Perfil de certificado confiável (Mac OS X 10.9 e posterior)**

    **Windows &gt; Perfil de certificado confiável (Windows 8.1 e posterior)**

    **Windows &gt; Perfil de certificado confiável (Windows Phone 8.1 e posterior)**

    Saiba mais: [Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) (Gerenciar configurações e funcionalidades em seus dispositivos com políticas do Microsoft Intune).

3.  Forneça as informações solicitadas para definir as configurações de perfil de certificado confiável para Android, iOS, Mac OS X, Windows 8.1 ou Windows Phone 8.1. Na configuração **Arquivo de certificado**, importe o Certificado de AC raiz confiável (**.cer**) que você exportou da AC emissora. A configuração **Repositório de destino** se aplica apenas aos dispositivos que executam o Windows 8.1 e posterior e apenas se o dispositivo tiver mais de um repositório de certificados.


4.  Quando tiver terminado, clique em **Salvar Política**.

A nova política é exibida no espaço de trabalho **Política** e pode ser implantada.

### Tarefa 3 – Criar perfis de certificado SCEP ou .PFX
Depois de criar um perfil de certificado de Autoridade de Certificação confiável, crie perfis de certificado SCEP ou .PFX para cada plataforma que você deseja usar. Quando você cria um perfil de certificado SCEP, deve especificar um perfil de certificado confiável para essa mesma plataforma. Isso vincula os dois perfis de certificado, embora ainda seja necessário implantar cada perfil separadamente.

##### Para criar um perfil de certificado SCEP

1.  Abra o [Console de administração do Intune](https://manage.microsoft.com), clique em **Política** &gt; **Adicionar política**.

2.  Configure um dos seguintes tipos de política:

    **Android &gt; Perfil de certificado SCEP (Android 4 e posterior)**

    **iOS &gt; Perfil de certificado SCEP (iOS 7.1 e posterior)**

    **Mac OS X &gt; Perfil de certificado SCEP (Mac OS X 10.9 e posterior)**

    **Windows &gt; Perfil de certificado SCEP (Windows 8.1 e posterior)**

    **Windows &gt; Perfil de certificado SCEP (Windows Phone 8.1 e posterior)**

    Saiba mais: [Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) (Gerenciar configurações e funcionalidades em seus dispositivos com políticas do Microsoft Intune).

3.  Siga as instruções na página de configuração do perfil para definir as configurações de perfil de certificado SCEP.

4.  Quando tiver terminado, clique em **Salvar Política**.

A nova política é exibida no espaço de trabalho **Política** e pode ser implantada.

##### Para criar um perfil de certificado .PFX

1.  Abra o [Console de administração do Intune](https://manage.microsoft.com), clique em **Política** &gt; **Adicionar política**.

2.  Configure um dos seguintes tipos de política:



-   **Android &gt; Perfil de certificado .PFX (Android 4 e posterior)**

    -   **Windows &gt; Perfil de Certificado PKCS nº 12 (.PFX) (Windows 10 e posterior)**

    -   **Windows &gt; Perfil de Certificado PKCS nº 12 (.PFX) (Windows Phone 10 e posterior)**

    -    **iOS > Perfil de Certificado PKCS nº 12 (.PFX) (iOS 7.1 e posterior)**    

    Saiba mais: [Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) (Gerenciar configurações e funcionalidades em seus dispositivos com políticas do Microsoft Intune).

3.  Forneça a informação solicitada no formulário de política.

4.  Quando tiver terminado, clique em **Salvar Política**.

A nova política é exibida no espaço de trabalho **Política** e pode ser implantada.

## Implantar perfis de certificado
Quando você implanta perfis de certificado, o arquivo de certificado do perfil de certificado de Autoridade de Certificação confiável é instalado em dispositivos e o perfil de certificado SCEP ou .PFX é usado pelo dispositivo para criar uma solicitação de certificado pelo dispositivo.

Perfis de certificado são instalados somente em dispositivos aplicáveis de acordo com a plataforma que você usa ao criar o perfil.

-   Você pode implantar perfis de certificado para coleções de usuários ou coleções de dispositivos.

    > [!TIP]
    > Para permitir que certificados sejam publicados em dispositivos rapidamente depois que o dispositivo for registrado, implante o perfil de certificado em um grupo de usuários (não um grupo de dispositivos). Se você o implantar em um grupo de dispositivos, um registro de dispositivo completo deve ocorrer antes do dispositivo receber a política.

-   Embora cada perfil seja implantado separadamente, o perfil de raiz confiável e o perfil do protocolo SCEP/.PFX devem ser implantados ou a política de certificação SCEP/.PFX falhará.

Você implanta os perfis de certificado da mesma maneira que implanta outra política para o Intune:

1.  No espaço de trabalho **Política**, selecione a política que deseja implantar e clique em **Gerenciar Implantação**.

2.  Na caixa de diálogo **Gerenciar implantação** :

    -   **Para implantar a política** - Selecione um ou mais grupos nos quais deseja implantar a política e clique em **Adicionar** &gt; **OK**.

    -   **Para fechar a caixa de diálogo sem implantá-la** - Clique em **Cancelar**.

Quando você seleciona uma política implantada, pode exibir mais informações sobre a implantação na parte inferior da lista de políticas.
###  Próximas etapas

Agora você pode usar certificados para ajudar a proteger perfis VPN, Wi-Fi e email:

-  [Configurar o acesso a email corporativo usando perfis de email](configure-access-to-corporate-email-using-email-profiles-with-Microsoft-Intune.md)
-  [Conexões Wi-Fi no Microsoft Intune](wi-fi-connections-in-microsoft-intune.md)
-  [Conexões VPN no Microsoft Intune](vpn-connections-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->

