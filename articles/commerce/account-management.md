---
title: Páginas e módulos de gerenciamento de contas
description: Este tópico aborda páginas e módulos de gerenciamento de contas no Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 3986505a7e0e8d33d5b8ff2c06f493335731a8d9
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785367"
---
# <a name="account-management-pages-and-modules"></a>Páginas e módulos de gerenciamento de contas

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tópico aborda páginas e módulos de gerenciamento de contas no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

O gerenciamento de contas refere-se a um grupo de páginas que é usado para gerenciar informações relacionadas à conta do usuário no Dynamics 365 Commerce. As páginas de gerenciamento de contas incluem a página de aterrissagem do gerenciamento de contas, a página de perfil do usuário, a página de endereço do usuário, a página do histórico de ordens, a página de detalhes de ordens, a página de fidelidade e a página da lista de desejos.

### <a name="account-management-landing-page"></a>Página de aterrissagem de gerenciamento de contas

A página de aterrissagem do gerenciamento de contas usa os seguintes módulos:

- **Posicionamento de conteúdo** – Este módulo é um módulo de contêiner que contém todos os módulos na página de aterrissagem de gerenciamento de contas.
- **Item de boas-vindas da conta** – Este módulo é usado para fornecer uma mensagem de boas-vindas na página de gerenciamento de contas. Inclui propriedades para o cabeçalho e o tamanho do bloco. A propriedade **Tamanho do bloco** define a largura do módulo no módulo de posicionamento de conteúdo. Os valores variam de **1** a **12**, em que **12** representa a largura total do contêiner de posicionamento de conteúdo.
- **Item de colocação de ordens da conta** – Este módulo é usado para fornecer um resumo do número de ordens que foram realizadas pela conta do usuário. Inclui propriedades para o cabeçalho, o tamanho do bloco e o link "exibir detalhes". O link "exibir detalhes" deve ser configurado para redirecionamento à página do histórico de ordens.
- **Item de colocação do perfil da conta** – Este módulo é usado para fornecer um resumo do perfil do usuário. Inclui propriedades para o cabeçalho, o tamanho do bloco e o link "exibir detalhes". O link "exibir detalhes" deve ser configurado para redirecionamento à página do perfil do usuário.
- **Item da lista de desejos da conta** – Este módulo é usado para fornecer um resumo dos itens na lista de desejos do cliente. Por exemplo, pode indicar: "Você tem 10 itens na sua lista de desejos". Inclui propriedades para o cabeçalho, o tamanho do bloco e o link "exibir detalhes". O link "exibir detalhes" deve ser configurado para redirecionamento à página da lista de desejos.
- **Item de endereço da conta** – Este módulo é usado para fornecer um resumo dos endereços do usuário. Por exemplo, pode indicar: "Você tem 2 endereços adicionados à sua conta". Inclui propriedades para o cabeçalho, o tamanho do bloco e o link "exibir detalhes". O link "exibir detalhes" deve ser configurado para redirecionamento à página do endereço do usuário.
- **Item de fidelidade da conta** – Este módulo é usado para mostrar e vincular às informações do programa de fidelidade. Inclui propriedades para o cabeçalho, o tamanho do bloco, o link "exibir detalhes" e o link "tornar-se membro". O link "exibir detalhes" deve ser configurado para redirecionamento à página de fidelidade. O link "tornar-se membro" deve ser configurado para redirecionamento a uma página onde os usuários podem participar do programa de fidelidade.

### <a name="order-history-page"></a>Página de histórico de ordens

A página de histórico de ordens usa o módulo de histórico de ordens para mostrar todas as ordens recentes que o usuário fez.

### <a name="order-details-page"></a>Página detalhes da ordem

A página de detalhes da ordem fornece informações detalhadas para cada ordem e é acessada na página de histórico de ordens. Ela usa o módulo de detalhes da ordem, que requer a ID da venda ou da transação para recuperar os detalhes da ordem.

### <a name="user-profile-page"></a>Página de perfil do usuário

A página de perfil do usuário mostra detalhes da conta do usuário, como nome e endereço de email do usuário. Ela usa o módulo de perfil de usuário. Embora o endereço de email não possa ser removido, ele pode ser editado.

### <a name="user-address-page"></a>Página de endereço do usuário

A página de endereço do usuário mostra a lista de endereços associados à conta do usuário. O usuário forneceu esses endereços durante a finalização da compra ou os adicionou diretamente nesta página. O módulo de endereço do usuário é usado para adicionar e editar endereços, definir o endereço principal e renderizar endereços existentes na página.

### <a name="wish-list-page"></a>Página da lista de desejos

A página da lista de desejos mostra os itens que foram adicionados à lista de desejos do cliente. Ele usa o módulo da lista de desejos para renderizar itens da lista de desejos.

### <a name="loyalty-page"></a>Página de fidelidade

A página de fidelidade permite que os clientes participem de um programa de fidelidade ou, se já são membros do programa de fidelidade, visualizem os detalhes do programa. Eles também podem ver os pontos que ganharam e resgataram em transações recentes.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do kit de início](starter-kit-overview.md)

[Módulo de contêiner](add-container-module.md)

[Módulo de caixa de compra](add-buy-box.md)

[Módulo de carrinho](add-cart-module.md)

[Módulo de finalização da compra](add-checkout-module.md)

[Módulo de confirmação da ordem](order-confirmation-module.md)

[Módulo de cabeçalho](author-header-module.md)

[Módulo de rodapé](author-footer-module.md)
