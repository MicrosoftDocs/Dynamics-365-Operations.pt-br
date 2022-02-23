---
title: Copiar coprodutos de uma versão de fórmula existente
description: Este procedimento mostra como copiar coprodutos de uma versão de fórmula existente para uma versão da fórmula diferente para um produto liberado.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, BOMConsistOf, PmfFormulaCoBy, BOMRouteCopyDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 79b70ccbdac2061baf3896ecbd9449da3c38842a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4421911"
---
# <a name="copy-co-products-from-an-existing-formula-version"></a>Copiar coprodutos de uma versão de fórmula existente

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como copiar coprodutos de uma versão de fórmula existente para uma versão da fórmula diferente para um produto liberado. É um pré-requisito que haja pelo menos uma versão de fórmula associada aos coprodutos. A empresa de dados de demonstração USP2 é utilizada para criar esse procedimento.


## <a name="find-a-released-product"></a>Localize um produto lançado
1. Vá para Produtos liberados.
2. Clique em Mostrar filtros.
    * Você está prestes a adicionar o campo Tipo de produção na caixa de diálogo do filtro.  
3. Clique no campo Adicionar filtro para adicionar o campo Tipo de produção.
    * Na próxima etapa, você precisa especificar manualmente a Fórmula no campo Tipo de produção antes de selecionar Aplicar. Isso definirá o filtro na lista de produtos liberados.  
4. Insira manualmente a fórmula no campo Tipo de produção.
5. Clique em Aplicar.

## <a name="select-a-released-product"></a>Selecione um produto liberado
1. Na lista, localize e selecione o PDV desejado.
2. Clique em Versões da fórmula.
    * No Painel de Ação Engenharia, clique em versões da fórmula.  

## <a name="copy-co-products"></a>Copiar coprodutos
1. No Painel de Ação, clique em Versão da fórmula.
2. Clique em Co-produtos.
3. Clique em Copiar.
4. No campo Número do item, insira ou selecione um valor.
5. No campo Versão da fórmula, insira ou selecione um valor.
6. Clique em OK.
7. Feche a página.

