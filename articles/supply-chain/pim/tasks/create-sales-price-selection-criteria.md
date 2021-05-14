---
title: Criar critérios de seleção de preço de venda
description: Este procedimento mostra como criar um critério de seleção preço de venda para modelos de preço de vendas baseado em atributo.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelSelectionCriteria, SysQueryForm, SysQueryTableLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 69d22c3321beaa2667ee20bff00acd746714b993
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920522"
---
# <a name="create-sales-price-selection-criteria"></a>Criar critérios de seleção de preço de venda

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como criar um critério de seleção preço de venda para modelos de preço de vendas baseado em atributo. Este procedimento exige que pelo menos um modelo de preço de vendas esteja disponível. Este exemplo usa o modelo de preço para o modelo de preço de vendas de solução do Palestrante na empresa de dados demo USMF. Normalmente, um gerente de produto usa este procedimento.

## <a name="add-a-new-criterion-for-an-existing-sales-price-model"></a>Adicionar um novo critério para um modelo existente de preço de venda

1. Vá para **Gerenciamento de informações do produto \> Produtos \> Modelos de configuração do produto**.
1. Na lista, selecione a linha do modelo de produto de solução do Palestrante, mas não selecione o link para o nome do modelo.
1. No Painel de Ação, selecione **Modelo**.
1. Selecione **Critérios de modelo de preço**.
1. Selecione **Novo**.
1. No campo **Nome**, digite 'Grupo de clientes 10'.
    * O nome do critério de modelo de preço é usado para ajudar a identificar os critérios de seleção subjacentes.  
1. No campo **Modelo de preço**, insira ou selecione um valor.
1. No campo **Tipo de ordem**, selecione *Ordem de venda*.
    * O tipo de ordem determina os campos de base de dados que estão disponíveis para a consulta de seleção.  
1. No campo **Válido a partir de**, informe uma data.
1. No campo **Expirar em**, informe uma data.
1. Selecione **Salvar**.

## <a name="create-the-query-for-the-selection-criteria"></a>Criar uma consulta para o critério de seleção

1. Selecione **Editar**.
2. No campo **Tabela**, selecione *Clientes*.
3. No campo **Campo**, selecione *Grupo de clientes*.
    * Neste exemplo, usaremos um grupo de clientes específico para os critérios de seleção.  
4. No campo **Critérios**, selecione *Grupo de clientes 10*.
5. Selecione **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]