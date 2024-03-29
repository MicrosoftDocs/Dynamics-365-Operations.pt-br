---
title: Criar, calcular e lançar demonstrativos para uma loja de varejo
description: Este artigo descreve as etapas manuais para criar, calcular e lançar um demonstrativo para uma loja.
author: jashanno
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailStatementTable
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 740857e6a902e21588855eef5e36cac68e560898
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873269"
---
# <a name="create-calculate-and-post-statements-for-a-retail-store"></a>Criar, calcular e lançar demonstrativos para uma loja de varejo

[!include [banner](../includes/banner.md)]

Este artigo descreve as etapas manuais para criar, calcular e lançar um demonstrativo para uma loja. Há também os trabalhos em lotes que podem ser configurados para as mesmas tarefas. As etapas para configurar e executar os trabalhos em lote podem ser encontradas em outros artigos. Para realizar este procedimento, você deve ter transações que foram executadas no PDV e inseridas no Dynamics 365 Commerce. Esta gravação usa a empresa USRT nos dados de demonstração.

1. Selecione **Finanças da loja** na home page.
2. Selecione **Novo demonstrativo**.
3. No campo **Número da loja**, selecione uma opção no menu suspenso.
4. Selecione **OK**.
5. O grupo **Configuração** tem as configurações que controlam que transações são incluídas no demonstrativo e como são agrupadas nas linhas do demonstrativo. Você pode abrir o grupo **Configuração** e alterar essas configurações ou pode usar os padrões.  
    - O campo **Método do demonstrativo** define como as linhas do demonstrativo serão agrupadas.  
    - Selecione um membro da equipe ou um registro no campo **equipe/registro** se desejar calcular um demonstrativo somente para o membro da equipe ou registro específico.  
6. No campo **Método de fechamento**, selecione uma opção.
7. Selecione **Calcular demonstrativo** no Painel de Ações.
8. Selecione **Sim**.
    - Depois de calcular o demonstrativo, deve haver linhas criadas com os valores totais para cada método de pagamento e o método do demonstrativo que foi usado.  
    - Insira um valor contado em cada linha caso seja necessário ser inserido ou atualizado. O campo Contado será preenchido com valores das declarações de meios de pagamento feitas no PDV.  
9. Selecione **Lançar demonstrativo** no Painel de Ações.
10. Selecione **Fechar**.
11. Feche o painel.
12. Na home page, selecione **Finanças da loja**.
13. Selecione a guia **Demonstrativos lançados**.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]