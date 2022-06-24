---
title: Home page do aplicativo móvel
description: Este artigo descreve o aplicativo móvel de finanças e operações (Dynamics 365) e fornece links para recursos que podem ajudar você a implementá-lo em sua organização.
author: ChrisGarty
ms.date: 05/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: intro-internal
ms.assetid: c99f818f-27b3-4e45-92b4-74272dad0e17
ms.search.region: Global
ms.author: cgarty
ms.dyn365.ops.version: Platform update 4
ms.search.validFrom: 2017-02-28
ms.openlocfilehash: d73a8d3cf8a7899f16db87148456671dea773636
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8868749"
---
# <a name="mobile-app-home-page"></a>Home page do aplicativo móvel

[!include [banner](../includes/banner.md)]
[!include [mobile app deprecation](../includes/mobile-app-deprecation-banner.md)]

Este artigo descreve o aplicativo móvel de **finanças e operações (Dynamics 365)** e fornece links para recursos que podem ajudar você a implementá-lo em sua organização.

## <a name="overview"></a>Visão Geral

O aplicativo móvel permite que sua organização disponibilize os processos empresariais nos dispositivos móveis. Depois que seu administrador de TI habilitar os espaços de trabalho de sua organização, os usuários podem entrar no aplicativo e começar imediatamente a executar os processos comerciais de seus dispositivos móveis. O aplicativo móvel inclui os seguintes recursos que podem ajudar a aumentar a produtividade:

- Os usuários podem exibir, editar e atuar nos dados corporativos, mesmo se eles tiverem conectividade de rede intermitente ou seus dispositivos móveis estiverem completamente offline. Quando um dispositivo restabelece uma conexão de rede, as operações de dados offline são sincronizadas automaticamente.
- Os administradores de TI ou desenvolvedores podem criar e publicar espaços de trabalho móveis que foram personalizados para sua organização. O aplicativo usa seu código de ativos existente. Portanto, não é necessário reimplementar os procedimentos de validação, lógica de negócio ou configuração de segurança.
- Os desenvolvedores ou administradores de TI podem facilmente criar espaços de trabalho móveis usando o criador de espaço de trabalho de apontar e clicar que é incluído no cliente da Web.
- Os administradores de TI ou desenvolvedores podem, como opção, otimizar os recursos offline dos espaços de trabalho, usando a estrutura de extensibilidade da lógica de negócios. Como os dados continuam sendo processados quando um dispositivo está offline, seu cenário móvel permanece avançado e fluido, mesmo se os dispositivos não tiverem conectividade de rede constante.

## <a name="elements-of-the-mobile-app"></a>Elementos do aplicativo móvel
A navegação no aplicativo móvel consiste em quatro conceitos básicos: o painel, os espaços de trabalho, as páginas e as ações. 

[![Conceitos de navegação no aplicativo móvel.](./media/mobilephoneapp1-1024x536.png)](./media/mobilephoneapp1.png)

1. Quando você inicia o aplicativo, você vai para o **painel**.
2. No painel, você pode ver uma lista de **espaços de trabalho** que foi publicada.
3. Em cada espaço de trabalho, você pode ver uma lista de **páginas** disponíveis para esse espaço de trabalho.
4. Estando em uma página, você pode executar várias ações. Eis alguns exemplos:

    - Exibir dados detalhados.
    - Navegue em outras páginas para obter dados relacionados, como detalhes da entidade ou linhas.
    - Consultar uma lista de **ações** disponíveis para essa página. As ações permitem que você crie ou edite os dados existentes.

## <a name="implementation-process"></a>Processo de implementação
A ilustração a seguir mostra o processo de implementação dos espaços de trabalho móveis fornecidos pela Microsoft e dos espaços de trabalho móveis personalizados. 

[![Processo de implementação de aplicativos móveis.](./media/Mobile-implementation-process-5.png)](./media/Mobile-implementation-process-5.png)

A tabela a seguir inclui links para recursos que podem ajudá-lo a implementar os espaços de trabalho móveis fornecidos pela Microsoft e os espaços de trabalho móveis personalizados. Os números na primeira coluna correspondem às etapas numeradas na ilustração anterior.

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
<td>Implemente o aplicativo de finanças e operações em sua organização.</td>
<td><ul><li>Caso ainda não tenha implantado uma versão do Microsoft Dynamics 365, consulte <a href="../deployment/deploy-demo-environment.md">Implantar um ambiente de demonstração</a>.</li><li>Para ver uma lista dos espaços de trabalho móveis que podem ser usados, consulte <a href="mobile-workspaces-released.md">Espaços de trabalho móveis lançados recentemente</a>.</li></ul></td>
</tr>
<tr class="even">
<td>2</td>
<td>Administrador do sistema</td>
<td><strong>Se estiver usando o Microsoft Dynamics 365 for Operations versão 1611:</strong> Baixe e instale os KBs que habilitam os espaços de trabalho móveis que são fornecidos pela Microsoft.</td>
<td>Para obter mais informações, consulte os seguintes tópicos:
<ul>

<li><a href="../../../finance/cost-accounting/cost-controlling-mobile-workspace.md">Espaços de trabalho móveis de controle de custo</a></li>
<li><a href="../../../supply-chain/inventory/inventory-on-hand-mobile-workspace.md">Espaço de trabalho móvel de estoque disponível</a></li>
<li><a href="../../../supply-chain/sales-marketing/sales-orders-mobile-workspace.md">Espaços de trabalho móveis das ordens de venda</a></li>
<li><a href="../../../supply-chain/procurement/vendor-collaboration-mobile-workspace.md">Espaço de trabalho móvel de colaboração de fornecedores</a></li>
<li><a href="/dynamics365/project-operations/prod-pma/project-time-entry-mobile-workspace">Espaço de trabalho móvel de entrada de tempo do projeto</a></li>
<li><a href="/dynamics365/project-operations/prod-exp/expense-management-mobile-workspace">Espaço de trabalho móvel de gerenciamento de despesas</a></li>

</ul></td>
</tr>
<tr class="odd">
<td>3</td>
<td>Administrador do sistema</td>
<td>Publique os espaços de trabalho móveis fornecidos pela Microsoft.</td>
<td><a href="publish-mobile-workspace.md">Publicar um espaço de trabalho móvel</a>
</td>
</tr>
<tr class="even">
<td>4</td>
<td>Desenvolvedor ou fornecedor de software independente (ISV)</td>
<td>Use a plataforma móvel para criar espaços de trabalho móveis personalizados.</td>
<td><a href="platform/mobile-platform-home-page.md">Plataforma móvel</a></td>
</tr>
<tr class="odd">
<td>5</td>
<td>ISV</td>
<td>Cria um pacote implantável que contém os espaços de trabalho móveis personalizados e carrega o pacote no Microsoft Dynamics Lifecycle Services (LCS).</td>
<td><a href="../deployment/create-apply-deployable-package.md">Criar um pacote implantável</a></td>
</tr>
<tr class="even">
<td>6</td>
<td>Administrador do sistema</td>
<td>Aplica o pacote implantável que contém os espaços de trabalho personalizados que são fornecidos pelo ISV (Fornecedor Independente de Software).</td>
<td><a href="../deployment/apply-deployable-package-system.md">Aplicar um pacote implantável</a></td>
</tr>
<tr class="odd">
<td>7</td>
<td>Administrador do sistema</td>
<td>Publica os espaços de trabalho móveis personalizados que são fornecidos pelo ISV.</td>
<td><a href="publish-mobile-workspace.md">Publicar um espaço de trabalho móvel</a></td>
</tr>
<tr class="even">
<td>8</td>
<td>Usuário</td>
<td>Baixe e instale o aplicativo móvel.</td>
<td>
<a href="https://go.microsoft.com/fwlink/?linkid=850662">Aplicativo do Finance and Operations para Android</a><BR/>
<a href="https://go.microsoft.com/fwlink/?linkid=850663">Aplicativo do Finance and Operations para iOS</a><BR/>
(Windows Phone não tem suporte)
</td>
</tr>
<tr class="odd">
<td>9</td>
<td>Usuário</td>
<td>Entrar e usar o aplicativo móvel. O aplicativo inclui os espaços de trabalho móveis que foram publicados pelo administrador do sistema.</td>
<td>Para ver uma lista dos espaços de trabalho móveis que são fornecidos pela Microsoft, consulte <a href="mobile-workspaces-released.md">Espaços de trabalho móveis lançados recentemente</a>.
</td>
</tr>
</tbody>
</table>

## <a name="troubleshooting"></a>Solução de problemas
[Recursos da plataforma móvel](platform/mobile-platform-home-page.md#troubleshooting-the-app)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
