---
title: "Localizações de estoque"
description: "As localizações de estoque são usadas com o depósito básico (WMS I) para determinar onde os itens serão armazenados e onde os itens serão separados em um depósito WMS I."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: WMSLocation
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2134
ms.assetid: 69bf6922-4151-447f-b678-4ba95637f54c
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: cdf9eaeba076576d4adaa5fb5e18cd5a3f1c7b2d
ms.lasthandoff: 03/31/2017


---

# <a name="inventory-locations"></a>Localizações de estoque

[!include[banner](../includes/banner.md)]


As localizações de estoque são usadas com o depósito básico (WMS I) para determinar onde os itens serão armazenados e onde os itens serão separados em um depósito WMS I.

Este tópico se aplica aos recursos do módulo Gerenciamento de estoque. Não se aplica aos recursos do módulo de Gerenciamento de depósito.

O termo localização se refere ao lugar de onde os itens são extraídos.

Para cada localização, o lugar em que o item é inserido também deve ser especificado. Por padrão, eles são iguais. Geralmente, os itens são inseridos e extraídos do mesmo lado da localização, mas nem sempre. Por exemplo, os itens armazenados em racks de armazenamento dinâmicos são inseridos de um corredor e extraídos de outro. A entrada principal é fornecida pelo nome da localização, que geralmente é definida pelas suas coordenadas: depósito, corredor, rack, prateleira e compartimento. Esse nome ou essa ID é inserida manualmente ou gerada a partir das coordenadas da localização, por exemplo, 01-02-03-4 para o corredor 1, rack 2, prateleira 3, compartimento 4 na página Localizações de estoque.
Propriedades da localização
-------------------

Uma localização possui as seguintes características:
-   Tamanho (altura, largura e profundidade e, portanto, volume)
-   Depósito, corredor, rack, prateleira e posição do compartimento.
-   Tipo de localização (localização em massa, local de separação, doca de entrada, doca de saída, localização de entrada de produção, local de inspeção ou supermercado de kanban)

O texto de verificação pode ser utilizado nos sistemas online para verificar se o operador selecionou a localização correta para um item específico. Este texto de verificação pode ser criado manualmente ou por padrão.

## <a name="sort-codes"></a>Códigos de classificação
Use os códigos de classificação para otimizar o manuseio das linhas de separação, que descrevem as informações necessárias para a separação de itens de estoque, incluindo a ordem de separação. Os códigos de classificação podem ser especificados pelo corredor e demais coordenadas ou atribuídos manualmente à localização.

## <a name="blocked-locations"></a>Localizações bloqueadas
Ocasionalmente, talvez você queira indicar que uma localização está bloqueada por um período, por exemplo, para permitir reparos. Outras vezes, talvez você queira indicar o bloqueio somente da entrada ou da saída.
Estrutura de árvore
--------------

Na página Localizações de estoque, você pode exibir o layout do depósito em uma estrutura de árvore com base nas coordenadas das localizações de estoque, em um formato de exibição definido.
Manter localizações de estoque por meio do formulário do depósito
---------------------------------------------------

É possível copiar localizações de um depósito para outro e criar localizações por meio de um assistente. Antes de executar o assistente você deve garantir que você definiu os nomes da localização padrão na página Depósito.



<a name="see-also"></a>Consulte também
--------

[Criar um layout de depósito (Guia de tarefas)](https://ax.help.dynamics.com/en/wiki/create-a-new-warehouse-layout/)



