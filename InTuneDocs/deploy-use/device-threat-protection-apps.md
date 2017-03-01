---
title: Implantar o aplicativo Lookout for Work | Microsoft Docs
description: Configurar e implantar aplicativos Lookout for Work para Android.
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 524c4209-ad57-4d35-955e-a00d796bf858
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 6f687a1db84b49bc173d2067ab95598b4485daa8
ms.openlocfilehash: ab94439d9fd5300d61c5991434d41f7fdca693d2


---

# <a name="configure-and-deploy-lookout-for-work-apps"></a>Configurar e implantar aplicativos Lookout for Work

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Este artigo explica como configurar e implantar o aplicativo Lookout for Work em dispositivos Android e iOS.

## <a name="android-google-play-store-app"></a>Android (aplicativo da Google Play Store)

1.    No [console do administrador do Microsoft Intune](https://manage.microsoft.com), acesse **Aplicativos** e escolha **Adicionar Aplicativos**.
2.    Na página **Configuração de Software** do editor, escolha **Link externo** e especifique a seguinte URL: https://play.google.com/store/apps/details?id=com.lookout.enterprise
  >[!NOTE]
  >Não clique na caixa para exigir um navegador gerenciado.

3.    Na página **Descrição do software**, preencha as seguintes informações:
  * **Editor:** Lookout Mobile Security
  * **Nome:** Lookout for Work
  * **Descrição:** o Lookout oferece a melhor proteção contra ameaças móveis para manter seu dispositivo em segurança. Quando o aplicativo Lookout é instalado no dispositivo, ele o protege contra ameaças e alerta você e o administrador da empresa se alguma ameaça for encontrada.
  * **Categoria:** Gerenciamento de Computador

4. Após a conclusão bem-sucedida, você verá a mensagem **Upload de dados para o Microsoft Intune concluído com êxito**.

  No Console do Intune, ao clicar em **Aplicativos**, agora você verá o aplicativo **Lookout for Work** na lista ![captura de tela da página de aplicativos do console do administrador do Intune mostrando os aplicativos Lookout for Work na lista](../media/mtp/lookout-app-listed-intune-console.png)

5. Implante o aplicativo nos usuários selecionando o aplicativo Lookout for Work e escolhendo **Gerenciar Implantação**.

  Você precisa selecionar os mesmos usuários adicionados à opção de Gerenciamento de Registro no console da Consulta MTP.  Consulte a Etapa 3 na seção [Configurar sua assinatura da Consulta MTP](configure-and-deploy-lookout-for-work-apps.md) para obter informações sobre como adicionar grupos de usuários à Consulta MTP.

  >[!IMPORTANT]
  > O assistente de implantação de aplicativo do Intune não está ciente dos grupos de usuários do Azure AD e usa os grupos de usuários do Intune em vez disso. Sendo assim, você precisa criar um grupo de usuários do Intune com base no grupo de usuários do Azure AD que está registrado no console da Consulta MTP, conforme descrito [neste](plan-your-user-and-device-groups.md) tópico.

6. Escolha a opção **Instalação Obrigatória** para exigir que o aplicativo Lookout seja instalado no dispositivo do usuário.

## <a name="ios-enterprise-signed-version-of-lookout-app"></a>iOS (versão Enterprise assinada do aplicativo Lookout)

1. Verifique se o **Gerenciamento do iOS** está configurado no dispositivo. Para obter instruções sobre como configurar seu dispositivo para gerenciamento de iOS, consulte [Configurar o gerenciamento de dispositivos iOS e Mac](set-up-ios-and-mac-management-with-microsoft-intune.md).

2. **Reassine** o aplicativo Lookout for Work do iOS. O Lookout distribui o aplicativo iOS Lookout for Work fora da iOS App Store. **Antes de distribuir o aplicativo**, você deve reassiná-lo com o Certificado de Desenvolvedor Enterprise do iOS. Para obter instruções detalhadas sobre como reassinar o aplicativo iOS Lookout for Work, consulte [Processo para reassinar o aplicativo iOS Lookout for Work](https://personal.support.lookout.com/hc/en-us/articles/114094038714) no site do Lookout.

3. Habilite a autenticação do Azure Active Directory para os usuários do iOS fazendo o seguinte:
  1.  Faça logon no [portal de gerenciamento do Azure Active Directory](https://manage.windowsazure.com) e navegue até a página do aplicativo.
  2.  Adicione o **aplicativo iOS Lookout for Work** como um **aplicativo de cliente nativo**.
  ![captura de tela da caixa de diálogo adicionar aplicativos mostrando a opção cliente nativo do aplicativo](../media/mtp/aad-add-app.png)
  3. Substitua o **com.lookout.enterprise.yourcompanyname** pela ID de pacote do cliente selecionada na assinatura do IPA.
  4.  Adicione o URI de redirecionamento adicional: **&lt;companyportal://code/ >** seguido por uma versão URL codificada do URI de redirecionamento original.
  5.  Adicione **Permissões delegadas** ao aplicativo.

  Para obter mais detalhes, consulte [Configurar um aplicativo de cliente nativo](https://azure.microsoft.com/en-us/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application).

4. Carregue o arquivo .ipa reassinado, conforme descrito no tópico [Adicionar aplicativo para dispositivos móveis no Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune). Defina a versão mínima do sistema operacional para iOS 8.0 ou posterior.

  ![captura de tela da página de aplicativos do console do administrador do Intune com o aplicativo Lookout for Work exibido na lista de aplicativos](../media/mtp/ios-app-uploaded-intune.png)

5. Crie a política de configuração de aplicativo gerenciado, conforme descrito no tópico [Configure iOS apps with mobile app configuration policies in Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune) (Configurar aplicativos iOS com políticas de configuração de aplicativo móvel no Microsoft Intune).

  ![captura de tela do assistente de criação de nova política com o iOS 8.0 ou posterior com a política de configuração do aplicativo destacada](../media/mtp/ios-app-config.png)

6. **Para implantar o aplicativo nos usuários**, selecione o aplicativo Lookout for Work e escolha **Gerenciar Implantação**.

  Você precisa selecionar os mesmos usuários que foram adicionados à opção de Gerenciamento de Registro no console do Lookout.  Consulte a Etapa 3 na seção [Configurar sua assinatura com a proteção contra ameaça do dispositivo Lookout](https://docs.microsoft.com/sccm/protect/deploy-use/configure-and-deploy-lookout-for-work-apps) para obter informações sobre como adicionar grupos de usuários ao Lookout MTP.

  >[!IMPORTANT]
  > O assistente de implantação de aplicativo do Intune não está ciente dos grupos de usuários do Azure AD e, em vez disso, usa os grupos de usuários do Intune, portanto você deve criar um grupo de usuários do Azure AD que está registrado no console do Lookout, conforme descrito [neste](plan-your-user-and-device-groups.md) tópico.

  Escolha a opção **Instalação Obrigatória** para exigir que o aplicativo Lookout seja instalado no dispositivo do usuário.

## <a name="what-happens-when-the-deployed-app-is-opened-on-the-device"></a>O que acontece quando o aplicativo implantado for aberto no dispositivo

Quando abrir o Lookout for Work no dispositivo, o usuário será solicitado a ativar o aplicativo e escolher a opção Entrar no Azure Active Directory. Uma explicação detalhada, com o fluxo do usuário final, pode ser encontrada nos tópicos a seguir:

* [Você é solicitado a instalar o Lookout for Work em seu dispositivo Android](http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

* [Você precisa resolver uma ameaça que o Lookout for Work encontrou em seu dispositivo Android](http://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)

## <a name="next-steps"></a>Próximas etapas
* [Habilitar a regra de proteção de dispositivo contra ameaças na política de conformidade](https://docs.microsoft.com/sccm/protect/deploy-use/enable-device-threat-protection-rule-compliance-policy)



<!--HONumber=Feb17_HO4-->

