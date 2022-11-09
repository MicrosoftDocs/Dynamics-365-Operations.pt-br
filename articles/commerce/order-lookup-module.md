---
title: Módulo de pesquisa de ordem
description: Este artigo abrange o módulo de pesquisa de ordem e explica como configurá-lo no Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 09/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2021-08-15
ms.dyn365.ops.version: Release 10.0.22
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: a891de4a1da6641a02b8316d16ac2e9a8180fac1
ms.sourcegitcommit: e25fe4228add88dd37f4f38ece86979e1c621f6a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2022
ms.locfileid: "9734234"
---
# <a name="order-lookup-module"></a>Módulo de pesquisa de ordem

[!include [banner](includes/banner.md)]

Este artigo abrange o módulo de pesquisa de ordem e explica como configurá-lo no Microsoft Dynamics 365 Commerce.

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


> [!NOTE]
> Para habilitar o recurso de pesquisa de ordens, verifique se a chave **Cotações** está habilitada em **Configuração da licença** > **Chaves de configuração**.
>
> ![A configuração da chave de licença de cotações deve estar ativada](./media/Quotations_License_Key_Configuration.png)

## <a name="additional-resources"></a>Recursos adicionais

[Habilitar pesquisa de ordem para finalização de compra do convidado](order-lookup-guest.md)

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
