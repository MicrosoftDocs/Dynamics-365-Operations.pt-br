---
title: Acesso a endereços privados por função de segurança
description: Este artigo explica como resolver o problema em que um cliente não pode acessar endereços particulares.
author: andreabichsel
manager: tfehr
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
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
ms.openlocfilehash: 6598094e7877a30c35e1b03794f82c8a4ec001a7
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "5111457"
---
# <a name="access-to-private-addresses-by-security-role"></a>Acesso a endereços privados por função de segurança

**Saída**

Depois que um cliente duplica uma função de segurança e entra com a nova função, o cliente não pode ver endereços que estavam marcados como particulares.

**Resolução**

Para solucionar o problema, o cliente deve rastrear essas etapas para a função de segurança duplicada.

1. Vá para **Administração da organização \> Catálogo de endereços global \> Parâmetros do catálogo de endereços global**.
2. Na guia **Segurança de local privado**, mova a nova opção de segurança da lista **Funções disponíveis** para a lista **Funções selecionadas**.
3. Selecione **Salvar**.

![Página de parâmetros do catálogo de endereços global](media/GAD-parameters.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]