--- 
title: Definir regras de cobertura para itens
description: "A empresa de dados demo usada para criar este procedimento é USMF."
author: YuyuScheller
manager: AnnBe
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 76334f7ee4efe33df4a86aaa11a59748387cec89
ms.openlocfilehash: fe92393cc264df68f084db6974f7d4607d37d3ab
ms.contentlocale: pt-br
ms.lasthandoff: 11/02/2017

---
# <a name="define-coverage-rules-for-items"></a>Definir regras de cobertura para itens

[!include [task guide banner](../../includes/task-guide-banner.md)]

A empresa de dados demo usada para criar este procedimento é USMF. Este procedimento mostra como criar regras de cobertura e substituir configurações de cobertura para um item específico. Também mostra como especificar as configurações padrão de estoque.


## <a name="create-a-coverage-group"></a>Crie um grupo de cobertura.
1. Ir para Grupos de cobertura.
2. Clique em Novo.
3. No campo Grupo de cobertura, digite um valor.
4. No campo Nome, digite um valor.
5. No campo Calendário, digite um valor.
    * Escolha o calendário utilizado pelo planejamento mestre para criar indicações de reabastecimento para itens desse grupo.  
6. No campo Código de cobertura, selecione uma opção.
    * Selecione Requisito para esse procedimento.  
7. No Tempo limite de cobertura (dias), insira '90'.
    * Para itens desse grupo, o planejamento mestre criará indicações de reabastecimento por até 90 dias no futuro.  
8. No campo Dias negativos, insira '1'.
9. No campo Dias positivos, insira '1'.
10. Expandir ou recolher a seção Outros.
11. No campo Margem de recebimento adicionada à data de requisição, insira '1'.
    * Por exemplo, se a margem de recebimento estiver definida para 1 dia, e uma linha da ordem de compra estiver programada para recebimento em 15 de maio, o planejamento mestre calculará a data de recebimento ajustada como 16 de maio.  
12. No campo Margem de emissão deduzida da data de requisição, insira '1'.
    * Por exemplo, se a margem de segurança estiver definida como 1 dia, e uma linha da ordem de venda estiver programada para entrega em 15 de maio, o agendamento do planejamento mestre calculará a data de entrega ajustada como 14 de maio.  
13. No campo Reordenar margem adicionada ao prazo de entrega do item, insira '1'.
14. Clique em Salvar.

## <a name="create-a-new-product"></a>Criar um novo produto
1. Vá para Produtos liberados.
2. Clique em Novo.
3. No campo Número do produto, digite um valor.
4. No campo Nome do produto, digite um valor.
5. No campo Grupo de modelo do item, clique no botão suspenso para abrir a pesquisa.
6. Na lista, localize e selecione o registro desejado.
7. Na lista, clique no link na linha selecionada.
8. No campo Grupo de item, clique no botão suspenso para abrir a pesquisa.
9. Na lista, localize e selecione o registro desejado.
10. Na lista, clique no link na linha selecionada.
11. No campo Grupo de dimensão de armazenamento, clique no botão suspenso para abrir a pesquisa.
12. Na lista, localize e selecione o registro desejado.
13. Na lista, clique no link na linha selecionada.
14. No campo Grupo de dimensão de rastreamento, clique no botão suspenso para abrir a pesquisa.
15. Na lista, localize e selecione o PDV desejado.
16. Na lista, clique no link na linha selecionada.
17. Clique em OK.

## <a name="setup-default-order-settings"></a>Configurar ordem padrão
1. No Painel de Ação, clique em Plano.
2. Clique em Configurações de ordem padrão.
3. No campo local de compra, digite o site usado como o padrão quando as ordens de compra são criadas.
4. No campo Local de estoque, digite o local onde o item está armazenado.
5. Expandir ou recolher a seção Estoque.
6. Defina Múltiplo para '10'.
7. Definir Min. quantidade de ordem para '10'.
8. Definir Máx. quantidade de ordem para '100'.
9. Definir Quantidade de ordem padrão para '10'.
10. No campo de prazo de entrega da compra, insira um número.
11. Marque ou desmarque a caixa de seleção Dias úteis.
12. Clique em Salvar.
13. No campo de ordem padrão, selecione 'Ordem de compra'.
14. Clique em Salvar.
15. Feche a página.
    * Feche a página Configurações padrão da ordem.  

## <a name="add-an-item-to-a-coverage-group"></a>Adicionar um item ao grupo de cobertura
1. Expandir ou recolher a seção Plano.
2. No campo Grupo de cobertura, clique no botão suspenso para abrir a pesquisa.
3. Na lista, localize o grupo de cobertura que você criou.
4. Na lista, clique no link na linha selecionada.

## <a name="create-item-coverage-rules"></a>Criar Regras de cobertura de item
1. No Painel de Ação, clique em Plano.
2. Clique em Cobertura de item.
3. Clique em Novo.
4. Clique na guia Geral.
5. Marque a caixa no cabeçalho de Substituir configurações do grupo de cobertura.
6. No Tempo limite de cobertura (dias), insira '60'.
    * Embora os itens no Requisito de grupo de recursos sejam planejados com 90 dias de antecedência, esse item será planejado com 60 dias.  
7. No campo Dias negativos, insira '2'.
8. No campo Dias positivos, insira '2'.
9. Clique na guia do prazo de entrega.
10. Marque a caixa no cabeçalho de Compra.
11. No campo Tempo de compra, insira '5'.
12. Clique em Salvar.


