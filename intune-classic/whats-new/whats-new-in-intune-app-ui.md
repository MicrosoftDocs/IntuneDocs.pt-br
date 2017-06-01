---
title: "Atualizações da interface do usuário para aplicativos de usuário final do Intune | Microsoft Docs"
description: "Descubra o que mudou na interface do usuário para aplicativos que funcionam em dispositivos de usuários finais com o Intune."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b782e382-8deb-48a7-a437-d7c5a17163f1
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 629a091c1016186700a95bf76b9feed9ef0adb79
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---
# <a name="ui-updates-for-intune-end-user-apps"></a>Atualizações da interface do usuário para aplicativos de usuário final do Intune
Saiba quais atualizações foram feitas na interface do usuário para os aplicativos que os usuários finais vão encontrar nesta versão do Microsoft Intune. Isso pode ajudá-lo nas comunicações com usuários e na atualização da documentação personalizada que você criou para dar suporte à sua implantação. Isso também pode ajudá-lo a entender como solucionar melhor os problemas enfrentados caso seja necessário ligar para a assistência técnica para obter suporte usando o Portal da Empresa.

## <a name="coming-soon-in-the-ui"></a>Em breve na interface do usuário
Esses são os planos de aprimoramento da experiência do usuário por meio da atualização de nossa interface do usuário.

> [!Note]
> Observe que as imagens abaixo podem ser visualizações, e o produto anunciado pode ser diferente das versões apresentadas.

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>Experiência de início de sessão aprimorada em aplicativos Portal da Empresa para todas as plataformas <!--User Story 1132123-->

Anunciamos uma mudança que entrará em vigor nos próximos meses, destinada a melhorar a experiência de entrada para aplicativos Portal da Empresa do Intune para Android, iOS e Windows. A nova experiência do usuário será exibida automaticamente em todas as plataformas para o aplicativo Portal da Empresa quando o Azure AD fizer essa alteração. Além disso, agora os usuários poderão entrar no Portal da Empresa através de outro dispositivo, com um código gerado de uso único. Isso é especialmente útil nos casos em que os usuários precisam entrar sem credenciais.  

Abaixo você pode ver a experiência de início de sessão anterior, a nova experiência de entrada com as credenciais e a nova experiência de entrada através de outro dispositivo.

__Experiência de início de sessão anterior__

![A página de entrada do Portal da Empresa, com um ícone de uma pessoa na frente de uma representação gráfica de um site. Abaixo está o botão "Entrar". Um link na parte inferior leva às informações de Privacidade e Cookies da Microsoft.](./media/cp_ios_aad_signin_before_1704_001.png)

![Depois de tocar em Entrar, o usuário insere as credenciais nesta página, que solicita um email e uma senha de usuário e também oferece meios para resolver falhas de senha.](./media/cp_ios_aad_signin_before_1704_002.png)

![Depois de fornecer a senha, o aplicativo Portal da Empresa inicia a sessão, mostrando isso por meio de uma barra de carregamento.](./media/cp_ios_aad_signin_before_1704_003.png)

__Nova experiência de início de sessão__

![A página de entrada do Portal da Empresa, com um ícone de uma pessoa na frente de uma representação gráfica de um site. Abaixo está o botão "Entrar". Um link na parte inferior leva às informações de Privacidade e Cookies da Microsoft.](./media/cp_ios_aad_signin_after_1704_001.png)

![O usuário é solicitado a fornecer somente o endereço de email em vez do email e da senha na mesma tela.](./media/cp_ios_aad_signin_after_1704_002.png)

![É solicitada a senha do usuário, depois que seu endereço de email é aceito.](./media/cp_ios_aad_signin_after_1704_003.png)

![Depois de concluir o processo de autenticação, o aplicativo Portal da Empresa inicia a sessão, mostrando isso por meio de uma barra de carregamento.](./media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

__Nova experiência de início de sessão ao entrar em outro dispositivo__

![A página de entrada do Portal da Empresa, com um ícone de uma pessoa na frente de uma representação gráfica de um site. Abaixo está o botão "Entrar". Um link na parte inferior leva às informações de Privacidade e Cookies da Microsoft.](./media/cp_ios_aad_signin_from_another_device_after_1704_001.png)

Toque no link __Entrar de outro dispositivo__.

![São fornecidas instruções para acessar a página aka.ms/devicelogin com uma senha exclusiva do seu computador de trabalho e, em seguida, usar o código para entrar.](./media/cp_ios_aad_signin_from_another_device_after_1704_003.png)

Inicie um navegador e acesse [https://aka.ms/devicelogin](https://aka.ms/devicelogin).

![Uma imagem do navegador do usuário em seu computador de trabalho em vez de seu aplicativo Portal da Empresa. A página de "Logon do dispositivo" que é exibida, solicita aos usuários o código que receberam no aplicativo Portal da Empresa.](./media/cp_ios_aad_signin_from_another_device_after_1704_004.png)

Insira o código que você viu no aplicativo Portal da Empresa. Ao selecionar __Continuar__, você será capaz de se autenticar usando qualquer método que tenha suporte pela sua empresa, como um cartão inteligente.

![O usuário inseriu o código exclusivo no campo, e o site de "Logon do dispositivo" pediu uma confirmação de que o Portal da Empresa do Intune era o aplicativo correto a receber autorização para entrar.](./media/cp_ios_aad_signin_from_another_device_after_1704_005.png)

![Uma página de confirmação, informando que o usuário entrou no aplicativo Portal da Empresa em seu dispositivo, e que essa página poderá ser fechada.](./media/cp_ios_aad_signin_from_another_device_after_1704_006.png)

O aplicativo Portal da Empresa começará a entrar.

![Depois de concluir o processo de autenticação, o aplicativo Portal da Empresa inicia a sessão, mostrando isso por meio de uma barra de carregamento.](./media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

## <a name="april-2017"></a>Abril de 2017

### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431--"></a>Novos ícones para o navegador gerenciado e o Portal da Empresa<!--918433, 918431-->

O navegador gerenciado está recebendo ícones atualizados para versões de Android e iOS do aplicativo. O novo ícone conterá o emblema Intune atualizado para torná-lo mais consistente com outros aplicativos no Enterprise Mobility + Security (EM+S).

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="/intune-classic/whats-new/media/cp_manbro_before_042017.png" alt="The previous version of the Managed Browser app icon." width=200 height=366 align=center>
          </td>
          <td>
             <img src="/intune-classic/whats-new/media/cp_manbro_after_042017.png" alt="The updated version of the Managed Browser app icon." width=200 height=366 align=center>
           </td>
      </tr>
   </table>
</body>
</html>

O Portal da Empresa também está recebendo ícones atualizados para as versões do Windows, iOS e Android do aplicativo para aprimorar a consistência com outros aplicativos EM+S. Esses ícones serão liberados gradualmente em plataformas a partir de abril até o fim de maio.

### <a name="sign-in-progress-indicator-in-android-company-portal---953374--"></a>Indicador de progresso de conexão no Portal da Empresa Android<!--953374-->

Uma atualização para o aplicativo de Portal da empresa Android mostra um indicador de progresso de conexão quando o usuário inicia ou reinicia o aplicativo. O indicador avança por novos status, começando com "Conectando …", e "Fazendo logon..." e "Verificando os requisitos de segurança..." antes de permitir que o usuário acesse o aplicativo.

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="/intune-classic/whats-new/media/cp_android_connecting_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Connecting' underneath it." width=200 height=366 align=center>
          </td>
          <td>
             <img src="/intune-classic/whats-new/media/cp_android_signing_in_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Signing in' underneath it." width=200 height=366 align=center>
           </td>
           <td>
              <img src="/intune-classic/whats-new/media/cp_android_checking_security_reqs_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Checking for security requirements' underneath it." width=200 height=366 align=center>
           </td>
      </tr>
   </table>
</body>
</html>

### <a name="improved-app-install-status-for-the-windows-10-company-portal-app---676495--"></a>Status de instalação do aplicativo aprimorado para o aplicativo de Portal da empresa do Windows 10 <!--676495-->
Agora, o aplicativo de Portal da Empresa do Windows 10 fornece uma barra de progresso da instalação na página de detalhes do aplicativo. Isso tem suporte para aplicativos modernos em dispositivos com a Atualização de Aniversário do Windows 10 e versões posteriores.

__Antes__
  ![Uma imagem da versão anterior da tela de carregamento, onde o status simplesmente mostra 'Instalando'.](./media/cp_win10_install_status_before_1704.png)

__Depois__
  ![Uma imagem da versão atualizada da tela de carregamento, que agora exibe uma barra de progresso da instalação.](./media/cp_win10_install_status_after_1704.png)

## <a name="february-2017"></a>Fevereiro de 2017

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622-announced-1702--"></a>Nova experiência do usuário para o aplicativo Portal da Empresa para Android <!--621622, announced 1702-->
A partir de março, o aplicativo de Portal da empresa para Android seguirá [as diretrizes de design de material](https://material.io/guidelines/material-design/introduction.html) para criar uma aparência mais moderna. Essa experiência do usuário aprimorada inclui:

* __Cores__: cabeçalhos de guia podem ser coloridos de acordo com sua paleta de cores personalizada.

![À esquerda, uma imagem do aplicativo Portal da Empresa para Android antes da atualização. À direita, uma imagem do aplicativo Portal da Empresa para Android após a atualização. As duas imagens mostram a guia Dispositivos como a guia selecionada entre as três guias disponíveis, Contato com o TI, Dispositivos e Aplicativos.](./media/CP_Android_DevicesTab_BeforeAfter.png)

* __Interface__: os botões __Aplicativos em Destaque__ e __Todos os Aplicativos__ foram atualizados na guia __Aplicativos__. O botão __Pesquisa__ agora é um botão de ação flutuante.

![À esquerda, uma imagem do aplicativo Portal da Empresa para Android antes da atualização. À direita, uma imagem do aplicativo Portal da Empresa para Android após a atualização. As duas imagens mostram a guia Aplicativos como a guia selecionada entre as três guias disponíveis, Contatar TI, Dispositivos e Aplicativos.](./media/CP_Android_AppsTab_BeforeAfter.png)

* __Navegação__: Todos os Aplicativos mostra uma exibição com guias de __Em Destaque__, __Todos__ e __Categorias__ para facilitar a navegação. __Contatar TI__ foi otimizada para melhor legibilidade.

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="/intune-classic/whats-new/media/cp_android_contactit_after.png" alt="The Company Portal app for Android displaying an updated version of the Contact IT tab. The tab shows available contact information for IT, including phone number, email address, IT website, and IT contact information." width=200 height=366 align=center>
          </td>
      </tr>
   </table>
</body>
</html>

## <a name="january-2017"></a>Janeiro de 2017

### <a name="modernizing-the-company-portal-website---753980-announced-1701--"></a>Modernizando o site Portal da Empresa <!--753980, announced 1701-->
A partir de fevereiro, o site Portal da Empresa oferecerá suporte a aplicativos destinados a usuários que não têm dispositivos gerenciados. O site será alinhado com outros produtos e serviços da Microsoft usando um novo esquema de cores contrastantes, ilustrações dinâmicas e um "menu hambúrguer", ![Imagem pequena do menu hambúrguer que foi adicionado no canto superior esquerdo do site do Portal da Empresa](./media/CP_hamburger_menu.png) que conterá detalhes de contato do suporte técnico e informações sobre dispositivos gerenciados existentes. A página de aterrissagem será reorganizada para enfatizar os aplicativos que estão disponíveis aos usuários, com carrosséis para aplicativos em destaque e atualizados recentemente.

![À esquerda, uma imagem da versão atual do site de Portal da Empresa com a versão anterior da exibição de Aplicativos, Meus Dispositivos e Destacados e Categorias. À direita, uma imagem da versão atualizada do site do Portal da Empresa com um carrossel de aplicativo atualizado, a lista de aplicativos publicados recentemente e uma exibição de Categorias atualizadas.](./media/CP_Website_BeforeAfter_Feb2016.png)


### <a name="see-also"></a>Consulte também
* [Blog do Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Mapa da Plataforma de Nuvem](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Novidades na visualização do Azure](https://docs.microsoft.com/intune/whats-new)
* [Arquivo de novidades](whats-new-archive.md)
