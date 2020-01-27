---
title: Acesso a endereços privados por função de segurança
description: Este tópico explica como resolver o problema onde um cliente não pode acessar endereços particulares.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 58f3322ad64f7de07e17d193ff665bd6536a4070
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897088"
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
