---
title: Aplicar um contrato de compra ao criar uma ordem de compra
description: Este procedimento mostra como utilizar um contrato de compra quando você cria uma ordem de compra.
author: kamaybac
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1913181e85929951ce240ac31a0ac3f1351f6ae51f6ed2790bae577b2100b308
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6731238"
---
# <a name="apply-a-purchase-agreement-when-creating-a-purchase-order"></a>Aplicar um contrato de compra ao criar uma ordem de compra

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como utilizar um contrato de compra quando você cria uma ordem de compra. O contrato de compra deve ser aplicado quando você cria a ordem de compra porque existem condições gerais que devem ser copiadas para o cabeçalho da ordem de compra. Normalmente essa tarefa é realizada por um agente de compras. Como um pré-requisito para esta guia, você deve ter um contrato de compra em vigor com um compromisso de quantidade do produto para um fornecedor e itens. O mesmo procedimento pode ser utilizado se você tiver um contrato de compra com outros tipos de compromissos.

## <a name="create-a-purchase-order"></a>Criar uma ordem de compra

1. Acesse **Produção e fornecimento \> Espaços de trabalho \> Preparação da ordem de compra**.
1. No Painel de Ações, selecione **Nova ordem de compra**.
1. A caixa de diálogo **Criar ordem de compra** é aberta. Selecione uma **Conta de fornecedor**. Inspecione e ajuste os outros campos de endereço, conforme necessário.
1. Expanda a Guia Rápida **Geral**.
1. No campo **Contrato de compra**, localize e selecione o contrato efetivo que você deseja usar. Todos os contratos disponíveis para o fornecedor estão listados aqui.  
1. Selecione **Sim**.
1. Selecione **OK**.

## <a name="add-a-line"></a>Adicionar uma linha

1. No campo **Número de item**, digite um valor. Se existem dimensões específicas de estoque ou de local no compromisso você deve inserir os mesmos valores na linha da ordem de compra para usar o contrato.
1. No campo **Site**, selecione no botão de menu suspenso para abrir a pesquisa. O local pode já estar preenchido com o valor padrão da ordem, ou do fornecedor. Se esse for o caso, ignore essa etapa.  
1. Na lista, localize e selecione o registro desejado.
1. Na lista, selecione o link na linha selecionada.
1. No campo **Quantidade.**, insira um número Confirme que o preço foi copiado do compromisso.  

## <a name="look-up-the-commitment"></a>Pesquisar o compromisso

1. Selecione **Atualizar linha**.
1. Selecione **Anexado**. Aqui você pode obter detalhes do contrato de compra. Por exemplo, é possível ver o preço e ver se o preço e o desconto são fixos, o que significa que se você alterar o preço ou o desconto na ordem de compra para um valor diferente daquele do compromisso, o sistema removerá a ligação para que a linha da ordem de compra não satisfaça o compromisso. Também é possível verificar se a opção Máximo é forçado está selecionada, o que significa que a quantidade do compromisso não pode ser excedida através da soma de todas as compras que satisfaçam o compromisso.  
1. Feche a página.

## <a name="look-up-the-purchase-agreement"></a>Pesquisar o contrato de compra

1. No **Painel de Ação**, selecione **Geral**.
1. Selecione **Contrato de compra**.
1. Feche a página.
1. Feche a página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]