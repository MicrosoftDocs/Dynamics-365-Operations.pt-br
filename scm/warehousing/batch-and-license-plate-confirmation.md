---
title: "Confirmação de lote e placa de licença"
description: "Este tópico descreve como configurar e aplicar a confirmação de lote e placa de licença de um dispositivo móvel."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 298ac47e2253f8add1aa3938dda15afe186afbeb
ms.openlocfilehash: 70a8c18560f0cfc7a44625520f2f035a6004618a
ms.contentlocale: pt-br
ms.lasthandoff: 06/20/2017


---

# <a name="batch-and-license-plate-confirmation"></a>Confirmação de lote e placa de licença

[!include[banner](../includes/banner.md)]

A confirmação do lote permite que você confirme se o lote correto está sendo separado do dispositivo móvel. Na separação inicial do trabalho somente para itens acima do lote, no qual o *lote acima* indica que o lote é maior que a localização na hierarquia de pesquisa, você deve verificar se o lote escolhido corresponde ao lote da linha de trabalho. 

A confirmação da placa de licença permite que você confirme se a placa de licença correta está sendo selecionada do dispositivo móvel. Ao escolher o trabalho de uma localização de fase, você deve verificar se a placa de licença que foi selecionada corresponde à placa de licença associada ao trabalho. Se o trabalho for iniciado pela verificação de uma placa de licença, a etapa de confirmação será ignorada.

## <a name="where-it-applies"></a>Aplica-se a
A confirmação aplica-se nos seguintes cenários:

- A confirmação de lote aplica-se às seleções iniciais de trabalho dos itens acima do lote.
- A confirmação de placa de licença se aplica a separações de locais de fase.

## <a name="set-up-batch-and-license-plate-confirmation"></a>Configurar confirmação de lote e placa de licença
Você pode configurar a confirmação de lote e de placa de licença dos itens de menu de dispositivo móvel.  
1.  Dos itens de menu de dispositivo móvel, insira a configuração de confirmação de trabalho.  
2.  Selecione a opção para o lote ou a confirmação da placa de licença. As duas opções disponíveis para as separações por tipo de trabalho que não têm uma confirmação automática ativada.  

