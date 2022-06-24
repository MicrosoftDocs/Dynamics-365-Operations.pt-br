---
title: Configurar nomes de diário de arrendamento
description: Este artigo explica como definir nomes de diário de arrendamento. Os nomes de diários de arrendamento especificam os diários em que as entradas originadas em Arrendamento de ativo são lançadas.
author: moaamer
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePostingAccounts
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 678587e0846f6ce6d6d8113290a90b3f4d1988cc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8874686"
---
# <a name="set-up-lease-journal-names"></a>Configurar nomes de diário de arrendamento

[!include [banner](../includes/banner.md)]


Os nomes de diários de arrendamento especificam os diários em que transações de Arrendamento de ativo são lançadas. Somente os nomes de diário atribuídos ao tipo de diário **Arrendamento de ativo** aparecem nos campos **Reconhecimento Inicial** e **Nome de Diário Mensal** na página **Parâmetros de arrendamento de ativos**. Somente o tipo de diário de **registro de fatura de fornecedor** pode ser atribuído ao campo **Nome do diário de fatura**.

O sistema bloqueia certos campos financeiros da edição para evitar variações entre as transações e os agendamentos. Alguns campos bloqueados incluem: **Conta**, **Valores**, **Dimensões financeiras**, **Moeda** e **Tipo de transação**. Além disso, não será possível adicionar ou excluir linhas de entrada de diário em qualquer entrada de diário de leasing de Ativo, pois isso poderá causar variações entre as agendas e as transações.


Para configurar nomes de diário de arrendamento, siga as etapas abaixo.

1. Acesse **Gerenciamento de ativos \> Configuração \> Parâmetros de gerenciamento de ativos**.
2. Na guia **Geral**, no campo **Nome do diário de reconhecimento inicial**,selecione um diário. Todas as entradas do diário de reconhecimento inicial serão lançadas nesse nome de diário.
3. No campo **Nome de diário de fatura**, selecione um diário. Se a opção **Pagar ao fornecedor** for definida como **Sim** para o registro de arrendamento, as faturas de pagamento de arrendamento e despesa serão lançadas nesse nome de diário.
4. No campo **Nome de diário de arrendamento**, selecione um diário. Todas as entradas de depreciação, juros e reclassificação de curto prazo serão lançadas nesse nome de diário. Se a opção **Pagar ao fornecedor** for definida como **Não** para o registro de arrendamento, as entradas de pagamento do arrendamento e de pagamento da despesa também serão lançadas nesse nome de diário.
5. No campo **Nome do diário de modificação do arrendamento**, selecione um diário. As transações de ajuste, rescisão e redução ao valor recuperável do arrendamento serão lançadas neste diário. O nome do diário selecionado não pode ter um fluxo de trabalho ou aprovação atribuído a ele. Se o nome do diário de modificação do arrendamento não for definido, as transações de ajuste, rescisão e redução ao valor recuperável do arrendamento serão lançadas no diário selecionado no campo **Nome do diário de arrendamento**. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
