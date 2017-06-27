---
title: "Configurar cartas de ordem de débito direto SEPA"
description: 
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 59491
ms.assetid: 653a135f-c515-4ae3-9da2-82b5e1f103b5
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: ebf80efa32b21184a8effdde4d46c4d0d2179efd
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="set-up-sepa-direct-debit-mandate"></a>Configurar cartas de ordem de débito direto SEPA

[!include[banner](../includes/banner.md)]




Um débito direto de SEPA (Área Única de Pagamentos em Euros) permite que um credor colete fundos da conta bancária de um cliente, desde que um mandato assinado tenha sido concedido pelo cliente ao credor. O cliente assina um mandato que autoriza o credor a cobrar um pagamento e a instruir o banco do cliente para pagar a cobrança. Este tópico está organizado para mostrar o processo de criação de mandatos de débito direto da SEPA.

## <a name="prerequisites"></a>Pré-requisitos
A tabela a seguir mostra os pré-requisitos que devem estar funcionando antes de começar.

| Categoria       | Pré-requisito                                                                                                                                              |
|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| País/região | O endereço principal da entidade legal deve estar nos seguintes países/regiões: Áustria, Bélgica, Alemanha, Espanha, França, Itália, ou Países Baixos. |

1. Configurar uma sequência de números para mandatos de débito direto. Cada mandato de débito direto deve ter um número único. Use a página **Sequências numéricas** para criar uma sequência numérica para mandatos de débito direto. Você usará esse identificador para atribuir a sequência numérica ao sistema de mandato de débito direto na página **Parâmetros de contas a receber**.

2. Configurar parâmetros de contas a receber para mandatos de débito direto Use a página **Parâmetros de contas a receber** para definir parâmetros para mandatos de débito direto. Para configurar os parâmetros, na guia **Débito direto**, altere os parâmetros padrão conforme necessário. Em seguida, na guia **Sequências numéricas**, atualize o campo **ID de carta de ordem de débito direto** com a sequência de números que você configurou anteriormente.

3. Definir um método de pagamento para mandatos de débito direto. É necessário configurar um método de pagamento para mandatos de débito direto. Use esse método de pagamento para consultar faturas para as quais serão gerados pagamentos de débito direto. Use a página **Métodos de pagamento** para configurar o método de pagamento. Para configurar um método de pagamento para mandatos de débito direto, você deve seguir essas etapas adicionais para um método de pagamento:

-   No campo **Tipo de pagamento**, selecione **Pagamento eletrônico**.
-   Opcional: se você espera que cada um de seus clientes tenha vários mandatos, no campo **Período**, selecione **Fatura**. Um pagamento separado será criado para cada fatura e cada pagamento usará o mandato especificado para a fatura.
-   Selecione a opção **Exigir mandato** para criar pagamentos usando mandatos de débito direto. A opção **Exigir mandato** só estará disponível se você selecionar **Pagamento eletrônico** no campo **Tipo de pagamento**.

Consulte também [Visão geral do débito direto](sepa-direct-debit-overview.md) 



