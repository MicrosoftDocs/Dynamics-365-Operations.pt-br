---
title: Fabricantes e modelos de ativo
description: Este tópico explica como configurar fabricantes de ativo e modelos relacionados no Asset Management.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetProductLookup, EntAssetModelLookup, EntAssetProduct
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ae2dfcebcbab77cba1795a8b559a3a4244abd00e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422088"
---
# <a name="asset-manufacturers-and-models"></a>Fabricantes e modelos de ativo

[!include [banner](../../includes/banner.md)]

 

Este tópico explica como configurar fabricantes de ativo e modelos relacionados no Asset Management. Os modelos podem ser relacionados aos tipos de ativo.

## <a name="set-up-product-model-relations"></a>Configurar relações entre produtos e modelos

1. Selecione **Gerenciamento de ativos** \> **Configuração** \> **Ativos** \> **Fabricante e modelo**.
2. Selecione **Novo** para criar um novo produto.
3. No campo **Fabricante**, insira um nome para o fabricante do ativo.
4. No campo **Descrição**, insira uma descrição.
5. Na Guia Rápida **Modelos**, selecione **Adicionar** para criar um modelo de ativo que deva estar relacionado ao fabricante do ativo.
6. No campo **Modelo**, insira um nome para o modelo do ativo.
7. No campo **Descrição**, insira uma descrição.
8. No campo **Tipo de ativo**, selecione o tipo de ativo ao qual o modelo do fabricante deve estar relacionado.

    > [!NOTE]
    > Você também pode configurar relações para tipos, fabricantes e modelos de ativo na pesquisa **Tipos de ativo**. Para saber mais, consulte [Tipos de ativo](../setup-for-objects/object-types.md).

    Na Guia Rápida **Detalhes**, o campo **Modelos** mostra o número de modelos de ativo configurados no fabricante do ativo selecionado. O campo **Ativos** mostra o número de ativos que usam o fabricante selecionado.
    
    O campo **Ativos** mostra o número de objetos que usam o modelo do fabricante.

> [!NOTE]
> Um tipo de ativo pode não ter nenhuma relação de modelo do fabricante, pode estar relacionado a um modelo do fabricante do ativo ou pode estar relacionado a vários modelos do fabricante do ativo. Se um tipo de ativo estiver relacionado a pelo menos um modelo do fabricante, apenas as combinações configuradas na pesquisa **Modelo do fabricante** poderão ser selecionadas nas páginas do Asset Management onde uma combinação de um tipo, fabricante e modelo de ativo pode ser configurada. Essas páginas incluem **Todos os ativos**, **Níveis de serviço de ativo**, **Padrões do tipo de trabalho** e **Linhas de orçamento de manutenção**. Se alguns tipos de ativo não estiverem relacionados a um modelo do fabricante, somente esses tipos de ativo, e os modelos do fabricante que também não tenham relação aos tipos de ativo, serão mostrados nas páginas.

## <a name="select-a-manufacturer-and-model-on-an-object"></a>Selecionar um fabricante e modelo em um objeto

1. Selecione **Gerenciamento de ativos** \> **Comum** \> **Ativos** \> **Todos os ativos**.
2. Na coluna **Ativo**, selecione o link para o ativo. A página **Detalhes** aparece.
3. Selecione **Editar**.
4. Na Guia Rápida **Geral**, selecione valores nos campos **Fabricante** e **Modelo**.
