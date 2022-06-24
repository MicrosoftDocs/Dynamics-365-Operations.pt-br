---
title: Comprar e vender licenças
description: Este artigo descreve como enviar solicitações para comprar e vender licenças no Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ESSLeaveBuyRequestEntry, EssWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a6d38a69a73ce14f099beb6b6b560bf6c5686b0c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875703"
---
# <a name="buy-and-sell-leave"></a>Comprar e vender licenças


>[!Important]
>A funcionalidade mencionada neste artigo está disponível atualmente para clientes individuais de Dynamics 365 Human Resources. Algumas ou todas as funcionalidades estarão disponíveis como parte de uma versão futura na infraestrutura do Finance após a versão Finance 10.0.26.

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

Se um fluxo de trabalho de solicitação de licença de compra ou venda falhar, os usuários com o privilégio **EssLeaveBuySellRequestApprover** podem analisar o registro de mensagens para todas as solicitações de compra e venda de licenças. Para isso, acesse **Licença e ausência > Vínculos > Comprar e vender pedidos de licença > Registro de mensagens** (no canto superior esquerdo). O **Registro de mensagens** mostra aos usuários como as transações foram processadas e o histórico de fluxo de trabalho associado.


## <a name="see-also"></a>Consulte também

[Visão geral de licença e ausência](hr-leave-and-absence-overview.md)</br>
[Gerenciar políticas de compra e venda de licenças](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
