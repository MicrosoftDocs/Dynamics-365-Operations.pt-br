---
title: Liberar ordens de produção
description: Uma ordem de produção liberada é uma ordem que foi autorizada para produção. O termo Liberada é usado para descrever um estado no ciclo de vida da ordem de produção, no qual a ordem de produção está disponível para a execução do chão de fábrica de produção para os processos de depósito.
author: johanhoffmann
ms.date: 03/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProdParmRelease
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2414
ms.assetid: 50c2257b-2924-44f5-b7c1-11f498092053
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 740ac516ffa01d8930aedabb9873834b07b7debf700dc61b14d93ac8d6dcd086
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6718861"
---
# <a name="release-production-orders"></a>Liberar ordens de produção

[!include [banner](../includes/banner.md)]

Uma ordem de produção liberada é uma ordem que foi autorizada para produção. O termo Liberada é usado para descrever um estado no ciclo de vida da ordem de produção, no qual a ordem de produção está disponível para a execução do chão de fábrica de produção para os processos de depósito.

## <a name="characteristics-of-the-released-state"></a>Características do estado Liberado

O estado **Liberado** é um estado no ciclo de vida da ordem de produção. As ordens de produção que estão no estado **Liberado** ficam disponíveis para a execução no chão de fábrica de produção e para os processos do depósito. O estado **Liberado** tem as seguintes características:

- Uma ordem de produção pode ser alterada para o estado **Liberado** da ordem de produção ou por meio de um processo em lote. A ordem de produção também pode ser atualizada automaticamente de ordens de produção planejadas que foram confirmadas usando o campo **Limite de tempo de confirmação** na página **Planejamento mestre**.
- O estado **Liberado** é o sinal dos operadores de chão de fábrica (operadores) para iniciar a execução dos trabalhos de produção no chão de fábrica.
- Os documentos de produção, como cartões de roteiro, roteiros de trabalho e fichas de trabalho fornecem informações sobre trabalhos de produção e podem ser emitidos.
- Para os materiais que são reservados fisicamente, o trabalho do depósito é gerado para escolher materiais da ordem de produção.

## <a name="releasing-jobs-to-the-shop-floor"></a>Liberação de trabalhos para o chão de fábrica

Depois que uma ordem de produção for liberada, os trabalhos de produção relacionados à ordem ficarão visíveis e prontos para o registro. Os operadores podem fazer inscrições de trabalhos, como Iniciar, Parar e Concluir na página **Termino do cartão de trabalho** ou página **Dispositivo de cartão de trabalho**. O tempo e a quantidade registrados são automaticamente transferidos das páginas de registro para revistas de produção para acompanhar o tempo e a quantidade consumidos.

## <a name="route-cards"></a>Cartões de roteiro

Os cartões de roteiro fornecem uma visão geral das informações provenientes das configurações de roteiros e operações e dos métodos de agendamento de operações e trabalho.

## <a name="route-jobs"></a>Roteiros de trabalho

Os roteiros de trabalho listam cada trabalho de uma operação em detalhes e incluem os tempos de configuração, processamento, espera e transporte. Por exemplo, uma operação como pintura poderá exigir trabalhos individuais, como tempo de configuração, tempo de execução para o processo de pintura e tempo de espera para a secagem.

## <a name="job-cards"></a>Fichas de trabalho

As fichas de trabalho listam os números dos trabalhos individuais de determinada operação. Um trabalho aparece em cada página. Os trabalhos incluídos em uma ficha de trabalho e seus tempos estimados baseiam-se nas informações de configuração de roteiros e operações. De uma ficha de trabalho, você pode abrir a página **Linhas do diário de produção**, **ficha de trabalho**. As pessoas que executam recursos de operações podem fornecer comentários sobre os processos de produção. Existem campos onde você pode inserir estatísticas de consumo e informações como a quantidade com erros.

## <a name="warehouse-work-for-raw-material-picking"></a>Trabalho de depósito para a separação de matéria-prima

O trabalho para a separação de matéria-prima é gerado durante a liberação. O trabalho é gerado apenas para a quantidade de materiais que foram fisicamente reservados para a ordem de produção antes da ordem ter sido liberada. A seguinte configuração é necessária para gerar trabalho de armazenamento para coleta de matérias-primas:

- Uma diretiva da localização da separação de matéria-prima que determina o local do depósito para escolher os materiais
- Um modelo de onda para matérias-primas, onde as políticas para a execução do trabalho de depósito são configuradas
- Uma localização de entrada de produção que determina onde os materiais são colocados

Ao usar locais controlados de placa de licença, você pode escolher se a quantidade encomendada ou a quantidade total disponível do item deve ser separada durante o processamento do trabalho de separação de matéria-prima. Para configurar essa opção:

1. Acesse **Gerenciamento de informações sobre produtos \> Produtos \> Produtos liberados** e abra o item relevante.
1. Expanda a FastTab **Depósito**.
1. Selecione uma das seguintes opções para o campo **Separação de materiais em locais de placa de licença**:
    - *Separação de ordens*: somente a quantidade encomendada deve ser separada.
    - *Preparação*: sempre que possível, a quantidade total disponível na placa de licença deve ser separada. Para que um trabalhador possa separar a quantidade total da placa de licença, a placa de licença não deve conter itens mistos e não deve ter dimensões mistas. Se a placa de licença contiver dimensões ou itens mistos, a separação continuará como se estivesse definida como *Separação de ordens*.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]