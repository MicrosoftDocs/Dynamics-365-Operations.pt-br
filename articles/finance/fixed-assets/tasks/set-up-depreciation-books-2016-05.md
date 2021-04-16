---
title: Configurar registros de depreciação
description: Este procedimento explica o processo de criação de um registro de depreciações e o associa a um grupo de ativos fixos.
author: saraschi2
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepBookTable, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b0ab7f9332e3224c3dadd62aae532ccffb05c82a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815587"
---
# <a name="set-up-depreciation-books"></a>Configurar registros de depreciação 

[!include [banner](../../includes/banner.md)]

Este procedimento explica o processo de criação de um registro de depreciações e o associa a um grupo de ativos fixos. 

## <a name="create-a-depreciation-book"></a>Crie um registro de depreciação
1. Vá para Ativos fixos > Configuração > Registros de depreciação.
2. Clique em Novo.
3. No campo de registro de depreciação, insira um valor.
4. No campo Descrição, digite um valor.
5. Marcar ou desmarcar a caixa de seleção Calcular depreciação.
6. No campo Perfil de depreciação, clique no botão suspenso para abrir a pesquisa.
7. Na lista, localize e selecione o perfil de depreciação desejado.
8. Na lista, clique no link na linha selecionada.
9. No campo Perfil de depreciação alternativa, clique no botão suspenso para abrir a pesquisa.
10. Na lista, selecione o perfil de depreciação desejado.
11. Na lista, clique no link na linha selecionada.
    * O perfil de depreciação extraordinário é usado para depreciação adicional para um ativo em condições incomuns. Por exemplo, você pode usá-lo para registrar a depreciação que resulta de acidentes naturais.  
12. Marque ou desmarque a caixa de seleção Criar ajustes de depreciação com ajustes de base.
13. No campo Calendário, clique no botão suspenso para abrir a pesquisa.
14. Na lista, clique no link na linha selecionada.

## <a name="associate-the-depreciation-book-with-a-fixed-asset-group"></a>Associar o registro de depreciação a um grupo de ativo fixo
1. Clique em Grupos de ativos fixos.
2. No campo Grupo de ativo fixo, clique no botão suspenso para abrir a pesquisa.
3. Na lista, localize e selecione o registro desejado.
4. Na lista, clique no link na linha selecionada.
5. No campo Convenção de depreciação, selecione uma opção.
6. No campo Vida útil, insira um número.
    * Observe que o valor do campo de períodos de depreciação será calculado depois de definir a vida útil.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]