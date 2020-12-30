---
title: Configurar grupos de ativos fixos
description: Este tópico explica como criar um novo grupo de ativos fixos.
author: saraschi2
manager: AnnBe
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetGroup, AssetGroupBookSetup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9bcb78158afbf7bb0e9b83b35e37b1532a7c6283
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440203"
---
# <a name="set-up-fixed-asset-groups"></a>Configurar grupos de ativos fixos

[!include [banner](../../includes/banner.md)]

Este tópico explica como criar um novo grupo de ativos fixos. Ela usa a função de contador e os dados de demonstração da entidade legal de USMF.

1. No Painel de navegação, vá para **Módulos > Ativos fixos > Configuração > Grupos de ativos fixos**.
2. Selecione **Novo**.
3. No campo **Grupo de ativo fixo**, digite um valor.
4. No campo **Nome**, digite um valor. Os ativos fixos e o código da sequência numérica de Autonumber no grupo de **Ativos fixos** substituirão as configurações nos parâmetros de ativos fixos. Você pode alterá-lo aqui se os ativos no grupo de ativos fixos forem diferentes da numeração de outros grupos.  
5. Selecione **Registros**.
6. No campo **Registro**, insira ou selecione um valor. Como o campo **Calcular depreciação** é definido como **Sim**, o registro do ativo será incluído nas propostas de depreciação. Se **Calcular a depreciação** for definido como **Não**, o ativo não será depreciado automaticamente.  
7. Defina a vida útil do ativo fixo, em anos. Observe que o valor do campo **Períodos de depreciação** será calculado depois de definir a vida útil.  
8. No campo **Convenção de depreciação**, selecione uma opção.
9. Feche a página.

