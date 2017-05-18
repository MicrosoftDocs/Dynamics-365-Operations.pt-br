---
title: "Espaço de trabalho móvel de gerenciamento de despesas"
description: "Este tópico fornece informações sobre o espaço de trabalho móvel Gerenciamento de despesas, que está disponível para o aplicativo móvel Microsoft Dynamics 365 for Operations. Este espaço de trabalho permite que os usuários capturem e carreguem um recibo, para que possam anexá-lo a um relatório de despesas posteriormente. O espaço de trabalho móvel também permite que os usuários criem rapidamente uma linha de despesa usando um recibo anexado."
author: annbe
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: end user, IT Pro
ms.reviewer: annbe
ms.search.scope: Operations
ms.custom: 274023
ms.assetid: 3605eda1-a7ed-4675-8031-5279c5a8f5e4
ms.search.region: Global
ms.author: annbe
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: 8bc47c5b170fd7dd8f6288682aad6eae1d2dc09a
ms.openlocfilehash: 9d3b7a4d5184c3c4958f4298f1d3dd4de0cd06d6
ms.contentlocale: pt-br
ms.lasthandoff: 04/26/2017


---

# <a name="expense-management-mobile-workspace"></a>Espaço de trabalho móvel de gerenciamento de despesas

[!include[banner](../includes/banner.md)]

"[!include[banner](../includes/banner.md)]"


Este tópico fornece informações sobre o espaço de trabalho móvel Gerenciamento de despesas, que está disponível para o aplicativo móvel Microsoft Dynamics 365 for Operations. Este espaço de trabalho permite que os usuários capturem e carreguem um recibo, para que possam anexá-lo a um relatório de despesas posteriormente. O espaço de trabalho móvel também permite que os usuários criem rapidamente uma linha de despesa usando um recibo anexado.

<a name="overview-of-the-expense-management-mobile-workspace"></a>Visão geral do espaço de trabalho móvel Gerenciamento de despesas
---------------------------------------------------

Muitas organizações exigem que uma cópia do recibo seja anexada a um relatório de despesas relacionado a viagem ou a negócios que um funcionário submete para reembolso. O espaço de trabalho móvel **Gerenciamento de despesas** permite que os usuários criem rapidamente novas linhas de despesa no dispositivo móvel de sua preferência usando uma foto do recibo anexada. Como alternativa, os usuários podem tirar uma foto de um recibo e anexá-la a um relatório de despesas depois. Especificamente, espaço de trabalho móvel **Gerenciamento de despesas** habilita um usuário para:

-   Tirar uma foto de um recibo e carregá-lo no Microsoft Dynamics 365 for Operations. Um usuário poderá anexar essa foto a um relatório de despesas posteriormente.
-   Carregar um arquivo como um recebo capturado. Um usuário poderá anexar esse arquivo a um relatório de despesas posteriormente.
-   Criar uma nova linha despesa usando um recibo anexado. Um usuário poderá adicionar o item de linha a um relatório de despesas posteriormente, e enviá-lo para aprovação e reembolso.

As seções restantes deste tópico explicam como implementar e usar o espaço de trabalho móvel **Gerenciamento de despesas**.

## <a name="prerequisites"></a>Pré-requisitos
Antes de implementar o espaço de trabalho móvel **Gerenciamento de despesas**, certifique-se de que seu administrador do sistema preencheu os seguintes pré-requisitos.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Pré-requisito</th>
<th>Função</th>
<th>descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Deve ser implementada a versão 1611 com atualização 3 ou superior de plataforma do Microsoft Dynamics 365.</td>
<td>Administrador do sistema</td>
<td>Se ainda não tiver o Dynamics 365 for Operations implantado em sua organização, o administrador do sistema deverá ver <a href="http://ax.help.dynamics.com/en/wiki/deploy-an-ax7-demo-environment/">Implantar o ambiente de demonstração do Microsoft Dynamics 365 for Operations</a>.</td>
</tr>
<tr class="even">
<td>O KB 4019015 deve ser implementado.</td>
<td>Administrador do sistema</td>
<td>O 4019015 KB (um hotfix de atualização ou de metadados X++) contém quatro espaços de trabalho móveis para gerenciamento da cadeia de suprimentos. Para implementar o KB 4019015, o administrador do sistema deve seguir estas etapas:
<ol>
<li>Baixar o KB 4019015 do Microsoft Dynamics Lifecycle Services (LCS).</li>
<li><a href="https://ax.help.dynamics.com/en/wiki/configuring-and-installing-a-metadata-hotfix-package/">Instalar o hotfix de metadados</a>.</li>
<li><a href="https://ax.help.dynamics.com/en/wiki/create-and-apply-a-deployable-package/">Criar um pacote implantável</a> que contenha os modelos <strong>ApplicationSuite</strong> e <strong>ExpenseMobile</strong> e, em seguida, carregar o pacote implantável para o LCS.</li>
<li><a href="https://ax.help.dynamics.com/en/wiki/apply-a-deployable-package-on-a-dynamics-ax-system/">Aplique o pacote implantável</a> ao seu sistema Dynamics 365 for Operations.</li>
</ol></td>
</tr>
<tr class="odd">
<td>O espaço de trabalho <strong>Gerenciamento de despesas</strong> deve ser publicado para o aplicativo móvel Dynamics 365 for Operations.</td>
<td>Administrador do sistema</td>
<td><ol>
<li>Inicie o Dynamics 365 for Operations em seu navegador.</li>
<li>Na página <strong>Parâmetros do sistema</strong>, selecione <strong>Gerenciar espaços de trabalho móveis</strong>.</li>
<li>Selecione o espaço de trabalho <strong>Gerenciamento de despesas</strong>.</li>
<li>Clique em <strong>Publicar espaço de trabalho móvel</strong>.</li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-dynamics-365-for-operations-mobile-app"></a>Baixe e instale o aplicativo móvel Dynamics 365 for Operations
Baixe e instale o aplicativo móvel Dynamics 365 for Operations de sua loja de aplicativos móveis.

-   Para Android: [Dynamics 365 for Operations na Google Play Store](https://play.google.com/store/apps/details?id=com.microsoft.dynamics365.operations.mobile)
-   Para iPhone: [Dynamics 365 for Operations na iTunes apps store](https://itunes.apple.com/us/app/dynamics-365-for-operations/id1180836730?mt=8)
-   Para Windows phone (Plataforma Universal do Windows \[UWP\]): Em breve!

## <a name="sign-in-to-the-dynamics-365-for-operations-mobile-app"></a>Entre no aplicativo móvel Dynamics 365 for Operations
1.  Inicie o aplicativo móvel no seu dispositivo.
2.  Insira a URL do Dynamics 365 for Operations.
3.  Insira a empresa à qual deseja se conectar. Por exemplo, insira **USMF**.
4.  No primeiro acesso, são solicitados nome de usuário e senha da sua conta do Dynamics 365 for Operations. Insira suas credenciais.
5.  Após se conectar, você verá os espaços de trabalho da sua empresa. Observe que se o seu administrador de sistema publicar uma nova área de trabalho depois, você pode efetuar pull para atualizar a lista dos espaços de trabalho móveis. [![Efetue pull para atualizar](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="capture-a-receipt-by-using-the-expense-management-mobile-workspace"></a>Obtenha um recibo usando o espaço de trabalho móvel Gerenciamento de despesas
1.  No seu dispositivo móvel, selecione o espaço de trabalho **Gerenciamento de despesas**.
2.  Selecione **Capturar recibo**.
3.  Selecione **Tirar foto** ou **Escolher imagem**.
4.  Se você selecionou **Tirar foto**, siga estas etapas:
    1.  Utilize a câmera de seu dispositivo móvel, para que você possa tirar uma foto do recibo. Quando terminar de tirar a foto, clique em **OK** para aceitar a foto.
    2.  Opcional: Insira um nome para a foto e observações.

     ou se você selecionou **Escolher imagem**, siga estas etapas:
    1.  Selecione uma imagem na lista.
    2.  Opcional: Insira um nome para a image e insira observações.

5.  Selecione **Concluído**.

## <a name="quick-expense-entry-by-using-the-expense-management-mobile-workspace"></a>Entrada rápida de despesas usando o espaço de trabalho móvel Gerenciamento de despesas
1.  No seu dispositivo móvel, selecione o espaço de trabalho **Gerenciamento de despesas**.
2.  Selecione **Entrada rápida de despesas**.
3.  Selecione a categoria da despesa. Você verá uma lista de categorias de despesas que estão carregadas para seu aplicativo para uso offline. Por padrão, até 50 itens são carregados, mas um desenvolvedor pode alterar esse número. Para obter mais informações, os desenvolvedores devem ver [plataforma móvel do Dynamics 365 for Operations](http://ax.help.dynamics.com/en/wiki/mobile-development-handbook/). Se sua categoria não estiver na lista, selecione **Pesquisar** para fazer uma pesquisa online no Dynamics 365 for Operations. Pesquise por categoria de despesa ou alterne para pesquisar por tipo de despesa.
4.  Insira a data da transação da despesa.
5.  Opcional: Insira o comerciante da despesa.
6.  Insira o valor da despesa.
7.  Selecione a moeda da despesa. Você verá uma lista de códigos de moeda que são carregados para seu aplicativo para uso offline. Por padrão, até 400 moedas são carregadas, mas um desenvolvedor pode alterar esse número. Para obter mais informações, os desenvolvedores devem ver [plataforma móvel do Dynamics 365 for Operations](http://ax.help.dynamics.com/en/wiki/mobile-development-handbook/). Se sua moeda não estiver na lista, selecione **Pesquisar** para fazer uma pesquisa online no Dynamics 365 for Operations. Pesquise por moeda ou alterne para pesquisar por nome de categoria.
8.  Selecione **Tirar foto** ou **Escolher imagem**.
9.  Se selecionou **Tirar foto**, utilize a câmera de seu dispositivo móvel, para tirar uma foto do recibo. Quando terminar de tirar a foto, clique em **OK** para aceitar a foto.  ou se você selecionou **Escolher imagem**, selecione uma imagem na lista.
10. Selecione **Concluído**.






