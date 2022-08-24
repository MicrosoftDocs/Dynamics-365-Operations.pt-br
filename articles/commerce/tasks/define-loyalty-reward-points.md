---
title: Definir pontos de premiação de fidelidade
description: Este procedimento orienta na definição de pontos de recompensa de fidelidade.
author: josaw1
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.industry: Retail
ms.search.form: RetailLoyaltyRewardPoints
ms.openlocfilehash: 9acd1429d17393f19a5e059b90a48b0b103535d3
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268883"
---
# <a name="define-loyalty-reward-points"></a>Definir pontos de premiação de fidelidade

[!include [banner](../includes/banner.md)]

Este procedimento orienta na definição de pontos de recompensa de fidelidade. Você deve definir pontos de recompensa de fidelidade antes de configurar um programa de fidelidade. Este procedimento usa a empresa de dados de demonstração USRT.

1. Acesse Varejo e Comércio > Clientes > Fidelidade > Pontos de premiação de fidelidade.
2. Clique em Novo.
3. No campo ID do ponto de recompensa, digite um valor.
4. No campo Descrição, digite um valor.
5. No campo Tipo de ponto de recompensa, selecione uma opção.
    * Selecione Quantidade se deseja que os pontos de recompensa sejam arredondados para o número inteiro mais próximo. Selecione Valor se deseja que os pontos de recompensa sejam arredondados de acordo com as regras de arredondamento de moeda. Se você selecionar Quantidade, ignore a próxima etapa deste procedimento.  
6. No campo Moeda, digite um valor.
    * Para pontos de recompensa de Tipo de valor, todos os pontos emitidos serão na moeda selecionada. Para pontos de recompensa de Tipo de quantidade, esse campo não é aplicável, ignore esta etapa.  
7. Marque ou desmarque a caixa de seleção Resgatável.
8. No campo Classificação de resgate, insira um número.
    * A Classificação de resgate será usada quando dois ou mais pontos resgatáveis de recompensa possam ser usados para pagar por produtos. Se os dois pontos de recompensa tiverem a mesma classificação de resgate, o que necessitar do número mais baixo de pontos será usado.  
9. No campo Valor do período de validade, insira um número.
    * Os pontos de recompensa expirarão no número especificado de dias, meses ou anos depois que forem emitidos. Um valor de "0" significa que os pontos de recompensa de fidelidade nunca expirarão.  
10. No campo Unidade do período de validade, selecione uma opção.
11. Clique em Salvar.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
