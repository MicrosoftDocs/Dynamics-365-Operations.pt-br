---
title: Configurar definição de preços com base no atributo para produtos configuráveis
description: Este artigo explica como configurar preços baseados em atributos.
author: t-benebo
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelList, PCPriceModel, PCConstraintEditor
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ec16a0a8078cddd433c99592aa4a7474cf923aec
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8849377"
---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a>Configurar definição de preços com base no atributo para produtos configuráveis

[!include [banner](../../includes/banner.md)]

Este artigo explica como configurar preços baseados em atributos. Como pré-requisito, você deve ter um modelo de configuração de produto com um ou vários componentes e atributos. Este exemplo usa o modelo de produto do Palestrante de avançado na empresa de dados demo USMF. Normalmente, um gerente de produto usa este procedimento.


## <a name="create-a-new-price-model"></a>Criar um novo modelo de preço

1. Acesse **Gerenciamento de informações do produto \> Produtos \> Modelos de configuração do produto**.
1. Na lista, selecione a linha do **Palestrante avançado**, mas não selecione o link do nome.
1. No Painel de Ação, selecione **Modelo**.
1. Selecione **Modelos de preço**.
1. Selecione **Novo**.
1. No campo **Nome do modelo de preço**, digite um valor. Use um nome que torne o modelo de fácil identificação.  
1. No campo **Descrição**, digite um valor.
1. Selecione **Salvar**.

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