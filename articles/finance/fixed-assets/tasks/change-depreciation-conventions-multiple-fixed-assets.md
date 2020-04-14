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
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 39930134782b40de05a92a6ad51c4f628f304a78
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142883"
---
# <a name="change-depreciation-conventions-for-multiple-fixed-assets"></a>Alterar convenções de depreciação para ativos fixos múltiplos

[!include [banner](../../includes/banner.md)]

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

