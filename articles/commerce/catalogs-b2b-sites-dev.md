---
title: Impacto da extensibilidade de catálogos do Commerce para personalizações B2B
description: Este artigo descreve o impacto da extensibilidade do recurso Catálogos do Commerce para B2B no Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 04/28/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2022-02-28
ms.openlocfilehash: f21d3375db69dd412325d00261bfc18e26d0c257
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8849006"
---
# <a name="extensibility-impact-of-commerce-catalogs-for-b2b-customizations"></a>Impacto da extensibilidade de catálogos do Commerce para personalizações B2B

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Este artigo descreve o impacto da extensibilidade do recurso **Catálogos do Commerce para B2B** no Microsoft Dynamics 365 Commerce.

Se estiver interessado em estender o contexto do catálogo para cenários personalizados, talvez suas personalizações precisem ser atualizadas. Esta atualização segue o processo padrão que os clientes devem seguir, pois suas personalizações podem não oferecer suporte automático aos últimos recursos após a realização de atualizações. Se as suas personalizações incluírem qualquer novo recurso ou correção de bugs nas experiências, recomendamos que você atualize o código de personalização apropriadamente. Esta atualização se assemelha às alterações que a Microsoft pode ter feito no código principal.

Revise os casos de personalização a seguir para determinar se suas personalizações devem ser atualizadas.

> [!NOTE]
> - Todas as interfaces de programação de aplicativos (APIs) de merchandising devem ter reconhecimento de catálogo. Portanto, é fundamental que você transmita o parâmetro **CatalogID**.
> - O catálogo padrão (**CatalogID**=**0**) não é um catálogo válido para usuários B2B (entre empresas) conectados. Portanto, todas as chamadas à API que transmitem "0" ou usam um valor padrão falharão porque os usuários do site não têm acesso ao catálogo 0. Para obter a experiência correta, as chamadas à API do cliente devem ser atualizadas para que transmitam a ID do catálogo selecionada no seletor de catálogo. Se você usar um valor padrão, e o usuário trocar de catálogo, o site deverá fornecer os dados do catálogo selecionado. Portanto, para fazer a correspondência entre as APIs que são executadas a partir do código principal do Commerce, as APIs personalizadas devem transmitir o catálogo selecionado.

Os seguintes casos de personalização exigem atualizações de desenvolvimento:

- **Caso 1:** um cliente introduz sua própria [ação de dados](e-commerce-extensibility/data-actions.md) que chama uma API relacionada a um produto ou uma ação de dados. As seguintes etapas de atualização são necessárias:

    1. Se a ação de dados usar uma chamada à API direta, atualize a ação de dados para que ela transmita a ID do catálogo, conforme mostrado na ilustração de exemplo a seguir.

        ![Ação de dados atualizada que transmite a ID do catálogo.](./media/customization1_a.png)

    1. Se a ação de dados chamar uma ação de dados diferente relacionada a produtos dentro da personalização, o código deverá ser atualizado para que transmita alguns novos parâmetros, como **requestContext**. O parâmetro **requestContext** é usado para recuperar a ID do catálogo atual, conforme mostrado na ilustração de exemplo a seguir.

        ![Ação de dados atualizada que transmite o novo parâmetro.](./media/customization1_b.png)

- **Caso 2:** um cliente tem uma [ação de dados substituída](e-commerce-extensibility/data-action-overrides.md). A seguinte etapa de atualização é necessária:

    - Atualize a ação de dados como no caso 1.

- **Caso 3:** um cliente tem uma extensão de exibição, um módulo de injetor de script ou um [módulo clonado](e-commerce-extensibility/modules-overview.md#clone-a-module-library-module) que inclui chamadas para APIs ou ações de dados. A seguinte etapa de atualização é necessária:

    - Atualize o código como no caso 1, conforme mostrado na ilustração de exemplo a seguir.

       ![Código atualizado que transmite o novo parâmetro.](./media/customization3.png)

- **Caso 4:** um cliente usa uma chamada à API **getById**. A seguinte etapa de atualização é necessária:

    - Alterne para a chamada à API **getByIds**, pois a chamada APT **getById** tem algumas limitações e não é compatível com reconhecimento de catálogo.

- **Caso 5:** um cliente tem uma ação de dados que recupera informações para vários produtos que podem ser de catálogos diferentes. A seguinte etapa de atualização é necessária:

    - Divida as chamadas à API por ID de catálogo. Por exemplo, em APIs de carrinhos, o carrinho pode conter produtos de catálogos diferentes. As linhas de produtos devem ser agrupadas por ID de catálogo e devem chamar a API para cada catálogo separadamente, conforme mostrado na ilustração de exemplo a seguir.

        ![Ação de dados atualizada que agrupa linhas de produtos por ID de catálogo.](./media/customization5.png)

## <a name="additional-resources"></a>Recursos adicionais

[Criar catálogos do Commerce para sites B2B](catalogs-b2b-sites.md)

[Perguntas frequentes sobre Catálogos do Commerce para B2B](catalogs-b2b-sites-FAQ.md)
