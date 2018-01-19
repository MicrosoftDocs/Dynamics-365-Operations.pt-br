--- 
title: " Definir pontos de premiação de fidelidade"
description: "Este procedimento orienta na definição de pontos de recompensa de fidelidade."
author: scott-tucker
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 05237a0ba3aa785432c8b1fc36284a47f9aabd4a
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="define-loyalty-reward-points"></a> Definir pontos de premiação de fidelidade

[!include[task guide banner](../includes/task-guide-banner.md)]

Este procedimento orienta na definição de pontos de recompensa de fidelidade. Você deve definir pontos de recompensa de fidelidade antes de configurar um programa de fidelidade. Este procedimento usa a empresa de dados de demonstração USRT.

1. Vá para Varejo e comércio > Clientes > Fidelidade > Pontos de recompensa de fidelidade.
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
    * Os pontos de recompensa expirarão no número especificado de dias, meses ou anos depois que forem emitidos. Um valor de '0' significa que os pontos de recompensa de fidelidade nunca expirarão.  
10. No campo Unidade do período de validade, selecione uma opção.
11. Clique em Salvar.


