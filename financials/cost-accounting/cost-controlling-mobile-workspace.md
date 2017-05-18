---
title: "Espaço de trabalho móvel de controle de custo"
description: "Este tópico fornece informações sobre o espaço de trabalho móvel de controle de custos disponível no aplicativo móvel Microsoft Dynamics 365 for Operations. Este espaço de trabalho permite que gerentes de centro de custos exibam informações sobre desempenho de centro de custo a qualquer momento e em qualquer lugar."
author: YuyuScheller
manager: AnnBe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: Operations, Core
ms.custom: 267114
ms.assetid: 612f2988-b2b9-420d-9825-40b99dc0e204
ms.search.region: global
ms.author: yuyus
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 31a9650774b2ddb70827ffa210154ca10c761236
ms.contentlocale: pt-br
ms.lasthandoff: 04/25/2017


---

# <a name="cost-controlling-mobile-workspace"></a>Espaço de trabalho móvel de controle de custo

[!include[banner](../includes/banner.md)]


Este tópico fornece informações sobre o espaço de trabalho móvel de controle de custos disponível no aplicativo móvel Microsoft Dynamics 365 for Operations. Este espaço de trabalho permite que gerentes de centro de custos exibam informações sobre desempenho de centro de custo a qualquer momento e em qualquer lugar. 

<a name="overview-of-the-cost-controlling-mobile-workspace"></a>Visão geral do espaço de trabalho móvel Controle de custos
-------------------------------------------------

O espaço de trabalho móvel **Controle de custos** fornece uma exibição instantânea do desempenho atual dos centros de custo comparando custos reais com os custos orçados. Você pode fazer uma busca detalhada nos status de elementos de custo individuais. Por exemplo, um funcionário recebe um convite para uma conferência internacional, mas a organização deve cobrir todas despesas de viagem. O funcionário pergunta a seu gerente se ele pode participar da conferência. O gerente abre o espaço de trabalho móvel **Controle de custos** no seu dispositivo móvel para ver se dispõe do orçamento para que o funcionário possa ir à conferência.

### <a name="data-security"></a>Segurança de dados

Os dados no espaço de trabalho móvel **Controle de custos** são protegidos pelas credenciais do usuário. Os gerentes do centro de custos podem ver os dados somente de seus próprios centros de custo. A segurança de nível de acesso é gerenciada no módulo **Contabilização de custos**. Os contadores de custo definem a configuração do espaço de trabalho móvel **Controle de custos** no módulo **Contabilidade de custos**. Após a publicação do espaço de trabalho no aplicativo móvel Microsoft Dynamics 365 for Operations, ele fica disponível no aplicativo. Com isso, todos os gerentes de centro de custo da organização podem ver os dados no mesmo formato.

### <a name="actions-views-and-links"></a>Ações, exibições e links

O espaço de trabalho móvel **Controle de custos** do aplicativo Dynamics 365 for Operations fornece estas ações, exibições e links:

-   **Ações:**
    -   Use **Selecione configuração** para selecionar um layout.
    -   Use **Selecione o objeto de custo** para selecionar os centros de custos para filtrar dados. **Observação:** Os centros de custo exibidos na lista dependem do acesso concedido no módulo **Contabilização de custos**.
-   **Exibições:** com base nas ações que são selecionadas e na configuração do módulo **Contabilidade de custos**, é possível exibir as seguintes informações nos cartões.
    -   Real vs. orçamento (período atual)
    -   Real vs. orçamento revisado (período atual)
    -   Real vs. orçamento (período anterior)
    -   Real vs. orçamento revisado (período anterior)
    -   Real vs. orçamento (desde o início do ano)
    -   Real vs. orçamento revisado (desde o início do ano)

    Os valores são exibidos em cada cartão: Real, orçamento, variação e % variação.
-   **Links:**
    -   Detalhes do período atual
    -   Detalhes do período anterior
    -   Detalhes desde o início do ano

    Quando você seleciona um link, um cartão será mostrado para cada elemento de custo. Os seguintes valores são mostrados em cada cartão: real, orçamento, variação de orçamento, % variação de orçamento, orçamento revisado, variação do orçamento revisado e % variação de orçamento revisado. 
    
    [![Cartão de um elemento de custo ](./media/cost-controlling.png)](./media/cost-controlling.png)

## <a name="prerequisites"></a>Pré-requisitos
Antes de usar o espaço de trabalho móvel **Controle de custos**, certifique-se de que o administrador do sistema tem os seguintes pré-requisitos funcionando.

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
<td>O espaço de trabalho <strong>Controle de custos</strong> deve ser publicado para o aplicativo móvel Dynamics 365 for Operations.</td>
<td>Administrador do sistema</td>
<td><ol>
<li>Inicie o Dynamics 365 for Operations em seu navegador.</li>
<li>Na página <strong>Parâmetros do sistema</strong>, selecione <strong>Gerenciar espaços de trabalho móveis</strong>.</li>
<li>Selecione o espaço de trabalho <strong>Visão geral do objeto de custo</strong>.</li>
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





