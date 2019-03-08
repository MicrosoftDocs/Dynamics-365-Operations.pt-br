---
title: Alterar convenções de depreciação para ativos fixos múltiplos
description: Esta tarefa atualiza a convenção de depreciação de um grupo de ativo fixo específico.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysQueryForm, SrsReportViewerForm
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a7a79b2edf64f0063253d3f2a23b0020eceb87c0
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "324252"
---
# <a name="change-depreciation-conventions-for-multiple-fixed-assets"></a>Alterar convenções de depreciação para ativos fixos múltiplos

[!include [task guide banner](../../includes/task-guide-banner.md)]

Esta tarefa atualiza a convenção de depreciação de um grupo de ativo fixo específico. Este guia de tarefa usa a empresa demo USMF.

1. Vá para Ativos fixos > Tarefas periódicas > Atualização em massa
2. No campo Livro de depreciação, clique no botão suspenso para abrir a pesquisa.
3. Na lista, clique no link na linha selecionada.
4. No campo Posicionado no início do serviço, insira uma data.
5. No campo Posicionado no fim do serviço, insira uma data.
    * Serão atualizados apenas os ativos do registro de depreciações selecionado que tiverem sido disponibilizados entre essas datas.  
6. No campo Convenção de depreciação atual, selecione uma opção.
    * Apenas os ativos com a convenção de depreciação atual serão atualizados.  
7. No campo Convenção de nova depreciação, selecione uma opção.
    * Verifique o relatório que imprimirá o destino desejado.  
8. Expanda os Registros para incluir a seção.
9. Clique em Filtro.
10. Na lista, selecione o grupo de Ativo fixo.
11. No campo Critérios, clique no botão suspenso para abrir a pesquisa.
12. Selecione o grupo de ativos fixos desejado.
13. Na lista, clique no link na linha selecionada.
14. Clique em OK.
15. Clique em OK.
    *  Os resultados do processo são mostrados no relatório de atualização em massa.     

