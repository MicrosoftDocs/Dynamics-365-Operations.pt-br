---
title: "Visão geral da reconciliação bancária avançada"
description: "Este artigo descreve o fluxo do processo de reconciliação avançado do banco. O recurso avançado de reconciliação bancária permite que você importe os extratos bancários que podem ser reconciliados automaticamente nas transações bancárias."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BankReconciliationMatchRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 22104
ms.assetid: b0705653-1fa6-4d94-9728-bcf9fb387ad1
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 00f022da597b1de2454e93123de31731c6a65962
ms.openlocfilehash: 20363ef1917f7d0796cb0d5cd8e623c598b5ee01
ms.lasthandoff: 03/31/2017


---

# <a name="advanced-bank-reconciliation-overview"></a>Visão geral da reconciliação bancária avançada

Este artigo descreve o fluxo do processo de reconciliação avançado do banco. O recurso avançado de reconciliação bancária permite que você importe os extratos bancários que podem ser reconciliados automaticamente nas transações bancárias.

O recurso de reconciliação bancária avançada permite que você importe extratos bancários. O extrato bancário importado pode ser reconciliado automaticamente nas transações bancárias. Veja as etapas do fluxo de reconciliação bancária avançada.

1.  Configurar uma importação de extrato bancário.
    -   Importar extratos bancários por meio da estrutura de entidade de dados.
    -   Três formatos de extratos bancários típicos são internos: ISO20022, BAI2, e MT940.
    -   A funcionalidade pode se estendida para qualquer formato.

2.  Configure uma sequência numérica para a reconciliação bancária avançada e defina as regras de correspondência da reconciliação bancária.
    -   Uma regra de correspondência da reconciliação é um conjunto de critérios usados para filtrar linhas de extrato bancário e Microsoft Dynamics 365 para operações deposita linhas de transação durante o processo de reconciliação. Dependendo prática comercial, você pode configurar mais de uma regra de correspondência e automatizar otimizar o processo de reconciliação.

3.  Reconciliar extratos bancários com dynamics 365 para transações bancárias de operações.
    -   Executar a correspondência e a criação automática de diários de reconciliação.
    -   Exiba os extratos bancários e o dynamics 365 para as transações bancárias de operações lado-a-lado.
    -   Lançar automaticamente o dynamics de 365 transações bancárias operações se aparece no extrato bancário e não aparece em dynamics 365 para as operações.
    -   Gere um demonstrativo da reconciliação.




