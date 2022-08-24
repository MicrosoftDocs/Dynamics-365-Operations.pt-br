---
title: Configurar um trabalhador
description: Este procedimento demonstra como configurar um trabalhador como um representante de vendas que esteja qualificado para a comissão sobre vendas no PDV.
author: josaw1
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.industry: Retail
ms.search.form: CommissionSalesGroup, CommissionSalesMember, DirPartyLookup, HcmWorker
ms.openlocfilehash: 8bbd3899da8e289dcf82fabc0fd21370655f38e0
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276038"
---
# <a name="configure-a-worker"></a>Configurar um trabalhador

[!include [banner](../includes/banner.md)]

Este procedimento demonstra como configurar um trabalhador como um representante de vendas que esteja qualificado para a comissão sobre vendas no PDV. Este procedimento usa a empresa de dados de demonstração USRT.


## <a name="create-a-commission-sales-group-for-the-worker"></a>Criar um grupo de comissão de venda para o trabalhador
1. Acesse Vendas e marketing > Comissões > Grupos de vendas.
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
1. Acesse Varejo e Comércio > Funcionários > Trabalhadores.
2. Na lista, localize e selecione o registro desejado.
3. Na lista, clique no link na linha selecionada.
4. Clique na guia Comércio.
    * Um trabalhador pode ser atribuído a um grupo de vendas padrão. O grupo de vendas padrão será automaticamente adicionado às linhas de vendas no PDV se a opção estiver habilitada no perfil de funcionalidade da loja.  
5. Clique em Editar.
6. No campo Grupo padrão, insira ou selecione um valor.
7. Clique em Salvar.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
