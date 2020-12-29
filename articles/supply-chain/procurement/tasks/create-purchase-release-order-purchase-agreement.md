---
title: Criar uma ordem de liberação de compra de um contrato de compra
description: Este procedimento mostra como utilizar um contrato de compra quando você cria uma ordem de compra.
author: mkirknel
manager: tfehr
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ee0c40dfc3c820343c7054238cc2da47e8203d59
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422124"
---
# <a name="create-a-purchase-release-order-from-a-purchase-agreement"></a>Criar uma ordem de liberação de compra de um contrato de compra

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como utilizar um contrato de compra quando você cria uma ordem de compra. O contrato de compra deve ser aplicado quando você cria a ordem de compra porque existem condições gerais que devem ser copiadas para o cabeçalho da ordem de compra. Normalmente essa tarefa é realizada por um agente de compras. Como um pré-requisito para esta guia, você deve ter um contrato de compra em vigor com um compromisso de quantidade do produto para um fornecedor e itens. O mesmo procedimento pode ser utilizado se você tiver um contrato de compra com outros tipos de compromissos. Você pode executar este guia na empresa USMF de dados de demonstração. Se você estiver usando USMF, é possível executar primeiro o guia "Criar um contrato de compra" para configurar as pré-condições necessárias para este guia.


## <a name="create-a-purchase-order"></a>Criar uma ordem de compra
1. No **Painel de Navegação**, vá para **Espaços de trabalho > Preparação da ordem de compra**. 
2. Clique em **Nova ordem de compra**.
3. No campo **Conta de fornecedor**, clique no botão suspenso para abrir a pesquisa.
4. Na lista, localize e selecione o registro desejado.
5. Na lista, clique no link na linha selecionada.
6. Expanda a Guia Rápida **Geral**.
7. No campo **Contrato de compra**, clique no botão suspenso para abrir a pesquisa. Todos os contratos disponíveis para o fornecedor estão listados aqui. Encontre o contrato efetivo que você deseja utilizar.  
8. Na lista, clique no link na linha selecionada.
9. Clique em **Sim**.
10. Clique em **OK**.

## <a name="add-a-line"></a>Adicionar uma linha
1. No campo **Número de item**, digite um valor. Se existem dimensões específicas de estoque ou de local no compromisso você deve inserir os mesmos valores na linha da ordem de compra para usar o contrato.  
2. No campo **Site**, clique no botão de menu suspenso para abrir a pesquisa. O local pode já estar preenchido com o valor padrão da ordem, ou do fornecedor. Se esse for o caso, ignore essa etapa.  
3. Na lista, localize e selecione o PDV desejado.
4. Na lista, clique no link na linha selecionada.
5. No campo **Quantidade.**, insira um número Confirme que o preço foi copiado do compromisso.  

## <a name="look-up-the-commitment"></a>Pesquisar o compromisso
1. Clique em **Atualizar linha**.
2. Clique em **Anexado**. Aqui você pode obter detalhes do contrato de compra. Por exemplo, é possível ver o preço e ver se o preço e o desconto são fixos, o que significa que se você alterar o preço ou o desconto na ordem de compra para um valor diferente daquele do compromisso, o sistema removerá a ligação para que a linha da ordem de compra não satisfaça o compromisso. Também é possível verificar se a opção Máximo é forçado está selecionada, o que significa que a quantidade do compromisso não pode ser excedida através da soma de todas as compras que satisfaçam o compromisso.  
3. Feche a página.

## <a name="look-up-the-purchase-agreement"></a>Pesquisar o contrato de compra
1. No **Painel de Ações**, clique em **Geral**.
2. Clique em **Contrato de compra**.
3. Feche a página.
4. Feche a página.

