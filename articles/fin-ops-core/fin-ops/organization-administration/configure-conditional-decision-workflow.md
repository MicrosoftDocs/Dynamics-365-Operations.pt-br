---
title: Configurar decisões condicionais em um fluxo de trabalho
description: Use os procedimentos a seguir para configurar as propriedades da decisão condicional.
author: ChrisGarty
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195703
ms.assetid: cd5554a4-210c-4c20-a7d3-4b1563c2b5df
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ed53eeb26e1b4b1df1647739ce1d115c7dd169f8
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747922"
---
# <a name="configure-conditional-decisions-in-a-workflow"></a>Configurar decisões condicionais em um fluxo de trabalho

[!include [banner](../includes/banner.md)]

Use os procedimentos a seguir para configurar as propriedades da decisão condicional.

Uma decisão condicional é um ponto em que um fluxo de trabalho se divide em duas ramificações. Para configurar uma decisão condicional, no editor de fluxo de trabalho, clique com o botão direito do mouse na decisão condicional e, em seguida, em **Propriedades** para abrir o formulário **Propriedades**.

## <a name="name-a-decision"></a>Nomeie uma decisão

Siga estas etapas para inserir um nome para a decisão condicional.

1. No painel esquerdo, clique em **Configurações Básicas**.
2. No campo **Nome**, insira um nome exclusivo para a decisão condicional.

## <a name="set-conditions"></a>Definir condições

O sistema determina qual ramificação é usada para avaliar o documento enviado para determinar se ele atende às condições específicas.

1. No painel esquerdo, clique em **Configurações Básicas**.
2. Clique em **Adicionar condição**.
3. Insira uma condição.
4. Insira condições adicionais, se forem necessárias.
5. Para verificar se as condições inseridas foram configuradas corretamente, execute as etapas a seguir:

    1. Clique em **Teste** para abrir o formulário **Condição de fluxo de trabalho de teste**.
    2. Selecione um registro na área **Validar condição** do formulário.
    3. Clique em **Teste**. O sistema avaliará o registro para determinar se ele atende às condições definidas.
    4. Clique em **OK** ou em **Cancelar** para retornar ao formulário **Propriedades**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]