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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 1fe285f05e5f1ddcb7bd206290b9954cbdaffc75
ms.sourcegitcommit: 105f65468b45799761c26e5d0ad9df4ff162c38d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "5487088"
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

## <a name="the-dock-management-profile-of-a-location-profile-is-not-preventing-inventory-types-from-being-mixed"></a>O perfil de gerenciamento de doca de um perfil de localização não está impedindo que os tipos de estoque sejam misturados.

### <a name="issue-description"></a>Descrição do problema

Você está usando *políticas de consolidação de remessa*. Você configurou um *perfil de gerenciamento de doca* para um *perfil de localização*, mas quando o trabalho é criado, os tipos de estoque são combinados na localização final.

### <a name="issue-resolution"></a>Resolução do problema

Os perfis de gerenciamento de doca exigem que o trabalho seja dividido antecipadamente. Em outras palavras, o perfil de gerenciamento de doca espera que um cabeçalho de trabalho não tenha vários locais de armazenamento.

Para o perfil de gerenciamento de doca gerenciar com eficiência a combinação de estoque, uma quebra de cabeçalho de trabalho deve ser configurada.

Neste exemplo, nosso perfil de gerenciamento de doca está configurado de forma que a opção **Tipos de estoque que não devem ser combinados** seja definida como *ID da remessa*, e vamos configurar uma quebra de cabeçalho de trabalho para ele:

1. Vá para **Gerenciamento de depósito \> Configuração \> Trabalho \> Modelo de trabalho**.
1. Selecione o **Tipo de ordem de serviço** a ser editado (por exemplo, *Ordens de compra*).
1. Selecione o modelo de trabalho a ser editado.
1. No Painel de Ações, selecione **Editar consulta**.
1. Abra a guia **Classificação** e adicione uma linha com as seguintes configurações:
    - **Tabela** - *Transações de trabalho temporário*
    - **Tabela derivada** - *Transações de trabalho temporário*
    - **Campo** - *ID da remessa*
1. Selecione **OK**.
1. Você retornará à página **Modelos de trabalho**. No Painel de Ação, selecione **Quebras de cabeçalho de trabalho**.
1. No Painel de Ações, selecione **Editar**.
1. Marque a caixa de seleção associada à *ID da remessa* do **Nome do campo**.
1. No Painel de ações, selecione **Salvar**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
