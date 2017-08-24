---
title: "Página inicial do aplicativo móvel"
description: "Este tópico descreve o aplicativo móvel do Microsoft Dynamics 365 for Unified Operations e fornece links para recursos que podem ajudá-lo a implementá-lo em sua organização."
author: sericks007
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, UnifiedOperations, Platform
ms.custom: 272853
ms.assetid: c99f818f-27b3-4e45-92b4-74272dad0e17
ms.search.region: Global
ms.author: sericks
ms.dyn365.ops.intro: Platform update 4
ms.search.validFrom: 2017-02-28
ms.translationtype: HT
ms.sourcegitcommit: 5230911e1febc66b294f1331846373a472789adf
ms.openlocfilehash: 46a77f2757bee9f688d8c0d23f15cd7eb27ebcb3
ms.contentlocale: pt-br
ms.lasthandoff: 08/04/2017

---

# <a name="mobile-app-home-page"></a>Página inicial do aplicativo móvel

[!include[banner](../includes/banner.md)]

Este tópico descreve o aplicativo móvel do Microsoft Dynamics 365 for Unified Operations e fornece links para recursos que podem ajudá-lo a implementá-lo em sua organização.

> [!NOTE]
> O aplicativo móvel foi anteriormente denominado *Microsoft Dynamics 365 for Finance and Operations*.

<a name="overview"></a>Visão Geral
--------

O aplicativo móvel permite que sua organização disponibilize os processos empresariais nos dispositivos móveis. Depois que seu administrador de TI habilitar os espaços de trabalho de sua organização, os usuários podem entrar no aplicativo e começar imediatamente a executar os processos comerciais de seus dispositivos móveis. O aplicativo móvel inclui os seguintes recursos que podem ajudar a aumentar a produtividade:

- Os usuários podem exibir, editar e atuar nos dados corporativos, mesmo se eles tiverem conectividade de rede intermitente ou seus dispositivos móveis estiverem completamente offline. Quando um dispositivo restabelece uma conexão de rede, operações de dados offline são sincronizadas automaticamente com o Dynamics 365 for Finance and Operations, edição Enterprise, ou com o Microsoft Dynamics 365 for Finance and Operations.
- Os administradores de TI ou desenvolvedores podem criar e publicar espaços de trabalho móveis que foram personalizados para sua organização. O aplicativo usa seu código de ativos existente. Portanto, não é necessário reimplementar os procedimentos de validação, lógica de negócio ou configuração de segurança.
- Os desenvolvedores ou administradores de TI podem facilmente criar espaços de trabalho móveis usando o criador de espaço de trabalho de apontar e clicar que é incluído no cliente da Web.
- Os administradores de TI ou desenvolvedores podem, como opção, otimizar os recursos offline dos espaços de trabalho, usando a estrutura de extensibilidade da lógica de negócios. Como os dados continuam sendo processados quando um dispositivo está offline, seu cenário móvel permanece avançado e fluido, mesmo se os dispositivos não tiverem conectividade de rede constante.

## <a name="elements-of-the-mobile-app"></a>Elementos do aplicativo móvel
A navegação no aplicativo móvel consiste em quatro conceitos básicos: o painel, os espaços de trabalho, as páginas e as ações. 

[![Conceitos de navegação no aplicativo móvel](./media/mobilephoneapp1-1024x536.png)](./media/mobilephoneapp1.png)

1. Quando você inicia o aplicativo, você vai para o **painel**.
2. No painel, você pode ver uma lista de **espaços de trabalho** que foi publicada.
3. Em cada espaço de trabalho, você pode ver uma lista de **páginas** disponíveis para esse espaço de trabalho.
4. Estando em uma página, você pode executar várias ações. Eis alguns exemplos:

    - Exibir dados detalhados.
    - Navegue em outras páginas para obter dados relacionados, como detalhes da entidade ou linhas.
    - Consultar uma lista de **ações** disponíveis para essa página. As ações permitem que você crie ou edite os dados existentes.

## <a name="implementation-process"></a>Processo de implementação
A ilustração a seguir mostra o processo de implementação dos espaços de trabalho móveis fornecidos pela Microsoft e dos espaços de trabalho móveis personalizados. 

![Processo de implementação de aplicativos móveis](./media/Mobile-implementation-process-5.png)

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
<td>Implemente o Finance and Operations ou o Finance and Operations na sua organização.</td>
<td><ul><li>Caso ainda não tenha implantado uma versão do Microsoft Dynamics 365, consulte <a href="../deployment/deploy-demo-environment.md">Implantar ambiente de demonstração</a>.</li><li>Para ver uma lista dos espaços de trabalho móveis que podem ser usados, consulte <a href="mobile-workspaces-released.md">Espaços de trabalho móveis lançados recentemente</a>.</li></ul></td>
</tr>
<tr class="even">
<td>2</td>
<td>Administrador do sistema</td>
<td><strong>Se estiver usando o Microsoft Dynamics 365 for Finance and Operations, versão 1611:</strong> Baixe e instale os KBs que habilitam espaços de trabalho móveis fornecidos pela Microsoft.</td>
<td>Para obter mais informações, consulte os seguintes tópicos:
<ul>

<li><a href="/dynamics365/unified-operations/financials/cost-accounting/cost-controlling-mobile-workspace">Espaços de trabalho móveis de controle de custo</a></li>
<li><a href="/dynamics365/unified-operations/supply-chain/inventory/inventory-on-hand-mobile-workspace">Espaço de trabalho móvel de estoque disponível</a></li>
<li><a href="/dynamics365/unified-operations/supply-chain/sales-marketing/sales-orders-mobile-workspace">Espaços de trabalho móveis das ordens de venda</a></li>
<li><a href="/dynamics365/unified-operations/supply-chain/procurement/vendor-collaboration-mobile-workspace">Espaço de trabalho móvel de colaboração de fornecedores</a></li>
<li><a href="/dynamics365/unified-operations/financials/project-management/project-time-entry-mobile-workspace">Espaço de trabalho móvel de entrada de tempo do projeto</a></li>
<li><a href="/dynamics365/unified-operations/financials/expense-management/expense-management-mobile-workspace">Espaço de trabalho móvel de gerenciamento de despesas</a></li>

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
<td><ul>
<li><a href="https://go.microsoft.com/fwlink/?linkid=850662">Para telefones Android</a></li>
<li><a href="https://go.microsoft.com/fwlink/?linkid=850663">Para iPhones</a></li></ul>
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

