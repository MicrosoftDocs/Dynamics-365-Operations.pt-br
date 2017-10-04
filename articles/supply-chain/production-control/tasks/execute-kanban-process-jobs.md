--- 
title: Executar trabalhos do processo kanban
description: Esse procedimento se concentra em executar trabalhos de processo do kanban.
author: ChristianRytt
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 50b5048a5f9277c47444fa69d2c8cc8e36ba7dcd
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="execute-kanban-process-jobs"></a>Executar trabalhos do processo kanban

[!include[task guide banner](../../includes/task-guide-banner.md)]

Esse procedimento se concentra em executar trabalhos de processo do kanban. O primeiro trabalho é preenchido com a quantidade prevista e não têm erros. O segundo trabalho é preenchido com erros. A empresa de dados demo usada para criar este procedimento é USMF. Esse procedimento é destinado ao operador da máquina.


## <a name="select-a-kanban-job"></a>Selecionar trabalho kanban
1. Vá para Controle de produção > Kanban > Quadro Kanban para trabalhos de processo.
2. No campo Célula de trabalho, clique no botão suspenso para abrir a pesquisa.
3. Clique na linha com grupo de recursos 1250. Isso filtra a Lista de trabalhos para exibir somente os trabalhos para a célula de trabalho 1250.
    * Marque a linha que tem o status do trabalho planejado.  

## <a name="complete-a-job-with-expected-quantity"></a>Execute um trabalho com quantidade prevista
1. Expandir ou recolher a seção Detalhes.
    * Esta seção exibe informações importantes sobre o número do cartão, o número do item, a quantidade encomendada, e o nome da atividade.  
2. Expanda ou recolha a seção Instruções de produção.
    * Esta seção exibe instruções de produção da atividade. As instruções podem ser texto, imagens, desenhos e outros documentos.  
3. Clique em Iniciar.
    * Selecione um trabalho que não esteja concluído. Use os ícones de status no campo status do trabalho para exibir o status do trabalho.      
4. Clique em Concluir.
    * Os trabalhos são preenchidos com a qualidade esperada.  

## <a name="complete-a-job-with-errors"></a>Execute um trabalho com erros
1. Clique em Iniciar.
    * Quando um trabalho é concluído, o próximo trabalho na lista é automaticamente selecionado. Por esse motivo você não precisará selecionar um trabalho antes de clicar em Início.  
2. No painel de Ação, clique em Fabricar.
3. Clique em Concluir (detalhes).
4. Na lista, marque a linha selecionada.
5. No campo Quantidade de erro, insira um número.
6. No campo Quantidade de mercadoria, insira um número.
7. Clique em OK.

