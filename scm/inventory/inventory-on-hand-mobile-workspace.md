---
title: "Espaço de trabalho móvel disponível em estoque"
description: "Este tópico fornece informações sobre o espaço de trabalho móvel disponível em estoque, que está disponível para o aplicativo móvel Microsoft Dynamics 365 for Operations. Este espaço de trabalho o ajuda a obter informações móveis para estoque reservado e disponível a qualquer hora e em qualquer lugar."
author: YuyuScheller
manager: AnnBe
ms.date: 05/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: Operations, Core
ms.custom: 267094
ms.assetid: 3fa385ba-894d-4a9e-b394-ef3697abf895
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 7387df37e047d5ab7a90b696a6ffa249094499c4
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="inventory-on-hand-mobile-workspace"></a>Espaço de trabalho móvel disponível em estoque

[!include[banner](../includes/banner.md)]


Este tópico fornece informações sobre o espaço de trabalho móvel disponível em estoque, que está disponível para o aplicativo móvel Microsoft Dynamics 365 for Operations. Este espaço de trabalho o ajuda a obter informações móveis para estoque reservado e disponível a qualquer hora e em qualquer lugar.

<a name="overview-of-the-inventory-on-hand-mobile-workspace"></a>Visão geral do espaço de trabalho móvel disponível em estoque
--------------------------------------------------

Geralmente, as empresas têm várias remessas e vários recebimentos de estoque a cada dia. Esses movimentos alteram constantemente o status disponível do estoque. O espaço de trabalho móvel **disponível em estoque** permite ver o status de estoque disponível entre empresas, para que você possa obter as informações mais recentes sobre dados de estoque no dispositivo móvel de sua escolha. Independentemente de trabalhar no depósito, em compras, em vendas, na fabricação ou no gerenciamento ou ter outras funções, você pode acessar os dados de estoque disponível a qualquer momento e em qualquer lugar. 

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
Antes de usar o espaço de trabalho móvel **disponível em estoque**, certifique-se de que o administrador do sistema tem os seguintes pré-requisitos funcionando.

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
<td>Deve ser implementada a versão 1611 com atualização 3 ou superior de plataforma do Microsoft Dynamics 365.</td>
<td>Administrador do sistema</td>
<td>Se ainda não tiver o Dynamics 365 for Operations implantado em sua organização, o administrador do sistema deverá ver <a href="/dynamics365/operations/dev-itpro/deployment/deploy-demo-environment">Implantar o ambiente de demonstração do Microsoft Dynamics 365 for Operations</a>.</td>
</tr>
<tr class="even">
<td>O KB 4013633 deve ser implementado.</td>
<td>Administrador do sistema</td>
<td>O 4013633 KB (um hotfix de atualização ou de metadados X++) contém quatro espaços de trabalho móveis para gerenciamento da cadeia de suprimentos. Para implementar o KB 4013633, o administrador do sistema deve seguir estas etapas:
<ol>
<li>Baixar o KB 4013633 do Microsoft Dynamics Lifecycle Services (LCS).</li>
<li><a href="/dynamics365/operations/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Instalar o hotfix de metadados</a>.</li>
<li><a href="/dynamics365/operations/dev-itpro/deployment/create-apply-deployable-package">Criar um pacote implantável</a> que contenha o modelo <strong>SCMMobile</strong> e, em seguida, carregar o pacote implantável para o LCS.</li>
<li><a href="/dynamics365/operations/dev-itpro/deployment/apply-deployable-package-system">Aplique o pacote implantável</a> ao seu sistema Dynamics 365 for Operations.</li>
</ol></td>
</tr>
<tr class="odd">
<td>O espaço de trabalho <strong>disponível em estoque</strong> deve ser publicado no aplicativo móvel Dynamics 365 for Operations.</td>
<td>Administrador do sistema</td>
<td><ol>
<li>Inicie o Dynamics 365 for Operations em seu navegador.</li>
<li>Na página <strong>Parâmetros do sistema</strong>, selecione <strong>Gerenciar espaços de trabalho móveis</strong>.</li>
<li>Selecione o espaço de trabalho <strong>estoque disponível</strong>.</li>
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

## <a name="view-the-onhand-inventory-for-a-product-by-using-the-inventory-onhand-mobile-workspace"></a>Exiba o estoque disponível para um produto usando o espaço de trabalho móvel disponível em estoque
1.  No seu dispositivo móvel, selecione o espaço de trabalho **Disponível em estoque**.
2.  Selecione **Verificar estoque disponível de um item**. Você verá uma lista de produtos que estão carregados para seu aplicativo para uso offline. Por padrão, 50 itens são carregados, mas um desenvolvedor pode alterar esse número. Para obter mais informações, os desenvolvedores devem ver [plataforma móvel do Dynamics 365 for Operations](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform).
3.  Se o item não estiver na lista, selecione **Pesquisar mais** para fazer uma pesquisa online no Dynamics 365 for Operations. Pesquise por número de produto ou alterne para uma pesquisa por nome de produto.
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






