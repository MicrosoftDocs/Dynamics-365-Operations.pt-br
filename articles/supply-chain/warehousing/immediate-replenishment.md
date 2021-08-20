---
title: Reabastecimento imediato
description: Este tópico descreve como você pode usar o reabastecimento imediato para reabastecer o estoque quando uma diretiva de local não atribua o estoque.
author: Mirzaab
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocDirTable, WHSReplenishmentTemplates
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 15a3cc4c50e49a50c354834761425cd107c23a9d79677e022cb1d339bb48c918
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6741923"
---
# <a name="immediate-replenishment"></a>Reabastecimento imediato

[!include [banner](../includes/banner.md)]

O reabastecimento imediato permite a você reabastecer o estoque imediatamente após uma linha de diretiva de local falhe ao alocar o estoque. O reabastecimento se baseia em uma única linha na configuração da diretiva de local. Se o estoque não estiver disponível na unidade de medida especificada por essa linha, o reabastecimento da unidade de medida ocorrerá imediatamente.

O reabastecimento imediato fornece uma alternativa ao método em que alocação de estoque se baseia em mais linhas na diretiva de local, onde a demanda é resumida no final da alocação e reabastecida na unidade de medida especificada pela última linha na diretiva de local.

Os benefícios de usar o reabastecimento imediato são o reabastecimento poder ser limitado por unidades específicas e a quantidade pode ser direcionada para locais específicos.

## <a name="business-scenario"></a>Cenário de negócios

Por exemplo, você tem um depósito com áreas de separação separadas para as unidades de medida "caixa" e "cada". Você deseja otimizar o processo de separação ao separar o máximo de caixas possível e ao escolher qualquer quantidade pendente inferior a uma caixa na área "cada".

Nesse caso, você pode usar o reabastecimento imediato. Na diretiva de local, você pode configurar o reabastecimento imediato para caixas de modo que o reabastecimento de demanda seja usado assim que houver uma escassez caixas que podem ser escolhidas para a quantidade de demanda. Assim, você otimiza o processo de separação de forma que a separação inclua o máximo de caixas possível. O reabastecimento imediato gerará o reabastecimento das caixas, e a demanda não será passada, de forma que as quantidades são separadas na unidade de medida "cada". Ou seja, somente as quantidades que devem ser separadas na unidade de medida "cada" (isto é, as quantidades inferiores a uma caixa) serão separadas da área "cada". Se ocorre escassez na área "caixa", você poderá separar o máximo de caixas possível da demanda total. As quantidades restantes serão separadas da área "cada".

## <a name="where-it-applies"></a>Aplica-se a

O reabastecimento imediato é usado durante a execução de onda se a alocação falhar para uma linha de diretiva de local para a qual um modelo de reabastecimento está definido.

## <a name="set-up-immediate-replenishment"></a>Configurar o reabastecimento imediato

- Acesse **Gerenciamento de depósito** \> **Configuração** \> **Diretivas de local** e, então, na guia **Linhas** , na lista **Modelo de reabastecimento imediato**, selecione um modelo de reabastecimento para demanda da onda.

O modelo de reabastecimento só será aplicado se a linha de diretiva de local falhar ao alocar uma unidade de medida dedicada.

## <a name="troubleshooting"></a>Solução de problemas

Se o reabastecimento imediato estiver selecionado para uma linha de diretiva de local, mas se nenhum trabalho de reabastecimento for gerado quando você usar os modelos de reabastecimento de demanda para essa linha de diretiva de local, duas causas principais deverão ser investigadas:

- Verifique se o modelo de reabastecimento de demanda aplicado foi configurado para usar os modelos de local e de trabalho corretos do tipo **Reabastecimento**.
- Verifique se há estoque disponível suficiente nos locais onde o modelo de reabastecimento de demanda procura estoque disponível para reabastecimento.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]