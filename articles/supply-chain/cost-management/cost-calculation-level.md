---
title: Nível de cálculo de custo
description: Este artigo descreve o nível de BOM (lista de materiais) denominado Nível de cálculo de custos. Esse nível de BOM exclui as ordens de produção e de lotes dos cálculos.
author: JennySong-SH
ms.date: 08/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2020-04-23
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: e63a868696e36c1d4f5d19ea87bdf4d682c39f8c
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9334945"
---
# <a name="cost-calculation-level"></a>Nível de cálculo de custo

[!include [banner](../includes/banner.md)]

O nível da BOM (lista de materiais) denominado **Nível de cálculo de custos** exclui ordens de produção e ordens de lotes dos cálculos. O sistema usa esse nível quando executa cálculos de custo em versões de custo. Em processos como recálculo e fechamento do estoque, o sistema usa o nível de BOM **Nível de custo**.

## <a name="turn-the-cost-calculation-level-feature-on-or-off"></a>Ativar ou desativar o recurso Nível de cálculo de custo

Para usar esse recurso, você deve habilitá-lo no seu sistema. A partir da versão 10.0.29 do Supply Chain Management, o recurso está ativado por padrão. Os administradores podem ativar ou desativar essa funcionalidade pesquisando o recurso *Nível de cálculo de custo* no espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="example-scenario"></a>Cenário de exemplo

O cenário simples a seguir mostra as diferenças entre os níveis de BOM **Nível de cálculo de custo** e **Nível de custo**.

Você tem três produtos: A, B e C. O produto C é o componente do produto B e o produto B é o componente do produto A.

- O **Nível de custo** atribui os seguintes níveis de BOM:

    - **Produto A:** 0
    - **Produto B:** 1
    - **Produto C:** 2

- O **Nível de cálculo de custo** atribui os seguintes níveis de BOM:

    - **Produto A:** 0
    - **Produto B:** 1
    - **Produto C:** 2

Uma ordem de produção do produto C é criada e o produto A é adicionado à BOM da ordem de produção. Depois que a ordem for estimada, os níveis de BOM serão atualizados da seguinte maneira:

- O **Nível de custo** atribui os seguintes níveis de BOM:

    - **Produto B:** 1
    - **Produto C:** 2
    - **Produto A:** 3

- O **Nível de cálculo de custo** atribui os seguintes níveis de BOM:

    - **Produto A:** 0
    - **Produto B:** 1
    - **Produto C:** 2

Esse comportamento garante que as alterações em BOMs da ordem de produção não afetem os cálculos de custo subsequentes.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]