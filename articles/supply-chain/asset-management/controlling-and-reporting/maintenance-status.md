---
title: Status de manutenção
description: Este tópico explica como calcular o status de manutenção no Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetStatusCalculate, EntAssetStatus
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 43389db93032ec29adb805f86ae04a686803176f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422079"
---
# <a name="maintenance-status"></a>Status de manutenção

[!include [banner](../../includes/banner.md)]

 

No Gerenciamento de Ativos, você pode fazer um cálculo para obter uma visão geral de um período específico de atividades novas, ativas e concluídas de solicitações de manutenção, ordens de serviço e tempo de inatividade de manutenção. Você também pode ver o número de avaliações de condição concluídas para o mesmo período. Use esse cálculo para obter uma visão geral da carga de trabalho referente às solicitações de manutenção e ordens de serviço recebidas e concluídas.

## <a name="make-a-maintenance-status-calculation"></a>Execute um cálculo de status de manutenção

1. Clique **Gerenciamento de ativos** > **Consultas** > **Status de manutenção**.

2. Na caixa de diálogo **Calcular status**, selecione o período para o qual você deseja fazer o cálculo nos campos **Data inicial** e **Data final**.

3. Você pode usar o campo **Nível** para indicar o nível de detalhamento desejado das linhas de manutenção em relação aos locais funcionais. 

  Por exemplo, se você inserir o número "1" no campo e tiver uma estrutura de local funcional de vários níveis, todas as linhas de manutenção de um local funcional serão mostradas no nível superior e, portanto, o status de uma linha podem ser adicionado aos locais funcionais localizados em nível inferior. 
  
  Se você inserir o número "0" no campo **Nível**, verá um resultado detalhado mostrando todas as linhas de manutenção em todos os níveis do local funcional ao qual elas estão relacionadas.

4. Clique em **OK** para iniciar o cálculo.

5. Clique nos botões **Agrupar por** para mostrar o nível de detalhes necessário para o cálculo. Os botões selecionados de **Agrupar por** são realçados. Clique em um botão para ativá-los ou desativá-los.

6. Lembre-se de clicar no botão **Atualizar** para atualizar o cálculo sempre que você fizer alterações, ativando ou desativando os botões **Agrupar por** ou fazendo um cálculo para um novo período.

7. Clique em **Status** se quiser criar um novo cálculo do status de manutenção.

>[!NOTE]
>Os resultados mostrados no **Status de manutenção** somente incluem solicitações de manutenção e ordens de serviço que têm data e hora inicial real. A data e a hora de término podem estar em branco.

## <a name="example-1"></a>Exemplo 1

Na captura de tela abaixo, os botões **Ano** e **Mês** foram ativados. Com essas opções de **Agrupar por** selecionadas, você terá uma visão geral mensal da carga de trabalho e da produtividade relacionada às solicitações de manutenção e às ordens de serviço. 

![Exemplo de carga de trabalho mensal](media/13-controlling-and-reporting.png)

## <a name="example-2"></a>Exemplo 2

Na captura de tela abaixo, foram adicionadas informações sobre locais funcionais. Agora, é possível comparar a carga de trabalho e a produtividade entre os locais funcionais, que podem representar locais geográficos, fábricas ou áreas de trabalho. 

![Exemplo de carga de trabalho mensal com locais funcionais](media/14-controlling-and-reporting.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]