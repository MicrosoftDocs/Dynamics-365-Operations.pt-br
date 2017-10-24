---
title: "Configurar uma decisão condicional em um fluxo de trabalho"
description: "Use os procedimentos a seguir para configurar as propriedades da decisão condicional."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 195703
ms.assetid: cd5554a4-210c-4c20-a7d3-4b1563c2b5df
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: e9d5c8add546cad0446e863f64cac8f9cb603cbb
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="configure-a-conditional-decision-in-a-workflow"></a>Configurar uma decisão condicional em um fluxo de trabalho

[!include[banner](../includes/banner.md)]


Use os procedimentos a seguir para configurar as propriedades da decisão condicional.

Uma decisão condicional é um ponto em que um fluxo de trabalho se divide em duas ramificações. Para configurar uma decisão condicional, no editor de fluxo de trabalho, clique com o botão direito do mouse na decisão condicional e, em seguida, em **Propriedades** para abrir o formulário**Propriedades**.

## <a name="name-a-decision"></a>Nomeie uma decisão
Siga estas etapas para inserir um nome para a decisão condicional.
1.  No painel esquerdo, clique em **Configurações Básicas**.
2.  No campo **Nome**, insira um nome exclusivo para a decisão condicional.

## <a name="set-conditions"></a>Definir condições
O sistema determina qual ramificação é usada para avaliar o documento enviado para determinar se ele atende às condições específicas.
1.  No painel esquerdo, clique em **Configurações Básicas**.
2.  Clique em **Adicionar condição**.
3.  Insira uma condição.
4.  Insira condições adicionais, se forem necessárias.
5.  Para verificar se as condições inseridas foram configuradas corretamente, execute as etapas a seguir:
    1.  Clique em **Teste** para abrir o formulário **Condição de fluxo de trabalho de teste**.
    2.  Selecione um registro na área **Validar condição** do formulário.
    3.  Clique em **Teste**. O sistema avaliará o registro para determinar se ele atende às condições definidas.
    4.  Clique em **OK** ou em **Cancelar** para retornar ao formulário **Propriedades**.






