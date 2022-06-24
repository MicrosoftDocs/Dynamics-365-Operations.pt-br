---
title: Criar grupos de permissões de PDV
description: Este artigo explica como criar um grupo de permissões de PDV.
author: scott-tucker
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailPosPermissionGroup, HcmJob
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 009f311dd00f48edb8c0f6622f0a5107881ab2ca
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905415"
---
# <a name="create-pos-permission-groups"></a>Criar grupos de permissões de PDV

[!include [banner](../includes/banner.md)]

Este artigo explica como criar um grupo de permissões de PDV. A empresa de dados de demonstração usada para criar esta tarefa é USRT. Esta tarefa é destinada à função Gerente de operações de comércio.

1. No painel de navegação, Acesse **Módulos > Varejo e Comércio > Funcionários > Grupos de permissões**.
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
12. No Painel de Navegação, Acesse **Módulos > Recursos humanos > Trabalhos > Trabalhos**.
13. A seguir, atribuiremos o grupo de permissões de PDV a um trabalho. Na lista, localize e selecione o registro desejado.
14. Selecione **Editar**.
15. Expanda a seção **Classificação do trabalho**.
16. No campo grupo de permissões de PDV, insira ou selecione um valor. Todos os trabalhadores em posições para esse trabalho usarão estas configurações de grupo de permissões de PDV a menos que as permissões de PDV dos trabalhadores tenham sido substituídas em suas posições.  
17. Selecione **Salvar**. Depois que as alterações forem salvas, será necessário executar a agenda de distribuição da equipe para enviar as alterações aos canais.  



[!INCLUDE[footer-include](../../includes/footer-banner.md)]