---
title: Configurar parâmetros de arrendamento (Versão Preliminar)
description: Este artigo descreve as definições de configuração para Arrendamento de ativos, como informações de segurança e configurações de contabilidade.
author: moaamer
ms.date: 01/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePostingAccounts
audience: Application User
ms.reviewer: twheeloc
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: e878fa7634cfdcc6c0db19a91e771757c545505b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8895070"
---
# <a name="configure-lease-parameters"></a>Configurar parâmetros de arrendamento

[!include [banner](../includes/banner.md)]

Várias definições de configuração afetam o comportamento do arrendamento de ativos. Essas configurações incluem nomes de diário, parâmetros gerais e configurações de perfil de lançamento.

1. Acesse **Gerenciamento de ativos \> Configuração \> Parâmetros de gerenciamento de ativos**.
2. Na guia **Arrendamentos**, selecione a FastTab **Geral**.

    O parâmetro **Permitir substituição de classificação manual** determina se a classificação de arrendamento pode ser substituída antes da confirmação do plano de pagamento.

    O parâmetro **Lote entre entidades** determina se é possível lançar em outras entidades legais desde a entidade legal atual. Se esse parâmetro estiver ativado, é possível criar entradas de diário para entidades legais às quais você tem acesso.

3. Defina a opção **Permitir a exclusão de arrendamentos confirmados** como **Sim** para permitir a exclusão de arrendamentos com planos de pagamento confirmados. Os arrendamentos não podem ser excluídos se transações lançadas ou não lançadas estiverem associadas, independentemente da configuração dessa opção. Não é possível restaurar um registro de arrendamento após ele ser excluído. Se você carregar registros de um arrendamento excluído, manualmente ou por meio de entidades de dados, as informações carregadas serão tratadas como novas e não como uma atualização de um arrendamento existente.

    Se você definir essa opção como **Sim** e o tipo de transição do registro for **Opção de catchup cumulativo A ou B**, o sistema definirá o campo **Taxa incremental de empréstimo** como o valor do campo **Taxa incremental de empréstimo na transição** na página **Configuração do registro**. Se essa opção for definida como **Não**, a taxa no arrendamento principal é definida como o valor do campo **Taxa incremental de empréstimo** na página **Detalhes do registro**, independentemente do tipo de transição do registro:

4. Defina a opção **Permitir reversões de depreciação na versão do livro fechado** como **Sim** para permitir a reversão das transações de despesas de depreciação. As transações de despesas podem ser revertidas mesmo quando a versão do livro é fechada.

    > [!NOTE]
    > Recomendamos manter essa opção como **Não**. A configuração dessa opção é usada como validação e controle para impedir que uma versão de livro fechada seja depreciada por engano. Ao manter a opção definida como **Não**, você ajuda a manter a precisão do valor líquido contábil e os cálculos de depreciação futuros.

5. Defina a opção **Permitir divisão de valor de pagamento permitido** como **Sim** para permitir uma divisão dos valores de pagamento na Guia Rápida **Linhas da agenda de pagamento** da página **Arrendamento**. Os tipos de divisão de pagamento são definidos em **Configuração** na página **Tipos de valor de pagamento**. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
