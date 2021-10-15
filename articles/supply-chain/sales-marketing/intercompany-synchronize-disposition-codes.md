---
title: Sincronizar códigos de disposição
description: Este tópico explica a sincronização de códigos de disposição para comércio intercompanhia
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 04a25324e79a1f9cb30a7da19d648bda995ba7b2
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548095"
---
# <a name="synchronize-intercompany-disposition-codes"></a>Sincronizar códigos de disposição intercompanhia

[!include [banner](../../includes/banner.md)]

Para dar suporte a devoluções intercompanhia, o Microsoft Dynamics 365 Supply Chain Management possibilita que você mapeie códigos de disposição definidos externamente para os códigos de disposição internos correspondentes. Quando uma cadeia intercompanhia estiver sendo configurada, as ações de disposição nas duas empresas que são mapeadas entre si deverão ser iguais. Se forem diferentes, o processo de sincronização não terá êxito.

## <a name="about-disposition-codes-for-three-legged-direct-returns"></a>Sobre códigos de disposição de devolução direta de 3 pernas

Os códigos de disposição são sincronizados entre a linha da ordem de venda intercompanhia e a linha da ordem de venda original. No entanto, a sincronização só terá um efeito imediato na linha da ordem de venda original. Esse efeito é que as linhas de encargos diversos são excluídas com base no código de disposição e encargos diversos que são configurados na Empresa A. A Empresa A é a empresa que está criando a ordem de devolução.

Em uma cadeia de entrega direta de 3 pernas, todas as ações de disposição têm suporte na linha da ordem de venda intercompanhia. No entanto, se um produto estiver sendo devolvido para o cliente, você deverá confirmar que o endereço de entrega na ordem de devolução corresponde ao endereço de entrega do cliente especificado na ordem original.

> [!NOTE]
> Não há códigos de disposição para ordens de compra. Portanto, a sincronização dos códigos de disposição da ordem de venda intercompanhia com a ordem de devolução original deve ser executada de ordem de venda para ordem de venda.

## <a name="replacing-returned-items"></a>Substituição de itens devolvidos

Se um item devolvido for substituído e uma ordem de substituição já tiver sido criada na Empresa B, não será possível selecionar um código de disposição e nenhuma ordem de substituição adicional será criada na Empresa A.

## <a name="rules-for-intercompany-direct-deliveries"></a>Regras para entregas diretas intercompanhia

As seguintes regras gerais se aplicam a ordens de devolução originais em cenários que envolvem entregas diretas intercompanhia:

- Se a ação de disposição subjacente na linha da ordem de venda original for Crédito e Sucata, Crédito ou Devolver ao Cliente, a ação de disposição de Crédito será aplicada. Porém, o código de ação Devolver ao Cliente definirá o valor líquido como 0 (zero) na linha existente e na linha recém-sincronizada da ordem de venda intercompanhia. Além disso, as linhas de sucata nunca são sincronizadas. Quando uma linha é adicionada a uma ordem de venda intercompanhia, ela nunca é sincronizada para uma ordem de venda que tem uma quantidade positiva e a ação de disposição de sucata (por exemplo, Crédito e Sucata ou Substituir e Sucata).
- Uma ação de disposição subjacente de Crédito e Substituir ou Sucata e Substituir não será rejeitada. Ela será tratada como uma ação de disposição Crédito e Substituir ou Sucata e Substituir. Essa regra se aplicará mesmo que nenhuma linha de sucata seja criada na Empresa A e nenhuma ordem de substituição seja criada na Empresa B (a empresa que recebeu o item devolvido). Uma ordem de substituição só será criada na Empresa A quando uma atualização de guia de remessa for realizada.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
