---
title: Verificar a disponibilidade do estoque
description: "Este procedimento mostra como verificar um valor disponível e o estoque físico disponível de um número de item específico."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: d103eb52a498e6273b1fdb43fc10dae4133e76b2
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# Verificar a disponibilidade do estoque

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como verificar um valor disponível e o estoque físico disponível de um número de item específico. Ele também mostra como obter informações de fornecimento relacionadas ao item. O estoque físico disponível é o estoque disponível que está disponível ou seja, comprado, recebido e registrado. O estoque disponível inclui o estoque disponível, mas também o estoque que é ordenado e esperado, mas que ainda não foi recebido ou registrado. Você pode ver todo esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados. Se você estiver usando USMF você pode usar os valores de exemplo mostrados. Essas tarefas normalmente seriam realizadas por um funcionário do depósito.


## Verifique estoque disponível de um item
1. Vá para Gerenciamento de estoque > Consultas e relatórios > Estoque disponível.
2. Selecione a linha do número do item.
    * Para ver o estoque disponível por número de item, selecione a linha na tabela definida como o estoque disponível e o campo que está definido como o número do item.  
3. No campo Critérios, selecione o item que você deseja consultar.
    * Se você estiver usando a empresa de dados de demonstração USMF, poderá selecionar 'M9201'.  
4. Clique em OK.
5. Clique em Dimensões.
    * A guia Dimensões permite selecionar quantos detalhes você deseja ver sobre seu estoque disponível. Se for necessário os dados relacionados à reserva, você deve exibir todas as dimensões de estoque dos itens que usam processos avançados de depósito (WHS).  
6. Clique em OK.
7. No Painel de Ação, clique em Informações relacionadas.
    * Se não for exibido isso, talvez você precise clicar no botão de reticências (…) para ver opções adicionais do painel de ações.  
8. Clique em Visão geral de fornecimento.
    * A guia de visão geral de fornecimento fornece informações de fornecimento de um item específico, como a quantidade disponível, o tempo de entrega e informações do fornecedor.  
9. Expanda a seção Disponível.
10. Expanda a seção Fornecedores.
11. Feche a página.
12. Feche a página.

## Verifique Estoque disponível físico
1. Vá para Gerenciamento de depósito > Consultas e relatórios > Estoque disponível ou físico.
2. No campo Número de item, digite um valor.
    * Você pode usar os campos de site e depósito para filtrar a lista de itens.  
3. Atualize a página.
4. Clique em Exibir dimensões.
    * A guia Exibir dimensões permite selecionar quantos detalhes você deseja ver sobre seu estoque disponível.  
5. Clique em OK.
6. Feche a página.

## Verifique o estoque disponível por localização
1. Vá para Gerenciamento de depósito > Consultas e relatórios > Disponível por local.
2. No campo Depósito, digite um valor.
    * Se você estiver usando a empresa de dados de demonstração USMF, você pode usar '51'.  
3. Atualize a página.
4. Clique em Exibir dimensões.
5. Clique em OK.
6. Feche a página.
