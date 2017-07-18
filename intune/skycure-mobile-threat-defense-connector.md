---
title: Conector do Skycure com o Intune
titleSuffix: Intune on Azure
description: "Integração do conector do Skycure com o Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: df4ce3f6-a093-432c-ab86-7a83865e389e
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c55fa5b3ea86127648850ae7374107ca65db9764
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# Conector de Defesa contra Ameaças Móveis do Skycure
<a id="skycure-mobile-threat-defense-connector" class="xliff"></a>

É possível controlar o acesso de dispositivos móveis a recursos corporativos usando o acesso condicional com base na avaliação de risco realizada pelo Skycure, uma solução de defesa contra ameaças móveis integrada ao Microsoft Intune. O risco é avaliado com base na telemetria coletada dos dispositivos com o Skycure em execução, incluindo:

-   Defesa física

-   Defesa de rede

-   Defesa do aplicativo

-   Defesa de vulnerabilidades

Você pode configurar políticas de acesso condicional com base na avaliação de risco do Skycure habilitada por meio de políticas de conformidade do dispositivo do Intune, que podem ser usadas para permitir ou bloquear o acesso de dispositivos incompatíveis a recursos corporativos com base em ameaças detectadas.

## Como o Intune e o Skycure ajudam a proteger os recursos da empresa?
<a id="how-do-intune-and-skycure-help-protect-your-company-resources" class="xliff"></a>

O aplicativo móvel do Skycure para Android e iOS captura o sistema de arquivos, a pilha de rede e a telemetria do dispositivo e dos aplicativos, quando disponível, e envia-os ao serviço de nuvem do Skycure para avaliar o risco do dispositivo a ameaças móveis.

A política de conformidade do dispositivo do Intune inclui uma regra para a Defesa contra Ameaças Móveis do Skycure, que se baseia na avaliação de risco do Skycure. Quando essa regra é habilitada, o Intune avalia a conformidade do dispositivo com a política habilitada.

Se o dispositivo for considerado fora de conformidade, o acesso a recursos como o Exchange Online e o SharePoint Online serão bloqueados. Os usuários com dispositivos bloqueados recebem orientação do aplicativo móvel do Skycure para resolver o problema e recuperar o acesso aos recursos corporativos.

O Intune dá suporte a dois modos de integração com o Skycure:

-   **Configuração básica**, que é um modo somente leitura que permite a visibilidade do Skycure para dispositivos no Intune.

-   **Integração total**, que permite ao Skycure relatar detalhes dos incidentes de risco e segurança do dispositivo no Intune.

## Cenários de exemplo
<a id="sample-scenarios" class="xliff"></a>

Confira alguns cenários comuns:

### Controlar o acesso com base em ameaças de aplicativos mal-intencionados
<a id="control-access-based-on-threats-from-malicious-apps" class="xliff"></a>

Quando aplicativos mal-intencionados, como malwares, são detectados nos dispositivos, é possível bloquear os dispositivos até que a ameaça seja resolvida:

-   Conectar-se ao email corporativo

-   Sincronizar arquivos corporativos com o aplicativo OneDrive for Work

-   Acessar aplicativos da empresa

**Bloquear quando aplicativos mal-intencionados forem detectados:**

![Aplicativos mal-intencionados detectados](./media/skycure-arch-1.png)

**Acesso concedido após a correção:**

![Acesso concedido a aplicativos mal-intencionados detectado](./media/skycure-arch-2.png)

### Controlar o acesso com base em ameaças à rede
<a id="control-access-based-on-threat-to-network" class="xliff"></a>

Detecta ameaças como **Man-in-the-middle** na rede e protege o acesso a redes Wi-Fi com base no risco do dispositivo.

**Bloquear o acesso à rede por meio de Wi-Fi:**

![Bloquear o acesso à rede por meio de Wi-Fi](./media/skycure-arch-3.png)

**Acesso concedido após a correção:**

![Acesso concedido após a correção](./media/skycure-arch-4.png)

### Controlar o acesso ao SharePoint Online com base em ameaças à rede
<a id="control-access-to-sharepoint-online-based-on-threat-to-network" class="xliff"></a>

Detectar ameaças como **Man-in-the-middle** na rede e impede a sincronização de arquivos corporativos com base no risco ao dispositivo.

**Bloquear o SharePoint Online quando ameaças à rede forem detectadas:**

![Bloquear o SharePoint Online quando ameaças à rede forem detectadas](./media/skycure-arch-5.png)

**Acesso concedido após a correção:**

![Acesso concedido após correção para exemplo do Sharepoint](./media/skycure-arch-6.png)

## Plataformas com suporte
<a id="supported-platforms" class="xliff"></a>

-   **Android 4.1 e posterior**

-   **iOS 8 e posterior**

## Pré-requisitos
<a id="pre-requisites" class="xliff"></a>

-   Azure Active Directory Premium

-   Assinatura do Microsoft Intune

-   Assinatura da Defesa contra Ameaças Móveis do Skycure

Para saber mais, veja o [site do Skycure](https://www.skycure.com/skycure-microsoft-integration/).

## Próximas etapas
<a id="next-steps" class="xliff"></a>

Estas são as etapas que precisam ser concluídas para integrar o Intune ao Skycure:

1.  [Configurar o Skycure para usar o SSO (Logon único) do Azure Active Directory](skycure-azure-sso-configure.md)

2.  [Baixar a política de configuração de aplicativo iOS do Skycure](skycure-ios-app-configuration-policy-download.md)

3.  [Adicionar e atribuir os aplicativos Skycure, o Microsoft Authenticator e a política de configuração do iOS](mtd-apps-ios-app-configuration-policy-add-assign.md)

4.  [Configurar a integração do Skycure com o Intune](skycure-mtd-connector-integration.md)

5.  [Habilitar a Defesa contra Ameaças Móveis do Skycure no Intune](mtd-connector-enable.md)

6.  [Criar a política de conformidade do dispositivo da Defesa contra Ameaças Móveis do Skycure no Intune](mtd-device-compliance-policy-create.md)