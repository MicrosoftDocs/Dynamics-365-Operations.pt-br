---
title: Bloqueio de estoque
description: Este tópico oferece uma visão geral do bloqueio de estoque, que faz parte do processo de inspeção de qualidade no Supply Chain Management. Você pode usar o bloqueio de estoque para evitar que os itens sejam processados ou consumidos.
author: perlynne
manager: tfehr
ms.date: 01/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventBlocking, InventQualityOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2094
ms.assetid: 1968e32f-eff9-4c17-8f7f-a870f0c38fbc
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 646ddc231b1ee25b13fdeb779b2bbeae6dd8c2a9
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5011588"
---
# <a name="inventory-blocking"></a>Bloqueio de estoque

[!include [banner](../includes/banner.md)]

Este tópico oferece uma visão geral do bloqueio de estoque, que faz parte do processo de inspeção de qualidade no Supply Chain Management. Você pode usar o bloqueio de estoque para evitar que os itens sejam processados ou consumidos.

Você pode bloquear itens de estoque das seguintes maneiras:
-   Manualmente
-   Criando uma ordem de qualidade
-   Usando um processo que gera uma ordem de qualidade
-   Usando um bloqueio de status de estoque

## <a name="blocking-items-manually"></a>Bloqueando itens manualmente
Você pode bloquear uma quantidade de um item criando uma transação na página **Bloqueio de estoque**. Somente os itens que estão disponíveis como estoque disponível podem ser bloqueados manualmente. Para quantidades bloqueadas manualmente, você deve decidir se as atividades de planejamento incluirão os recebimentos esperados como uma quantidade disponível esperada. Os recebimentos esperados são itens bloqueados que você espera que estejam disponíveis como inventário disponível após a conclusão da inspeção. É possível manter a data esperada. Por padrão, a opção **Recebimentos esperados** é selecionada para os itens bloqueados por meio de uma ordem de qualidade. Você pode cancelar o bloqueio manual em uma quantidade ao excluir a transação na página **Bloqueio de estoque**.

## <a name="blocking-items-by-creating-a-quality-order"></a>Bloqueando itens ao criar uma ordem de qualidade
Você pode especificar os itens que devem ser inspecionados ao criar uma ordem de qualidade na página **Ordens de qualidade**. Quando você criar uma ordem de qualidade, a quantidade especificada para um item será bloqueada. O plano de amostragem associado aos controles de uma ordem de qualidade controla somente a quantidade de itens que devem ser inspecionados, e não a quantidade que está bloqueada. A quantidade inserida na ordem de qualidade é a quantidade bloqueada, independentemente da quantidade que o plano de amostragem especifica que deve ser enviada para inspeção.

> [!NOTE]
> O uso dos recursos data de vencimento do lote e status do estoque de bloqueio não têm suporte no planejamento mestre. Isso pode resultar em dupla exclusão do estoque disponível, que pode ocorrer durante o planejamento mestre. Recomendamos que você se baseie nos códigos de disposição em lotes, em vez do status do estoque, para bloquear lotes expirados.

## <a name="blocking-items-by-using-a-process-that-generates-a-quality-order"></a>Bloqueando itens ao usar um processo que gera uma ordem de qualidade
Se um processo de qualidade especificar que um item deve ser inspecionado, uma quantidade do item será automaticamente bloqueada. Dessa forma, quando uma ordem de qualidade for gerada automaticamente, o plano de amostragem do item associado aos controles da ordem de qualidade controlará a quantidade de itens bloqueados, e não apenas a quantidade que deve ser inspecionada. Se a opção **Bloqueio total** da página **Amostragem de itens** estiver selecionada, a quantidade total de, por exemplo, uma linha de ordem de compra, será bloqueada durante a inspeção, independentemente da quantidade de amostragem do item.
### <a name="example"></a>Exemplo

No exemplo a seguir, uma ordem de qualidade será gerada quando uma guia de remessa de ordem de compra for lançada. Na página **Associações de qualidade**, você especificou que o lançamento de uma guia de remessa de ordem de compra será especificado como o processo que ativa uma ordem de qualidade.

|Configurar                                                                     |Ação do usuário                 |Resultado             |
|--------------------------------------------------------------------------|----------------------------|-------------------|
| Uma associação de qualidade especifica que uma ordem de qualidade deverá ser gerada quando uma guia de remessa de ordem de compra for lançada. A configuração de amostragem do item da ordem de qualidade especifica que 10% da quantidade na linha de ordem de compra serão inspecionados. Além disso, por causa da opção **Bloqueio total** selecionada na configuração da amostragem de item, a quantidade total da linha de ordem de compra deverá ser bloqueada durante a inspeção, independentemente da quantidade que será enviada para inspeção. | A guia de remessa é lançada. | Uma ordem de qualidade é gerada. Dez por cento da quantidade da ordem de compra para o item serão enviados para inspeção. A quantidade total da linha de ordem de compra é bloqueada. |

## <a name="blocking-items-by-using-inventory-status-blocking"></a>Bloqueando itens ao usar um bloqueio de status de estoque
Você pode especificar quais status de estoque estão bloqueando os status usando o parâmetro **Bloqueio de estoque** na página **Status de estoque**. Você não pode usar status de estoque como status de bloqueio para ordens de produção, ordens de venda, ordens de transferência, transações de saída ou integrações de projeto. Para o trabalho de saída, use itens com status de estoque disponível. Se os itens tiverem um status **Quebrado** e se o planejamento mestre for executado nesses itens, os itens serão considerados ausentes e o estoque será reabastecido automaticamente.



<a name="additional-resources"></a>Recursos adicionais
--------

[Criar e manter um bloqueio de estoque](tasks/create-maintain-inventory-blocking.md)

[Processos de gerenciamento de qualidade](quality-management-processes.md)

[Verificar a qualidade de mercadorias](tasks/inspect-quality-goods.md)
