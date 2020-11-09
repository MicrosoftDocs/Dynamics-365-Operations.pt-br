---
title: Criar um conhecimento de embarque
description: Este tópico descreve como criar um conhecimento de embarque ao usar processos de gerenciamento de depósito.
author: MarkusFogelberg
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSBillOfLading, WHSLoadPlanningWorkbench, WHSBillOfLadingCarrier, WHSBillOfLadingOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 193583
ms.assetid: 1ad0c1cb-4346-4042-a59b-923115fac03e
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bd014f5804681936920b47e999709f153def11bc
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4016669"
---
# <a name="create-a-bill-of-lading"></a>Criar um conhecimento de embarque

[!include [banner](../includes/banner.md)]

Este tópico descreve como criar um conhecimento de embarque ao usar processos de gerenciamento de depósito.  

Um conhecimento de embarque é um documento legal entre a empresa que envia os itens e a transportadora. O documento acompanha os itens enviados, e serve como um recibo de remessa quando os itens são entregues no destino. Se você estiver usando o gerenciamento de depósito, há duas maneiras de gerar um conhecimento de embarque:

  -   Crie o relatório manualmente usando a página **Conhecimento de embarque**.
  -   Gere o relatório na **Bancada do planejamento de carga**.

Se você gerar o conhecimento de embarque na **Bancada de planejamento de carga** , o status da carga deverá ser **Enviada**. Se houver mais de uma remessa na carga, um conhecimento de embarque será criado para cada remessa. Depois que um conhecimento de embarque for criado, você poderá alterá-lo na página **Conhecimento de embarque**.

## <a name="master-bill-of-lading"></a>Conhecimento de embarque mestre
Se houver mais de uma remessa na carga, você poderá gerar um conhecimento de embarque mestre. O resultado será o mesmo layout e informações de um conhecimento de embarque, mas com conteúdo resumido de todas as remessas. Se a opção **Criar um conhecimento de embarque mestre quando houver mais de uma remessa em uma carga** for definida como **Sim** na página **Parâmetros de gerenciamento de transporte** , um conhecimento de embarque mestre será gerado automaticamente se você criar um conhecimento de embarque na **Bancada de planejamento de carga** e houver mais de uma remessa. Você também pode obter uma lista dos conhecimentos de embarque clicando em **Informações relacionadas** &gt; **Conhecimento de embarque**. Se você criar conhecimentos de embarque manualmente, poderá criar um conhecimento de embarque mestre na página **Conhecimento de embarque**.



