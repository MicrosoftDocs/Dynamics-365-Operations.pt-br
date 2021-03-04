---
title: Solucionar problemas de configuração do depósito
description: Este tópico descreve como corrigir problemas comuns que você pode encontrar ao configurar o Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 9bbe92627f53b3b4b04597be144d602b3cae7ed7
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4646098"
---
# <a name="troubleshoot-warehouse-configuration"></a>Solucionar problemas de configuração do depósito

[!include [banner](../includes/banner.md)]

Este tópico descreve como corrigir problemas comuns que você pode encontrar ao configurar o Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-receive-the-following-error-message-the-license-plate-or-location-is-not-valid"></a>Recebo a seguinte mensagem de erro: "A placa de licença ou local não é válido."

### <a name="issue-description"></a>Descrição do problema

Você recebe essa mensagem de erro ao verificar uma ID de placa de licença ou local.

### <a name="issue-resolution"></a>Resolução do problema

Certifique-se de que a ID da placa de licença não foi reservada por outra pessoa. Esse problema costumava ocorrer quando o valor que um usuário verificava no aplicativo de depósito era um local e uma ID de placa de licença válidos. Contudo, esse problema foi resolvido na versão 10.0.11.

## <a name="i-receive-the-following-error-message-license-plate-must-be-specified-for-this-location"></a>Recebo a seguinte mensagem de erro: "A placa de licença deve ser especificada para este local."

### <a name="issue-description"></a>Descrição do problema

Você receberá essa mensagem de erro se criar uma ordem de transferência usando um depósito habilitado para gerenciamento avançado de depósito (WMS) e, depois que o trabalho for concluído, você tenta confirmar a remessa.

### <a name="issue-resolution"></a>Resolução do problema

O campo **Local de recebimento padrão** está em branco para um depósito de trânsito do depósito "de". Para corrigir esse problema, especifique um local de recebimento padrão no depósito de trânsito. Certifique-se de que esse local seja controlado por placa de licença.

## <a name="i-receive-the-following-error-message-you-cant-create-a-work-template-line-for-inventory-status-change-because-the-work-type-is-not-valid-select-a-different-work-type"></a>Recebo a seguinte mensagem de erro: "Você não pode criar uma linha de modelo de trabalho para a mudança de status de estoque porque o tipo de trabalho não é válido. Selecione um tipo de trabalho diferente."

### <a name="issue-description"></a>Descrição do problema

Para um modelo de trabalho, você não pode selecionar *Alteração do status do estoque* na coluna **Tipo de trabalho** da seção **Detalhes do modelo de trabalho**.

### <a name="issue-resolution"></a>Resolução do problema

Esse comportamento é por design. O tipo de trabalho *Alteração do status do estoque* é usado apenas por processos do sistema. Ele não pode ser configurado. Como a lista de tipos de trabalho é fixada como uma enumeração, as entradas extras não podem ser filtradas do menu suspenso **Tipo de trabalho**.

## <a name="i-receive-the-following-error-message-the-quantity-is-not-valid-for-unit-1"></a>Recebo a seguinte mensagem de erro: "A quantidade não é válida para a unidade 1%."

### <a name="issue-description"></a>Descrição do problema

A quantidade não é válida para a unidade *ea* quando há trabalhos de separação com várias placas de licença em um local.

### <a name="issue-resolution"></a>Resolução do problema

Verifique se os campos **ID do grupo de sequências de unidade** e **Conversões de unidades** no produto lançado ou na variante do produto estão definidos corretamente.

Observe que a mensagem de erro foi melhorada na versão 10.0.15 (consulte [KB 4581627](https://fix.lcs.dynamics.com/Issue/Details/?bugId=486531)). A nova mensagem de erro é: "A quantidade não é válida. Espera-se %1 %2."

## <a name="in-location-directives-for-sales-order-put-work-the-multiple-sku-option-doesnt-evaluate-multiple-location-directive-actions"></a>Em diretivas de local para execução de ordem de venda, a opção de SKU múltiplo não avalia várias ações de diretiva de local.

### <a name="issue-description"></a>Descrição do problema

As diretivas de local do tipo de ordem de trabalho *Ordens de venda* e do tipo de trabalho *Colocar* não avaliam várias ações da diretiva de local quando a opção **Várias SKUs** é selecionada. Somente a primeira ação da diretiva de local é avaliada.

### <a name="issue-resolution"></a>Resolução do problema

Um novo recurso, *Avaliar todas as ações para diretivas de local Várias SKUs*, foi adicionado na versão 10.0.15 (consulte [KB 4579866](https://fix.lcs.dynamics.com/Issue/Details?kb=4579866&bugId=475946&dbType=3&qc=1bc41a56de7a3ee419fa76397a6bf282fce5be9b93e427c08a6d916d1dfa3091)). Esse recurso avalia todas as ações para diretivas de local Várias SKUs. Se você precisar desse recurso, use o [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para ativá-lo.

## <a name="i-cant-use-the-warehouse-app-to-do-partial-picking"></a>Não consigo usar o aplicativo de depósito para fazer separação parcial.

### <a name="issue-description"></a>Descrição do problema

Em vendas e ordens de transferência, não é possível ignorar itens e fazer a separação parcial.

### <a name="issue-resolution"></a>Resolução do problema

Na página **Itens de menu do dispositivo móvel**, para cada item de menu configurado para processar ordens de venda ou ordens de transferência, defina a opção **Permitir divisão de trabalho** na FastTab **Geral** como *Sim*.

## <a name="how-can-i-do-an-inventory-status-change-for-partial-quantity-work"></a>Como posso fazer uma mudança de status de estoque para trabalho de quantidade parcial?

### <a name="issue-description"></a>Descrição do problema

Você deseja fazer uma mudança de status de estoque para uma quantidade parcial de um lote.

### <a name="issue-resolution"></a>Resolução do problema

Para permitir que os trabalhadores façam essa mudança, é possível criar um item de menu para o aplicativo de depósito. Na página **Itens de menu do dispositivo móvel**, crie (ou edite) um item de menu que tenha as seguintes configurações:

- **Modo:** *Trabalho*
- **Usar trabalho existente:** *Não*
- **Processo de criação de trabalho:** *Movimento*
- **Exibir status do estoque:** *Sim*

Você pode definir outros campos na página conforme necessário.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]