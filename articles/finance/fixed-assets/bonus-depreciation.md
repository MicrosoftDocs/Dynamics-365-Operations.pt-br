---
title: Depreciação extra
description: Este artigo fornece uma visão geral da funcionalidade de depreciações bônus.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBonus
audience: Application User
ms.reviewer: roschlom
ms.custom: 3621
ms.assetid: 835ec594-744e-461c-a676-1b9abc094173
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f811b913f751a860c21fc120b15bac406281d7f8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5827017"
---
# <a name="bonus-depreciation"></a>Depreciação extra

[!include [banner](../includes/banner.md)]

Este artigo fornece uma visão geral da funcionalidade de depreciações bônus.

Com a depreciação extra, você pode obter valores de depreciação extra durante o primeiro ano em que o ativo é disponibilizado e depreciado. A depreciação extra será obtida antes de qualquer outro cálculo de depreciação. Portanto, é aconselhável usar a depreciação extra com registros que lançar à funcionalidade de contabilização está desabilitado. Você pode usar a opção **Transações de exclusão não lançadas na contabilidade** para excluir transações de histórico dos registros ainda não lançados na contabilidade. Você poderá então acomodar a depreciação extra posteriormente no ciclo de vida de ativo excluindo as transações de depreciação que foram lançadas anteriormente. 

É possível calcular a depreciação extra usando o processo de proposta ou criar transações de depreciação extra manuais. Você não pode criar transações de depreciação extra se existirem transações de depreciação ou transações de ajuste de depreciação para aquele registro de depreciações de ativo.

Quando você usa o processo de proposta para calcular a depreciação extra, todas as transações extras existentes são incluídas no cálculo base. O cálculo também inclui todas as depreciações extras anteriores que tenham sido inseridas manualmente para o ativo. 

Se mais de uma depreciação extra for obtida para um ativo, a prioridade deverá ser levada em conta. Cada extra reduz a base do ativo para o próximo extra. O valor residual não é considerado na base do ativo para cálculos de depreciação extra e a convenção de depreciação não se aplica à depreciação extra. 

Atualmente, nos Estados Unidos, determinada propriedade qualifica-se como a propriedade da Seção 179. Usando a dedução da seção 179, é possível recuperar todo ou parte do custo de determinada propriedade, até um limite. É possível recuperar os custos deduzindo-os no ano em que você disponibilizar a propriedade.

## <a name="example"></a>Exemplo
As seguintes depreciações extras estão associadas a um registro de depreciações de ativo:

-   **Seção 179:** 1.000,00, Prioridade 1
-   **Zona de liberdade:** 30%, Prioridade 2

O custo de aquisição de ativo é US$ 5.000,00. Quando a depreciação extra for calculada, o primeiro valor de depreciação extra será de US$ 1.000,00 para a depreciação da Seção 179. 

O próximo valor de depreciação extra, para a depreciação da Zona de Liberdade, será calculado da seguinte forma: 

Custo de aquisição – 1.000 (depreciação da Seção 179) × 30% = 1.200 

Se o valor da depreciação extra for maior que o custo de aquisição pendente, o valor da depreciação extra será o resultado do cálculo da depreciação extra ou o custo de aquisição pendente, o que for menor. 

Se o custo de aquisição pendente for 0 (zero) ou menos, as transações de depreciação extra não serão geradas. 

Quando a depreciação extra for calculada usando o processo de proposta, uma transação de depreciação extra será criada para todos os registros de depreciações extras aplicáveis, associados ao registro de depreciações do ativo. 

É possível criar um número ilimitado de registros de depreciação extra. Depois de atribuí-los ao registro de depreciações de grupo de ativos, eles serão aplicados ao registro de depreciações de ativo. 

A depreciação extra é inserida como uma porcentagem ou um valor fixo. Quando você lançar propostas de depreciação, as transações de depreciação extra serão lançadas no registro de depreciações como transações separadas das transações de depreciação.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]