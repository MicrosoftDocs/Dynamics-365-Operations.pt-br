---
title: Relatórios de preços de varejo
description: Este tópico fornece uma visão geral do recurso de relatório de preços que pode ser usado para exibir as alterações de preço futuras dos produtos variados.
author: shajain
manager: AnnBe
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16181
ms.assetid: b1b57734-1406-4ed6-8e28-21c705ee17e2
ms.search.region: global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2019-01-18
ms.dyn365.ops.version: AX 10.0.0
ms.openlocfilehash: 91c0a96abdd7df9e85e63ca6b1b47a57f3f401eb
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3021656"
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
