---
title: Definir pontos de premiação de fidelidade
description: Este procedimento orienta na definição de pontos de recompensa de fidelidade.
author: scott-tucker
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailLoyaltyRewardPoints
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: af217a5e756db571e3e351b743aa44b842f478f1
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000475"
---
# <a name="define-loyalty-reward-points"></a>Definir pontos de premiação de fidelidade

[!include [banner](../includes/banner.md)]

Este procedimento orienta na definição de pontos de recompensa de fidelidade. Você deve definir pontos de recompensa de fidelidade antes de configurar um programa de fidelidade. Este procedimento usa a empresa de dados de demonstração USRT.

1. Vá para Varejo e Comércio > Clientes > Fidelidade > Pontos de premiação de fidelidade.
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

