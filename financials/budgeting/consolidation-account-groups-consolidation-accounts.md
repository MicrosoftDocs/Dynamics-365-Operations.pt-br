---
title: "Grupos da consolidação e contas adicionais de consolidação"
description: "Este tópico fornece informações sobre grupos da consolidação e contas adicionais de consolidação, e explica como são usadas no Microsoft Dynamics 365 para as operações."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 265544
ms.assetid: 71c31df7-b655-46a8-8844-4f92a8bd71b0
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 9f4d7fdd8cfa7a540fce219f6ae4792e57dfbe44
ms.openlocfilehash: f9c5aaa389c9c2f85d1ab91cbf3d2222cbebef55
ms.lasthandoff: 03/31/2017


---

# <a name="consolidation-account-groups-and-additional-consolidation-accounts"></a>Grupos da consolidação e contas adicionais de consolidação

Este tópico fornece informações sobre grupos da consolidação e contas adicionais de consolidação, e explica como são usadas no Microsoft Dynamics 365 para as operações.

<a name="consolidation-account-groups"></a>Grupos de contas de consolidação
----------------------------

Os grupos da consolidação permitem criar grupos de contas que você deseja utilizar para consolidar os dados. O mais geral, um grupo de contas de consolidação representa um plano de contas é mapeado obrigatório pelo governo ou contas a um grupo definido por sedes empresarial. Você pode encontrar grupos da consolidação ** de instalação ** em área ** consolidações ** de módulo. Quando você adicionar um novo grupo, insira um identificador exclusivo para o grupo de conta e um nome.

## <a name="additional-consolidation-accounts"></a>Contas de consolidação adicionais
Contas adicionais de consolidação permitem atribuir uma conta de um plano de contas existente para um grupo de contas da consolidação. Você poderá especificar um valor e um nome de conta da consolidação. 

Você pode localizar contas adicionais de consolidação ** de instalação ** em área ** consolidações ** de módulo. Quando você cria uma nova conta de consolidação, você deve especificar as seguintes informações:

-   ** A conta principal ** – este campo está uma pesquisa que mostra todas as contas principais com base no plano de contas que você selecionou na página. Quando você seleciona uma conta, o nome é automaticamente inserido com ** nome de conta principal ** no campo.
-   ** Grupo de contas de consolidação ** – use este campo para especificar o grupo para atribuir a conta. Se consolidar de duas formas diferentes, você deve adicionar a mesma conta para todos os quatro grupos da consolidação.
-   ** Conta de consolidação ** – insira o valor da conta da consolidação. Este valor não precisará ser uma conta de um plano de contas. Pode ser qualquer valor que você exigir.
-   ** Nome da consolidação ** – insira o nome de conta conforme deseja que seja exibo em consultas e relatórios.
-   ** O nível de SAT ** – este campo é usado para declarar demonstrativos de conta para as autoridades fiscais mexicanas. 

Quando terminar de criar os grupos da consolidação e contas adicionais de consolidação, você pode selecionar o grupo no processo de consolidação online.



