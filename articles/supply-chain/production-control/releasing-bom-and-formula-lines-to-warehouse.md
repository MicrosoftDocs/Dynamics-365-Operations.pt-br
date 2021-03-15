---
title: Liberar linhas de BOM e fórmula para o depósito
description: Este tópico descreve o processo para liberar matéria-prima para linhas de BOM e linhas de fórmula para o depósito.
author: johanhoffmann
manager: tfehr
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysOperationTemplateForm, ProdParmReleaseToWarehouse, WHSReleaseToWarehouseProdBOM
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: ba042e708d63766941cc3ebfc375872e384f0f0b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5011024"
---
# <a name="release-bom-and-formula-lines-to-the-warehouse"></a>Liberar linhas de BOM e fórmula para o depósito

[!include [banner](../includes/banner.md)]

Este tópico descreve o processo para liberar matéria-prima para linhas de BOM e linhas de fórmula para o depósito. Quando você libera uma linha da BOM e da fórmula para o depósito, o sistema determina primeiro se o material já está disponível no local de entrada de produção no chão de fábrica em que o material será consumido para o processo de produção.

- Se o material estiver disponível no local de entrada de produção, é separado desse local imediatamente após o sinal ser fornecido para a liberação do material para o depósito.
- Se o material não estiver disponível no local de entrada de produção, a liberação do material indique que o material deve ser movido de locais do depósito para o local de entrada de produção. O material é movido através do trabalho de depósito para separação de matérias-primas. Portanto, os processos de depósito para a separação de matérias-primas deverão ser configurados. Para obter mais informações, consulte [Visão geral de reabastecimento](../warehousing/replenishment.md) e [Controlar o trabalho do depósito por meio de modelos de trabalho e diretivas de localização](../warehousing/control-warehouse-location-directives.md).

## <a name="methods-for-releasing-bom-and-formula-lines"></a>Métodos para liberar linhas da BOM e da fórmula

Você pode configurar linhas da BOM e da fórmula de forma que isso ocorra como parte da liberação de uma ordem de produção ou de lote. Se preferir, a versão pode ser controlada por um trabalho em lotes ou ser feita como uma interação manual.

O método usado para liberar linhas da BOM e da fórmula é controlado pelo parâmetro **Liberação da linha de produção**. Você pode localizar este parâmetro em **Controle de produção** \> **Configuração** \> **Parâmetros de produção**.

- **Liberar linhas da BOM e da fórmula como parte da liberação de uma ordem de produção ou de lote** – Neste método, as linhas da BOM e da fórmula de uma ordem de produção ou de lote são liberadas como parte do processo de liberação da ordem. Geralmente, durante a liberação de uma ordem de produção ou de lote, os trabalhos de produção são liberados a trabalhadores de chão de fábrica e os documentos de produção são impressos. Durante esse processo, o status da ordem também muda para **Liberado**.
- **Liberar linhas da BOM e da fórmula por meio de um trabalho em lotes ou como uma interação manual** – Neste método, as linhas da BOM e da fórmula podem ser liberadas apenas através do trabalho em lotes **Versão automática das linhas da BOM e da fórmula** ou como uma interação manual. Para liberar manualmente as linhas da BOM e da fórmula, a página de listagem da ordem de produção ou de detalhes da ordem de produção, no painel de ações, selecione **Liberar para o depósito**.

Para uma demonstração rápida de como liberar a BOM e as linhas de fórmula para produção usando um trabalho em lotes, assista a esse breve vídeo no YouTube: [Liberar escolha de produção para o depósito em lote](https://www.youtube.com/watch?v=8urAJn50dQ8).

## <a name="releasing-the-bom-and-formula-lines-by-using-a-batch-job"></a>Liberando as linhas da BOM e da fórmula usando um trabalho em lotes

Os trabalhos em lotes da **Liberação automática das linhas da BOM e da fórmula** são feitos por meio das linhas da BOM e da fórmula selecionadas que têm uma quantidade restante para liberar. Os trabalhos consideram somente ordens que têm um status **Liberado**, **Iniciado** ou **Informado como concluído**. Se uma linha da BOM ou da fórmula tiver uma quantidade restante para liberar, o trabalho libera a quantidade que pode ser coberta pela quantidade que já foi reservada fisicamente e a quantidade que está disponível fisicamente.

### <a name="example-of-a-batch-job-release"></a>Exemplo de uma liberação de trabalho em lote

| Cenário | Quantidade restante a ser liberada | Quantidade reservada fisicamente | Quantidade disponível fisicamente | Quantidade liberada pelo trabalho em lotes |
|----------|-------------------------------|------------------------------|-------------------------------|------------------------------------|
| 1        | 100                           | 20                           | 90                            | 100                                |
| 2        | 100                           | 20                           | 70                            | 90                                 |
| 3        | 100                           | 0                            | 90                            | 90                                 |
| 4        | 100                           | 0                            | 110                           | 100                                |
| 5        | 100                           | 20                           | 0                             | 20                                 |

### <a name="batch-job-setup"></a>Configuração de trabalho em lotes

Na consulta do trabalho em lotes **Liberação automática das linhas da BOM e da fórmula**, você pode configurar um critério de filtragem para especificar quantos dias depois o trabalho deve procurar por linhas que têm quantidades não liberadas. Na consulta do trabalho, no campo **Data da matéria-prima**, use a função **(LessThanDate())** como um critério de filtragem.

A ilustração a seguir mostra uma ordem de produção que tem dois trabalhos, 10 e 20, que abrange a montagem e embalagem da ordem de produção. Cada trabalho é configurado para consumir uma quantidade de material. Nesta ilustração, o limite de tempo de liberação que é indicada pela seta verde abaixo da linha do tempo é igual ao número de dias que foi especificado no critério **(LessThanDate())**. Por exemplo, **(LessThanDate (2))** indica que o trabalho deverá procurar quantidades não liberadas somente dentro de um limite de tempo de dois dias.

![Exemplo de uma ordem de produção que tem dois trabalhos em lote](media/bach-job-setup.PNG)

## <a name="releasing-material-per-operation-number-or-in-proportion-to-the-amount-of-finished-goods"></a>Liberando material por número de operação ou em relação ao valor de mercadorias acabadas

Se você liberar materiais usando a definição do parâmetro **Na liberação da ordem de produção**, quando você faz a liberação manual, você tem duas opções para controlar a liberação do material:

- Liberar material por número de operação.
- Liberar material em relação ao valor de mercadorias acabadas.

### <a name="release-material-per-operation-number"></a>Liberar material por número de operação

Para controlar as operações nas quais o material deve ser liberado, use a página **Liberar para o depósito**.

- Selecione **Controle de produção** \> **Ordens de produção** \> **Todas as ordens de produção**, selecione uma ordem de produção e na guia **Depósito**, selecione **Liberar para o depósito**. Depois use os campos **Da Oper. N°** e **Para Oper. N°** para especificar a faixa de números da operação.

A ilustração a seguir mostra uma ordem de produção que tem duas operações, 10 e 20. Neste exemplo, se você limitar a liberação para operação 10, somente o material M9203 será liberado.

![Exemplo da liberação de material por número da operação](media/two-operations.PNG)

Para obter uma demonstração rápida de como liberar o material de acordo com a quantidade de mercadorias, assista a esse breve vídeo no YouTube sobre [aprimoramentos no processo de liberação da ordem de produção](https://www.youtube.com/watch?v=Rm3ojAz6Zu0).

### <a name="release-material-in-proportion-to-the-amount-of-finished-goods"></a>Liberar material em relação ao valor de mercadorias acabadas

Você pode liberar a matéria-prima para uma quantidade parcial de mercadorias concluídas ou em uma unidade específica.

- Para liberar a matéria-prima para uma quantidade parcial de mercadorias acabadas, selecione **Controle de produção** \> **Ordens de produção** \> **Todas as ordens de produção**, selecione uma ordem de produção e na guia **Depósito**, selecione **Liberar para depósito**. Insira a quantidade no campo **Quantidade**.

    Por exemplo, uma ordem de produção é criada e planejada para 1,000 peças (pcs.). O supervisor do chão de fábrica está planejando a produção de 100 peças para o próximo turno e quer liberar materiais somente para esse turno. Neste caso, o supervisor pode usar o campo **Quantidade** para liberar os materiais de 100 peças isso está planejado para próximo turno.

- Para liberar matéria-prima em uma unidade específica, selecione **Controle de produção** \> **Ordens de produção** \> **Todas as ordens de produção**, selecione uma ordem de produção e na guia **Depósito**, selecione **Liberar para depósito**. Use o campo **Unidade** para selecionar a unidade de mercadoria acabada na qual será liberado o material.

    As unidades disponíveis estão definidas no ID do grupo de sequências da unidade da mercadoria acabada.

    Por exemplo, uma mercadoria acabada tem a seguinte conversão de unidades entre as libras (lbs.) e o palete (PL): 1 PL = 100 libras. Para criar uma ordem de produção para 10.000 libras das mercadorias acabadas, você pode liberar matérias-primas para o número de paletes que você pretende produzir. Selecione **PL** como a unidade e um número correspondente no campo **Quantidade**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]