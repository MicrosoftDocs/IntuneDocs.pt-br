---
# required metadata

title: Configurações personalizadas para perfis de VPN | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Configurações personalizadas para perfis de VPN

## Criar uma configuração personalizada
Você pode usar configurações personalizadas para criar perfis de VPN no Intune. Parta criar uma configuração personalizada:

   1. No console de administração do Intune **Política** -> **Adicionar Política** -> *<Expand platform>* -> **Configuração personalizada** -> **Criar Política**.
   2. Forneça um nome para a política.
   3. Para cada configuração de URI, clique em **Adicionar** e forneça as informações solicitadas. Aqui está um exemplo:

   ![Caixa de diálogo de configuração personalizada de perfil de VPN](intune/media/Intune_Add_VPN_URI.png)

   4.  Depois de inserir todas as configurações de URI, clique em **Salvar política** e, em seguida, implante a política.

## Implantar uma política de configuração

1.  No espaço de trabalho **Política**, selecione a política que deseja implantar e clique em **Gerenciar Implantação**.

2.  Na caixa de diálogo **Gerenciar implantação** :

    -   **Para implantar a política** - Selecione um ou mais grupos nos quais deseja implantar a política e clique em **Adicionar** &gt; **OK**.

    -   **Para fechar a caixa de diálogo sem implantá-la** - Clique em **Cancelar**.

Quando você seleciona uma política implantada, pode exibir mais informações sobre a implantação na parte inferior da lista de políticas.

##Exemplo de configurações de URI para uma configuração personalizada de perfil de VPN
Aqui estão exemplos de entradas para valores de URI a fim de criar uma configuração personalizada para uma VPN em uma empresa fictícia chamada Contoso. Para obter mais informações, como o tipo de dados para cada entrada, consulte [VPNv2 CSP](https://msdn.microsoft.com/en-us/library/windows/hardware/dn914776.aspx)

VPN de Contoso nativo (IKEv2):
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Servers

vpn.contoso.com
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/NativeProtocolType

Ikev2
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/RoutingPolicyType

SplitTunnel
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/UserMethod

Eap
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/Eap/Configuration
&lt;EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig"&gt;&lt;EapMethod&gt;&lt;Type xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;13&lt;/Type&gt;&lt;VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/VendorId&gt;&lt;VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/VendorType&gt;&lt;AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/AuthorId&gt;&lt;/EapMethod&gt;&lt;Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig"&gt;&lt;Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1"&gt;&lt;Type&gt;13&lt;/Type&gt;&lt;EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1"&gt;&lt;CredentialsSource&gt;&lt;CertificateStore&gt;&lt;SimpleCertSelection&gt;true&lt;/SimpleCertSelection&gt;&lt;/CertificateStore&gt;&lt;/CredentialsSource&gt;&lt;ServerValidation&gt;&lt;DisableUserPromptForServerValidation&gt;false&lt;/DisableUserPromptForServerValidation&gt;&lt;ServerNames&gt;&lt;/ServerNames&gt;&lt;/ServerValidation&gt;&lt;DifferentUsername&gt;false&lt;/DifferentUsername&gt;&lt;PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2"&gt;false&lt;/PerformServerValidation&gt;&lt;AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2"&gt;false&lt;/AcceptServerName&gt;&lt;/EapType&gt;&lt;/Eap&gt;&lt;/Config&gt;&lt;/EapHostConfig&gt;

**./Vendor/MSFT/VPNv2/ContosoVPN/ByPassForLocal**
Verdadeiro

**./Vendor/MSFT/VPNv2/ContosoVPN/RememberCredentials**
1

**./Vendor/MSFT/VPNv2/ContosoVPN/DomainNameInformationList/1/DomainName**
Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/DnsSuffix**
Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/TrustedNetworkDetection**
Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/Address**
10.0.0.0

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/PrefixSize**
8

**./Vendor/MSFT/VPNv2/ContosoVPN/AlwaysOn**
verdadeiro

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/0/App/Id**
%PROGRAMFILES%\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/1/App/Id**
%PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/2/App/Id**
Microsoft.MicrosoftEdge_8wekyb3d8bbwe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/0/App/Id**
%PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/1/App/Id**
Microsoft.MicrosoftEdge_8wekyb3d8bbwe

Para dúvidas sobre como essas configurações devem ser usadas, ou obter mais detalhes sobre o que fazer, os clientes devem consultar a documentação do CSP:
https://msdn.microsoft.com/en-us/library/windows/hardware/dn914776(v=vs.85).aspx

## Configurações de URI para VPN por aplicativo Android em PulseSecure
### URI PERSONALIZADO PARA LISTA DE PACOTES 
-  Tipo de dados = Cadeia de caracteres
-  OMA-URI = ./Vendor/MSFT/VPN/Profile/<Name>/PackageList 
-  Valor = lista de pacotes separados por delimitador.
   - Delimitadores: ponto e vírgula (;), dois pontos (:), vírgula (,), barra vertical (|)

Exemplos: 
- com.android.chrome
- com.android.chrome;com.android.browser

### URI PERSONALIZADO PARA MODO (OPCIONAL)
- Tipo de Dados = Cadeia de caracteres
- OMA-URI = ./Vendor/MSFT/VPN/Profile/NAME/Mode 

> Anotações
> - Usar o mesmo *nome* que você atribuiu ao perfil personalizado
> - Valores possíveis: *GLOBAL*, *LISTA BRANCA*, *LISTA NEGRA*
> - O padrão será *GLOBAL* se nenhum PackageList for fornecido (compatibilidade com versões anteriores com perfis de todo o sistema)
> - O padrão será *LISTA BRANCA* se for fornecido um PackageList


### Consulte também
(Conexões VPN no Microsoft Intune) [vpn-connections-in-microsoft-intune.md]


<!--HONumber=May16_HO1-->

