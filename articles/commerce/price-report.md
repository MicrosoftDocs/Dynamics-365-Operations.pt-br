---
title: Relatórios de preços de varejo
description: Este artigo fornece uma visão geral do recurso de relatório de preços que pode ser usado para exibir as alterações de preço futuras dos produtos variados.
author: ShalabhjainMSFT
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.region: global
ms.author: shajain
ms.search.validFrom: 2019-01-18
ms.dyn365.ops.version: AX 10.0.0
ms.custom: 16181
ms.assetid: b1b57734-1406-4ed6-8e28-21c705ee17e2
ms.search.industry: Retail
ms.search.form: ''
ms.openlocfilehash: 09350d15660978126d36199a3b4e93f6be5fe157
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269018"
---
# <a name="retail-price-reports"></a>Relatórios de preços de varejo

[!include [banner](includes/banner.md)]


A fim de fornecer preços competitivos para seus clientes, os varejistas costumam alterar os preços dos produtos. Os gerentes de lojas querem ter a capacidade de acessar facilmente as mudanças de preços recentes ou futuras para que possam planejar os recursos necessários para atualizar as etiquetas de preços exibidos nas prateleiras das lojas. Com a versão 10.0 do Retail, um gerente de loja pode abrir o relatório **Preço** navegando até **Todas as lojas \> Loja \> Relatório de preço** e exibindo os preços atualizados dos produtos associados à loja. 

Para habilitar o relatório de preço, o parâmetro **Habilitar o relatório de preço para loja** deve ser ativado. Esse parâmetro está localizado na guia **Parâmetros do Commerce \> Descontos \> Diversos**. Abrir a página **Relatório de preço** exibe uma caixa de diálogo com várias configurações. As configurações disponíveis estão listadas abaixo.

| Configuração | descrição |
|---|---|
| Data inicial/data final| O intervalo de datas para o qual o relatório de preço deve ser gerado. A duração é atualmente limitada a 7 dias. |
| Canal| A loja para a qual o relatório de preço deve ser gerado. |
| Exibir produtos com estoque disponível| Definir isso como **Sim** mostrará os preços apenas para os produtos que atualmente possuem inventário físico disponível na loja. |
| Exibir preços para grades | Definir isso como **Sim** mostrará os preços das variantes juntamente com os produtos mestre. Isso só deve ser **Ativado** se você tiver preços específicos de variantes, porque o número de linhas aumenta muito. Em versões futuras, habilitaremos os preços baseados em dimensões para que o gerente da loja possa escolher as dimensões para as quais os preços devem ser exibidos. |
| Exibir produtos com alterações de preço | Definir isso como **Sim** mostrará os preços apenas para as datas em que o preço foi alterado. O preço de *um dia antes* da **data inicial** selecionada sempre será exibido, para que o gerente da loja possa identificar facilmente os produtos que não alteraram os preços durante toda a duração selecionada e também pode exibir o preço atual. |

Depois que o relatório é gerado, o arquivo do Excel pode ser baixado para qualquer necessidade adicional de filtragem. O relatório de preços também pode ser usado para verificar os preços históricos de produtos para datas passadas.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
