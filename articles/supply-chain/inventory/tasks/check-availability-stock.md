---
title: Verificar a disponibilidade do estoque
description: Este procedimento mostra como verificar um valor disponível e o estoque físico disponível de um número de item específico.
author: ShylaThompson
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventOnHandItemListPage, SysQueryForm, InventDimParmFixed, InventSupply, DefaultDashboard, WHSInventPhysicalOnhand, WHSOnHand, InventOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c1b68a40ba433f7db6eb910961cd429629387bbe
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5834088"
---
# <a name="check-the-availability-of-stock"></a>Verificar a disponibilidade do estoque

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como verificar um valor disponível e o estoque físico disponível de um número de item específico. Ele também mostra como obter informações de fornecimento relacionadas ao item. O estoque físico disponível é o estoque disponível que está disponível ou seja, comprado, recebido e registrado. O estoque disponível inclui o estoque disponível, mas também o estoque que é ordenado e esperado, mas que ainda não foi recebido ou registrado. Você pode ver todo esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados. Se você estiver usando USMF você pode usar os valores de exemplo mostrados. Essas tarefas normalmente seriam realizadas por um funcionário do depósito.


## <a name="check-on-hand-inventory-for-an-item"></a>Verifique estoque disponível de um item
1. Vá para **Painel de navegação > Módulos > Gerenciamento de estoque > Consultas e relatórios > Estoque disponível**.
2. Selecione a linha **Número do item**. Para consultar o estoque disponível por número do item, selecione a linha em que a tabela está definida como **Estoque disponível** e o campo está definido como o número do **Item**.
3. No campo **Critérios**, selecione o item que você deseja consultar. Se você estiver usando a empresa de dados de demonstração USMF, poderá selecionar 'M9201'.  
4. Clique em **OK**.
5. No **Painel de Ações**, clique em **Dimensões**. A guia **Dimensões** permite selecionar o nível de detalhes de seu estoque disponível que você deseja ver. Se for necessário os dados relacionados à reserva, você deve exibir todas as dimensões de estoque dos itens que usam processos avançados de depósito (WMS).
6. Clique em **OK**.
7. No **Painel de Ação**, clique em **Informações relacionadas**. Se essa opção não for exibida, talvez seja necessário clicar no botão de reticências (…) para ver opções adicionais do Painel de Ações.
8. Clique em **Visão geral do fornecimento**. A guia **Visão geral do fornecimento** apresenta informações de fornecimento de um item específico, como a quantidade disponível, o tempo de entrega e informações do fornecedor.  
9. Expanda a seção **Disponível**.
10. Expanda a seção **Fornecedores**.
11. Feche a página.
12. Feche a página.

## <a name="check-physical-on-hand-inventory"></a>Verifique Estoque disponível físico
1. Vá para **Painel de navegação > Módulos > Gerenciamento de depósito > Consultas e relatórios > Estoque disponível físico**.
2. No campo **Número de item**, digite um valor. Você pode usar os campos de site e depósito para filtrar a lista de itens. 
3. Atualize a página.
4. No **Painel de Ações**, clique em **Exibir Dimensões**. A guia Exibir dimensões permite selecionar quantos detalhes você deseja ver sobre seu estoque disponível.
5. Clique em **OK**.
6. Feche a página.

## <a name="check-on-hand-inventory-by-location"></a>Verifique o estoque disponível por localização
1. Vá para **Painel de navegação > Módulos > Gerenciamento de depósito > Consultas e relatórios > Disponibilidade por localização**.
2. No campo **Depósito**, digite um valor. Se você estiver usando a empresa de dados de demonstração USMF, você pode usar '51'.  
3. Atualize a página.
4. Clique em **Exibir Dimensões**.
5. Clique em **OK**.
6. Feche a página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]