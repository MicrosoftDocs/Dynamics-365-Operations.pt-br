---
title: Área de trabalho móvel para aprovação de ordem de compra
description: Este tópico fornece informações sobre a área de trabalho móvel de aprovação do pedido de compra, que permite visualizar pedidos e responder a eles através de ações. Por exemplo, você pode aprovar ou rejeitar uma ordem de compra.
author: kamaybac
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchVendorPortalRequests
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30211
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 26f0dc3b128daf8c7d8a05d6f3cacc5b7de0c756
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2021
ms.locfileid: "5909099"
---
# <a name="purchase-order-approval-mobile-workspace"></a>Área de trabalho móvel para aprovação de ordem de compra

[!include [banner](../includes/banner.md)]

Este tópico fornece informações sobre a área de trabalho móvel de **Aprovação de ordem de compra**. Esta área de trabalho permite que você veja pedidos e responda através de ações. Por exemplo, você pode aprovar ou rejeitar uma ordem de compra.
 
## <a name="overview"></a>Visão Geral 
As ordens de compra que exigem aprovação passam por um fluxo de trabalho de aprovação. O fluxo de trabalho pode incluir várias etapas que exigem que uma ou mais pessoas ajam. Por exemplo, uma pessoa pode ter que completar uma tarefa ou aprovar a ordem de compra. 

A área de trabalho móvel **Aprovação de ordem de compra** permite facilmente responder e exibir ordens de compra no dispositivo móvel. Este espaço de trabalho também permite tomar as mesmas medidas de fluxo de trabalho que você toma no cliente Web.

## <a name="prerequisites"></a>Pré-requisitos
Os pré-requisitos variam, dependendo da versão do Supply Chain Management que foi implantada para sua organização.

### <a name="prerequisites-if-you-use-supply-chain-management"></a>Pré-requisito para usar o Supply Chain Management 
Se o Supply Chain Management tiver sido implantado na organização, o administrador do sistema deverá publicar o espaço de trabalho móvel **Aprovação de ordem de compra**. Para obter instruções, consulte [Publicar um espaço de trabalho móvel](../../fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a>Pré-requisitos se você usa a versão 1611 do Microsoft Dynamics 365 for Operations com a atualização de plataforma 3 ou posterior
Se o Microsoft Dynamics 365 for Operations versão 1611 com a atualização de plataforma 3 ou posterior foi implantado na organização, o administrador do sistema deverá atender aos pré-requisitos a seguir. 

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
<td>Implementar o KB 4017918.</td>
<td>Administrador do sistema</td>
<td>o KB 4017918 é um hotfix de metadados ou atualização X++ que contém a área de trabalho móvel <strong>Aprovação de ordem de compra</strong>. Para implementar o KB 4017918, o administrador do sistema deve seguir estas etapas.
<ol>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/download-hotfix-lcs">Baixe o hotfix de metadados do Microsoft Dynamics Lifecycle Services (LCS)</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Instalar o hotfix de metadados</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/create-apply-deployable-package">Criar um pacote implantável</a> que contenha o modelo <strong>SCMMobile</strong> e, em seguida, carregar o pacote implantável para o LCS.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system">Aplicar o pacote implantável</a>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Publicar a área de trabalho móvel de <strong>Aprovação de ordem de compra</strong>.</td>
<td>Administrador do sistema</td>
<td>Consulte <a href="/dynamics365/fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace">Publicar um espaço de trabalho móvel</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>Baixa e instala o aplicativo móvel.
Baixe e instale o aplicativo móvel Finance and Operations:

- [Para telefones Android](https://go.microsoft.com/fwlink/?linkid=850662)
- [Para iPhones](https://go.microsoft.com/fwlink/?linkid=850663)


## <a name="sign-in-to-the-mobile-app"></a>Entrar no aplicativo móvel

1. Inicie o aplicativo móvel no seu dispositivo.
2. Insira a URL do Microsoft Dynamics 365.
3. Na primeira vez que você iniciar a sessão, será solicitado o nome de usuário e a senha. Insira suas credenciais.
4. Depois de entrar, serão exibidos os espaços de trabalho disponíveis da sua empresa. Observe que se o seu administrador de sistema publica um novo espaço de de trabalho depois, você terá que atualizar a lista dos espaços de trabalho móveis.

![A área de trabalho de aprovação de ordem de compra na lista dos espaços de trabalho disponíveis](./media/po-workspaces.png)

## <a name="view-orders-that-are-assigned-to-you"></a>Exibir ordens atribuídos a você
1. No seu dispositivo móvel, selecione a área de trabalho **Aprovação de ordem de compra**.
2. Selecione **Ordens atribuída a mim** para exibir todas as ordens de compra para a qual foi solicitado a você tomar uma ação no fluxo de trabalho de aprovação de ordem de compra.
3. Selecione uma ordem. Na página **Detalhes da ordem**, você verá as informações e as linhas de cabeçalho da ordem. Também é possível localizar diretrizes de tarefas de fluxo de trabalho.
4. Selecione **Distribuições contábeis** para abrir a página **Distribuições contábeis de cabeçalho**.
5. Retorne à página **Detalhes da ordem**, e selecione uma linha. Nos detalhes de linha de ordem, você também pode explorar distribuições contábeis específicas de linha.

## <a name="complete-an-action-on-the-purchase-order"></a>Conclua uma ação na ordem de compra
Depois de ver a ordem de compra que lhe foi atribuído e ler as instruções de fluxo de trabalho, você deve estar pronto para agir.

1. No seu dispositivo móvel, selecione a área de trabalho **Aprovação de ordem de compra**.
2. Selecione **Ordens atribuída a mim** para exibir todas as ordens de compra para a qual foi solicitado a você tomar uma ação no fluxo de trabalho de aprovação de ordem de compra.
3. Selecione uma ordem, e exiba a página de detalhes.
4. Selecione **Ações** para mostrar as ações disponíveis. As ações disponíveis dependem da tarefa que lhe foi atribuída.

    | Ação de tarefa    | Ação de aprovação  |
    |----------------|------------------|
    | Completo       | Aprovar          |
    | Retornar         | Rejeitar           |
    | Solicitar Alteração | Solicitar Alteração   |
    | Delegado       | Delegado         |

5. Selecione a ação adequada.
6. Na página **Concluir tarefa**, insira um comentário. Observe que se você selecionar a ação **Delegar**, será necessário selecionar um usuário para o qual delegar a tarefa.
7. Selecione **Concluído**. Depois de atualizar sua área de trabalho, a ordem de compra não estará na lista. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]