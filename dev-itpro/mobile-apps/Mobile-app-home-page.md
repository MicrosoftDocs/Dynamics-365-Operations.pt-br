---
title: "Home page do aplicativo móvel Dynamics 365 for Operations"
description: "Este tópico descreve o aplicativo móvel do Microsoft Dynamics 365 for Operations e fornece links para recursos que podem ajudá-lo a implementá-lo em sua organização."
author: sericks007
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: annbe
ms.search.scope: Operations, Platform
ms.custom: 272853
ms.assetid: c99f818f-27b3-4e45-92b4-74272dad0e17
ms.search.region: Global
ms.author: sericks
ms.dyn365.ops.intro: Platform update 4
ms.search.validFrom: 2017-02-28
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: e1a9e0eeb45f011ccb2aa091e68aff92782e1ae7
ms.contentlocale: pt-br
ms.lasthandoff: 04/25/2017


---

# <a name="dynamics-365-for-operations-mobile-app-home-page"></a>Home page do aplicativo móvel Dynamics 365 for Operations

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/banner.md)]


Este tópico descreve o aplicativo móvel do Microsoft Dynamics 365 for Operations e fornece links para recursos que podem ajudá-lo a implementá-lo em sua organização.

<a name="overview"></a>Visão Geral
--------

O aplicativo móvel Microsoft Dynamics 365 for Operations permite que sua organização disponibilize os processos empresariais nos dispositivos móveis. Depois que seu administrador de TI habilitar o recurso dos espaços de trabalho de sua organização, os usuários podem entrar no aplicativo e começar imediatamente a executar os processos comerciais de seus dispositivos móveis. O aplicativo móvel Dynamics 365 for Operations inclui os seguintes recursos que podem ajudar a aumentar a produtividade:

-   Os usuários podem exibir, editar e atuar nos dados corporativos, mesmo se eles tiverem conectividade de rede intermitente ou seus dispositivos móveis estiverem completamente offline. Quando um dispositivo restabelece uma conexão de rede, as operações de dados offline são sincronizadas automaticamente com o Dynamics 365 for Operations.
-   Os administradores de TI ou desenvolvedores podem criar e publicar espaços de trabalho móveis que foram personalizados para sua organização. O aplicativo usa seu código de ativos existente. Portanto, não é necessário reimplementar os procedimentos de validação, lógica de negócio ou configuração de segurança.
-   Os administradores de TI ou desenvolvedores criam espaços de trabalho móveis facilmente, usando o criador de espaço de trabalho apontar e clicar que é incluído no cliente da Web do Dynamics 365 for Operations.
-   Os administradores de TI ou desenvolvedores podem, como opção, otimizar os recursos offline dos espaços de trabalho, usando a estrutura de extensibilidade da lógica de negócios. Como os dados continuam sendo processados quando um dispositivo está offline, seu cenário móvel permanece avançado e fluido, mesmo se os dispositivos não tiverem conectividade de rede constante.

## <a name="elements-of-the-mobile-app"></a>Elementos do aplicativo móvel
A navegação no aplicativo móvel consiste em quatro conceitos simples: o painel, espaços de trabalho, as páginas e as ações. 

[![Conceitos de navegação no aplicativo móvel](./media/mobilephoneapp1-1024x536.png)](./media/mobilephoneapp1.png)

-   Quando você inicia o aplicativo, você vai para o **painel**.
-   No painel, você pode ver uma lista **espaços de trabalho** que será publicada em seu ambiente do Dynamics 365 for Operations.
-   Em cada espaço de trabalho, você pode ver uma lista **páginas** disponíveis para esse espaço de trabalho.
-   Em uma página, é possível ver os dados que são coletados de uma ou mais páginas no Dynamics 365 for Operations.
-   Em uma página, você pode navegar para outras páginas para obter dados relacionados, como detalhes da entidade ou linhas.
-   Em uma página, também é possível ver uma lista de **ações** que estão disponíveis para essa página.
-   As ações permitem que você crie ou edite os dados existentes.

## <a name="implementation-process"></a>Processo de implementação
A ilustração a seguir mostra o processo para implementar o aplicativo móvel Dynamics 365 for Operations em sua organização. 

[![](./media/mobile-implementation-process_4.png)](./media/mobile-implementation-process_4.png) 

A tabela a seguir tem links para os recursos que podem ajudá-lo a implementar o aplicativo móvel Dynamics 365 for Operations em sua organização. Os números na primeira coluna correspondem às etapas numeradas na ilustração anterior.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Etapa</th>
<th>Função</th>
<th>Ação</th>
<th>Recursos para ajudá-lo a concluir a ação</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>1</td>
<td>Administrador do sistema</td>
<td>Implementam o Dynamics 365 for Operations da organização.</td>
<td>Se ainda não tiver o Dynamics 365 for Operations implantado em sua organização, consulte <a href="https://docs.microsoft.com/en-us/dynamics365/operations/dev-itpro/deployment/deploy-demo-environment">Implantar um Microsoft Dynamics 365 para ambiente de demonstração</a>.</td>
</tr>
<tr class="even">
<td>2</td>
<td>Administrador do sistema</td>
<td>Baixe e instale os KBs que habilitam os espaços de trabalho móveis que são fornecidos pela Microsoft.</td>
<td>Consulte a seção &quot;Pré-requisitos&quot; no tópico sobre o espaço de trabalho móvel que sua organização quer usar:
<ul>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/financials/cost-accounting/cost-controlling-mobile-workspace">Espaços de trabalho móveis de controle de custo</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/supply-chain/production-control/inventory-on-hand-mobile-workspace">Espaço de trabalho móvel de estoque disponível</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/supply-chain/production-control/sales-orders-mobile-workspace">Espaços de trabalho móveis das ordens de venda</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/supply-chain/procurement/vendor-collaboration-mobile-workspace">Espaço de trabalho móvel de colaboração de fornecedor</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/financials/project-management/project-time-entry-mobile-workspace">Espaço de trabalho móvel de entrada de tempo do projeto</a></li>
</ul></td>
</tr>
<tr class="odd">
<td>3</td>
<td>Administrador do sistema</td>
<td>Publica os espaços de trabalho móveis fornecidos pela Microsoft.</td>
<td>Consulte a seção &quot;Pré-requisitos&quot; no tópico sobre o espaço de trabalho móvel que sua organização quer usar:
<ul>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/financials/cost-accounting/cost-controlling-mobile-workspace">Espaços de trabalho móveis de controle de custo</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/supply-chain/production-control/inventory-on-hand-mobile-workspace">Espaço de trabalho móvel de estoque disponível</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/supply-chain/production-control/sales-orders-mobile-workspace">Espaços de trabalho móveis das ordens de venda</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/supply-chain/procurement/vendor-collaboration-mobile-workspace">Espaço de trabalho móvel de colaboração de fornecedor</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/financials/project-management/project-time-entry-mobile-workspace">Espaço de trabalho móvel de entrada de tempo do projeto</a></li>
</ul></td>
</tr>
<tr class="even">
<td>4</td>
<td>Desenvolvedor ou fornecedores de software independentes (ISVs)</td>
<td>Use a estrutura móvel do Dynamics 365 for Operations para criar espaços de trabalho móveis personalizados.</td>
<td><ul>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform">Estrutura móvel do Dynamics 365 for Operations</a></li>
<li><a href="http://ax.help.dynamics.com/en/wiki/operations-mobile-workspace-x-apis/">Espaço de trabalho X++ APIs do Dynamics 365 for Operations</a></li>
</ul></td>
</tr>
<tr class="odd">
<td>5</td>
<td>ISV</td>
<td>Cria um pacote implantável que contém os espaços de trabalho móveis personalizados e carrega o pacote no Microsoft Dynamics Lifecycle Services (LCS).</td>
<td><a href="https://docs.microsoft.com/en-us/dynamics365/operations/dev-itpro/deployment/create-apply-deployable-package">Gera um pacote implantável</a></td>
</tr>
<tr class="even">
<td>6</td>
<td>Administrador do sistema</td>
<td>Aplica o pacote implantável que contém os espaços de trabalho personalizados que são fornecidos pelo ISV.</td>
<td><a href="https://docs.microsoft.com/en-us/dynamics365/operations/dev-itpro/deployment/apply-deployable-package-system">Aplica um pacote implantável em um sistema Microsoft Dynamics 365 for Operations</a></td>
</tr>
<tr class="odd">
<td>7</td>
<td>Administrador do sistema</td>
<td>Publica os espaços de trabalho móveis personalizados que são fornecidos pelo ISV.</td>
<td><a href="https://docs.microsoft.com/en-us/dynamics365/operations/dev-itpro/mobile-apps/publish-mobile-workspace">Publica um espaço de trabalho móvel</a></td>
</tr>
<tr class="even">
<td>8</td>
<td>Usuário</td>
<td>Baixa e instala o aplicativo móvel Dynamics 365 for Operations.</td>
<td><ul>
<li>Para Android: <a href="https://play.google.com/store/apps/details?id=com.microsoft.dynamics365.operations.mobile">Dynamics 365 for Operations na Google Play Store</a></li>
<li>Para iPhone: <a href="https://itunes.apple.com/us/app/dynamics-365-for-operations/id1180836730?mt=8">Dynamics 365 for Operations na iTunes apps store</a></li>
</ul></td>
</tr>
<tr class="odd">
<td>9</td>
<td>Usuário</td>
<td>Entra e usa o aplicativo móvel Dynamics 365 for Operations. O aplicativo tem os espaços de trabalho móveis que foram publicados.</td>
<td>A Microsoft forneceu os seguintes espaços de trabalho móveis:
<ul>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/financials/cost-accounting/cost-controlling-mobile-workspace">Espaços de trabalho móveis de controle de custo</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/supply-chain/production-control/inventory-on-hand-mobile-workspace">Espaço de trabalho móvel de estoque disponível</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/supply-chain/production-control/sales-orders-mobile-workspace">Espaços de trabalho móveis das ordens de venda</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/supply-chain/procurement/vendor-collaboration-mobile-workspace">Espaço de trabalho móvel de colaboração de fornecedor</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/financials/project-management/project-time-entry-mobile-workspace">Espaço de trabalho móvel de entrada de tempo do projeto</a></li>
</ul></td>
</tr>
</tbody>
</table>



<a name="see-also"></a>Consulte também
--------

[Espaços de trabalho móveis recentemente liberados para o aplicativo móvel Dynamics 365 for Operations](mobile-workspaces-released.md)





