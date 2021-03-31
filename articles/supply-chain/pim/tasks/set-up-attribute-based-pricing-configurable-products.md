---
title: Configurar definição de preços com base no atributo para os produtos configuráveis
description: Este tópico explica como configurar preços baseados em atributos.
author: ShylaThompson
manager: tfehr
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelList, PCPriceModel, PCConstraintEditor
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e540e0f25afa65e84cdb11fb0c56437b72891f9f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5220743"
---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a>Configurar definição de preços com base no atributo para os produtos configuráveis

[!include [banner](../../includes/banner.md)]

Este tópico explica como configurar preços baseados em atributos. Como pré-requisito, você deve ter um modelo de configuração de produto com um ou vários componentes e atributos. Este exemplo usa o modelo de produto do Palestrante de avançado na empresa de dados demo USMF. Normalmente, um gerente de produto usa este procedimento.


## <a name="create-a-new-price-model"></a>Criar um novo modelo de preço
1. Selecione **Definição de modelo de variante de produto** na página inicial.
2. Selecione **Configurar modelos de produtos** na seção **links**.
3. Na lista, selecione a linha do **Palestrante avançado**, mas não selecione o link do nome.
4. No Painel de Ação, selecione **Modelo**.
5. Selecione **Modelos de preço**.
6. Selecione **Novo**.
7. No campo **Nome do modelo de preço**, digite um valor. Use um nome que torne o modelo de fácil identificação.  
8. No campo **Descrição**, digite um valor.
9. Selecione **Salvar**.

## <a name="add-price-elements"></a>Adicionar Elementos de preço
1. Selecione **Editar**. Cada componente em um modelo de produto pode ter um elemento de preço base e qualquer quantidade de regras de expressão de preço. Você também pode adicionar os preços em moedas diferentes.  
2. No campo **Expressão de preço base**, digite um valor. Por exemplo, digite 100. Uma expressão do preço base pode ser um valor numérico, ou pode consistir em um cálculo aritmético que envolve um ou mais atributos.  
3. Selecione **Adicionar**.
4. No campo **Nome**, digite `Rosewood`. O nome de expressão de preço ajuda a identificar qual elemento de preço representa. Neste exemplo, estamos criando um elemento de preço para a opção de término do gabinete do Palestrante Rosewood.  
5. Selecione **Editar condição**. Uma condição de preço ajuda a garantir que um elemento de expressão de preço seja incluído no preço de vendas apenas se uma combinação específica de atributos estiver presente.  
6. No campo **ConstraintBody**, insira `CabinetFinish=="Rosewood"`.
7. Selecione **OK**.
8. No campo **Expressão**, digite um valor. Por exemplo, digite `50`. 
9. Feche a página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]