---
title: Folhas de custos
description: A configuração da folha de custos envolve dois objetivos. Como primeiro objetivo, você define o formato para exibir as informações de custo de bens vendidos sobre um item manufaturado ou ordem de produção. A exibição formatada é nomeada folha de custos. Como segundo objetivo, você define a base para calcular custos indiretos. A configuração de folha de custo cria no recurso de grupo de custo para exibir informações e para as fórmulas de cálculo de custo indireto. Os dois objetivos da configuração de folha de custos são descritos neste artigo.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostSheetDesigner, CostSheetCalculationFactor
audience: Application User
ms.reviewer: kamaybac
ms.custom: 53201
ms.assetid: e7d72b43-3892-49ae-8821-9eede3f4d24a
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5df761015ed9382f59fa8ba7df9e5856db06287c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4987645"
---
# <a name="costing-sheets"></a>Folhas de custos

[!include [banner](../includes/banner.md)]

A configuração da folha de custos envolve dois objetivos. Como primeiro objetivo, você define o formato para exibir as informações de custo de bens vendidos sobre um item manufaturado ou ordem de produção. A exibição formatada é nomeada folha de custos. Como segundo objetivo, você define a base para calcular custos indiretos. A configuração de folha de custo cria no recurso de grupo de custo para exibir informações e para as fórmulas de cálculo de custo indireto. Os dois objetivos da configuração de folha de custos são descritos neste artigo. 

Uma folha de custos é a exibição de informações formatada sobre o custo de bens vendidos sobre um item manufaturado ou uma ordem de produção. Ao configurar uma folha de custos, você define o formato das informações e também define a base para calcular custos indiretos. A configuração de folha de custos cria recursos do grupo de custo para exibir informações e para as fórmulas que são usadas para calcular custo indireto. Aqui há mais informações sobre os dois objetivos da configuração da folha de custos:
-   **Definir o formato para a folha de custos.** O formato definido pelo usuário para uma folha de avaliação de custo identifica a segmentação de custos que contém o custo dos produtos vendidos de um item fabricado. As informações sobre custo dos produtos vendidos de um item, por exemplo, poderiam ser segmentadas em material, mão-de-obra e custos gerais indiretos, com base nos grupos de custos. Estes grupos de custos são atribuídos aos itens, categorias de custo para operações bancárias e fórmulas de cálculo de custo indireto. O formato para a folha de custos em geral precisa de totais intermediários quando forem definidos vários grupos de custos. Por exemplo, vários grupos de custos relacionados ao material podem ser agregados. A definição de um formato de folha de custos é opcional, mas um formato de folha de custos deve ser definido se custos indiretos serão calculados.
-   **Definir a base para calcular custos indiretos.** Os custos indiretos refletem os custos gerais indiretos de fabricação associados à produção de um item fabricado. Uma fórmula de cálculo de custo indireto pode ser expressa como uma sobretaxa ou uma taxa. Uma sobretaxa representa uma porcentagem de valor, enquanto uma taxa representa um valor por hora para uma operação de roteiro. Um grupo de custos define a base para a fórmula de cálculo, como uma sobretaxa de 100 por cento para um grupo de custo de trabalho ou um preço por hora de BRL 50,00 para um grupo de custos de máquina. Se quiser definir uma fórmula de cálculo e a base do grupo de custos, a configuração da folha de custos exige que você identifique o grupo de custos que representa os custos gerais indiretos e selecione se uma sobretaxa ou abordagem de taxa será usada.

Cada fórmula de cálculo deve ser inserida como um registro de custo. O registro de custo consiste em uma versão de avaliação de custo especificada, uma porcentagem de sobretaxa ou um valor de taxa, a base do grupo de custo, um status e uma data efetiva. Quando um registro de custo é inserido inicialmente, ele tem o status **Pendente** e uma data de efetivação. Quando você ativar o registro de custo, o status será atualizado de modo que o registro seja o registro ativo atual, e a data efetiva seja atualizada para a data de ativação. O registro de custo também pode especificar um site para uma fórmula de cálculo específica do site. Como alternativa, você pode deixar o campo **Site** em branco para indicar que a fórmula de cálculo é uma fórmula para toda a empresa. O registro de custo pode consistir opcionalmente em um item especificado ou um grupo de itens quando a fórmula de cálculo for sinalizada como fórmula por item. 

Os registros de custo atuais ativos para as fórmulas de cálculo de custo indireto são usados para estimar os custos da ordem de produção. Eles também são usados para calcular os custos reais relacionados ao consumo real de tempo e material. Os registros de custo pendentes são usados em cálculos da lista de materiais (BOM) para uma data futura. 

Duas políticas de bloqueio para uma versão de avaliação de custo determinam se os custos pendentes podem ser mantidos e se o custo pendente pode ser iniciado. Use as políticas de bloqueio para permitir a manutenção de dados e, consequentemente, impedir a manutenção de dados para os dados de custo em uma versão de avaliação de custo. 

Após definir o formato de folha de custos e os cálculos para os custos indiretos, você deverá executar uma etapa separada para validar e salvar as informações. A folha de custos representa um formato de toda a empresa para exibir consistentemente as informações de custos de produtos vendidos. 

A folha de custos é exibida como parte da página **Calcular custo do item**. A folha de custos pode ser exibida para um registro de custo calculado do item manufaturado na página **Preço de item** ou para um registro de cálculo específico da ordem na página **Resultados de cálculo de BOM**. Ela também pode ser exibida como parte da página **Cálculo de preço** de uma ordem de produção.





