---
title: Criar esquemas de competência
description: Este guia de tarefas aborda a criação de um esquema de competência.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
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
ms.openlocfilehash: e0ae55000a5cf1593d057d940dc3dbbf9e5cb3f3
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834869"
---
# <a name="create-accrual-schemes"></a>Criar esquemas de competência

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este guia de tarefas aborda a criação de um esquema de competência. Esta tarefa usa a empresa de demonstração USMF.

1. Vá para Contabilidade > Configuração do diário > Esquemas de competência.
2. Clique em Novo.
3. No campo Identificação de competência, digite um valor.
4. No campo Descrição do esquema de competência, digite um valor.
5. No campo Débito, especifique os valores desejados.
    * A conta principal definida substituirá a conta principal de débito na linha de comprovante do diário, bem como será usada para o estorno do diferimento com base nas transações de competência do razão.  
6. No campo Crédito, especifique os valores desejados.
    * A conta principal definida substituirá a conta principal de crédito na linha de comprovante do diário, bem como será usada para o estorno do diferimento com base nas transações de competência do razão.  
7. No campo Comprovante, selecione como deseja que o comprovante seja determinado quando as transações são lançadas.
8. No campo Descrição, digite um valor para descrever as transações que serão lançadas.
9. No campo Frequência do período, selecione a frequência com que as transações devem ocorrer.
10. No campo Número de ocorrências por período, insira um número.
11. No campo Lançar transações, selecione quando as transações devem ser lançadas, como Mensalmente.

