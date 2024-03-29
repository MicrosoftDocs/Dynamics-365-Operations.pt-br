---
title: Depreciação de ativo fixo
description: Este artigo oferece uma visão geral da depreciação em Ativos fixos.
author: moaamer
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 3121
ms.assetid: 98ff891f-e0e2-4184-b618-28107a50851f
ms.search.form: AssetBonus, AssetBookTable
ms.openlocfilehash: 9761fc9846324d1c165274b72033e195bf4ea3e0
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275285"
---
# <a name="fixed-asset-depreciation"></a>Depreciação de ativo fixo

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este artigo oferece uma visão geral da depreciação em Ativos fixos.

Depreciação é uma transação periódica que normalmente reduz o valor do ativo fixo no balanço e é cobrada como uma despesa em uma conta de lucros e perdas. Portanto, uma conta principal é geralmente usada para creditar a depreciação periódica no balanço. Contrapartida é uma conta na parte de lucros e perdas do plano de contas.

A partir da versão 10.0.24, a opção de configuração de registro de ativos **Calcular depreciação positiva** na página **Registros** permite a depreciação para debitar um ativo fixo que é adquirido com valor contábil negativo (crédito).

## <a name="depreciation-adjustment"></a>Ajuste de depreciação
Normalmente, apenas uma correção para uma transação de depreciação já lançada é lançada como sendo um ajuste de depreciação. Portanto, a conta principal e a contrapartida são configuradas como as contas para depreciação. Um ajuste de depreciação pode ser um valor positivo ou negativo, embora a funcionalidade da conta principal (como conta do balanço) e da contrapartida (normalmente, como conta de lucros e perdas) permaneça a mesma.

## <a name="extraordinary-depreciation"></a>Depreciação extraordinária
A depreciação extraordinária funciona independentemente da depreciação básica. Portanto, uma conta principal é usada para creditar o valor de depreciação para o saldo e reduzir o valor do ativo fixo. Contrapartida é uma conta de lucros e perdas, na qual a depreciação calculada para o período fiscal é cobrada como uma despesa. 

A depreciação extraordinária funciona independentemente da depreciação básica. Ter uma depreciação extraordinária como um tipo de transação separado permite que você lance e informe a depreciação extraordinária separadamente da depreciação básica.

## <a name="special-depreciation-allowance"></a>Provisão para depreciação especial
É possível usar a depreciação de provisão especial para obter valores de depreciação extra durante o primeiro ano em que um ativo é disponibilizado e depreciado. Provisão para depreciação especial deve ser obtida antes de qualquer outro cálculo de depreciação. Porque as provisões de depreciação especial seja geralmente desconhecidas até posteriormente na vida útil do ativo fixo, é aconselhável usar este tipo de depreciação a um registro de não lançar na contabilidade. Você pode usar a opção Transações de exclusão não lançadas na contabilidade para excluir transações de histórico dos registros ainda não lançados na contabilidade. Você poderá excluir o histórico do registro de ativos, lançar a provisão para depreciação especial quando soube, e lançá-los nas outras transações de depreciação para o ano. 

É possível criar um número ilimitado de registros de depreciação de provisão especial. Depois de atribuí-los ao registro de depreciações de grupo de ativos, eles serão aplicados ao registro de depreciações de ativo. 

A depreciação de provisão especial é inserida como uma porcentagem ou um valor fixo. Quando você lançar propostas de depreciação, as transações de depreciação extra serão lançadas no registro de depreciações como transações separadas das transações de depreciação.

## <a name="depreciation-calendars"></a>Calendários de depreciação
Cada livro tiver um calendário usado quando depreciar ativos fixos. O método usará o calendário fiscal do razão por padrão se você não indicar um calendário. Você deve selecionar um calendário fiscal para um registro quando o perfil de depreciação associado do registro usar um ano de depreciação fiscal. 

Você pode criar calendários compartilhados usando a página **Calendários fiscais** na Contabilidade.

Para obter mais informações, consulte [Métodos e convenções de depreciação](depreciation-methods-conventions.md).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
