---
title: Acesso a endereços privados por função de segurança
description: Este artigo explica como resolver o problema em que um cliente não pode acessar endereços particulares.
author: andreabichsel
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8daee1b645836e96a4bf3057cb317d5409d4583a
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5803912"
---
# <a name="access-to-private-addresses-by-security-role"></a>Acesso a endereços privados por função de segurança

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Saída**

Depois que um cliente duplica uma função de segurança e entra com a nova função, o cliente não pode ver endereços que estavam marcados como particulares.

**Resolução**

Para solucionar o problema, o cliente deve rastrear essas etapas para a função de segurança duplicada.

1. Vá para **Administração da organização \> Catálogo de endereços global \> Parâmetros do catálogo de endereços global**.
2. Na guia **Segurança de local privado**, mova a nova opção de segurança da lista **Funções disponíveis** para a lista **Funções selecionadas**.
3. Selecione **Salvar**.

![Página de parâmetros do catálogo de endereços global](media/GAD-parameters.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]