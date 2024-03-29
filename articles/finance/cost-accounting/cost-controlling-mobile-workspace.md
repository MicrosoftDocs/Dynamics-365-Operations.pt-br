---
title: Espaço de trabalho móvel de controle de custo
description: Este artigo fornece informações sobre o espaço de trabalho móvel do controle de custos. Este espaço de trabalho permite que gerentes de centro de custos exibam informações sobre desempenho de centro de custo a qualquer momento e em qualquer lugar.
author: AndersGirke
ms.date: 05/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMMobileCostObjectOverviewDetailsCurrentPeriod, CAMMobileCostObjectList, CAMMobileCostObjectOverviewDetailsPreviousPeriod, CAMMobileCostObjectOverview, CAMMobileCostObjectOverviewDetailsYearToDate, CAMMobileCostControlWorkspaceConfiguration
audience: Application User
ms.reviewer: twheeloc
ms.custom: 267114
ms.assetid: 612f2988-b2b9-420d-9825-40b99dc0e204
ms.search.region: global
ms.author: aevengir
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 2d6d3fdcc0b0387a92f138b0ba7cf537f473b91a
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9069553"
---
# <a name="cost-controlling-mobile-workspace"></a>Espaço de trabalho móvel de controle de custo

[!include [banner](../includes/banner.md)]
[!include [mobile app deprecation](../../fin-ops-core/dev-itpro/includes/mobile-app-deprecation-banner.md)]

Este artigo fornece informações sobre o espaço de trabalho móvel do **Controle de custos**. Este espaço de trabalho permite que gerentes de centro de custos exibam informações sobre desempenho de centro de custo a qualquer momento e em qualquer lugar.

Esse espaço de trabalho móvel deve ser usado com o aplicativo móvel de finanças e operações (Dynamics 365).

## <a name="overview"></a>Visão geral
O espaço de trabalho móvel **Controle de custos** fornece uma exibição instantânea do desempenho atual dos centros de custo comparando custos reais com os custos orçados. Você pode fazer uma busca detalhada nos status de elementos de custo individuais.

Por exemplo, um funcionário recebe um convite para uma conferência internacional, mas a organização deve cobrir todas despesas de viagem. O funcionário pergunta a seu gerente se ele pode participar da conferência. O gerente abre o espaço de trabalho móvel **Controle de custos** no seu dispositivo móvel para ver se dispõe do orçamento para que o funcionário possa ir à conferência.

### <a name="data-security"></a>Segurança de dados
Os dados no espaço de trabalho móvel **Controle de custos** são protegidos pelas credenciais do usuário. Os gerentes do centro de custos podem ver os dados somente de seus próprios centros de custo. A segurança de nível de acesso é gerenciada no módulo **Contabilização de custos**.

Os contadores de custo definem a configuração do espaço de trabalho móvel **Controle de custos** no módulo **Contabilidade de custos**. Após a publicação do espaço de trabalho no aplicativo móvel, ele fica disponível no aplicativo. Com isso, todos os gerentes de centro de custo da organização podem ver os dados no mesmo formato.

### <a name="actions-views-and-links"></a>Ações, exibições e links
O espaço de trabalho móvel **Controle de custo** fornece as seguintes ações, exibições e links:

-   **Ações:**

    -   Use **Selecione configuração** para selecionar um layout.
    -   Use **Selecione o objeto de custo** para selecionar os centros de custos para filtrar dados.
    
        > [!NOTE]
        > Os centros de custo exibidos na lista dependem do acesso concedido no módulo **Contabilização de custos**.

-   **Exibições:** com base nas ações que são selecionadas e na configuração do módulo **Contabilidade de custos**, é possível exibir as seguintes informações nos cartões:

    -   Real versus orçamento (período atual)
    -   Real versus orçamento revisado (período atual)
    -   Real vs. orçamento (período anterior)
    -   Real vs. orçamento revisado (período anterior)
    -   Real vs. orçamento (desde o início do ano)
    -   Real vs. orçamento revisado (desde o início do ano)

    Os valores a seguir são exibidos em cada cartão: Real, Orçamento, Variação e % de variação.

-   **Links:**

    -   Detalhes do período atual
    -   Detalhes do período anterior
    -   Detalhes desde o início do ano

    Quando você seleciona um link, um cartão será mostrado para cada elemento de custo. Os valores a seguir são mostrados em cada cartão: Real, Orçamento, Variação do Orçamento, % de Variação do Orçamento, Orçamento revisado, Variação do Orçamento Revisado e % de Variação do Orçamento Revisado.
    
    [![Cartão de um elemento de custo.](./media/Cost-controlling.png)](./media/Cost-controlling.png)

## <a name="prerequisites"></a>Pré-requisitos
Os pré-requisitos variam conforme a versão do Microsoft Dynamics 365 implantada na organização.

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-finance"></a>Pré-requisitos se você usa o Microsoft Dynamics 365 Finance
Se o Finance foi implantado na organização, o administrador do sistema deve publicar o espaço de trabalho móvel **Controle de custo**. Para obter instruções, consulte [Publicar um espaço de trabalho móvel](../../fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-version-1611-with-platform-update-3-or-later"></a>Pré-requisitos se você usa a versão 1611 com a atualização de plataforma 3 ou posterior
Se a versão 1611 com a atualização de plataforma 3 ou posterior foi implantada na organização, o administrador do sistema deve atender aos seguintes pré-requisitos.

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

<td>O KB 4013633 é uma atualização X++ ou hotfix de metadados que contém o espaço de trabalho móvel de <strong>Controle de custo</strong>. Para implementar o KB 4013633, o administrador do sistema deve seguir estas etapas.
<ol>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/download-hotfix-lcs">Baixe o hotfix de metadados do Microsoft Dynamics Lifecycle Services (LCS)</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Instalar o hotfix de metadados</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/create-apply-deployable-package">Criar um pacote implantável</a> que contenha o modelo <strong>SCMMobile</strong> e, em seguida, carregar o pacote implantável para o LCS.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system">Aplicar o pacote implantável</a>.</li>

</ol></td>
</tr>
<tr class="even">
<td>Publicar o espaço de trabalho móvel do <strong>Controle de custo</strong>.</td>
<td>Administrador do sistema</td>
<td>Consulte <a href="/dynamics365/fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace">Publicar um espaço de trabalho móvel</a>.</td>
</tr>
</tbody>
</table>


## <a name="download-and-install-the-mobile-app"></a>Baixa e instala o aplicativo móvel.
Baixe e instale o aplicativo móvel de finanças e operações (Dynamics 365):

-   [Para telefones Android](https://go.microsoft.com/fwlink/?linkid=850662)
-   [Para iPhones](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Entrar no aplicativo móvel

1.  Inicie o aplicativo móvel no seu dispositivo.
2.  Insira sua URL do Dynamics 365.
3.  Na primeira vez que você iniciar a sessão, será solicitado o nome de usuário e a senha. Insira suas credenciais.
4.  Depois de entrar, serão exibidos os espaços de trabalho disponíveis da sua empresa. Observe que se o seu administrador de sistema publica um novo espaço de de trabalho depois, você terá que atualizar a lista dos espaços de trabalho móveis.

[![Efetue pull para atualizar.](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="view-the-performance-of-your-cost-center-by-using-the-cost-controlling-mobile-workspace"></a>Exiba o desempenho do seu centro de custos usando o espaço de trabalho móvel de controle de custo.

1.  No seu dispositivo móvel, selecione o espaço de trabalho **Controle de custo**.
2.  Selecione **Controle de objeto de custo**.
3.  Selecione **Ações**.
4.  Selecione **Selecionar configuração** para selecionar um layout de controle de custos.
5.  Selecione **Concluído**.
6.  Selecione **Ações**.
7.  Selecione **Selecionar objeto de custo** para selecionar os centros de custo aos quais você tem acesso.
8.  Selecione **Concluído**.
9.  Exiba o desempenho geral do seu centro de custo.
10. Selecione o link **Detalhes do período atual**.
11. Exiba o desempenho dos elementos de custo individuais.
12. Você também pode pesquisar elementos de custo específicos.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]

