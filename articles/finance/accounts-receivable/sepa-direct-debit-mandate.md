---
title: Configurar carta de ordem de débito direto SEPA
description: Um débito direto de SEPA (Área Única de Pagamentos em Euros) permite que um credor colete fundos da conta bancária de um cliente, desde que um mandato assinado tenha sido concedido pelo cliente ao credor.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustParameters
audience: Application User
ms.reviewer: roschlom
ms.custom: 59491
ms.assetid: 653a135f-c515-4ae3-9da2-82b5e1f103b5
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c6ee3861e967246e79b072aaa69f2be02db9231b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4995484"
---
# <a name="set-up-sepa-direct-debit-mandate"></a>Configurar carta de ordem de débito direto SEPA

[!include [banner](../includes/banner.md)]

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

Recursos adicionais

[Visão geral de débito direto SEPA](sepa-direct-debit-overview.md) 

[Criar um mandato de débito direto para um cliente](tasks/create-direct-debit-mandate-customer.md) 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]