---
title: Grupos de contas de consolidação e contas adicionais de consolidação
description: Este tópico fornece informações sobre grupos de contas de consolidação e contas de consolidação adicionais e explica como eles são usados.
author: panolte
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerConsolidateAccountGroup
audience: Application User
ms.reviewer: kfend
ms.custom: 265544
ms.assetid: 71c31df7-b655-46a8-8844-4f92a8bd71b0
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 5ca7a50fcac53f1636da15b2d7977174b087ac25
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2022
ms.locfileid: "8711683"
---
# <a name="consolidation-account-groups-and-additional-consolidation-accounts"></a>Grupos de conta de consolidação e contas de consolidação adicionais

[!include [banner](../includes/banner.md)]

Este tópico fornece informações sobre grupos de contas de consolidação e contas de consolidação adicionais e explica como eles são usados.

## <a name="consolidation-account-groups"></a>Grupos de contas de consolidação

Grupos de contas de consolidação permitem que você crie grupos das contas que deseja usar para consolidar dados. Normalmente, um grupo de contas de consolidação representa um plano de contas exigido pelo governo. Um grupo de contas de consolidação também pode mapear contas para um grupo definido pela matriz da empresa. Você pode encontrar grupos de conta de consolidação na área **Configuração** do módulo **Consolidações**. Ao adicionar um novo grupo, você insere um identificador exclusivo para o grupo de conta, além de um nome.

## <a name="additional-consolidation-accounts"></a>Contas de consolidação adicionais
Contas de consolidação adicionais permitem atribuir uma conta de um plano de contas existente a um grupo de contas de consolidação. Você pode então especificar um valor e um nome de conta de consolidação. 

Você pode encontrar contas de consolidação adicionais na área **Configuração** do módulo **Consolidações**. Ao criar uma conta de consolidação, você deve especificar as seguintes informações:

-   **Conta principal** – Este campo é uma pesquisa que mostra todas as contas principais com base no plano de contas selecionado por você na página. Ao selecionar uma conta, o nome é automaticamente inserido no campo **Nome da conta principal**.
-   **Grupo de contas de consolidação** – Use esse campo para especificar o grupo ao qual a conta será atribuída. Se houver consolidação de duas formas diferentes, você deve adicionar a mesma conta a todos os quatro grupos de contas de consolidação.
-   **Conta de consolidação** – Insira o valor da conta de consolidação. Não é preciso que esse valor seja uma conta de um plano de contas. Pode ser qualquer valor que você solicitar.
-   **Nome da conta de consolidação** – Insira o nome da conta da forma como ele deve ser exibido nas consultas e nos relatórios.
-   **Nível SAT** – Este campo é usado para declarar demonstrativos de conta às autoridades fiscais mexicanas. 

Após ter concluído a criação de seus grupos de contas de consolidação e contas de consolidação adicionais, você poderá selecionar o grupo no Processo de consolidação online.


Para obter mais informações, consulte [Criar grupos de consolidação e contas de consolidação adicionais](../general-ledger/tasks/create-consolidation-groups.md). 





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
