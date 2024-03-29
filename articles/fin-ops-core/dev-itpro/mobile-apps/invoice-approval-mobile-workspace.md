---
title: Espaço de trabalho móvel para aprovações de fatura
description: Este artigo fornece informações sobre a área de trabalho móvel Aprovações de fatura.
author: abruer
ms.date: 05/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 4cc05d9fcea129cfb2ed8ed8df4bd4034a1fed4c
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9066380"
---
# <a name="invoice-approvals-mobile-workspace"></a>Espaço de trabalho móvel para aprovações de fatura

[!include [banner](../includes/banner.md)]
[!include [mobile app deprecation](../includes/mobile-app-deprecation-banner.md)]

Este artigo fornece informações sobre a área de trabalho móvel **Aprovações de fatura**. Este espaço de trabalho fornece uma lista de faturas que foram atribuídas a você por meio do processo de fluxo de trabalho do cabeçalho da fatura de fornecedor. 

Esse espaço de trabalho móvel deve ser usado com o aplicativo móvel de finanças e operações.

## <a name="overview"></a>Visão geral

O espaço de trabalho móvel **Aprovações de fatura** permite que auxiliares e gerentes de contas a pagar visualizem faturas que lhes foram atribuídas como parte do processo de fluxo de trabalho do cabeçalho da fatura de fornecedor. Você pode visualizar informações de fatura e mesmo detalhes de linhas e de distribuição para ajudá-lo a tomar decisões acertadas de aprovação. A partir do espaço de trabalho, você pode tomar medidas para mover a fatura no processo de fluxo de trabalho. 

## <a name="prerequisites"></a>Pré-requisitos

Antes de usar este espaço de trabalho móvel, os seguintes pré-requisitos devem ser atendidos.

<table>
<thead>
<tr class="header">
<th>Pré-requisito</th>
<th>Função</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>O Microsoft Dynamics 365 Finance deve ser implantado em sua organização.</td>
<td>Administrador do sistema</td>
<td>Consulte <a href="../deployment/deploy-demo-environment.md">Implantar um ambiente de demonstração</a>.
</td>
</tr>
<tr class="even">
<td>A área de trabalho móvel <strong>Aprovações de fatura</strong> deve ser publicada.</td>
<td>Administrador do sistema</td>
<td>Consulte <a href="publish-mobile-workspace.md">Publicar um espaço de trabalho móvel</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>Baixa e instala o aplicativo móvel.

Baixe e instale o aplicativo móvel de finanças e operações:

-   [Para telefones Android](https://go.microsoft.com/fwlink/?linkid=850662)
-   [Para iPhones](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Entrar no aplicativo móvel

1.  Inicie o aplicativo móvel no seu dispositivo.
2.  Insira a URL do Microsoft Dynamics 365.
3.  Na primeira vez que você iniciar a sessão, será solicitado o nome de usuário e a senha. Insira suas credenciais.
4.  Depois de entrar, serão exibidos os espaços de trabalho disponíveis da sua empresa. Observe que se o seu administrador de sistema publica um novo espaço de de trabalho depois, você terá que atualizar a lista dos espaços de trabalho móveis.

    [![Efetue pull para atualizar.](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="approve-invoices-by-using-the-invoice-approvals-mobile-workspace"></a>Aprovar faturas usando o espaço de trabalho móvel para aprovações de fatura
1.  No seu dispositivo móvel, selecione o espaço de trabalho **Aprovações de fatura**.
2.  Selecione a fatura que foi atribuída a você pelo processo de fluxo de trabalho do cabeçalho da fatura de fornecedor.
3.  Na página **Detalhes da fatura**, reveja as informações de cabeçalho da fatura, como informações de fornecedor e data.
4.  Selecione uma linha da fatura para exibir informações mais detalhadas sobre ela na exibição **Detalhes de linha de fatura**.
5.  Na exibição **Detalhes de linha de fatura**, selecione **Distribuições** para exibir as distribuições de linha. Aqui você pode visualizar a contabilidade para a linha de fatura. As informações apresentadas incluem as dimensões financeiras e a conta principal.
6.  Na página **Detalhes da fatura**, selecione **Distribuições** para exibir todas as distribuições. Aqui você pode visualizar a contabilidade para a fatura inteira. As informações apresentadas incluem as dimensões financeiras e as contas principais. 
7.  Selecione **Anexos** para exibir quaisquer notas ou arquivos anexados à fatura.
8.  Na página **Detalhes da fatura**, selecione a ação de fluxo de trabalho apropriada para concluir o seu processo de revisão.
9.  Selecione **Concluído**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

