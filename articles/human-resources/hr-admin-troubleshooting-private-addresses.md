---
title: Acesso a endereços privados por função de segurança
description: Este tópico explica como resolver o problema onde um cliente não pode acessar endereços particulares.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 05895d58cfd108c45c3c75921cb6930b904a6482
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8068375"
---
# <a name="access-to-private-addresses-by-security-role"></a>Acesso a endereços privados por função de segurança


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Saída**

Depois que um cliente duplica uma função de segurança e entra com a nova função, o cliente não pode ver endereços que estavam marcados como particulares.

**Resolução**

Para solucionar o problema, o cliente deve rastrear essas etapas para a função de segurança duplicada.

1. Acesse **Administração da organização \> Catálogo de endereços global \> Parâmetros do catálogo de endereços global**.
2. Na guia **Segurança de local privado**, mova a nova opção de segurança da lista **Funções disponíveis** para a lista **Funções selecionadas**.
3. Selecione **Salvar**.

![Página de parâmetros do catálogo de endereços global.](media/GAD-parameters.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
