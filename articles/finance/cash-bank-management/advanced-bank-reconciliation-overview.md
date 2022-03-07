---
title: Visão geral da reconciliação bancária avançada
description: Este artigo descreve o fluxo do processo de reconciliação avançado do banco. O recurso avançado de reconciliação bancária permite que você importe os extratos bancários que podem ser reconciliados automaticamente nas transações bancárias.
author: panolte
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankReconciliationMatchRule
audience: Application User
ms.reviewer: roschlom
ms.custom: 22104
ms.assetid: b0705653-1fa6-4d94-9728-bcf9fb387ad1
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1f85ece0b25237c194777b41566860c49d4b9d39
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5258199"
---
# <a name="advanced-bank-reconciliation-overview"></a>Visão geral da reconciliação bancária avançada

[!include [banner](../includes/banner.md)]

Este artigo descreve o fluxo do processo de reconciliação avançado do banco. O recurso avançado de reconciliação bancária permite que você importe os extratos bancários que podem ser reconciliados automaticamente nas transações bancárias.

O recurso de reconciliação bancária avançada permite que você importe extratos bancários. O extrato bancário importado pode ser reconciliado automaticamente nas transações bancárias. Veja as etapas do fluxo de reconciliação bancária avançada.

1.  Configurar uma importação de extrato bancário.
    -   Importar extratos bancários por meio da estrutura de entidade de dados.
    -   Três formatos de extratos bancários típicos são internos: ISO20022, BAI2, e MT940.
    -   A funcionalidade pode se estendida para qualquer formato.

2.  Configure uma sequência numérica para a reconciliação bancária avançada e defina as regras de correspondência da reconciliação bancária.
    -   Uma regra de correspondência de reconciliação é um conjunto de critérios usados para filtrar as linhas do extrato bancário e as linhas de transações bancárias no Microsoft Dynamics 365 Finance durante o processo de reconciliação. Dependendo da prática empresarial, você pode configurar mais de uma regra de correspondência para automatizar e otimizar o processo de reconciliação.

3.  Reconciliar extratos bancários com as transações bancárias do Finance.
    -   Executar a correspondência e a criação automática de diários de reconciliação.
    -   Visualizar extratos bancários e as transações bancárias do Finance lado a lado.
    -   Lance as transações bancárias do Finance automaticamente se elas forem exibidas no extrato bancário, mas não aparecerem no aplicativo Finance.
    -   Gere um demonstrativo da reconciliação.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]