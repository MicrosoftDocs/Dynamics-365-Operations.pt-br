---
title: Alteração de base nos cálculos de imposto ICMS-DIF para produtos de fornecedores em outros estados
description: Este artigo descreve a configuração para cálculos do tipo de imposto ICMS-DIF quando uma nota fiscal é recebida no estado brasileiro do Rio Grande do Sul (RS) ou de São Paulo (SP).
author: Kai-Cloud
ms.date: 06/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2022-1-17
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: 1bd9982a3804778a27203b4311682ee8bc3c4841
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/02/2022
ms.locfileid: "9218639"
---
# <a name="basis-change-dual-base-in-icms-dif-tax-calculations-for-products-from-suppliers-in-other-states"></a>Alteração de base (base dupla) nos cálculos de imposto ICMS-DIF para produtos de fornecedores em outros estados

Este artigo descreve a configuração para cálculos do tipo de imposto **ICMS-DIF** quando uma nota fiscal é recebida no estado brasileiro do Rio Grande do Sul (RS) ou de São Paulo (SP).

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
    - No campo **Base marginal**, selecione a opção **Valor líquido por linha**.
    - Defina o código de tributação para seu valor fiscal seja **3**. Dessa forma, a transação de ajuste será automaticamente criada quando o módulo **Livros fiscais** for habilitado.
    - Na configuração do grupo de impostos sobre vendas, selecione a opção **Imposto sobre o uso** para o código de imposto sobre vendas **ICMS-DIF**.

### <a name="use-the-delta-tax-rate-in-the-configuration-of-dual-base-icms-dif-sales-tax-codes"></a>Use a taxa de imposto delta para a configuração dos códigos de imposto de vendas ICMS-DIF de base dupla

Quando as configurações descritas anteriormente forem usadas, o código do imposto sobre vendas **ICMS-DIF** será calculado a partir da regra de base dupla. No entanto, a taxa de imposto nominal passa a ser de 18%, que difere da taxa de 6% na regra de base simples. Essa diferença causa problemas de inconsistência na nota fiscal e no relatório de imposto. A partir da versão 10.0.29 do Microsoft Dynamics 365 Finance, você pode habilitar o recurso **(Brasil) Configurar a taxa de imposto delta no código de imposto ICMS-DIF para o recurso de caso** de base dupla em **Gerenciamento de recursos** para remover a inconsistência.

- Além de concluir as etapas na seção anterior, selecione o código de imposto de vendas **ICMS 12** no campo **Imposto sobre vendas no campo Imposto sobre vendas**.
- Defina a taxa de imposto do código do imposto de vendas **ICMS-DIF** para 18%. O campo **Porcentagem/valor** mostrará a taxa de imposto nominal como 6%.

> [!NOTE]
> Os códigos de imposto sobre vendas **ICMS-DIF** e **ICMS 12** devem ser atribuídos no mesmo grupo de impostos sobre vendas.

## <a name="basis-change-dual-base-in-icms-dif-tax-calculations-for-products-to-non-taxpayer-consumers-difal-in-other-states"></a>Alteração de base (base dupla) nos cálculos de imposto ICMS-DIF para produtos destinados a consumidores não contribuintes (DIFAL) em outros estados

Habilite o recurso **cálculo de base duplo (Brasil) para ICMS-DIFAL em transações de vendas** no **Gerenciamento de recursos** para dar suporte à base de ICMS-DIF em negociações com consumidores não contribuintes de outro estado. O código de imposto sobre vendas de ICMS-DIF é efetivo em transações de ordem de venda e de fatura de texto livre.

Habilite o recurso **(Brasil) Cálculo de base duplo para ICMS DIFAL para os casos de IPI** no **Gerenciamento de recursos** para dar suporte a cenários nos quais a negociação com consumidores não contribuintes de outro estado também é responsabilizada por imposto sobre produtos industrializados (IPI). O valor do imposto do código do imposto sobre vendas IPI será reconhecido e aplicado na base de impostos do ICMS-DIFAL.

- No cabeçalho da ordem de venda ou fatura de texto livre, na **FastTab de informações fiscais**, a opção **Usuário final** deve ser definida como **Sim**.
- No cabeçalho da ordem de compra ou fatura de fornecedor, na **FastTab de informações fiscais**, a opção **Uso e consumo** deve ser definida como **Sim**.
