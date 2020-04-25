---
title: Item onde é usado
description: Este tópico explica como obter uma visão geral de onde o item é usado no Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: aa1f00ba6b8259221aa2b1ee460be43ee9a311b2
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3205453"
---
# <a name="item-where-used"></a>Item onde é usado

[!include [banner](../../includes/banner.md)]

 

Você pode criar um cálculo para que um item específico obtenha uma visão geral de onde o item foi usado no Gerenciamento de Ativos. Os resultados mostram o contexto no qual o item foi usado durante seu tempo de vida. A página **Item onde usado** pode ser aberta do menu principal do Gerenciamento de Ativos e também pode ser acessada das seguintes páginas:

- [BOMs de Ativos](../objects/object-BOM.md)

- [Peças sobressalentes nos padrões do tipo de ativo](../setup-for-objects/object-types.md#spare-parts-on-the-asset-type-setup)

- [Categorias do tipo de trabalho e tipos de trabalho de manutenção, grades do tipo de trabalho de manutenção, comércios de trabalho de manutenção e listas de verificação de manutenção](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md)

- [Previsão de manutenção](../work-orders/maintenance-forecasts.md)

- [Compras](../work-orders/procurement.md)

- [Compra da ordem de serviço](../work-orders/procurement.md)

## <a name="make-an-item-where-used-calculation"></a>Criar um cálculo de item onde usado

1. Clique em **Gerenciamento de ativos** > **Consultas** > **Item onde usado** ou selecione o botão **Item onde usado** em uma das páginas mencionadas acima.

2. Na caixa de diálogo **Item onde usado**, selecione o item para o qual você deseja fazer o cálculo no campo **Número do item**.

3. Você pode usar o campo **Nível** para indicar o nível de detalhamento desejado das linhas de item em relação aos locais funcionais. 

    Por exemplo, se você inserir o número “1 "no campo e tiver uma estrutura de local funcional com vários níveis, todas as linhas do item de um local funcional serão mostrados em nível superior. Portanto, relação/quantidade em uma linha podem ser adicionado de locais funcionais localizados em nível inferior. 
    
    Se você inserir o número "0" no campo **Nível**, verá um resultado detalhado mostrando todas as linhas de item em todos os níveis do local funcional ao qual elas estão relacionadas.

4. Na seção **Incluir**, selecione "Sim" nos botões de alternância que você deseja incluir no cálculo.

5. Clique em **OK**para iniciar o cálculo.

6. Na guia **Item onde usado**, selecione os botões **Agrupar por** para mostrar o nível de detalhe necessário do cálculo. Os botões selecionados de **Agrupar por** são realçados. Clique em um botão para ativá-los ou desativá-los.

7. Se quiser mostrar as dimensões relacionadas ao item, clique em **Exibir dimensões** e selecione as dimensões a serem mostradas.

## <a name="example"></a>Exemplo

Na captura de tela abaixo, você verá um exemplo de um cálculo de item onde usado para o número do item "1000".

![Exemplo de item onde cálculo usado](media/12-controlling-and-reporting.png)

