---
title: Módulo de pesquisa de ordem
description: Este tópico abrange o módulo de pesquisa de ordem e explica como configurá-lo no Microsoft Dynamics 365 Commerce.
author: stuharg
ms.date: 09/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2021-08-15
ms.dyn365.ops.version: Release 10.0.22
ms.openlocfilehash: 0ae5c8a2eea84a9aa707f7c2f6f29950f2f48faa
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/23/2021
ms.locfileid: "7675108"
---
# <a name="order-lookup-module"></a>Módulo de pesquisa de ordem

[!include [banner](includes/banner.md)]

Este tópico abrange o módulo de pesquisa de ordem e explica como configurá-lo no Microsoft Dynamics 365 Commerce.

O módulo de pesquisa de ordem fornece um formulário que os clientes podem usar para pesquisar ordens colocadas em um site de comércio eletrônico. Ele é usado como parte do recurso [Habilitar pesquisa de ordem para finalização de compra do convidado](order-lookup-guest.md). O módulo de pesquisa de ordem pode ser usado para procurar ordens que foram enviadas por meio de um site de comércio eletrônico, do ponto de venda do varejo (PDV) ou de um call center. O formulário pode recuperar ordens que foram enviadas por usuários convidados e por usuários registrados.

A ilustração a seguir mostra um exemplo do formulário processado pelo módulo de pesquisa de ordem. Quando os clientes preenchem o formulário e selecionam **Localizar sua ordem**, eles serão redirecionados para a página de detalhes da ordem.

![Formulário para o módulo de pesquisa de ordem em uma página.](./media/OrderLookup_module.PNG)

## <a name="order-lookup-module-properties"></a>Propriedades do módulo de pesquisa de ordem

| Nome da propriedade     | Alíquota     | descrição |
|-------------------|-----------|-------------|
| Título           | Texto      | O título que é exibido na parte superior do formulário (por exemplo, "Localizar seu pedido"). |
| Rich text         | Rich text | Texto explicativo opcional que é exibido abaixo do título. |
| Tipo de status da ordem | Enum.      | <p>Selecione o tipo de informação que o formulário solicitará do cliente, além da ID de confirmação da ordem. Há suporte para os seguintes valores atualmente:</p><ul><li><b>Email</b> – O formulário incluirá um campo no qual os clientes podem inserir o endereço de email usado quando fizeram a ordem.</li><li><b>Nenhum</b> – O formulário não solicitará informações além da ID de confirmação da ordem.</li></ul> |

## <a name="add-an-order-lookup-module-to-a-page"></a>Adicionar um módulo de pesquisa de ordem a uma página

O módulo de pesquisa de ordem pode ser adicionado ao corpo de qualquer página do site de comércio eletrônico. Se desejar usar o módulo de pesquisa de ordem para habilitar a pesquisa de ordem para finalização de compra do convidado, adicione-o a uma página que não exija que o usuário esteja conectado. Para localizar uma definição **Requer entrada?** no modo de exibição de árvore do site do Commerce, selecione o slot **Página padrão (obrigatório)** e veja a parte inferior do painel à direita.

## <a name="additional-resources"></a>Recursos adicionais

[Habilitar pesquisa de ordem para finalização de compra do convidado](order-lookup-guest.md)

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
