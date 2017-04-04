---
title: "Configurar cartas de ordem de débito direto SEPA"
description: 
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 59491
ms.assetid: 653a135f-c515-4ae3-9da2-82b5e1f103b5
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 114dee90b0fe525f0b3efabbf651d2804a22dd7d
ms.openlocfilehash: bb835f8dad16938b56365c7b06d4a0228f9aba66
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-sepa-direct-debit-mandate"></a>Configurar cartas de ordem de débito direto SEPA



Um débito direto de SEPA (Área Única de Pagamentos em Euros) permite que um credor colete fundos da conta bancária de um cliente, desde que um mandato assinado tenha sido concedido pelo cliente ao credor. O cliente assina um mandato que autoriza o credor a cobrar um pagamento e a instruir o banco do cliente para pagar a cobrança. Este tópico é organizado para mostrar o processo de configurar cartas de ordem de débito direto do SEPA.

## <a name="prerequisites"></a>Pré-requisitos
A tabela a seguir mostra os pré-requisitos que devem estar funcionando antes de começar.

| Categoria       | Pré-requisito                                                                                                                                              |
|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| País/região | O endereço principal da entidade legal deve estar nos seguintes países/regiões: Áustria, Bélgica, Alemanha, Espanha, França, Itália, ou Países Baixos. |

1. Configurar uma sequência numérica para cartas de ordem que de débito direto cada carta de ordem de débito direto deve ter um número exclusivo. Use a página **Sequências numéricas** para criar uma sequência numérica para mandatos de débito direto. Você usará esse identificador para atribuir a sequência numérica ao sistema de mandato de débito direto na página **Parâmetros de contas a receber**.

2. Configurar parâmetros de contas a receber para cartas de ordem de débito direto usam ** parâmetros de contas a receber ** a página para configurar parâmetros para cartas de ordem de débito direto. Para configurar os parâmetros, ** ** débito direto na alteração, como parâmetros padrão é necessário. ** O, em número define seqüencialmente ** na guia, atualizar ** ID de carta de ordem de débito direto colocam-no ** com a sequência numérica a anterior configurado.

3. Configurar um método de pagamento para cartas de ordem que de débito direto deve configurar um método de pagamento para cartas de ordem de débito direto. Use esse método de pagamento para consultar faturas para as quais serão gerados pagamentos de débito direto. Use a página **Métodos de pagamento** para configurar o método de pagamento. Para configurar um método de pagamento para mandatos de débito direto, você deve seguir essas etapas adicionais para um método de pagamento:

-   No campo **Tipo de pagamento**, selecione **Pagamento eletrônico**.
-   Opcional: Se você esperar cada um de seus clientes ter diversas cartas de ordem, no campo período ** **, selecione ** fatura **. Um pagamento separado será criado para cada nota fiscal, e toda pagamento usada a carta de ordem especificada para a nota fiscal.
-   Selecione a opção **Exigir mandato** para criar pagamentos usando mandatos de débito direto. A opção **Exigir mandato** só estará disponível se você selecionar **Pagamento eletrônico** no campo **Tipo de pagamento**.

Consulte visão geral também [] débito direto (sepa-direct-debit-overview.md) 

