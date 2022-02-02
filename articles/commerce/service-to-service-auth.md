---
title: Configurar autenticação de serviço a serviço
description: Este tópico descreve como configurar a autenticação de serviço a serviço no Microsoft Dynamics 365 Commerce para chamar de forma segura APIs de serviço para classificações e opiniões.
author: gvrmohanreddy
ms.date: 01/12/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: da780de5f15d72bdac85a261eae809125c830260
ms.sourcegitcommit: 7adf9ad53b4e6d1c4d5d612ce0977b76c61ec173
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2022
ms.locfileid: "7968506"
---
# <a name="configure-service-to-service-authentication"></a>Configurar autenticação de serviço a serviço

[!include [banner](includes/banner.md)]

Este tópico descreve como configurar a autenticação de serviço a serviço (S2S) no Microsoft Dynamics 365 Commerce para chamar de forma segura interfaces de programação de aplicativos (APIs) de serviço para classificações e opiniões.

Ofertas do Dynamics 365 Commerce [classificações e opiniões](ratings-reviews-overview.md) como uma solução omni-channel. Essa solução permite acessar APIs de serviço de fora do Commerce. Assim, várias tarefas possam ser executadas. Essas tarefas incluem a importação de classificações e opiniões do sistema externo para o Commerce e a exportação de classificações e opiniões do Commerce. Para habilitar o Commerce para chamar de forma segura APIs de serviço de classificações e opiniões, primeiro configure a autenticação S2S concluindo os procedimentos deste tópico.

## <a name="add-a-new-app-registration"></a>Adicionar um novo registro do aplicativo

Antes de adicionar um novo registro do aplicativo, crie um aplicativo usando o [portal do Azure](https://portal.azure.com). Para registrar um aplicativo no Azure Active Directory (Azure AD) e habilitar a autenticação, siga as etapas em [Usar o Azure Active Directory com um conector personalizado no Power Automate](/connectors/custom-connectors/azure-active-directory-authentication).

Colete os seguintes IDs do portal do Azure. Esses IDs serão necessários nas etapas a seguir.

- ID da solicitação de emprego do cliente
- ID (locatário) do diretório cliente

Para adicionar um novo registro do aplicativo no criador de sites do Commerce, siga estas etapas:

1. Acesse **Início \> Opiniões \> Configurações**.
1. Em **Autenticação de serviço a serviço (S2S)**, selecione **Gerenciar**.

    ![Botão Gerenciar na seção Autenticação de serviço a serviço (S2S) no criador de sites do Commerce.](media/Ratings-reviews-settings-service-to-service-authentication.png)

1. No painel **Entradas de aplicativo S2S** que aparece à direita, selecione **Adicionar um novo registro de aplicativo S2S**.
1. Na caixa de diálogo **Adicionar entrada de aplicativo S2S**, insira as informações obrigatórias a seguir. Use os valores do registro de aplicativo do Azure.

    - **Nome**: insira o nome do seu aplicativo (por exemplo, **Fabrikam App**).
    - **ID do aplicativo cliente**: insira o ID do aplicativo (por exemplo, **00000000-0000-0000-0000-000000000000**).
    - **ID (Locatário) do diretório**: insira o ID do diretório (por exemplo, **00000000-0000-0000-0000-000000000000**).

    ![Caixa de diálogo Adicionar entrada de aplicativo S2S no criador de sites do Commerce.](media/Ratings-reviews-settings-S2S-APP-entry.png)

1. Selecione **Enviar**. O nome do aplicativo deve aparecer na lista, no painel **Entradas de aplicativo S2S**.
1. Feche o painel **Entradas de aplicativo S2S**.
1. Selecione **Salvar**.

## <a name="edit-an-existing-app-registration"></a>Editar um registro de aplicativo existente

Para editar um registro de aplicativo existente no criador de sites do Commerce, siga estas etapas:

1. Acesse **Início \> Opiniões \> Configurações**.
1. Em **Autenticação de serviço a serviço (S2S)**, selecione **Gerenciar**.
1. No painel **Entradas de aplicativo S2S**, selecione o símbolo de lápis ao lado da entrada que você deseja editar.
1. Atualize os valores nos campos **Nome**, **ID do aplicativo cliente** e **ID (Locatário) do diretório**, conforme necessário.
1. Selecione **Enviar**.
1. Feche o painel **Entradas de aplicativo S2S**.
1. Selecione **Salvar**.

## <a name="remove-an-existing-app-registration"></a>Remover um registro de aplicativo existente

Para remover um registro de aplicativo existente no criador de sites do Commerce, siga estas etapas:

1. Acesse **Início \> Opiniões \> Configurações**.
1. Em **Autenticação de serviço a serviço (S2S)**, selecione **Gerenciar**.
1. No painel **Entradas de aplicativo S2S**, selecione o símbolo de lixeira ao lado da entrada que você deseja remover. A entrada é removida da lista.
1. Feche o painel **Entradas de aplicativo S2S**.
1. Selecione **Salvar**.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de classificações e opiniões](ratings-reviews-overview.md)

[Aceitar o uso das classificações e opiniões](opt-in-ratings-reviews.md)

[Gerenciar classificações e opiniões](manage-reviews.md)

[Configurar classificações e opiniões](configure-ratings-reviews.md)

[Sincronizar classificações de produto](sync-product-ratings.md)

[Habilitar a publicação manual de classificações e opiniões por um moderador](manual-publish-rating-reviews.md)

[Importar e exportar avaliações e revisões](import-export-reviews.md)

[Perguntas frequentes sobre classificações e opiniões](ratings-reviews-faq.md) 
