---
title: Digitar um acréscimo a um ativo fixo
description: Este procedimento mostra como adicionar um acréscimo a um ativo fixo existente.
author: saraschi2
manager: AnnBe
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetAddition
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fe1a1d4db696ac013afee05b697b301383232134
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1839944"
---
# <a name="enter-an-addition-to-a-fixed-asset"></a>Digitar um acréscimo a um ativo fixo

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como adicionar um acréscimo a um ativo fixo existente. A finalidade das adições de ativo fixo são rastrear adições, manutenção, ou melhorias de um ativo fixo, além de serem informacionais. Algumas alterações para métodos de depreciação de ativos ou a vida útil devem ser feitas separadamente.   

O procedimento usa a função de contador e os dados de demonstração da entidade legal de USMF.

1. No Painel de navegação, vá para **Módulos > Ativos fixos > Ativos fixos > Ativos fixos**.
2. Na lista, localize e selecione o ativo fixo que você deseja adicionar.
3. Na lista, clique no link na linha selecionada.
4. No Painel de Ação, clique em **Ativo fixo**.
5. Clique em **Acréscimos de ativo fixo**.
6. Clique em **Novo**.
7. No campo **Nome**, digite um valor.
8. No campo **Data de aquisição**, defina a data de compra ou de serviço de adição.
9. No campo **Custo unitário**, insira o custo do item, manutenção ou outro aperfeiçoamento do ativo.
10. No campo **Quantidade.**, insira um número Os custos totais não terão nenhum efeito no valor do ativo fixo e são para fins de rastreamento e informação. Se os custos serão capitalizados, então um texto de transação de ajuste deve ser postado separadamente.  
11. Clique na guia **Geral**.

    * Defina **Aumenta a vida útil** como **Sim** se a adição aumentar a vida útil do ativo.  
    * Este campo serve somente para informar. Para aumentar a vida útil, modifique a vida útil nos métodos de depreciação e/ou registros de depreciações para o ativo.  

