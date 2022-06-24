---
title: Gerenciamento de faturas para sites de comércio eletrônico B2B
description: Este artigo descreve os recursos de gerenciamento de faturas de sites de comércio eletrônico entre empresas (B2B) do Microsoft Dynamics 365 Commerce.
author: shajain
ms.date: 02/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: fa6b81187481a6b7f47ea02291e5a581052d6c7b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8854917"
---
# <a name="invoice-management-for-b2b-e-commerce-websites"></a>Gerenciamento de faturas para sites de comércio eletrônico B2B

[!include [banner](../../includes/banner.md)]

Este artigo descreve os recursos de gerenciamento de faturas de sites de comércio eletrônico entre empresas (B2B) do Microsoft Dynamics 365 Commerce.

É uma prática comum de empresas que lidam com transações B2B aceitar ordens no crédito de clientes e enviar uma fatura a clientes depois que eles atendem à ordem. As condições de pagamento são definidas para clientes e pode haver descontos para motivar clientes a pagar no prazo ou antes. Para ajudar a aumentar a probabilidade de pagamentos serem recebidos no prazo, os sites de comércio eletrônico B2B permitem que clientes exibam todas as faturas. O cliente pode filtrar facilmente as faturas para exibir faturas pagas, não pagas e parcialmente pagas junto com as datas de conclusão.

![Página Faturas em um site B2B.](../media/ViewInvoices.png)

> [!NOTE]
> Um usuário conectado pode exibir e pagar somente suas próprias faturas. Se uma conta de organização estiver configurada no menu suspenso **Conta de fatura** na FastTab **Fatura e entrega** do registro do cliente no Commerce headquarters, o usuário poderá exibir e pagar faturas para a conta da organização.

Na página **Faturas** de um site B2B, um usuário pode selecionar uma fatura não paga ou parcialmente paga e, depois, selecionar **Pagar fatura**. A fatura selecionada é adicionada ao carrinho e o usuário pode continuar com o pagamento. O usuário pode decidir se deve pagar o valor total ou um valor parcial da fatura. O usuário não pode usar o método de pagamento da conta para pagar faturas.

> [!NOTE]
> As faturas só poderão ser adicionadas ao carrinho se nenhum item estiver nele no momento. Por outro lado, os itens só poderão ser adicionados ao carrinho se não houver faturas nele no momento. A Microsoft pretende remover essa restrição em versões futuras do Commerce.

![Carrinho em um site da B2B.](../media/PayInvoice.png)

Na página **Faturas**, um usuário também pode selecionar **Solicitar fatura** ao lado de uma fatura. Dessa forma, o usuário pode solicitar que os detalhes da fatura sejam enviados para o endereço de email registrado.

![Caixa de diálogo Solicitar fatura.](../media/RequestInvoice2.png)

Depois que um usuário solicita uma fatura, a solicitação é movida para a seção **Solicitações B2B** da página **Minha conta**. Após a execução dos trabalhos **P-0001** e **Sincronizar ordens e solicitações de canal** no Commerce headquarters, o email da fatura é disparado e o status da solicitação B2B é marcado como concluído.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
