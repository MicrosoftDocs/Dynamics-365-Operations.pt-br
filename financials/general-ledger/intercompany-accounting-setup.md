---
title: "Configuração de contabilidade intercompanhia"
description: "Este tópico explica como configurar a contabilidade intercompanhia de forma que você possa usar diários intercompanhia para alocações contábil e diários financeiros, como diários, diários de notas fiscais do fornecedor, e os diários de pagamento."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerInterCompany
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15761
ms.assetid: 1362297b-7a51-4930-b822-2b204a2e3c37
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ef99caf4570969d2b920cec8b53669ce2094965
ms.openlocfilehash: 5fd279327013f26230146be38e23e9955c6f12c7
ms.lasthandoff: 03/31/2017


---

# <a name="intercompany-accounting-setup"></a>Configuração de contabilidade intercompanhia

Este tópico explica como configurar a contabilidade intercompanhia de forma que você possa usar diários intercompanhia para alocações contábil e diários financeiros, como diários, diários de notas fiscais do fornecedor, e os diários de pagamento.

Diários intercompanhia podem ser criados em vários cenários, como para diários, diários de notas fiscais de fornecedor, alocações contábeis, e pagamentos centralizados. Para habilitar estes cenários, você deve configurar a contabilidade intercompanhia.

## <a name="define-main-accounts"></a>Defina contas principais
Primeiro, você deve criar as contas principais intercompanhia que serão usadas para as entradas Devido para e Devido por. É recomendável usar contas principais exclusivas para cada empresa, para simplificar a reconciliação e alienação de lançamentos contábeis intercompanhia. Se estiver usando um parceiro comercial ou uma dimensão opostos para identificar o participante intercompanhia, defina esta dimensão como uma dimensão principal fixa na conta definida na contabilidade intercompanhia. Quando você configurou as listas principais, você deve definir o balanço ** tipo de conta do principal ** ** ** ** contas principais ** na página.

## <a name="define-journal-names"></a>Defina nomes de diário
Em seguida, você deve definir um nome do diário. ** O definir o tipo de diário ** de campo ** ** ** ** nomes de diário na página. É recomendável usar um nome de diário específico para contabilidade intercompanhia.

## <a name="define-intercompany-accounting-setup"></a>Defina a configuração de contabilidade intercompanhia
** Contabilidade intercompanhia ** a página é usado para criar os pares de entidades legais a determinadas transações si. A configuração de contabilidade intercompanhia for compartilhada, para que a configuração está visível em de todas as entidades legais. Ao criar um novo controle a entidade legal, garanta que você saiba da entidade legal definida como empresa de origem com a empresa de destino. Ao inserir transações intercompanhia, a transação determina qual entidade legal é iniciando ou origem da transação. Por exemplo, a contabilização intercompanhia é configurado para USMF (origem) e USSI (destino). Se um usuário for ativo em USSI e insere uma transação intercompanhia com USMF, a transação não será lançada como a contabilização intercompanhia é definida apenas para USMF o originador. Se uma ou outra empresa podem se originar uma transação, será preciso criar um segundo controle a entidade legal do recíproco de instalação. 

** Selecione a conta de débito de vencimento (e) ** ** conta de crédito devido (a) ** a fonte a entidade legal e de destino. Defina que ** o nome de diário ** será usado quando a transação é criada na empresa de destino. O diário da empresa de origem é conhecido como já selecionados pelo usuário ao criar a transação intercompanhia. 

Finalmente, selecione qual entidade legal receberá os valores de apoio contabilização, como o desconto à vista ou lucros realizados e perdas para pagamentos centralizados. 

Uma relação recíproco pode ser facilmente configurado ** contabilidade intercompanhia ** na página criar usando ** o relacionamento recíproco ** o botão depois que os controle a entidade legal é criado. Quando o controle recíproco é criado, as informações para a empresa de destino será copiada para a empresa de origem e vice-versa. O diário definido para a empresa de destino permanecerá. A maioria de organizações usam a mesma convenção de nomenclatura para os nomes de diário, para que o nome de diário é o mesmo. Se o nome são diferentes, um aviso parecerá no campo para notificá-lo o diário não existe e um diário diferente pode ser selecionado.


