---
title: Configurar um trabalhador
description: Este procedimento demonstra como configurar um trabalhador como um representante de vendas que esteja qualificado para a comissão sobre vendas no PDV.
author: jblucher
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CommissionSalesGroup, CommissionSalesMember, DirPartyLookup, HcmWorker
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: aee84f2dc39d2225985992fac0f9c20985ed9804
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3021584"
---
# <a name="configure-a-worker"></a>Configurar um trabalhador

[!include[task guide banner](../includes/task-guide-banner.md)]

Este procedimento demonstra como configurar um trabalhador como um representante de vendas que esteja qualificado para a comissão sobre vendas no PDV. Este procedimento usa a empresa de dados de demonstração USRT.


## <a name="create-a-commission-sales-group-for-the-worker"></a>Criar um grupo de comissão de venda para o trabalhador
1. Vá para Vendas e marketing > Comissões > Grupos de vendas.
    * Os trabalhadores podem ser atribuídos a um ou mais grupos de vendas. No PDV, você pode escolher qualquer grupo de vendas que contenha trabalhadores do catálogo de endereços da loja.  
2. Clique em Novo.
3. No campo Grupo, digite um valor.
4. No campo Nome, digite um valor.
5. Clique em Salvar.
6. No Painel de Ação, clique em Geral.
7. Clique em Rep. de vendas.
    * Um grupo de vendas pode conter mais de um trabalhador. As comissões podem ser divididas entre os trabalhadores com base na sua definição da cota de comissão.  
8. No campo Nome, insira ou selecione um valor.
9. No campo Cota de comissão, insira um número.
10. Clique em Salvar.
11. Feche a página.
12. Feche a página.

## <a name="assign-the-workers-default-sales-group"></a>Atribuir o grupo de vendas padrão do trabalhador
1. Vá para Varejo e Comércio > Funcionários > Trabalhadores.
2. Na lista, localize e selecione o registro desejado.
3. Na lista, clique no link na linha selecionada.
4. Clique na guia Comércio.
    * Um trabalhador pode ser atribuído a um grupo de vendas padrão. O grupo de vendas padrão será automaticamente adicionado às linhas de vendas no PDV se a opção estiver habilitada no perfil de funcionalidade da loja.  
5. Clique em Editar.
6. No campo Grupo padrão, insira ou selecione um valor.
7. Clique em Salvar.

