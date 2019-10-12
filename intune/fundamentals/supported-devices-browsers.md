---
title: Sistemas operacionais e navegadores com suporte no Microsoft Intune
titleSuffix: ''
description: Lista as plataformas de dispositivo e navegadores com suporte para o gerenciamento de dispositivo do Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/29/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5d1ac59c-a885-4276-8576-f3cf81c2d268
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: c87cb90ee7803b0848c57b91a801976b2aa4d6e9
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71721702"
---
# <a name="supported-operating-systems-and-browsers-in-intune"></a>Navegadores e sistemas operacionais compatíveis no Intune

Antes de configurar o Microsoft Intune, examine os sistemas operacionais e navegadores compatíveis.

Para obter ajuda para instalar o Intune em seu dispositivo, confira [Usando dispositivos gerenciados para realizar o trabalho]https://docs.microsoft.com/intune-user-help/company-portal-frequently-asked-questions) e [Uso de largura de banda de rede do Intune](network-bandwidth-use.md).

Para saber mais sobre o suporte à configuração do provedor de serviço, visite a [Referência do provedor do serviço de configuração](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference).

## <a name="intune-supported-operating-systems"></a>Sistemas operacionais compatíveis com o Intune

É possível gerenciar dispositivos que executam os seguintes sistemas operacionais:

[!INCLUDE [mdm-supported-devices](../../intune-classic/includes/mdm-supported-devices.md)]

### <a name="supported-samsung-knox-standard-devices"></a>Dispositivos Samsung Knox Standard com suporte

Para evitar erros de ativação do KNOX que impedem o registro do MDM, o aplicativo Portal da Empresa apenas tenta a ativação do Samsung KNOX durante o registro de MDM quando o dispositivo aparece na [lista de dispositivos KNOX com suporte](https://www.samsungknox.com/knox-supported-devices/knox-workspace). Dispositivos que não dão suporte à ativação de Samsung Knox são registrados como dispositivos Android padrão. Um dispositivo Samsung pode ter alguns números de modelo que oferecem suporte a Knox, enquanto outros não. Verifique a compatibilidade com KNOX com o revendedor do dispositivo antes de comprar e implantar dispositivos Samsung.

> [!NOTE]
> O registro de dispositivos Samsung Knox pode exigir a [habilitação de acesso a servidores da Samsung](https://support.samsungknox.com/hc/articles/115013833108-Our-corporate-devices-are-behind-a-firewall-How-do-I-enable-Knox-Workspace-devices-to-contact-Samsung-servers). 

Os modelos de dispositivo Samsung na lista a seguir não dão suporte ao KNOX. Eles são registrados como dispositivos Android nativos pelo aplicativo Portal da Empresa para Android:

| **Nome do Dispositivo** | **Números de Modelos de Dispositivo** |
| --- | --- |
| Galaxy Avant | SM-G386T |
| Galaxy Core 2/Core 2 Duos | SM-G355H<br>SM-G355M |
| Galaxy Core Lite | SM-G3588V |
| Galaxy Core Prime | SM-G360H |
| Galaxy Core LTE | SM-G386F<br>SM-G386W |
| Galaxy Grand | GT-I9082L<br>GT-I9082<br>GT-I9080L |
| Galaxy Grand 3 | SM-G7200 |
| Galaxy Grand Neo | GT-I9060I |
| Galaxy Grand Prime Value Edition | SM-G531H |
| Galaxy J Max | SM-T285YD |
| Galaxy J1 | SM-J100H<br>SM-J100M<br>SM-J100ML |
| Galaxy J1 Ace | SM-J110F<br>SM-J110H |
| Galaxy J1 Mini | SM-J105M |
| Galaxy J2/J2 Pro | SM-J200H<br>SM-J210F |
| Galaxy J3 | SM-J320F<br>SM-J320FN<br>SM-J320H<br>SM-J320M |
| Galaxy K Zoom | SM-C115 |
| Galaxy Light | SGH-T399N |
| Galaxy Note 3 | SM-N9002<br>SM-N9009 |
| Galaxy Note 7/Note 7 Duos | SM-N930S<br>SM-N9300<br>SM-N930F<br>SM-N930T<br>SM-N9300<br>SM-N930F<br>SM-N930S<br>SM-N930T |
| Galaxy Note 10.1 3G | SM-P602 |
| Galaxy S2 Plus | GT-I9105P |
| Galaxy S3 Mini | SM-G730A<br>SM-G730V |
| Galaxy S3 Neo | GT-I9300<br>GT-I9300I |
| Galaxy S4 | SM-S975L |
| Galaxy S4 Neo | SM-G318ML |
| Galaxy S5 | SM-G9006W |
| Galaxy S6 Edge | 404SC |
| Galaxy Tab A 7.0&quot; | SM-T280<br>SM-T285 |
| Galaxy Tab 3 7&quot;/Tab 3 Lite 7&quot; | SM-T116<br>SM-T210<br>SM-T211 |
| Galaxy Tab 3 8.0&quot; | SM-T311 |
| Galaxy Tab 3 10.1&quot; | GT-P5200<br>GT-P5210<br>GT-P5220 |
| Galaxy Trend 2 Lite | SM-G318H |
| Galaxy V Plus | SM-G318HZ |
| Galaxy Young 2 Duos | SM-G130BU |


### <a name="windows-pc-software-client"></a>Cliente de software de computadores Windows

Um [cliente de software do Intune](../manage-windows-pcs-with-microsoft-intune.md) pode ser implantado e instalado em computadores Windows como um método alternativo de registro. Essa funcionalidade só está disponível no Portal Clássico do Intune. É possível usar o cliente de software do Intune para gerenciar computadores Windows 7 e posterior, com exceção do Windows 10 Home Edition.

<!--  ### Exchange ActiveSync management

You can manage [Exchange ActiveSync devices](../enrollment/device-enrollment.md#mobile-device-management-with-exchange-activesync-and-intune) from the Intune console. This option provides a limited set of management capabilities when compared to the other methods. See [Capabilities of built-in Mobile Device Management in Office 365](https://support.office.com/article/Capabilities-of-built-in-Mobile-Device-Management-for-Office-365-a1da44e5-7475-4992-be91-9ccec25905b0) for a list of supported devices.  -->

## <a name="intune-supported-web-browsers"></a>Navegadores da web com suporte para o Intune

Diferentes tarefas administrativas exigem o uso de um dos seguintes sites administrativos.

- [Centro de administração do Microsoft 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Portal do Azure](https://portal.azure.com/)

Há suporte para os seguintes navegadores nesses portais:
- Microsoft Edge (última versão)
- Microsoft Internet Explorer 11
- Safari (última versão, somente Mac)
- Chrome (última versão)
- Firefox (última versão)




### <a name="intune-classic-portal"></a>Portal clássico do Intune

O portal clássico do Intune é usado somente para gerenciar dispositivos registrados com o cliente de software de computador do Intune (https://manage.microsoft.com). O portal clássico do Intune requer suporte do navegador Silverlight.

Os seguintes navegadores Silverlight dão suporte ao Portal Clássico do Intune:
- Internet Explorer 10 ou posterior
- Google Chrome (versões anteriores à versão 42)
- Mozilla Firefox com o Silverlight habilitado (versões anteriores à versão 56)

> [!Note]
> Não há suporte para o Microsoft Edge nem para navegadores móveis no Portal Clássico do Intune, pois eles não dão suporte ao [Microsoft Silverlight](https://msdn.microsoft.com/library/cc838158(v=vs.95).aspx).

Apenas usuários com permissões de administrador de serviços ou administradores de locatários com a função de administrador global podem entrar nesse portal. Para acessar o console de administração, sua conta deve ter uma licença para usar o Intune e um status de entrada de **Permitido**.