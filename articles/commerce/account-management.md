---
title: Páginas e módulos de gerenciamento de contas
description: Este artigo aborda páginas e módulos de gerenciamento de contas no Microsoft Dynamics 365 Commerce.
author: v-chgri
ms.date: 03/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: 2db9a1218802234297e9d027691e5887d6a5c808
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274446"
---
# <a name="account-management-pages-and-modules"></a>Páginas e módulos de gerenciamento de contas

[!include [banner](includes/banner.md)]

Este artigo aborda páginas e módulos de gerenciamento de contas no Microsoft Dynamics 365 Commerce.

O gerenciamento de contas refere-se a um grupo de páginas que é usado para gerenciar informações relacionadas à conta do usuário no Dynamics 365 Commerce. As páginas de gerenciamento de contas incluem a página de aterrissagem do gerenciamento de contas, a página de perfil do usuário, a página de endereço do usuário, a página do histórico de ordens, a página de detalhes de ordens, a página de fidelidade e a página da lista de desejos.

### <a name="account-management-landing-page"></a>Página de aterrissagem de gerenciamento de contas

A página de aterrissagem do gerenciamento de contas usa os seguintes módulos:

- **Contêiner** - Todos os módulos de página de aterrissagem de gerenciamento de contas devem ser colocados em um contêiner. 
- **Bloco de boas-vindas da conta** – Este módulo é usado para fornecer uma mensagem de boas-vindas na página de gerenciamento de contas. Ele inclui propriedades para o título.
- **Bloco genérico de conta** - Este módulo pode ser usado para fornecer títulos e links às páginas de gerenciamento de contas, como as páginas "Histórico de pedidos" ou "Meu perfil". O módulo de bloco genérico pode ser usado para configurar um bloco para qualquer página. Na Fabrikam, esse módulo é usado para links a página Histórico de pedidos" e "Meu perfil" na página de aterrissagem do gerenciamento de conta.
- **Bloco da lista de desejos da conta** – Este módulo é usado para fornecer um resumo dos itens na lista de desejos do cliente. Por exemplo, pode indicar: "Você tem 10 itens na sua lista de desejos". Inclui propriedades para o título e o link "Exibir detalhes". O link "Exibir detalhes" deve ser configurado para redirecionamento à página da lista de desejos. 
- **Bloco de endereços da conta** – Este módulo é usado para fornecer um resumo dos endereços do usuário. Por exemplo, pode indicar: "Você tem 2 endereços adicionados à sua conta". Inclui propriedades para o título e o link "Exibir detalhes". O link "Exibir detalhes" deve ser configurado para redirecionamento à página de endereços do usuário.
- **Bloco de fidelidade da conta** – Este módulo é usado para exibir e vincular às informações do programa de fidelidade. Este bloco tem dois estados: um estado mostra links para ingressar em um programa de fidelidade, se o usuário ainda não for um membro. O outro estado mostra links para exibir a página de detalhes do programa de fidelidade quando o usuário já for membro. As propriedades incluem o título, o link "Inscrição" e o link "Exibir fidelidade". O link "Exibir fidelidade" deve ser configurado para redirecionamento à página do programa de fidelidade. O link "Inscrição" deve ser configurado para redirecionamento a uma página onde os usuários podem ingressar no programa de fidelidade. 

### <a name="order-history-page"></a>Página de histórico de ordens

A página de histórico de ordens usa o módulo de histórico de ordens para mostrar todas as ordens recentes que o usuário fez.

### <a name="order-details-page"></a>Página detalhes da ordem

A página de detalhes da ordem fornece informações detalhadas para cada ordem e é acessada na página de histórico de ordens. Ela usa o módulo de detalhes da ordem, que requer a ID da venda ou da transação para recuperar os detalhes da ordem.

### <a name="my-profile-page"></a>Minha Página de Perfil

A página Meu perfil mostra os detalhes do perfil de conta do usuário usando o módulo perfil de conta. A página mostra o endereço de email associado à conta do usuário, bem como as preferências configuradas para a conta. Se você estiver configurando atributos personalizados do cliente, uma seção "Informações Adicionais" também exibirá esses atributos. Os usuários podem editar seu nome, suas preferências ou informações adicionais (se disponíveis).

### <a name="user-address-page"></a>Página de endereço do usuário

A página de endereço do usuário mostra a lista de endereços associados à conta do usuário. O usuário forneceu esses endereços durante a finalização da compra ou os adicionou diretamente nesta página. O módulo de endereço do usuário é usado para adicionar e editar endereços, definir o endereço principal e renderizar endereços existentes na página.

### <a name="wish-list-page"></a>Página da lista de desejos

A página da lista de desejos mostra os itens que foram adicionados à lista de desejos do cliente. Ele usa o módulo da lista de desejos para renderizar itens da lista de desejos.

### <a name="loyalty-page"></a>Página de fidelidade

A página do programa de fidelidade permite que os clientes vejam os detalhes de sua participação se já forem membros do programa de fidelidade. Eles também podem ver os pontos que ganharam e resgataram em transações recentes. A página usa o módulo de detalhes da fidelidade para apresentar os detalhes da fidelidade. 

Para ingressar no programa de fidelidade, uma página de marketing pode ser criada com módulos de condições de inscrição e fidelidade. Se o usuário não for membro de um programa de fidelidade, esses módulos permitirão que o usuário se inscreva.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Módulo de contêiner](add-container-module.md)

[Módulo de caixa de compra](add-buy-box.md)

[Módulo de carrinho](add-cart-module.md)

[Módulo de finalização da compra](add-checkout-module.md)

[Módulo de confirmação da ordem](order-confirmation-module.md)

[Módulo de cabeçalho](author-header-module.md)

[Módulo de rodapé](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
