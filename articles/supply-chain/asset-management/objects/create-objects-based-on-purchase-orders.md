---
title: Crie ativos com base em ordens de compra
description: Este tópico explica como criar uma lista de itens de ativo que pode ser usada como base para a criação de ativos para trabalhos de manutenção em Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6eba14e285f23338cad0243fca567b30c6d4d3f2
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2019
ms.locfileid: "2571567"
---
# <a name="create-assets-based-on-purchase-orders"></a>Crie ativos com base em ordens de compra

[!include [banner](../../includes/banner.md)]

 

Este tópico explica como criar uma lista de itens de ativo que pode ser usada como base para a criação de ativos para trabalhos de manutenção em Gerenciamento de Ativos. Com base nos itens de ativos, você pode exibir uma lista das linhas de ordem de compra criadas nesses itens. O objetivo dessa funcionalidade é criar facilmente um ativo em Gerenciamento de Ativos com base em uma ordem de compra.

Primeiro, você configura os itens a serem usados para a criação de ativos de uma ordem de compra em **Itens de ativo**. Após criar uma linha de ordem de compra, você cria os ativos em **Ativos pendentes**. É possível decidir em que estágio da ordem de compra o ativo deve ser criado.


## <a name="select-asset-items"></a>Selecione itens do ativo

1. Clique em **Gerenciamento de ativos** > **Configuração** > **Ativos** > **Itens**.
2. Clique em **Novo** para criar um novo item de ativo.
3. Selecione o item no campo **Número do item**. Quando você deixar esse campo, o nome do item será automaticamente inserido no campo **Nome do produto**.
4. Na Guia Rápida **Geral**, selecione um tipo de ativo para o item.
5. Selecione o fabricante do ativo e o modelo do item.
6. Salve o item.


## <a name="create-assets-from-pending-assets"></a>Crie ativos a partir de ativos pendentes

1. Clique em **Gerenciamento de ativos** > **Comum** > **Ativos** > **Ativos Pendentes**.
2. Você verá uma lista atualizada das ordens de compra com base nos itens selecionados em **Itens de ativo**.
3. Você pode filtrar o status de ordens de compra para selecionar em que estado do ciclo de vida o ativo deve ser criado. Por exemplo, talvez você só queira criar ativos quando o recebimento de um produto for lançado em uma ordem de compra.
4. Selecione o link **Número de referência** em uma linha de ordem de compra para exibir informações detalhadas sobre o item.
5. Se desejar editar as dimensões que serão exibidas na Guia Rápida **Dimensões de estoque**, clique no botão **Exibir Dimensões** e faça seleções.
6. Se desejar criar um ativo com base em uma linha de ordem de compra, marque a caixa de seleção na coluna **Marcar** para essa linha na página de lista e clique em **Criar ativos**. Uma mensagem será exibida, informando a ID do ativo.
7. Selecione o ativo na lista **Todos os ativos** e clique em **Editar** para adicionar mais informações ao ativo.
8. Em **Ativos pendentes**, se desejar excluir uma linha porque você não deseja criar um ativo, marque a caixa de seleção na coluna **Marcar** para essa linha e clique em **Descartar ativos pendentes**. Uma mensagem será exibida, informando a ID do ativo. Você não está excluindo a ordem de compra ou a ordem de venda, mas apenas o registro de onde poderia ter criado um ativo em **Gerenciamento de Ativos**.

>[!NOTE]
>Todas as dimensões do produto (tamanho, cor, configuração etc.) serão automaticamente transferidas para os atributos de ativo. As dimensões de rastreamento (número de série) são armazenadas diretamente no ativo quando o ativo é criado.


## <a name="find-pending-assets"></a>Localize ativos pendentes

Você pode executar uma **Contagem de ativos pendentes** para verificar os ativos pendentes. Por exemplo, essa função pode ser usada para receber uma notificação sempre que um ativo pendente está pronto para ser criado como um ativo.

1. Clique em **Gerenciamento de ativos** > **Periódico** > **Ativos** > **Contagem de ativos pendentes**.
2. Clique em **OK** para executar o trabalho e atualizar a lista em **Ativos pendentes**.
3. Você pode configurar este trabalho para executar como um trabalho em lotes, por exemplo, uma vez a cada dia.

**Cuidado:** se os dados forem alterados em uma ordem de compra *após* você criar um ativo com base no item relativo, as alterações não serão refletidas no ativo.
