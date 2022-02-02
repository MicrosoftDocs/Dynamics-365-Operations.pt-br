---
title: Alteração de base nos cálculos de imposto ICMS-DIF para produtos de fornecedores em outros estados
description: Este tópico descreve a configuração para cálculos do tipo de imposto ICMS-DIF quando uma nota fiscal é recebida no estado brasileiro do Rio Grande do Sul (RS) ou de São Paulo (SP).
author: Kai-Cloud
ms.date: 1/20/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2022-1-17
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: 16f78b85567e6d08c588e621119513ff070bf618
ms.sourcegitcommit: 68655c5673aef9892063e5913ffee6bfc3817387
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2022
ms.locfileid: "8016159"
---
# <a name="basis-change-in-icms-dif-tax-calculations-for-products-from-suppliers-in-other-states"></a>Alteração de base nos cálculos de imposto ICMS-DIF para produtos de fornecedores em outros estados

Este tópico descreve a configuração para cálculos do tipo de imposto **ICMS-DIF** quando uma nota fiscal é recebida no estado brasileiro do Rio Grande do Sul (RS) ou de São Paulo (SP).

De acordo com a definição na legislação estadual, o Imposto sobre Circulação de Mercadorias e Serviços (ICMS) coletado deve seguir esta regra:

*ICMS a coletar* = ([(*Valor da operação* – *ICMS da origem*) ÷ (1 – *ICMS% interna*)] × *ICMS% interna*) – *valor do ICMS da origem*

## <a name="example"></a>Exemplo

Uma empresa brasileira no estado do RS recebe uma nota fiscal para uma compra de um fornecedor no estado de SP. A empresa deve coletar a diferença percentual do ICMS entre o estado do RS (18%) e o estado de SP (12%). No entanto, a base deve ser calculada de acordo com a regra anterior.

- **Valor da operação:** 1.000,00 reais (R$1.000,00)
- **ICMS interestadual:** R$120,00
- **Porcentagem de ICMS no estado do RS:** 18%
- **ICMS para coletar no estado do RS:** (\[(1.000 – 120) ÷ (1 – 0,18)\] × 0,18) – 120 = R$73,17 

## <a name="resolution"></a>Resolução

Para calcular o ICMS-DIF diferencial de acordo com as regras do estado RS, você deve configurar códigos de impostos sobre vendas e um grupo de impostos sobre vendas da seguinte maneira:

1. Crie um código de imposto sobre vendas para receber o ICMS de 12% (para o outro estado). Esse código é usado para registrar o valor do imposto a receber do fornecedor.
2. Crie um código de imposto para coletar o ICMS-DIF. Esse código de imposto sobre vendas deve ter um valor percentual de 18% (para seu próprio estado) para definir a diferença entre 18% e 12%. Defina o tipo de imposto como **ICMS-DIF**. Esse código de imposto sobre vendas deve ser definido da seguinte maneira nos parâmetros de cálculo:

    - No campo **Origem**, selecione **Porcentagem de valor bruto**.
    - No campo **Base marginal**, selecione **Valor líquido por linha** ou **Valor líquido do saldo de fatura**.
    - Defina o código de tributação para seu valor fiscal seja **3**. Dessa forma, a transação de ajuste será automaticamente criada quando o módulo **Livros fiscais** for habilitado.
    - Na configuração do grupo de impostos sobre vendas, selecione a opção **Imposto sobre o uso** para o código de imposto sobre vendas **ICMS-DIF**.
