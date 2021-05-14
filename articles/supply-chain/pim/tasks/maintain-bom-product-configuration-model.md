---
title: Manter BOM para um modelo de configuração de produtos
description: Executar este procedimento exige um modelo de configuração de produto existente.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCBOMLineDetails, InventItemIdLookupSimple
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b4ad73265e321b6339c061a7866b55cb2769954b
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921308"
---
# <a name="maintain-bom-for-a-product-configuration-model"></a>Manter BOM para um modelo de configuração de produtos

[!include [banner](../../includes/banner.md)]

Executar este procedimento exige um modelo de configuração de produto existente. O modelo de alto-falante avançado na empresa de demonstração USMF é usado para criar este procedimento.

## <a name="add-a-bom-line"></a>Adicione uma linha da BOM

1. Vá para **Gerenciamento de informações do produto \> Produtos \> Modelos de configuração do produto**.
1. Na lista, localize e selecione o registro desejado.
    * Selecione o alto-falante avançado para este procedimento.  
1. Na lista, selecione o link na linha selecionada.
1. Expanda a seção **Linhas de BOM**.
1. Selecione **Adicionar**.
1. No campo **Nome**, digite um valor.
1. No campo **Descrição**, digite um valor.
1. Selecione **Salvar**.

## <a name="add-bom-line-details"></a>Adicione Detalhes da linha de BOM

1. Selecione **Detalhes da linha de BOM**.
2. No campo **Número do item**, insira ou selecione um valor.
    * Por exemplo, você pode selecionar o item M0055.  
    * Para cada propriedade da linha da BOM, você pode selecionar se ela tem um valor fixo ou está mapeada a um atributo.  
3. Marque a caixa de seleção **Definir**.
4. Selecione *Sim* no campo **Cálculo**.
    * Definir a propriedade **Cálculo** como *Sim* garante que a linha de BOM seja incluída em cálculos de custo.  
5. Selecione a guia **Configuração**.
6. Marque a caixa de seleção **Definir**.
7. No campo **Quantidade.**, insira um número
    * O campo Quantidade determina a quantidade do item que será incluída na BOM. Pode ser um candidato óbvio para um mapeamento de atributos.  
8. Selecione a guia **Dimensão**.
    * Verifique qualquer uma das dimensões do produto estão ativas, e consequentemente deve ter um valor ou um atributo atribuído.  
9. Selecione **OK**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]