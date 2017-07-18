---
title: "Configurações do Intune Endpoint Protection para Windows 10"
titleSuffix: Intune on Azure
description: "Conheça as configurações do Intune que você pode usar para controlar as configurações do Endpoint Protection, como o BitLocker, em dispositivos Windows 10.”"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3af7c91b-8292-4c7e-8d25-8834fcf3517a
ms.reviewer: ilwu
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4994656afcf1cdb97fdcd3877f6dabdadfb7d374
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# Configurações do Endpoint Protection para o Windows 10 e posterior no Microsoft Intune
<a id="endpoint-protection-settings-for-windows-10-and-later-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

O perfil do Endpoint Protection permite controlar os recursos de segurança em dispositivos Windows 10, como o BitLocker.

Use as informações neste tópico para saber como criar perfis do Endpoint Protection.

## Criar um perfil de Endpoint Protection
<a id="create-an-endpoint-protection-profile" class="xliff"></a>

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Configuração do dispositivo**.
2. Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.
3. Na folha de perfis, escolha **Criar Perfil**.
4. Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil de recursos do dispositivo.
5. Na lista suspensa **Plataforma**, escolha **Windows 10 e posterior**.
6. Na lista suspensa de tipos de **Tipo de perfil**, escolha **Endpoint Protection**. 
7. Na folha **Criptografia do Windows**, defina as configurações desejadas. Use os detalhes neste tópico para ajudar a entender o que cada configuração faz. Quando terminar, escolha **OK**.
8. Volte para a folha **Criar Perfil** e escolha **Criar**.

O perfil é criado e exibido na folha da lista de perfis.

## Referência de configurações de perfil do Endpoint Protection
<a id="endpoint-protection-profile-settings-reference" class="xliff"></a>

### Configurações do Windows
<a id="windows-settings" class="xliff"></a>

- **Exigir que os dispositivos sejam criptografados (somente no Desktop)** – Se habilitado, é solicitado que os usuários habilitem a criptografia de dispositivo. Além disso, é solicitado que eles confirmem que a criptografia de outro provedor não foi habilitada. Se a criptografia do Windows for ativada enquanto outro método de criptografia está ativo, o dispositivo pode se tornar instável.
- **Exigir que o cartão de memória seja criptografado (somente em dispositivos móveis)** – Habilite essa configuração para criptografar os cartões de memória removíveis usados pelo dispositivo.


### Configurações base do BitLocker
<a id="bitlocker-base-settings" class="xliff"></a>

- **Configurar métodos de criptografia** – Habilite essa configuração para definir os algoritmos de criptografia para o sistema operacional, dados e unidades removíveis.
    - **Criptografia para unidades do sistema operacional** – Escolha o método de criptografia para unidades do sistema operacional. Recomendamos que você use o algoritmo XTS-AES.
    - **Criptografia para unidades de dados fixas** – Escolha o método de criptografia para unidades de dados fixas (internas). Recomendamos que você use o algoritmo XTS-AES.
    - **Criptografia para unidades de dados removíveis** – Escolha o método de criptografia para unidades de dados removíveis. Se a unidade removível for usada com dispositivos que não executam o Windows 10, é recomendável usar o algoritmo AES-CBC.


### Configurações de unidade do sistema operacional do BitLocker
<a id="bitlocker-os-drive-settings" class="xliff"></a>

- **Exigir autenticação adicional na inicialização** - 
    - **Bloquear o BitLocker em dispositivos sem um chip TPM compatível** - 
    - **Inicialização de TPM** – Configure se o chip do TPM é permitido, não permitido ou necessário. 
    - **PIN de inicialização de TPM** – Configure se utilizar um PIN de inicialização com o chip do TPM é permitido, não permitido ou necessário. 
    - **Chave de inicialização de TPM** – Configure se utilizar uma chave de inicialização com o chip do TPM é permitido, não permitido ou necessário. 
    - **Chave e PIN de inicialização de TPM** – Configure se utilizar uma chave e um PIN de inicialização com o chip do TPM é permitido, não permitido ou necessário.
- **Tamanho mínimo do PIN** – Habilite essa configuração para configurar um tamanho mínimo para o PIN de inicialização de TPM.
    - **Número mínimo de caracteres** – Insira o número de caracteres necessário para o PIN de inicialização variando de **4**-**20**.
- **Habilitar a recuperação de unidade do sistema operacional** – Habilite essa configuração para controlar como as unidades do sistema operacional protegidas pelo BitLocker são recuperadas quando as informações de inicialização necessária não estão disponíveis.
    - **Permitir agente de recuperação de dados com base em certificado** – Habilite essa configuração se quiser que os agentes de recuperação de dados possam ser usados com as unidades do sistema operacional protegidas pelo BitLocker.
    - **Criação de senha de recuperação pelo usuário** – Configure se é permitido, necessário ou não permitido que os usuários gerem uma senha de recuperação de 48 dígitos.
    - **Criação de chave de recuperação pelo usuário** – Configure se é permitido, necessário ou não permitido que os usuários gerem uma chave de recuperação de 256 bits.
    - **Ocultar as opções de recuperação no Assistente de instalação do BitLocker** – Habilite essa configuração para impedir que os usuários visualizem ou alterem as opções de recuperação ao ativarem o BitLocker.
    - **Salvar informações de recuperação do BitLocker no AD DS** – Habilita o armazenamento de informações de recuperação do BitLocker no Active Directory.
    - **Configurar o armazenamento de informações de recuperação do BitLocker no AD DS** – Configure quais blocos de informações de recuperação do BitLocker são armazenadas no Active Directory. Escolha:
        - **Fazer backup de pacotes de chaves e senhas de recuperação**
        - **Fazer backup somente de senhas de recuperação**
    - **Exigir que informações de recuperação sejam armazenadas no AD DS antes de habilitar o BitLocker** – Habilite essa configuração para impedir que os usuários ativem o BitLocker, a menos que o dispositivo esteja ingressado no domínio e as informações de recuperação do BitLocker tenham sido armazenadas com êxito no Active Directory.
- **Habilitar mensagem e URL de recuperação pré-inicialização** – Habilite essa configuração para definir a mensagem e a URL que são exibidas na tela de recuperação de chave pré-inicialização.
    - **Mensagem de recuperação pré-inicialização** – Configure como a mensagem de recuperação pré-inicialização é exibida para os usuários. Escolha:
        - **Usar mensagem e URL de recuperação padrão**
        - **Usar mensagem e URL de recuperação vazia**
        - **Usar mensagem de recuperação personalizada**
        - **Usar URL de recuperação personalizada**


### Configurações de unidades de dados fixas do BitLocker
<a id="bitlocker-fixed-data-drive-settings" class="xliff"></a>

- **Negar acesso de gravação a unidades de dados fixas não protegidas pelo BitLocker** – Se habilitado, a proteção do BitLocker deve ser habilitada em todas as unidades de dados fixas ou internas para que seja possível efetuar gravações nelas.
- **Habilitar a recuperação de unidades fixas** – Habilite essa configuração para controlar como as unidades fixas protegidas pelo BitLocker são recuperadas quando as informações de inicialização necessária não estão disponíveis.
    - **Permitir agente de recuperação de dados** – Habilite essa configuração se quiser que os agentes de recuperação de dados possam ser usados com as unidades fixas protegidas pelo BitLocker.
    - **Criação de senha de recuperação pelo usuário** – Configure se é permitido, necessário ou não permitido que os usuários gerem uma senha de recuperação de 48 dígitos.  
    - **Criação de chave de recuperação pelo usuário** – Configure se é permitido, necessário ou não permitido que os usuários gerem uma chave de recuperação de 256 bits.
    - **Ocultar as opções de recuperação no Assistente de instalação do BitLocker** – Habilite essa configuração para impedir que os usuários visualizem ou alterem as opções de recuperação ao ativarem o BitLocker.
    - **Salvar informações de recuperação do BitLocker no AD DS** – Habilita o armazenamento de informações de recuperação do BitLocker no Active Directory.
    - **Configurar o armazenamento de informações de recuperação do BitLocker no AD DS** – Configure quais blocos de informações de recuperação do BitLocker são armazenadas no Active Directory. Escolha:
        - **Fazer backup de pacotes de chaves e senhas de recuperação**
        - **Fazer backup somente de senhas de recuperação**
    - **Exigir que informações de recuperação sejam armazenadas no AD DS antes de habilitar o BitLocker** – Habilite essa configuração para impedir que os usuários ativem o BitLocker, a menos que o dispositivo esteja ingressado no domínio e as informações de recuperação do BitLocker tenham sido armazenadas com êxito no Active Directory.


### Configurações de unidade de dados removíveis do BitLocker
<a id="bitlocker-removable-data-drive-settings" class="xliff"></a>

- **Negar acesso de gravação para unidades de dados removíveis não protegidas pelo BitLocker** – Especifique se a criptografia do BitLocker é necessária para unidades de armazenamento removível.
    - **Bloquear o acesso de gravação para dispositivos configurados em outra organização** – Especifique se as unidades de dados removíveis que pertencem a outra organização podem ser gravadas.



## Próximas etapas
<a id="next-steps" class="xliff"></a>

Se você desejar atribuir esse perfil aos grupos, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).

