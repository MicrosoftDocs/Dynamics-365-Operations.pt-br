---
title: Configurar tipos de despesa
description: Este artigo explica como configurar tipos de despesa em Arrendamento de ativos.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseExpenseTypeTable
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2019-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 9978041059437d5d3556236c7ac02c00db93f933
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8908028"
---
# <a name="set-up-expense-types"></a>Configurar tipos de despesa

[!include [banner](../includes/banner.md)]

Este artigo explica como configurar tipos de despesa em Arrendamento de ativos. Os custos que não são representados pela agenda de pagamento são conhecidos como *custos de despesas*. Exemplos desses custos incluem impostos sobre propriedades, custos de manutenção de área comum e despesas de seguro.

## <a name="add-an-administrative-expense-type"></a>Adicionar um tipo de despesa administrativa

1. Acesse **Arrendamento de ativo \> Configuração \> Tipos de despesa**.
2. Selecione **Novo**.
3. Nos campos apropriados, insira o novo tipo de despesa e uma descrição.

## <a name="assign-accounts-to-administrative-costs"></a>Atribuir contas a custos administrativos

Em seguida, você deverá associar contas aos tipos de despesa. Essas contas serão debitadas quando as entradas da agenda de despesas forem lançadas. A contrapartida é especificada nas linhas da **Agenda de pagamento de custos de execução** em cada arrendamento.

1. Acesse **Gerenciamento de ativos \> Configuração \> Parâmetros de gerenciamento de ativos**.
2. Na guia **Contas**, na Guia Rápida **Custos de execução**, no campo **Tipo de despesa**, selecione o tipo de despesa.
3. Selecione **Adicionar**.
4. No campo **Tipo de registro**, selecione o tipo de registro a ser vinculado aos custos administrativos.

    > [!NOTE]
    > Vários tipos de registro podem ser vinculados à mesma conta de despesa.

5. No campo **Código da conta**, especifique a quais arrendamentos o registro deve ser aplicado:

    - **Todos** – aplique o registro a todos os arrendamentos.
    - **Grupo** – aplique o registro a um grupo específico de arrendamentos.
    - **Tabela** – aplique o registro a arrendamentos específicos.

6. Se você tiver selecionado **Grupo** ou **Tabela** no campo **Código de conta**, selecione um número da conta ou número do grupo no campo **Número da Conta/Grupo**.
7. Nos campos apropriados, selecione a conta principal do arrendamento mercantil e a conta principal do arrendamento operacional.

Depois de concluir estas etapas, você poderá adicionar despesas por meio das linhas de **Agenda de pagamento de custos de execução** na página **Detalhes do arrendamento** de um arrendamento selecionado. Como alternativa, você pode adicionar despesas ao criar um novo arrendamento.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
