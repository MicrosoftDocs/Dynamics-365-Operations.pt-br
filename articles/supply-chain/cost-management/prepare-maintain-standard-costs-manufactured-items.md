---
title: Preparar para manter custos padrão para itens fabricados
description: Este artigo descreve as etapas de preparação para manter custos para itens fabricados.
author: JennySong-SH
ms.date: 01/17/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventStdCostConv
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 423da8022faf8066c5aa524c49c5071d0871de04
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886005"
---
# <a name="prepare-to-maintain-standard-costs-for-manufactured-items"></a>Preparar para manter custos padrão para itens fabricados

[!include [banner](../includes/banner.md)]

Este artigo descreve as etapas de preparação para manter custos para itens fabricados. As etapas para itens fabricados diferem levemente das etapas para itens comprados.

As diretivas atribuídas aos itens fabricados podem afetar os cálculos de custo para os itens pai fabricados. Para se preparar para manter custos para itens fabricados, siga estas etapas.

1. Atribua um grupo de modelo de item ao item fabricado. 

   O grupo de modelo de item identifica que custos padrão serão usados.

2. Atribua um grupo de itens ao item fabricado. 

   O grupo de itens contém contas contábeis que se aplicam ao item fabricado. As contas contábeis para um item fabricado que tem um modelo de estoque de custo padrão incluem diversas variações de produção, a variação de alteração de custo e a reavaliação de custo de estoque.

3. Atribua a unidade de medida do item para o item. 

   Os custos do item são sempre expressos na unidade de medida de estoque do item.

4. Não atribua um grupo de custos ao item fabricado, a não ser que ele seja tratado como um item comprado.

5. Atribua um grupo de cálculo de BOM (lista de materiais) ao item fabricado. 

   O grupo de cálculo de BOM do item define as condições de aviso aplicáveis. Dessa maneira, quando um cálculo de BOM for feito, mensagens de aviso sobre possíveis fontes de erros de cálculo poderão ser geradas. Por exemplo, uma mensagem de aviso pode identificar quando uma BOM ativa ou um roteiro não existe. O grupo de cálculo de BOM contém uma diretiva para interromper o detalhamento que indica quando um item fabricado deve ser tratado como um item comprado.

6. Se o item fabricado tiver custos constantes, atribua uma quantidade de ordem padrão a ele. 

   A quantidade de ordem padrão é um tamanho de lote contábil para amortização dos custos constantes. Exemplos de custos constantes incluem os tempos de configuração em operações bancárias e uma quantidade constante de componentes na BOM.

7. Defina o BOM para o item fabricado. 

   Uma ou mais versões de BOM podem ser definidas para o item fabricado. Verifique se as versões desejadas foram marcadas como aprovadas e ativas, além de terem as datas efetivas que você deseja. A versão de BOM pode abranger empresas ou ser específica para sites.

8. Defina o roteiro para o item fabricado. 

   Uma ou mais versões de roteiro podem ser definidas para o item fabricado. Verifique se as versões desejadas foram marcadas como aprovadas e ativas, além de terem as datas efetivas que você deseja. A versão de roteiro deve ser específica para sites.

Se desejar usar informações de roteiro para avaliação de custo, etapas de preparação adicionais serão necessárias. Por exemplo, as categorias de custo que são atribuídas às operações de roteiro devem estar corretas e completas.

## <a name="related-articles"></a>Artigos relacionados

[Amortizar custos constantes para um item fabricado](amortize-constant-costs-manufactured-item.md)

[Configurar produtos que podem ser produzidos ou obtidos](manufactured-items-treated-as-purchased-items.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]