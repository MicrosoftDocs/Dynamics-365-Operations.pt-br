---
title: Controle de horas de trabalho
description: Este tópico explica o controle de hora de trabalho no Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 916e7b8d5d494dbae0659504957f7f0798a6834b
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918363"
---
# <a name="work-hour-control"></a>Controle de horas de trabalho

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

No Gerenciamento de ativos, é possível calcular as horas para obter uma visão geral de horas reais em comparação com as horas de orçamento em ativos, locais funcionais ou ordens de serviço. As horas reais são baseadas em transações lançadas.

## <a name="work-hour-control-for-assets-functional-locations-and-work-orders"></a>Controle de hora de trabalho para ativos, locais funcionais e ordens de serviço

Os cálculos efetuados para ativos, locais funcionais e ordens de trabalho são quase idênticos. A única diferença é que para ativos e locais funcionais, você também podem incluir subativos e sub-locais em seu cálculo. A data é a data da transação quando o registro foi feito.

1. Clique em **Gerenciamento de ativos** > **Consultas** > **Ativos** > **Controle de horas de ativos** ou **Controle de horas do local funcional**, ou **Gerenciamento de ativos** > **Consultas** > **Ordens de serviço** > **Controle de horas da ordem de serviço**.

2. Na caixa de diálogo **Controle de horas de ativo**.

3. Na caixa de diálogo **Controle de horas de ativo** / **Controle de horas do local funcional** / **Controle de horas da ordem de serviço**, selecione um período a ser calculado nos campos **De** e **Até**.

4. Se necessário, selecione um **Conjunto de dimensões financeiras** para ser incluído no cálculo.

5. Selecione "Sim" no botão de alternância **Ignorar zero** se não desejar exibir resultados contendo zero horas.

6. Você pode usar o campo **Nível** para indicar o nível de detalhamento desejado das linhas de controle de hora em relação aos locais funcionais. Por exemplo, se você inserir o número "1" no campo e tiver uma hierarquia de localização funcional em vários níveis, todas as linhas de controles de horas para um local funcional serão mostradas no nível superior e, portanto, as horas em uma linha poderão ser adicionadas em locais funcionais localizados em um nível inferior. Se você inserir o número "0" no campo **Nível**, verá um resultado detalhado mostrando todas as linhas de controle de horas em todo o nível do local funcional ao qual elas estão relacionadas.

7. Selecione "Sim" no botão de alternância **incluir subativos** para exibir custos relacionados a subativos como linhas separadas.

8. Para limitar a pesquisa, você poderá selecionar ativos específicos/locais funcionais/ordens de trabalho na Guia Rápida **Registros a serem incluídos**.

9. Clique em **OK**para iniciar o cálculo.

10. Nos grupos do painel de ação **Agrupar por...** na página **Controle de custos de ativos**, clique nos botões relevantes para mostrar o nível de detalhe necessário do cálculo. Os botões do painel de ações selecionados são destacados. Clique em um botão para ativá-los ou desativá-los.

A figura abaixo mostra um exemplo de cálculo de **Controle de hora de ativo**.

![Figura 1](media/04-controlling-and-reporting.png)

Outra maneira de fazer um cálculo de uma hora é selecionar vários ativos em **Todos os ativos** ou **Ativos válidos**. Em seguida, clique no botão **Controle de horas** na Guia Rápida **Geral**. Os ativos selecionados são inseridos automaticamente no campo **Ativo** na Guia Rápida **Registros a incluir**. Clique em **OK** na caixa de diálogo **Controle de horas de ativo** e o cálculo para os ativos selecionados é exibido. O mesmo procedimento pode ser feito para locais funcionais em **Todos os locais funcionais** ou **Locais funcionais ativos**, e para ordens de serviço **Todas as ordens de serviço** ou **Ordens de serviço ativas**.

>[!NOTE]
>O campo **Orçamento original** mostra as horas do orçamento da previsão da ordem de serviço. O campo **Horas reais** mostra as horas lançadas nas ordens de serviço. O campo **Horas comprometidas** mostra a quantidade de horas totais com os quais sua empresa está comprometida em relação às ordens de serviço.

