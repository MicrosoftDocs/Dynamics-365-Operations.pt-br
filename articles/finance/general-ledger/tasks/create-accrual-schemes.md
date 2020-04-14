---
title: Criar esquemas de competência
description: Este tópico explica como criar um esquema de competência.
author: aprilolson
manager: AnnBe
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAccrualTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a83870c4cec4de2e51e90ff1889d4beff6c23f95
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3145183"
---
# <a name="create-accrual-schemes"></a>Criar esquemas de competência

[!include [banner](../../includes/banner.md)]

Este tópico explica como criar um esquema de competência. Esta tarefa usa a empresa de demonstração USMF.

1. Vá até **Painel de Navegação > Módulos > Contabilidade > Configuração do diário > Esquemas de competência**.
2. Selecione **Novo**.
3. No campo **Identificação de competência**, digite um valor.
4. No campo **Descrição do esquema de competência**, digite um valor.
5. No campo **Débito**, especifique os valores desejados. A conta principal definida substituirá a conta principal de débito na linha de comprovante do diário, bem como será usada para o estorno do diferimento com base nas transações de competência do razão.  
6. No campo **Crédito**, especifique os valores desejados. A conta principal definida substituirá a conta principal de crédito na linha de comprovante do diário, bem como será usada para o estorno do diferimento com base nas transações de competência do razão.  
7. No campo **Comprovante**, selecione como deseja que o comprovante seja determinado quando as transações são lançadas.
8. No campo **Descrição**, digite um valor para descrever as transações que serão lançadas.
9. No campo **Frequência do período**, selecione a frequência com que as transações devem ocorrer.
10. No campo **Número de ocorrências por período**, insira um número.
11. No campo **Lançar transações**, selecione quando as transações devem ser lançadas, como **Mensalmente**.

