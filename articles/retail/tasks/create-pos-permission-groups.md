--- 
title: "Criar grupos de permissões de PDV"
description: "Este procedimento mostra como criar um grupo de permissões de PDV."
author: scott-tucker
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: bcda7c3a5c2cc97fbc6e4945e4d5f0ec42a7a478
ms.contentlocale: pt-br
ms.lasthandoff: 02/07/2018

---
# <a name="create-pos-permission-groups"></a>Criar grupos de permissões de PDV

[!include [task guide banner](../includes/task-guide-banner.md)]

Este procedimento mostra como criar um grupo de permissões de PDV. A empresa de dados de demonstração usada para criar esta tarefa é USRT. Esta tarefa é destinada à função Gerente de operações de varejo.

1. Vá para Grupos de permissões.
2. Clique em Novo.
3. No campo ID do grupo de permissões de PDV, digite um valor.
4. No campo Descrição, digite um valor.
5. Selecione Sim no campo Exibir entradas do relógio de ponto.
    * Agora você pode habilitar ou desabilitar várias permissões para seu grupo de permissões de PDV. Para algumas permissões, você pode definir um valor que será usado para avaliar se o usuário do PDV pode executar a ação.  Este guia de tarefas mostra como habilitar algumas permissões que podem ser dadas a um caixa.  
6. Selecione Sim no campo Permitir criar ordem.
7. Selecione Sim no campo Permitir editar ordem.
8. Selecione Sim no campo Permitir recuperar ordem.
9. Selecione Sim no campo Permitir alteração de senha.
10. Selecione Sim no campo Permitir fechamento cego.
11. Clique em Salvar.
    * Depois que as alterações forem salvas, é necessário executar a agenda de distribuição da equipe para enviar as alterações aos canais de varejo.  
12. Feche a página.
13. Vá para Trabalhos.
    * A seguir, atribuiremos o grupo de permissões de PDV a um trabalho.  
14. Na lista, localize e selecione o PDV desejado.
15. Na lista, clique no link na linha selecionada.
16. Clique em Editar.
17. Expanda a seção Classificação do trabalho.
18. No campo grupo de permissões de PDV, insira ou selecione um valor.
    * Todos os trabalhadores em posições para esse trabalho usarão estas configurações de grupo de permissões de PDV a menos que as permissões de PDV dos trabalhadores tenham sido substituídas em suas posições.  
19. Clique em Salvar.
    * Depois que as alterações forem salvas, é necessário executar a agenda de distribuição da equipe para enviar as alterações aos canais de varejo.  


