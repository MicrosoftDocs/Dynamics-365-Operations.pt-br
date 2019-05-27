---
title: Configuração de contabilidade intercompanhia
description: Este tópico explica como configurar a contabilidade intercompanhia, de forma que você possa usar diários intercompanhia para alocações do razão e diários financeiros, como diários, diários de fatura de fornecedor e diários de pagamento.
author: kweekley
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerInterCompany
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 15761
ms.assetid: 1362297b-7a51-4930-b822-2b204a2e3c37
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ce07a29d7aa5057d0b61c7fcc6bb87a0a2755fc9
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1550273"
---
# <a name="intercompany-accounting-setup"></a>Configuração de contabilidade intercompanhia

[!include [banner](../includes/banner.md)]

Este tópico explica como configurar a contabilidade intercompanhia, de forma que você possa usar diários intercompanhia para alocações do razão e diários financeiros, como diários, diários de fatura de fornecedor e diários de pagamento.

Os diários intercompanhia podem ser criados em vários cenários, como para diários, diários de fatura de fornecedor, alocações do razão e pagamentos centralizados. Para habilitar estes cenários, você deve configurar a contabilidade intercompanhia.

## <a name="define-main-accounts"></a>Definição de contas principais
Primeiro, você deve criar as contas principais intercompanhia que serão usadas para as entradas Devido para e Devido por. É recomendável usar contas principais exclusivas para cada empresa, para simplificar a reconciliação e alienação de lançamentos contábeis intercompanhia. Se estiver usando um parceiro comercial ou uma dimensão equivalente para identificar o participante intercompanhia, você poderá definir essa dimensão como uma dimensão fixa na conta principal que é definida na contabilidade intercompanhia. Ao configurar as contas principais, é necessário definir o campo, **Tipo de conta principal** como **Balanço** na página **Contas principais**.

## <a name="define-journal-names"></a>Definição de nomes de diário
Em seguida, você deve definir um nome do diário. Defina o campo **Tipo de diário** como **Diário** na página **Nomes de diário**. É recomendável usar um nome de diário específico para contabilidade intercompanhia.

## <a name="define-intercompany-accounting-setup"></a>Definição de configuração de contabilidade intercompanhia
A página **Contabilidade intercompanhia** é usada para criar os pares de entidades legais que podem realizar transações entre si. A configuração de contabilidade intercompanhia for compartilhada, para que a configuração fique visível em de todas as entidades legais. Ao criar um novo par de entidade legal, certifique-se de qual entidade legal é definida como empresa de origem e empresa de destino. Ao inserir transações intercompanhia, a transação determina qual entidade legal está iniciando ou originando a transação. Por exemplo, a contabilidade intercompanhia é configurada para USMF (origem) e USSI (destino). Se um usuário estiver ativo no USSI e inserir uma transação intercompanhia com USMF, a transação não será lançada porque a contabilidade intercompanhia somente é definida para USMF sendo o originador. Se uma empresa puder originar uma transação, será preciso criar um segundo par de entidade legal da instalação recíproca. 

Selecione a **Conta de débito (Devido por)** e **Conta de crédito (Devido para** para a entidade legal de origem e de destino. Defina qual **Nome de diário** será usado quando a transação for criada na empresa de destino. O diário da empresa de origem é conhecido, pois foi selecionado pelo usuário ao criar a transação intercompanhia. 

Por fim, selecione qual entidade legal receberá os valores contábeis para suporte, como o desconto à vista ou ganhos/perdas realizados para pagamentos centralizados. 

Um relacionamento recíproco pode ser configurado facilmente na página **Contabilidade intercompanhia** usando o botão **Criar relacionamento recíproco** depois que o primeiro par de entidade legal for criado. Quando o par recíproco for criado, as informações da empresa de destino serão copiadas para a empresa de origem e vice-versa. O diário definido para a empresa de destino permanecerá. A maioria de organizações usa a mesma convenção de nomenclatura para os nomes de diário, de forma que o nome do diário seja igual. Se o nome do diário for diferente, um aviso aparecerá no campo para notificá-lo de que o diário não existe e um diário diferente poderá ser selecionado.



