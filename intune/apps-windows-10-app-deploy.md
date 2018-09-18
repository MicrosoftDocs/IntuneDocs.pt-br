---
title: Implantação de aplicativo do Windows 10 usando o Microsoft Intune
titlesuffix: ''
description: Saiba mais sobre os cenários de aplicativo do Windows 10 disponíveis no Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/31/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: abebfb5e-054b-435a-903d-d1c31767bcf2
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7508f2c2eca06ceacf203103ab2cad53abc39a65
ms.sourcegitcommit: 2d1e89fa5fa721e79648e41fde147a035e7b047d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/31/2018
ms.locfileid: "43347425"
---
# <a name="windows-10-app-deployment-using-microsoft-intune"></a>Implantação de aplicativo do Windows 10 usando o Microsoft Intune 

Atualmente, o Microsoft Intune dá suporte a uma variedade de tipos de aplicativos e cenários de implantação em dispositivos Windows 10. Depois de adicionar um aplicativo ao Intune, você pode atribuí-lo a usuários e dispositivos. As informações a seguir fornecem mais detalhes relacionados aos cenários do Windows 10 compatíveis. Além disso, as informações a seguir fornecem detalhes importantes a serem observados ao implantar aplicativos no Windows. 

Os aplicativos LOB (linha de negócios) e os aplicativos da Microsoft Store para Empresas são os tipos de aplicativo compatíveis com dispositivos Windows 10.

> [!Note]
> A atualização mínima necessária do Windows 10 para implantação de aplicativos no contexto de dispositivo é a de [23 de maio de 2018 – KB4100403 (Build do sistema operacional 17134.81)](https://support.microsoft.com/en-us/help/4100403/windows-10-update-kb4100403).

## <a name="windows-10-line-of-business-apps"></a>Aplicativos de linha de negócios do Windows 10

Os aplicativos LOB do Windows 10 são autenticados e carregados no console de administração do Intune e podem incluir aplicativos modernos, como aplicativos UWP (da Plataforma Universal do Windows) e Pacotes do Aplicativo do Windows (AppX), além de aplicativos do Win32, como arquivos de pacote simples do Microsoft Installer (MSI). As atualizações de aplicativos LOB precisam ser carregadas e implantadas manualmente todas as vezes pelo administrador. As atualizações implantadas são instaladas automaticamente em dispositivos do usuário final que instalaram o aplicativo sem nenhuma intervenção do usuário. O usuário não tem controle sobre as atualizações. 

## <a name="microsoft-store-for-business-apps"></a>Aplicativos da Microsoft Store para Empresas

Aplicativos da Microsoft Store para Empresas que são aplicativos modernos adquiridos no portal de administração da Microsoft Store para Empresas e, em seguida, sincronizados com o Microsoft Intune para gerenciamento. Os aplicativos podem ser **licenciados online** ou **licenciados offline**. As atualizações dos aplicativos da Microsoft Store para Empresas são gerenciadas diretamente pela Microsoft Store, sem nenhuma ação adicional exigida pelo administrador. O administrador também pode impedir atualizações em aplicativos específicos usando o URI (Uniform Resource Identifier) personalizado. Para obter mais informações, confira [Gerenciamento de aplicativos empresariais – Impedir atualizações automáticas do aplicativo](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management#prevent-app-from-automatic-updates). No dispositivo, o usuário final também pode desabilitar atualizações de todos os aplicativos da Microsoft Store para Empresas no dispositivo. 

## <a name="installing-apps-on-windows-10-devices"></a>Instalando aplicativos em dispositivos Windows 10
Dependendo do tipo de aplicativo, o aplicativo pode ser instalado em um dispositivo Windows 10 de uma destas duas maneiras:

- **Contexto de Usuário**: quando um aplicativo for implantado no contexto de usuário, o aplicativo gerenciado será instalado para esse usuário no dispositivo quando o usuário entrar no dispositivo. Observe que a instalação do aplicativo não funcionará enquanto o usuário não entrar no dispositivo. 
    - Os aplicativos de linha de negócios modernos e os aplicativos da Microsoft Store para Empresas (online e offline) podem ser implantados no contexto de usuário e darão suporte à intenção Obrigatória e Disponível.
- **Contexto de Dispositivo**: quando um aplicativo for implantado no contexto de dispositivo, o aplicativo gerenciado será instalado diretamente no dispositivo pelo Intune.
    - Somente os aplicativos de linha de negócios modernos e os aplicativos licenciados Online da Microsoft Store para Empresas podem ser implantados no contexto de dispositivo e darão suporte apenas à intenção Obrigatório.

> [!Note]
> Ainda não há suporte para a implantação do MSI no MDM no contexto de dispositivo em dispositivos Windows 10.

Quando um aplicativo é implantado no contexto de dispositivo, a instalação terá êxito apenas quando for direcionada a um dispositivo que dê suporte ao contexto de dispositivo. Além disso, a implantação no contexto de dispositivo dá suporte às seguintes condições:
- Se um aplicativo for implantado no contexto de dispositivo e direcionado a um usuário, a instalação falhará com o seguinte status e o erro será exibido no console de administração:
    - Status: com falha.
    - Erro: um usuário não pode ser direcionado com uma instalação de contexto de Dispositivo.
- Se um aplicativo for implantado no contexto de dispositivo, mas direcionado a um dispositivo que não dê suporte ao contexto de dispositivo, a instalação falhará com o seguinte status e erro no console de administração:
    - Status: com falha.
    - Erro: essa plataforma não dá suporte a instalações de contexto de dispositivo. 

> [!Note]
> Depois que uma atribuição de aplicativo é salva com uma implantação específica, o contexto não pode ser alterado quanto à essa atribuição, exceto em aplicativos modernos. No caso de aplicativos modernos, o contexto pode ser alterado do contexto de usuário para o contexto de dispositivo. 

Se houver um conflito nas políticas em um único usuário/dispositivo, estas serão as prioridades de política que serão usadas para determinar a política final:
- Uma política de contexto de dispositivo tem uma prioridade mais alta do que uma política de contexto de usuário. 
- Uma política de instalação tem uma prioridade mais alta do que uma política de desinstalação.

Para obter mais informações sobre como atribuir aplicativos usando o Microsoft Intune, confira [Atribuir aplicativos a grupos com o Microsoft Intune](apps-deploy.md) e [Incluir e excluir atribuições de aplicativo no Microsoft Intune](apps-inc-exl-assignments.md). Para obter mais informações sobre os tipos de aplicativo no Intune, confira [Adicionar aplicativos ao Microsoft Intune](apps-add.md).

## <a name="next-steps"></a>Próximas etapas

- Para saber mais sobre como atribuir aplicativos a grupos, confira [Atribuir aplicativos a grupos com o Microsoft Intune](apps-deploy.md).
- Para saber mais sobre como monitorar as atribuições de aplicativo, consulte [Como monitorar aplicativos](apps-monitor.md).