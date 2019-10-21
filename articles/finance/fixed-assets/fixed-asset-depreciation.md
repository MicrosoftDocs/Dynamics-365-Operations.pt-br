---
title: Depreciação de ativo fixo
description: Este tópico oferece uma visão geral da depreciação de ativos fixos.
author: ShylaThompson
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBonus, AssetBookTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 3121
ms.assetid: 98ff891f-e0e2-4184-b618-28107a50851f
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1056dadab4294072cc064670f5cfcda239e22e19
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176399"
---
# <a name="fixed-asset-depreciation"></a>Depreciação de ativo fixo

[!include [banner](../includes/banner.md)]

Este tópico oferece uma visão geral da depreciação de ativos fixos.

Depreciação é uma transação periódica que normalmente reduz o valor do ativo fixo no balanço e é cobrada como uma despesa em uma conta de lucros e perdas. Portanto, uma conta principal é geralmente usada para creditar a depreciação periódica no balanço. Contrapartida é uma conta na parte de lucros e perdas do plano de contas.

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



