---
title: Configurar documentos de transferência para movimentação de mercadorias dentro de uma empresa
description: Este procedimento mostra como criar documentos de transferência para a movimentação de mercadorias em uma empresa.
author: v-oloski
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventTransferOrders, InventLocationIdLookup, TransportationDocument, HcmWorkerLookUp, SrsReportViewerForm, InventTransferParmShip
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2228f7354a91eda7e03ba4d3001265bfcbc20e90
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5816841"
---
# <a name="set-up-the-transfer-documents-for-goods-movement-inside-a-company"></a>Configurar documentos de transferência para movimentação de mercadorias dentro de uma empresa

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como criar documentos de transferência para a movimentação de mercadorias em uma empresa. Este procedimento está disponível somente para entidades legais com um endereço principal na Lituânia. O procedimento foi criado usando a empresa de dados de demonstração DEMF com endereço principal na Lituânia. Antes de concluir este procedimento, você deve concluir o procedimento "Configurar documentos de transferência para a movimentação de mercadorias em uma empresa". Este procedimento é destinado a contadores de estoque. Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.


## <a name="create-a-transfer-order"></a>Criar uma ordem de transferência
1. Vá para Gerenciamento de estoque > Ordens de entrada > Ordem de transferência.
2. Clique em Novo.
3. No campo Depósito de origem, insira ou selecione um valor.
4. No campo Depósito de destino, insira ou selecione um valor.
5. Clique em Adicionar.
6. Na lista, marque a linha selecionada.
7. No campo Número do item, insira ou selecione um valor.

## <a name="enter-transportation-details-for-the-transfer-order"></a>Inserir detalhes de transporte da ordem de transferência
1. Clique em Salvar.
2. No Painel de Ação, clique em Remessa.
3. Clique em Detalhes de Transporte.
4. Selecione Sim no campo Imprimir detalhes de transporte.
5. No campo Mercadorias emitidas por, insira ou selecione um valor.
6. No campo Pacote, digite um valor.
7. No campo Nível de risco da carga, digite um valor.
8. No campo Transportadora, insira ou selecione um valor.
9. No campo Modelo, insira ou selecione um valor.
10. No campo Número de registro, digite um valor.
11. No campo Número de registro da carroceria, digite um valor.
12. No campo Motorista, insira ou selecione um valor.
13. No campo Nome do motorista, digite um valor.
14. Clique em Salvar.
15. Feche a página.

## <a name="view-the-packing-slip-for-the-unposted-transfer-order"></a>Exibir a guia de remessa da ordem transferência não lançada
1. Clique em Guia de remessa.
2. Clique em OK.
3. Feche a página.

## <a name="view-the-packing-slip-for-the-posted-transfer-order"></a>Exibir a guia de remessa da ordem transferência lançada
1. No Painel de Ação, clique em Ordem de transferência.
2. No Painel de Ação, clique em Remessa.
3. Clique em Remeter ordem de transferência.
4. Clique na guia Geral.
5. No campo Atualizar, selecione uma opção.
6. Clique na guia Visão geral.
7. No campo Guia de remessa, digite um valor.
8. Clique em OK.
9. No Painel de Ação, clique em Remessa.
10. Clique em Guia de remessa.
11. Clique em OK.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]