---
title: "Espaço de trabalho móvel das ordens de venda"
description: "Este tópico fornece informações sobre o espaço de trabalho móvel das ordens de venda disponível no aplicativo móvel Microsoft Dynamics 365 for Operations. Este espaço de trabalho o ajuda a ficar atualizado sobre suas ordens de venda a qualquer momento e em qualquer lugar."
author: YuyuScheller
manager: AnnBe
ms.date: 04/21/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: Operations, Core
ms.custom: 267134
ms.assetid: 0ce96511-002b-4de7-b31e-4303f94edc84
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 119b80e5d8067ffbf75d8b067f4803558c2c94b0
ms.contentlocale: pt-br
ms.lasthandoff: 04/25/2017


---

# <a name="sales-orders-mobile-workspace"></a>Espaço de trabalho móvel das ordens de venda

[!include[banner](../includes/banner.md)]


Este tópico fornece informações sobre o espaço de trabalho móvel das ordens de venda disponível no aplicativo móvel Microsoft Dynamics 365 for Operations. Este espaço de trabalho o ajuda a ficar atualizado sobre suas ordens de venda a qualquer momento e em qualquer lugar. 

<a name="overview-of-the-sales-orders-mobile-workspace"></a>Visão geral do espaço de trabalho móvel das ordens de venda
---------------------------------------------

O espaço de trabalho **Ordens de venda** acessa móvel o Microsoft Dynamics 365 for Operations e permite que você visualize informações detalhadas sobre cada ordem de venda. Essas informações incluem o status da ordem, as informações de contato do cliente e informações de contato do tomador da ordem. O espaço de trabalho móvel **Ordens de venda** fornece uma visualização instantânea das ordens de venda. Você pode exibir todas as ordens de vendas, exibir as ordens de venda por cliente ou exibir informações sobre uma ordem de venda específica. O espaço de trabalho móvel oferece duas visualizações para ajudá-lo a analisar as ordens de venda em profundidade.

### <a name="view-all-sales-orders"></a>Exibir todas as ordens de venda

Essa exibição lista todas as ordens do cliente.

-   Use um dos seguintes filtros para selecionar as ordens de vendas que deseja exibir:
    -   Pesquisar por ordem de cliente
    -   Pesquisa por conta de cliente
    -   Pesquisa por nome de cliente
    -   Pesquisar por status
    -   Pesquisar por status de lançamento
    -   Procurar por data e hora de criação
-   Depois de selecionar as ordens de venda, você pode visualizar os detalhes de ordens específicas. Especificamente, você pode exibir as seguintes informações:
    -   Informações de nome e endereço do cliente
    -   Várias datas da ordem de venda, como a data de remessa solicitada e a data de remessa confirmada
    -   Informações de contato do tomador da ordem
    -   Informações de contato do cliente
    -   Linhas da ordem
    -   Remessas que mostram como e quando uma ordem de venda foi enviada

### <a name="view-orders-for-a-customer"></a>Exibir ordens de um cliente

Essa exibição lista ordens de vendas por cliente.

-   Use um dos seguintes filtros para exibir as ordens de um cliente:
    -   Pesquisar por nome
    -   Pesquisar por conta
-   Após selecionar um cliente, você pode exibir as seguintes informações:
    -   Nome e grupo do cliente
    -   Informações de contato do cliente
    -   Ordens de vendas do cliente e detalhes sobre essas ordens de venda:
        -   Informações de nome e endereço do cliente
        -   Várias datas da ordem de venda
        -   Informações de contato do tomador da ordem
        -   Informações de contato do cliente
        -   Linhas da ordem
        -   Remessas que mostram como e quando uma ordem de venda foi enviada

## <a name="prerequisites"></a>Pré-requisitos
Antes de usar o espaço de trabalho móvel **Ordens de venda**, certifique-se de que o administrador do sistema tem os seguintes pré-requisitos funcionando.

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
<td>Deve ser implementada a versão 1611 com atualização 3 ou superior de plataforma do Dynamics 365 for Operations.</td>
<td>Administrador do sistema</td>
<td>Se ainda não tiver o Dynamics 365 for Operations implantado em sua organização, o administrador do sistema deverá ver <a href="http://ax.help.dynamics.com/en/wiki/deploy-an-ax7-demo-environment/">Implantar o ambiente de demonstração do Microsoft Dynamics 365 for Operations</a>.</td>
</tr>
<tr class="even">
<td>O KB 4013633 deve ser implementado.</td>
<td>Administrador do sistema</td>
<td>O 4013633 KB (um hotfix de atualização ou de metadados X++) contém quatro espaços de trabalho móveis para gerenciamento da cadeia de suprimentos. Para implementar o KB 4013633, o administrador do sistema deve seguir estas etapas:
<ol>
<li>Baixar o KB 4013633 do Microsoft Dynamics Lifecycle Services (LCS).</li>
<li><a href="https://ax.help.dynamics.com/en/wiki/configuring-and-installing-a-metadata-hotfix-package/">Instalar o hotfix de metadados</a>.</li>
<li><a href="https://ax.help.dynamics.com/en/wiki/create-and-apply-a-deployable-package/">Criar um pacote implantável</a> que contenha o modelo <strong>SCMMobile</strong> e, em seguida, carregar o pacote implantável para o LCS.</li>
<li><a href="https://ax.help.dynamics.com/en/wiki/apply-a-deployable-package-on-a-dynamics-ax-system/">Aplique o pacote implantável</a> ao seu sistema Dynamics 365 for Operations.</li>
</ol></td>
</tr>
<tr class="odd">
<td>O espaço de trabalho móvel <strong>Ordens de venda</strong> deve ser publicado no aplicativo móvel Dynamics 365 for Operations.</td>
<td>Administrador do sistema</td>
<td><ol>
<li>Inicie o Dynamics 365 for Operations em seu navegador.</li>
<li>Na página <strong>Parâmetros do sistema</strong>, selecione <strong>Gerenciar espaços de trabalho móveis</strong>.</li>
<li>Selecione o espaço de trabalho <strong>Ordens de venda</strong>.</li>
<li>Clique em <strong>Publicar espaço de trabalho móvel</strong>.</li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-dynamics-365-for-operations-mobile-app"></a>Baixe e instale o aplicativo móvel Dynamics 365 for Operations
Baixe e instale o aplicativo móvel Dynamics 365 for Operations de sua loja de aplicativos móveis.

-   Para Android: [Dynamics 365 for Operations na Google Play Store](https://play.google.com/store/apps/details?id=com.microsoft.dynamics365.operations.mobile)
-   Para iPhone: [Dynamics 365 for Operations na iTunes apps store](https://itunes.apple.com/us/app/dynamics-365-for-operations/id1180836730?mt=8)

## <a name="sign-in-to-the-dynamics-365-for-operations-mobile-app"></a>Entre no aplicativo móvel Dynamics 365 for Operations
1.  Inicie o aplicativo móvel no seu dispositivo.
2.  Insira a URL do Dynamics 365 for Operations.
3.  Insira a empresa à qual deseja se conectar. Por exemplo, insira **USMF**.
4.  No primeiro acesso, são solicitados nome de usuário e senha da sua conta do Dynamics 365 for Operations. Insira suas credenciais.
5.  Após se conectar, você verá os espaços de trabalho da sua empresa. Observe que se seu administrador do sistema publicar posteriormente um novo espaço de trabalho, você pode efetuar pull para atualizar a lista dos espaços de trabalho móveis. 

    [![Efetue pull para atualizar](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="view-information-about-sales-orders-for-a-customer-by-using-the-mobile-workspace"></a>Exiba informações sobre ordens de venda para um cliente usando o espaço de trabalho móvel
1.  No seu dispositivo móvel, selecione o espaço de trabalho **Ordens de vendas**.
2.  Selecione **Exibir ordens para um cliente**.
3.  Use as informações de conta ou nome do cliente para localizar o cliente.
4.  Selecione o cliente.
5.  Selecione **Informações de contato** ou **Ordens de venda**. Se selecionar **Ordens de venda**, será mostrada uma lista de ordens de venda do cliente.
6.  Selecione **Ordem de venda**. Agora você pode exibir informações sobre linhas de ordens de vendas, informações sobre remessas, informações de contato do cliente e informações do tomador da ordem.





