---
title: Criar critérios de seleção de preço de venda
description: Este procedimento mostra como criar um critério de seleção preço de venda para modelos de preço de vendas baseado em atributo.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelSelectionCriteria, SysQueryForm, SysQueryTableLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ed8c60b188b7c7090546e8367455e0f58ce9359b
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3147677"
---
# <a name="create-sales-price-selection-criteria"></a>Criar critérios de seleção de preço de venda

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como criar um critério de seleção preço de venda para modelos de preço de vendas baseado em atributo. Este procedimento exige que pelo menos um modelo de preço de vendas esteja disponível. Este exemplo usa o modelo de preço para o modelo de preço de vendas de solução do Palestrante na empresa de dados demo USMF. Normalmente, um gerente de produto usa este procedimento.


## <a name="add-a-new-criterion-for-an-existing-sales-price-model"></a>Adicionar um novo critério para um modelo existente de preço de venda
1. Clique em Definição de modelo de variante de produto.
2. Clique em Modelos de configuração do produto.
3. Na lista, selecione a linha do modelo de produto de solução do Palestrante, mas não clique no link para o nome do modelo.
4. No Painel de Ação, clique em Modelo.
5. Clique em Critério de modelo de preço.
6. Clique em Novo.
7. No campo Nome, digite "Grupo de clientes 10".
    * O nome do critério de modelo de preço é usado para ajudar a identificar os critérios de seleção subjacentes.  
8. No campo Modelo de preço, insira ou selecione um valor.
9. No campo Tipo de ordem, selecione Ordem de venda.
    * O tipo de ordem determina os campos de base de dados que estão disponíveis para a consulta de seleção.  
10. No campo Validar de, insira uma data.
11. No campo Expirar em, insira uma data.
12. Clique em Salvar.

## <a name="create-the-query-for-the-selection-criteria"></a>Criar uma consulta para o critério de seleção
1. Clique em Editar.
2. No campo Tabela, selecione Clientes. 
3. No campo Campo, selecione Grupo de cliente.
    * Neste exemplo, usaremos um grupo de clientes específico para os critérios de seleção.  
4. No campo Critérios, selecione Grupo de cliente 10. 
5. Clique em OK.

