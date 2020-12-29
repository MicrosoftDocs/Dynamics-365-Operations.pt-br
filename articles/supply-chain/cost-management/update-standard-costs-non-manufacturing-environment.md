---
title: Atualizar custos padrão em um ambiente que não seja de manufatura
description: Este artigo oferece diretrizes para a atualização de custos padrão em um ambiente que não seja de fabricação.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostingVersion, InventItemPrice
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 79723
ms.assetid: 7ba0c408-2450-4042-9542-6fdf83c12e6c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 09dca3012952b739a75a6930908752fba73a4550
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422131"
---
# <a name="update-standard-costs-in-a-non-manufacturing-environment"></a>Atualizar custos padrão em um ambiente que não seja de manufatura

[!include [banner](../includes/banner.md)]

Este artigo oferece diretrizes para a atualização de custos padrão em um ambiente que não seja de fabricação.

As diretrizes a seguir pressupõem o uso de uma abordagem de duas versões para atualizar o custo padrão. Nesta abordagem, uma versão de avaliação de custo contém os custos padrão definidos originalmente para o período de congelamento, e a segunda versão de avaliação de custo contém as atualizações incrementais. Cada atualização é inserida como um registro de custo que é incluído na segunda versão de avaliação de custo, e ocasionalmente ela é habilitada. Como alternativa, a abordagem de uma versão usa o conjunto de custos padrão originalmente definido. A abordagem de duas versões requer que você defina uma segunda versão de custo. Veja as diretrizes para a definição desta versão de avaliação de custo:

-   Atribua um tipo de avaliação de custo de **Custos padrão**.
-   Atribua um identificador significativo que indique o conteúdo da versão de avaliação de custo, como **ATUALIZAÇÕES-2016**.
-   Verifique se o conteúdo inclui registros de custo.
-   Permita que os registros de custo sejam inseridos para todos os sites. Se você especificar um site, os registros de custo poderão ser inseridos somente para esse site.
-   Indique o princípio de fallback como **Nenhum**. O princípio de fallback só se aplica a cálculos de custo de itens fabricados.

Para corrigir, ajustar ou atualizar os custos padrão para novos itens, siga estas etapas.

1.  Use a página **Configuração da versão** **de avaliação de custo** para habilitar os dados de custo a serem inseridos na segunda versão de avaliação de custo. Opcionalmente impeça a ativação de custos pendentes, de forma que a ativação seja permitida depois que os custos pendentes tiverem sido definidos com exatidão e por completo. Opcionalmente, você também pode inserir uma data no campo **Data inicial**. Como diretriz geral, use a data quando você planeja habilitar as atualizações incrementais. Como alternativa, deixe o campo **Data inicial** em branco para a versão de avaliação de custos e insira uma data no campo **Data inicial** para cada registro de custo.
2.  Use a página **Preço de item** para inserir atualizações como os registros de custo do item que são incluídos na segunda versão de avaliação de custo.
3.  Use o relatório **Preços de item** para verificar a integridade e a precisão dos registros de custo de item que são incluídos na segunda versão de custo.
4.  Use a página **Manutenção de versão de avaliação de custo** para alterar o sinalizador de bloqueio para permitir a ativação dos registros de custos pendentes incluídos na segunda versão de avaliação de custo.
5.  Use a página **Preços ativos** (aberta da página **Manutenção de versão de avaliação de custo**) para ativar todos os registros de custos pendentes incluídos na segunda versão de avaliação de custo. Você também pode ativar os registros de custo pendente para itens individuais clicando no botão **Ativar preço pendente** na página **Preço de item**.
6.  Use a página **Configuração de versão de avaliação de custo** para alterar os sinalizadores de bloqueio incluídos na segunda versão de avaliação de custo para impedir a manutenção adicional de dados. As diretivas de bloqueio impedem a entrada de novos custos pendentes e a ativação de custos pendentes.




