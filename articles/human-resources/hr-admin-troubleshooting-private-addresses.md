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
ms.openlocfilehash: 0b96733946e4ef79de244730d0c442b9900426c1
ms.sourcegitcommit: 7e32e5e39e762a4b1606161cb603a450d13b5251
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2021
ms.locfileid: "7413330"
---
# <a name="access-to-private-addresses-by-security-role"></a>Acesso a endereços privados por função de segurança

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
