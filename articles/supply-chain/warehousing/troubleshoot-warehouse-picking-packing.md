---
title: Resolver problemas de separação e embalagem
description: Este tópico descreve como corrigir problemas comuns que você pode encontrar ao separar e embalar no Microsoft Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: 2cce1038ed393fc8a7bb489a37fc0921b0ac755e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993919"
---
# <a name="troubleshoot-picking-and-packing"></a>Resolver problemas de separação e embalagem

[!include [banner](../includes/banner.md)]

Este tópico descreve como corrigir problemas comuns que você pode encontrar ao separar e embalar no Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-receive-the-following-error-message-dimension-location-cant-be-left-blank-if-dimension-serial-number-is-set"></a>Recebo a seguinte mensagem de erro: "O local da dimensão não pode ser deixado em branco se o número de série da dimensão estiver definido."

### <a name="issue-description"></a>Descrição do problema

Você receberá essa mensagem de erro se criar uma ordem de transferência para um item de série usando um depósito habilitado para gerenciamento avançado de depósito (WMS) e, depois que o trabalho for concluído, você tenta confirmar a remessa.

### <a name="issue-resolution"></a>Resolução do problema

O campo **Local de recebimento padrão** está em branco para um depósito de trânsito do depósito "de". Para corrigir esse problema, especifique um local de recebimento padrão no depósito de trânsito. Certifique-se de que esse local seja controlado por placa de licença.

## <a name="i-receive-the-following-error-message-invalid-license-plate"></a>Recebo a seguinte mensagem de erro: "Placa de licença inválida."

### <a name="issue-description"></a>Descrição do problema

Você recebe essa mensagem de erro no aplicativo de depósito ao verificar a ID de uma placa de licença.

### <a name="issue-resolution"></a>Resolução do problema

Certifique-se de que a ID de placa de licença exista na tabela de placas de licença e que os itens e quantidades na placa estejam disponíveis (em outras palavras, eles não estão bloqueados).

## <a name="i-receive-the-following-error-message-field-load-weight-1-can-only-contain-positive-numbers-update-has-been-canceled"></a>Recebo a seguinte mensagem de erro: "O campo 'Peso da carga' (= -%1) só pode conter números positivos. A atualização foi cancelada."

### <a name="issue-description"></a>Descrição do problema

Você recebe essa mensagem de erro se houver trabalho aberto ao processar o trabalho de locais de embalagem para locais de preparo ou de locais de preparo para locais de doca.

### <a name="issue-resolution"></a>Resolução do problema

Para corrigir esse problema, acesso **Administração do sistema \> Tarefas periódicas \> Banco de dados \> Verificação de consistência** e execute o processo para **Verificação de consistência do peso da carga do depósito**.

## <a name="i-receive-the-following-error-message-the-quantity-is-not-valid-for-unit-1"></a>Recebo a seguinte mensagem de erro: "A quantidade não é válida para a unidade %1."

### <a name="issue-description"></a>Descrição do problema

Você recebe essa mensagem de erro ao tentar executar uma *separação dividida* em vários lotes.

### <a name="issue-resolution"></a>Resolução do problema

O funcionário do depósito deve usar o processo *Separação insuficiente* no aplicativo de depósito. Se você estiver tentando selecionar vários lotes do mesmo local, também pode usar a opção **Completo** no aplicativo de depósito.

## <a name="i-cant-move-inventory-to-a-location-that-is-license-platecontrolled"></a>Não consigo mover o estoque para um local controlado por placa de licença.

### <a name="issue-description"></a>Descrição do problema

Você não consegue reduzir as quantidades selecionadas em uma carga.

### <a name="issue-resolution"></a>Resolução do problema

Em versões anteriores, você não consegue reduzir as quantidades selecionadas em uma carga. Contudo, agora você pode desfazer a separação em um local controlado por placa de licença. Você deve especificar um valor **Local** e um valor **Placa de licença** para a linha de carga na página **Reduzir quantidade separada**.

## <a name="can-i-print-a-delivery-note-or-packing-content-by-warehouse"></a>Posso imprimir uma nota de entrega ou conteúdo de embalagem por depósito?

### <a name="issue-description"></a>Descrição do problema

Você deseja imprimir uma nota de entrega ou conteúdo de embalagem por depósito ou local na página **Atualização de linha de modelo de auditoria de trabalho**.

### <a name="issue-resolution"></a>Resolução do problema

Ao imprimir um documento usando as configurações de gerenciamento de impressão, limite o escopo (local/depósito) por meio do gerenciamento de impressão em vez de selecionar **Editar configurações de impressão** na página **Atualização de linha de modelo de auditoria de trabalho**.

## <a name="i-cant-cancel-a-packing-slip-after-its-posted-from-a-sales-order"></a>Não consigo cancelar uma guia de remessa depois de lançada em uma ordem de venda.

### <a name="issue-description"></a>Descrição do problema

Quando os processos de separação e remessa são habilitados para WMS, você não consegue cancelar uma guia de remessa depois de lançada em uma ordem de venda.

### <a name="issue-resolution"></a>Resolução do problema

Para corrigir guias de remessa lançadas para itens habilitados para WMS, o lançamento deve ocorrer a partir da carga, não a partir da ordem. A Microsoft avaliou esse problema e determinou que é uma limitação de recurso. Em geral, uma ordem de venda que foi separada e enviada por meio de processos de gerenciamento de depósito pode ser atualizado em relação à guia de remessa a partir da carga ou remessa e do próprio documento de ordem de venda. Contudo, se você atualizar a guia de remessa a partir do documento de ordem de venda, a reversão da guia de remessa ainda não poderá ser feita a partir da carga ou da ordem de venda. Portanto, recomendamos que você use a guia de remessa a partir da carga. Nesse caso, será habilitada a reversão que deve ser feita a partir da carga.

## <a name="i-receive-the-following-error-message-not-enough-work-can-be-found-for-cluster"></a>Recebo a seguinte mensagem de erro: "Não é possível encontrar um trabalho suficiente para o cluster."

### <a name="issue-description"></a>Descrição do problema

Quando você usa o processo *Separação de cluster direcionada pelo sistema*, se você configurar um perfil de cluster em que, por exemplo, 10 posições podem ser separadas, o processo funciona conforme planejado quando há trabalho suficiente para separar até 10 posições. Entretanto, se houver apenas oito posições para separar, você receberá essa mensagem de erro porque não há trabalho suficiente para um cluster.

### <a name="issue-resolution"></a>Resolução do problema

Para corrigir esse problema, edite o perfil do cluster e defina a opção **Ativar posições** como *Não*.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]