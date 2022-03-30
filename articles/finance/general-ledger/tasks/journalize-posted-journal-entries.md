---
title: Lançar em diário entradas de diário
description: Este procedimento aborda como lançar em diário entradas de diário postadas.
author: aprilolson
ms.date: 03/09/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerParameters, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8d8fca167563b14c825ebe29874c6488ddfb4d9a
ms.sourcegitcommit: 06acdfbccd7bd213a2397ea7b85d104f01914437
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/10/2022
ms.locfileid: "8400866"
---
# <a name="journalize-posted-journal-entries"></a>Lançar em diário entradas de diário

[!include [banner](../../includes/banner.md)]

O processo de lançar em diário na contabilidade é uma forma de agrupar e informar entradas de comprovante lançadas na contabilidade. Com base nos critérios fornecidos, o processamento gera uma lista de comprovantes que usam uma sequência numérica única e que têm o valor de **número diário** de contabilidade como referência.

Siga estas etapas para lançar entradas em diário. Este procedimento usa a empresa de dados de demonstração **USMF**.

1. Acesse **Contabilidade** \> **Configuração do razão** \> **Parâmetros da contabilidade**.
2. No campo **Diário-razão estendido**, selecione um valor. Se você selecionar **Sim**, as versões de relatório serão diferentes.
3. Selecione se o período pode ser inserido se o processo se lançando em diário não foi executado. Se você selecionar **Sim**, o período não poderá ser fechado até o processo se lançando em diário foi preenchido para o período.
4. Feche a página.
5. Acesse **Contabilidade** \> **Tarefas periódicas** \> **Lançamento em diário** e selecione **Filtrar**.
6. Selecione a linha dos critérios do filtro que você deseja definir.
7. No campo **Critérios**, informe ou selecione os critérios do filtro.
8. Selecione **OK** para fechar a página.
9. Selecione **OK** para iniciar o processo de lançamento em diário. Um relatório será gerado depois que o processo foi concluído.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
