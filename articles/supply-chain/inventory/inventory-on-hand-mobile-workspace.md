---
title: Espaço de trabalho móvel de estoque disponível
description: Este tópico fornece informações sobre a área de trabalho móvel de estoque disponível. Este espaço de trabalho o ajuda a obter informações móveis para estoque reservado e disponível a qualquer hora e em qualquer lugar.
author: Mirzaab
manager: tfehr
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 267094
ms.assetid: 3fa385ba-894d-4a9e-b394-ef3697abf895
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 4a41f877816e331351a0950dcdc07ee07f643beb
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4421940"
---
# <a name="inventory-on-hand-mobile-workspace"></a>Espaço de trabalho móvel de estoque disponível

[!include [banner](../includes/banner.md)]

Este tópico fornece informações sobre a área de trabalho móvel de **Estoque disponível**. Este espaço de trabalho ajuda você a obter informações sobre estoque reservado e disponível a qualquer hora e em qualquer lugar.

Esse espaço de trabalho móvel deve ser usado com o aplicativo móvel Finance and Operations.

## <a name="overview"></a>Visão Geral
Geralmente, as empresas têm várias remessas e vários recebimentos de estoque a cada dia. Esses movimentos alteram constantemente o status disponível do estoque. O espaço de trabalho móvel de **Estoque disponível** permite ver o status de estoque disponível entre empresas, para que você possa obter as informações mais recentes sobre dados de estoque no dispositivo móvel de sua escolha. Independentemente de trabalhar no depósito, em compras, em vendas, na fabricação ou no gerenciamento ou ter outras funções, você pode acessar os dados de estoque disponível a qualquer momento e em qualquer lugar. 

O espaço de trabalho móvel fornece uma exibição instantânea do status disponível através de recursos. Isso permite exibir o estoque disponível pelas instalações, reservas de material atual e estoque disponível não reservado. Também é possível inserir números de item para consultar o estoque disponível e executar uma pesquisa filtrada de produtos ou variantes disponíveis. 

Especificamente, espaço de trabalho móvel fornece esses recursos:

-   Você pode pesquisar por número ou o nome de produto para encontrar produtos para exibir o status disponível do estoque.
-   Para produtos selecionados, é possível exibir as seguintes informações:

    -   Estoque disponível por site
    -   Estoque disponível por depósito
    -   Estoque disponível por local
    -   Estoque disponível por lote (para produtos controlados por lote)
    -   Estoque disponível por status de estoque
    
-   O estoque disponível do produto é mostrado das seguintes maneiras:

    -   Por estoque físico (esta exibição representa o valor total.)
    -   Por reserva física (esta exibição representa o valor reservado.)
    -   Por físico disponível (Esta exibição representa o valor disponível que não tem reservas).

## <a name="prerequisites"></a>Pré-requisitos
Os pré-requisitos diferem com base na versão do Supply Chain Management que foi implantada para sua organização.

### <a name="prerequisites-if-you-use-supply-chain-management"></a>Pré-requisito para usar o Supply Chain Management
Se o Supply Chain Management tiver sido implantado para sua organização, o administrador do sistema deverá publicar o espaço de trabalho móvel **Estoque disponível**. Para obter instruções, consulte [Publicar um espaço de trabalho móvel](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-platform-update-3-or-later"></a>Pré-requisitos se você usa a Platform update 3 ou posterior 
Se a Platform update 3 ou posterior tiver sido implantada para sua organização, o administrador do sistema deverá atender aos pré-requisitos a seguir. 

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

<td>o KB 4013633 é um hotfix de metadados ou uma atualização X++ que contém o espaço de trabalho móvel de <strong>Estoque disponível</strong>. Para implementar o KB 4013633, o administrador do sistema deve seguir estas etapas.
<ol>
<li><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Baixe o hotfix de metadados do Microsoft Dynamics Lifecycle Services (LCS)</a>.</li>
<li><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Instalar o hotfix de metadados</a>.</li>
<li><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Criar um pacote implantável</a> que contenha o modelo <strong>SCMMobile</strong> e, em seguida, carregar o pacote implantável para o LCS.</li>
<li><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Aplicar o pacote implantável</a>.</li>

</ol></td>
</tr>
<tr class="even">
<td>Publicar o <strong>Espaço de trabalho móvel de estoque disponível</strong>.</td>
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
4.  Depois de entrar, serão exibidos os espaços de trabalho disponíveis da sua empresa. Observe que se o seu administrador de sistema publica um novo espaço de de trabalho depois, você terá que atualizar a lista dos espaços de trabalho móveis.

    [![Efetue pull para atualizar](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="view-the-on-hand-inventory-for-a-product-by-using-the-inventory-on-hand-mobile-workspace"></a>Exiba o estoque disponível para um produto usando o espaço de trabalho móvel de estoque disponível

1.  No seu dispositivo móvel, selecione o espaço de trabalho de **Estoque disponível**.

2.  Selecione **Verificar estoque disponível de um item**. Você verá uma lista de produtos que estão carregados para seu aplicativo para uso offline. Por padrão, 50 itens são carregados, mas um desenvolvedor pode alterar esse número. Para obter mais informações, os desenvolvedores devem acessar a [Plataforma móvel](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).
3.  Se o item não estiver na lista, selecione **Pesquisar mais**. Pesquise por número de produto ou alterne para uma pesquisa por nome de produto.

4.  Selecione um produto. Se o item tiver uma imagem, ela será mostrada.
5.  Selecione uma das seguintes opções para exibir o status do estoque disponível:

    -   Exibir estoque por site
    -   Exibir estoque disponível por depósito
    -   Exibir estoque disponível por local
    -   Exibir estoque disponível por lote (para produtos controlados por lote)
    -   Exibir estoque disponível por status do estoque

    O estoque disponível do produto é mostrado das seguintes maneiras:
    -   Por estoque físico (esta exibição representa o valor total.)
    -   Por reserva física (esta exibição representa o valor reservado.)
    -   Por físico disponível (Esta exibição representa o valor disponível que não tem reservas).
