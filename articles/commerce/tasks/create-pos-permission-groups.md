---
title: Criar grupos de permissões de PDV
description: Este tópico explica como criar um grupo de permissões de PDV.
author: scott-tucker
manager: AnnBe
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailPosPermissionGroup, HcmJob
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ac03e1bfb7a2463b31feca0a4303c182a00ad259
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4964811"
---
# <a name="create-pos-permission-groups"></a>Criar grupos de permissões de PDV

[!include [banner](../includes/banner.md)]

Este tópico explica como criar um grupo de permissões de PDV. A empresa de dados de demonstração usada para criar esta tarefa é USRT. Esta tarefa é destinada à função Gerente de operações de comércio.

1. No painel de navegação, vá para **Módulos > Varejo e Comércio > Funcionários > Grupos de permissões**.
2. Selecione **Novo**.
3. No campo **ID do grupo de permissões de PDV**, digite um valor.
4. No campo **Descrição**, digite um valor.
5. Selecione **Sim** no campo **Exibir entradas do relógio de ponto**. Agora você pode habilitar ou desabilitar várias permissões para seu grupo de permissões de PDV. Para algumas permissões, você pode definir um valor que será usado para avaliar se o usuário do PDV pode executar a ação. Este guia de tarefas mostra como habilitar algumas permissões que podem ser dadas a um caixa.  
6. Selecione **Sim** no **campo Permitir criar ordem**.
7. Selecione **Sim** no campo **Permitir editar ordem**.
8. Selecione **Sim** no campo **Permitir recuperar ordem**.
9. Selecione **Sim** no campo **Permitir alteração de senha**.
10. Selecione **Sim** no campo **Permitir fechamento cego**.
11. Selecione **Salvar**. Depois que as alterações forem salvas, será necessário executar a agenda de distribuição da equipe para enviar as alterações aos canais de comércio. 
12. No Painel de Navegação, vá para **Módulos > Recursos humanos > Trabalhos > Trabalhos**.
13. A seguir, atribuiremos o grupo de permissões de PDV a um trabalho. Na lista, localize e selecione o registro desejado.
14. Selecione **Editar**.
15. Expanda a seção **Classificação do trabalho**.
16. No campo grupo de permissões de PDV, insira ou selecione um valor. Todos os trabalhadores em posições para esse trabalho usarão estas configurações de grupo de permissões de PDV a menos que as permissões de PDV dos trabalhadores tenham sido substituídas em suas posições.  
17. Selecione **Salvar**. Depois que as alterações forem salvas, será necessário executar a agenda de distribuição da equipe para enviar as alterações aos canais.  



[!INCLUDE[footer-include](../../includes/footer-banner.md)]