---
title: "Configurações de VPN do Intune para dispositivos iOS | Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: saiba mais sobre as configurações do Intune que você pode usar para configurar conexões VPN em dispositivos iOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1447c123-ea33-4ea0-aab4-69577cdb8d00
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6cd3069a63bd657d1c9f5e33b96db39a3b3f98d2
ms.openlocfilehash: 23322313bfedb089f2665f53795996a26efe40e0


---

# <a name="vpn-settings-for-ios-devices-in-intune-azure-preview"></a>Configurações de VPN para dispositivos iOS na versão prévia do Intune Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Dependendo das configurações escolhidas, nem todos os valores na lista abaixo serão configuráveis.

## <a name="base-vpn-settings"></a>Configurações de VPN de base


**Nome da conexão** – Insira um nome para esta conexão. Usuários finais verão esse nome quando navegarem pela lista de conexões VPN disponíveis em seus dispositivos.
- **Endereço IP ou FQDN** – Forneça o endereço IP ou o nome de domínio totalmente qualificado do servidor VPN ao qual os dispositivos se conectarão. Exemplos: **192.168.1.1**, **vpn.contoso.com**.
- **Método de autenticação** – Escolha como os dispositivos se autenticarão do servidor VPN:
    - **Certificados** – Em **Certificado de autenticação**, escolha um perfil de certificado SCEP ou PKCS criado anteriormente para autenticar a conexão. Para obter mais detalhes sobre os perfis de certificado, consulte [Como configurar certificados](how-to-configure-certificates.md).
    - **Nome de usuário e senha** – Os usuários finais deverão fornecer um nome de usuário e senha para fazer logon no servidor VPN.
- **Tipo de Conexão** – Selecione o tipo de conexão VPN na lista de fornecedores a seguir:
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **Dell SonicWALL Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**
    - **Cisco (IPsec)**
    - **Citrix**
    - **VPN personalizado**
- **Túnel dividido** - **Habilitar** ou **Desabilitar** essa opção que permite que os dispositivos decidam qual conexão usar dependendo do tráfego. Por exemplo, um usuário em um hotel usará a conexão VPN para acessar arquivos de trabalho, porém usará a rede padrão do hotel para navegação regular na Web.


## <a name="custom-vpn-settings"></a>Configurações de VPN personalizado

Se você selecionou **VPN Personalizada**, como o tipo de conexão, defina essas configurações adicionais:

- **Identificador de VPN** Este é um identificador para o aplicativo VPN que você está usando e é fornecido pelo seu provedor VPN.
- **Digite os pares de chave-valor para os atributos personalizados de VPN** Adicione ou importe as **Chaves** e os **Valores** que personalizam sua conexão VPN. Novamente, esses valores geralmente são fornecidos pelo seu provedor de VPN.

## <a name="apps-per-app-vpn-settings"></a>Configurações de aplicativos (VPN por aplicativo)

- **VPN por aplicativo** – Habilite essa opção se você quiser que as URLs habilitem a conexão VPN quando eles forem acessadas de um navegador Safari. Para configurar isso, você deve selecionar **Certificados** como o método de autenticação nas configurações de VPN de base.
- **URLs que habilitam a conexão VPN ao usar o navegador Safari** – clique em Adicionar para adicionar uma ou mais URLs de site da web. Quando essas URLs forem acessadas, a conexão VPN será habilitada.

- **Regras de sob demanda** – Isso permite configurar regras condicionais que controlam quando a conexão VPN é iniciada. Por exemplo, você pode criar uma condição em que a conexão VPN é usada somente quando um dispositivo não está conectado a uma das redes Wi-Fi da empresa. Como alternativa, você poderia criar uma condição em que, se um dispositivo não puder acessar um domínio de pesquisa DNS especificado, a conexão VPN não será iniciada.

    - **Domínios de pesquisa de DNS ou SSIDs** – Selecione se essa condição usará a rede sem fio **SSIDs** ou os **domínios de pesquisa de DNS**. Escolha Adicionar para configurar um ou mais SSIDs ou pesquisar domínios.
    - **Teste de cadeia de caracteres de URL** – opcionalmente, forneça uma URL que usa a regra como um teste. Se o dispositivo no qual esse perfil está instalado puder acessar essa URL sem redirecionamento, a conexão da VPN será estabelecida e o dispositivo se conectará à URL de destino. O usuário não verá o site da investigação de cadeia de caracteres de URL. Um exemplo de uma investigação de cadeia de caracteres de URL é o endereço de um servidor Web de auditoria que verifica a conformidade do dispositivo antes da conexão com a VPN. Outra possibilidade é que a URL teste a capacidade da VPN de se conectar a um site, antes de conectar o dispositivo à URL de destino por meio da VPN.
    - **Ação de domínio** – Escolha uma das seguintes opções:
        - Conectar se necessário – 
        - Nunca conectar – 
    - **Ação** – Escolha uma das seguintes opções:
        - Conectar – 
        - Avaliar conexão – 
        - Ignorar – 
        - Desconectar – 


## <a name="proxy-settings"></a>Configurações de proxy

- **Automático** – Use um arquivo de configuração para definir o servidor proxy. Digite a **URL do servidor proxy** (por exemplo **http://proxy.contoso.com**) que contém o arquivo de configuração.
- **Endereço** – Insira o endereço do servidor proxy (como um endereço IP).
- **Número da porta** – Insira o número de porta associado ao servidor proxy.



<!--HONumber=Feb17_HO2-->

