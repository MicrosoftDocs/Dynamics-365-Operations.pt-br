---
title: Comprar e vender licenças
description: No Dynamics 365 Human Resources, você pode enviar solicitações para comprar e vender licenças com base nas políticas de licença de compra e venda configuradas por sua empresa.
author: andreabichsel
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ESSLeaveBuyRequestEntry, EssWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1225bcfd0c7c9dfecde2aec54983fca8a298f1cf92d2929d8b1fbe2bdf05e5f9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6779725"
---
# <a name="buy-and-sell-leave"></a>Comprar e vender licenças

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

No Dynamics 365 Human Resources, você pode enviar solicitações para comprar e vender licenças com base nas políticas de licença de compra e venda configuradas por sua empresa.  

## <a name="request-to-buy-leave"></a>Solicitação para comprar licenças

1. No espaço de trabalho **Autoatendimento para funcionários**, selecione **Solicitação para comprar licenças** no grupo **Saldos de folgas**. 

2. Adicione um **tipo de licença** e insira um **Valor** para a quantidade de licenças que deseja comprar. 

3. Selecione **Enviar** quando estiver pronto para enviar sua solicitação. 

Os saldos serão atualizados automaticamente ou passarão por um processo de aprovação antes da atualização. Isso depende de como a política de compras foi configurada.

## <a name="request-to-sell-leave"></a>Solicitação de venda de licença

1. No espaço de trabalho **Autoatendimento para funcionários**, selecione **Solicitação de venda de licença** no bloco **Saldos de folgas**. 

2. Adicione um **Tipo de licença** e insira um **Valor** para a quantidade de licenças que deseja vender. 

3. Selecione **Enviar** quando estiver pronto para enviar sua solicitação.

Os saldos serão atualizados automaticamente ou passarão por um processo de aprovação antes da atualização. Isso depende de como a política de compras foi configurada.


## <a name="troubleshooting"></a>Solução de problemas 

Se um fluxo de trabalho de solicitação de licença de compra ou venda falhar, os usuários com o privilégio **EssLeaveBuySellRequestApprover** podem analisar o registro de mensagens para todas as solicitações de compra e venda de licenças. Para isso, Acesse **Licença e ausência > Vincular > Comprar e vender pedidos de licença > Registro de mensagens** (no canto superior esquerdo). O **Registro de mensagens** mostra aos usuários como as transações foram processadas e o histórico de fluxo de trabalho associado.


## <a name="see-also"></a>Consulte também

[Visão geral de licença e ausência](hr-leave-and-absence-overview.md)</br>
[Gerenciar políticas de compra e venda de licenças](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
