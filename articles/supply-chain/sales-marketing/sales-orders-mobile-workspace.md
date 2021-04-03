---
title: Espaço de trabalho móvel das ordens de venda
description: Este tópico fornece informações sobre a área de trabalho móvel de ordens de vendas. Este espaço de trabalho o ajuda a ficar atualizado sobre suas ordens de venda a qualquer momento e em qualquer lugar.
author: Mirzaab
manager: tfehr
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 267134
ms.assetid: 0ce96511-002b-4de7-b31e-4303f94edc84
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 41d1ec66774658de6a66a99e752d81a31cd354bf
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5260987"
---
# <a name="sales-orders-mobile-workspace"></a>Espaço de trabalho móvel das ordens de venda

[!include [banner](../includes/banner.md)]

Este tópico fornece informações sobre a área de trabalho móvel de **Ordens de venda**. Este espaço de trabalho o ajuda a ficar atualizado sobre suas ordens de venda a qualquer momento e em qualquer lugar. 

Esse espaço de trabalho móvel deve ser usado com o aplicativo móvel Finance and Operations.

## <a name="overview"></a>Visão Geral
A área de trabalho móvel **Ordens de venda** permite exibir informações detalhadas sobre cada ordem de venda. Essas informações incluem o status da ordem, as informações de contato do cliente e informações de contato do tomador da ordem. O espaço de trabalho móvel **Ordens de venda** fornece uma visualização instantânea das ordens de venda. Você pode exibir todas as ordens de vendas, exibir as ordens de venda por cliente ou exibir informações sobre uma ordem de venda específica. 

O espaço de trabalho móvel oferece duas visualizações para ajudá-lo a analisar as ordens de venda em profundidade.

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
Os pré-requisitos variam conforme a versão do Microsoft Dynamics 365 implantada na organização.

### <a name="prerequisites-if-you-use-supply-chain-management"></a>Pré-requisito para usar o Supply Chain Management 
Se o Supply Chain Management foi implantado para sua organização, o administrador do sistema deverá publicar o espaço de trabalho móvel **Ordens de venda**. Para obter instruções, consulte [Publicar um espaço de trabalho móvel](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a>Pré-requisitos se você usa a versão 1611 do Dynamics 365 for Operations com a atualização de plataforma 3 ou posterior
Se o Dynamics 365 for Operations versão 1611 com a atualização de plataforma 3 ou posterior foi implantado na organização, o administrador do sistema deverá atender aos pré-requisitos a seguir. 

<table>
<thead>
<tr class="header">
<th>Pré-requisito</th>
<th>Função</th>
<th>descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Implementar o KB 4013633.</td>
<td>Administrador do sistema</td>

<td>o KB 4013633 é um hotfix de metadados ou uma atualização X++ que contém a área de trabalho móvel de <strong>Ordens de venda</strong>. Para implementar o KB 4013633, o administrador do sistema deve seguir estas etapas.
<ol>
<li><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Baixe o hotfix de metadados do Microsoft Dynamics Lifecycle Services (LCS)</a>.</li>
<li><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Instalar o hotfix de metadados</a>.</li>
<li><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Criar um pacote implantável</a> que contenha o modelo <strong>SCMMobile</strong> e, em seguida, carregar o pacote implantável para o LCS.</li>
<li><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Aplicar o pacote implantável</a>.</li>

</ol></td>
</tr>
<tr class="even">
<td>Publicando a área de trabalho móvel <strong>Ordens de venda</strong>.</td>
<td>Administrador do sistema</td>
<td>Consulte <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publicar um espaço de trabalho móvel</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>Baixa e instala o aplicativo móvel.
Baixe e instale o aplicativo móvel Finance and Operations:

-   [Para telefones Android](https://go.microsoft.com/fwlink/?linkid=850662)
-   [Para iPhones](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Entrar no aplicativo móvel

1.  Inicie o aplicativo móvel no seu dispositivo.
2.  Insira sua URL do Dynamics 365.
3.  Na primeira vez que você iniciar a sessão, será solicitado o nome de usuário e a senha. Insira suas credenciais.
4.  Após se conectar, você verá os espaços de trabalho da sua empresa. Observe que se o seu administrador de sistema publica um novo espaço de de trabalho depois, você terá que atualizar a lista dos espaços de trabalho móveis.

[![Efetue pull para atualizar](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="view-information-about-sales-orders-for-a-customer-by-using-the-sales-order-mobile-workspace"></a>Exiba informações sobre ordens de venda para um cliente usando a área de trabalho móvel de ordens de venda

1.  No seu dispositivo móvel, selecione o espaço de trabalho **Ordens de vendas**.
2.  Selecione **Exibir ordens para um cliente**.
3.  Use as informações de conta ou nome do cliente para localizar o cliente.
4.  Selecione o cliente.
5.  Selecione **Informações de contato** ou **Ordens de venda**. Se selecionar **Ordens de venda**, será mostrada uma lista de ordens de venda do cliente.
6.  Selecione **Ordem de venda**. Agora você pode exibir informações sobre linhas de ordens de vendas, informações sobre remessas, informações de contato do cliente e informações do tomador da ordem.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]