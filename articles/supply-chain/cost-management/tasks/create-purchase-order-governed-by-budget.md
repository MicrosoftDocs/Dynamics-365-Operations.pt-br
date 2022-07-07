---
title: Criar uma ordem de compra regida por orçamento
description: Use este procedimento para criar uma ordem de compra que seja verificada para o orçamento disponível.
author: JennySong-SH
ms.date: 06/15/2020
ms.topic: business-process
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: aa9777ad3aa487dfb558879335f93f347b8ac749
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016178"
---
# <a name="create-a-purchase-order-governed-by-budget"></a>Criar uma ordem de compra regida por orçamento

[!include [banner](../../includes/banner.md)]

Use este procedimento para criar uma ordem de compra que seja verificada para o orçamento disponível.

## <a name="review-the-budget-control-configuration"></a>Revise a configuração de controle de orçamento

1. Acesse **Orçamento > Configuração > Controle de orçamento > Configuração de controle de orçamento**.
1. Selecione a guia **Fundos de orçamento disponíveis**.
1. Selecione a guia **Documentos e diários**.
1. Selecione a guia **Definir regras de controle de orçamento**.
1. Selecione a guia **Definir grupos orçamentários**.
1. Feche a página.

## <a name="create-a-purchase-order"></a>Crie uma ordem de compra

1. Acesse **Compras e Fornecimento > Ordens de compra > Todas as ordens de compra**.
1. Selecione **Novo**.
1. No campo **Conta de fornecedor**, insira ou selecione um valor.
1. Expanda a Guia Rápida **Geral**.
1. No campo **Data contábil**, defina a data.
1. Selecione **OK** para fechar a caixa de diálogo e abrir a nova ordem de compra.
1. Na Guia Rápida **Linhas de ordem de compra**, selecione **Adicionar linha** na barra de ferramentas para adicionar uma nova linha e preencha a linha conforme necessário para adicionar um item à ordem.
1. Na Guia Rápida **Linhas de ordem de compra**, selecione **Finanças \> Distribuir valores**.
1. No campo **Conta contábil**, especifique uma conta.
1. Feche a página.

## <a name="perform-budget-checking"></a>Executar verificação de orçamento

1. Continue trabalhando com a ordem de compra para a qual você acabou de adicionar uma linha.
1. Na Guia Rápida **Linhas de ordem de compra**, selecione **Finanças \> Executar verificação de orçamento**.
1. Na Guia Rápida **Linhas de ordem de compra**, selecione **Finanças \> Erros ou avisos da verificação de orçamento**.
1. A caixa de diálogo **Erros ou avisos da verificação de orçamento** será aberta. Verifique os resultados da verificação e, em seguida, selecione **Fechar** para fechar a caixa de diálogo.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]