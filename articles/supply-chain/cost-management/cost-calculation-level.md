---
title: Nível de cálculo de custo
description: Este tópico descreve o nível de BOM (lista de materiais) denominado Nível de cálculo de custos. Esse nível de BOM exclui as ordens de produção e de lotes dos cálculos.
author: AndersGirke
ms.date: 04/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-23
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: f7cde239107528a6bc2aeb0e424d024d4f3fb2a6
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5839478"
---
# <a name="cost-calculation-level"></a>Nível de cálculo de custo

O nível da BOM (lista de materiais) denominado **Nível de cálculo de custos** exclui ordens de produção e ordens de lotes dos cálculos. O sistema usa esse nível quando executa cálculos de custo em versões de custo. Em processos como recálculo e fechamento do estoque, o sistema usa o nível de BOM **Nível de custo**.

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