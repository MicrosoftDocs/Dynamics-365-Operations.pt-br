---
title: Depreciação de consumo
description: Este artigo fornece uma visão geral do Método de consumo de depreciação.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 13751
ms.assetid: d25a681f-49a5-4bfc-aa76-1c6373e35dd8
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1b0bc761160dc7d46519aad13ec2575cb882fc0641830b76952763b54834a64d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6747480"
---
# <a name="consumption-depreciation"></a>Depreciação de consumo

[!include [banner](../includes/banner.md)]

Este artigo fornece uma visão geral do Método de consumo de depreciação.

Se você configurar um perfil de depreciação para ativos fixos e selecionar **Consumo** no campo **Método** na página **Perfis de depreciação**, os ativos fixos são atribuídos ao perfil de depreciação com base em sua utilização. Você não precisa definir porcentagens e intervalos na página **Perfis de depreciação**. Depois de criar um período de depreciação que utiliza o método de consumo, você pode configurar o método de várias maneiras.

## <a name="set-up-and-use-consumption-depreciation"></a>Configurar e usar a depreciação de consumo
1.  Na página **Perfis de depreciação**, crie o perfil de depreciação. Para cálculos de consumo, o perfil de depreciação deve ter uma ID e um nome, e **Consumo** deve ser selecionado no campo **Método**.
2.  Na página **Fatores de consumo**, configure os fatores de consumo. Todos os fatores de consumo devem ter uma ID e o nome, e um fator de consumo que é especificado como uma quantidade ou porcentagem.
3.  Na página **Unidades de consumo**, configure as unidades de consumo. Cada unidade de consumo devem ter uma ID e um nome. As unidades de depreciação são usadas para calcular a depreciação de consumo na página **Depreciação de consumo**. Exemplos de unidades são quilômetro (km), quilograma (kg) ou hora.
4.  Na página **Ativos fixos**, configure ativos fixos individuais. Os perfis de depreciação fazem parte do método ou do registro de depreciação selecionado para cada ativo fixo. Você deve configurar modelos de depreciação ou registros de depreciação para depreciação de consumo se algum de seus ativos fixos utilizar perfis de depreciação com base no método de consumo. Essa configuração é feita na guia **Depreciação** da página **Modelos de depreciação** ou na Guia Rápida **Geral** da página **Perfil de depreciação**. É possível usar o mesmo método de depreciação para muitos ativos fixos. Os perfis de depreciação fazem parte do método ou do registro de depreciação selecionado para cada ativo fixo. Não é possível adicionar ou modificar perfis de depreciação diretamente na página **Ativos fixos**. Você pode modificar perfis de depreciação somente na página **Registros de depreciação**.
5.  Na página **Modelos de depreciação** ou página **Registros de depreciação**, no grupo de campos **Depreciação de consumo**, insira informações nos seguintes campos.
    -   Fator de consumo
    -   Unidade
    -   Depreciação de unidade
    -   Consumo estimado

    O campo **Consumo lançado** mostra a depreciação de consumo, em unidades, já lançada para a combinação do ativo fixo e método de depreciação, ou para o registro de depreciação. Não é possível atualizar manualmente o valor deste campo.

## <a name="examples"></a>Exemplos
### <a name="example-1"></a>Exemplo 1

O seguinte fator de consumo é definido para o dia 31 de janeiro:

-   A quantidade
-   O preço unitário de depreciação que é especificado para o ativo fixo é 1,5.

A proposta de depreciação em 31 de janeiro é a seguinte: Quantidade × Depreciação de unidade 1.000 × 1,5 = 1.500. Se o fator especificado para o ativo fixo for um fator de porcentagem, a quantidade estimada no campo **Consumo estimado** para o modelo de depreciação do ativo fixo é multiplicada pela porcentagem configurada par a data final selecionada. A quantidade resultante então é sugerida como a quantidade de depreciação para o período.

### <a name="example-2"></a>Exemplo 2

O seguinte fator da depreciação de consumo está definido para o dia 31 de janeiro:

-   A porcentagem é 10.
-   O preço unitário de depreciação que é especificado para o ativo fixo é 1,5.
-   A quantidade prevista do ativo fixo é 2.000.

A proposta de depreciação em 31 de janeiro é a seguinte: Quantidade estimada × Porcentagem × Depreciação de unidade 2.000 × 0,10 × 1,5 = 300





[!INCLUDE[footer-include](../../includes/footer-banner.md)]