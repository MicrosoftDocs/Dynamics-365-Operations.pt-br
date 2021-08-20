---
title: Os campos de peso nas linhas de carga não correspondem aos campos de peso na carga
description: Os campos de peso nas linhas de carga não correspondem aos campos de peso na carga
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSShipmentDetails_WHSShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f71ac7b2777cb77fccdf1a4c72a47c9b406bbd68b2d20c41ddc96028d2ffc348
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6756694"
---
# <a name="the-weight-fields-on-load-lines-dont-match-the-weight-fields-on-the-load"></a>Os campos de peso nas linhas de carga não correspondem aos campos de peso na carga

Códigos de erro: WHSLoadWeightOnLinesDoNotMatchLoadWarning

## <a name="symptoms"></a>Sintomas

O sistema mostra a seguinte mensagem de erro:

> Os campos de peso nas linhas de carga não correspondem aos campos de peso na carga %1. Execute a Verificação de consistência do peso da carga do depósito para recalcular os campos de peso.

## <a name="cause"></a>Causa

Os campos **Peso líquido** e **Peso da tara** estão definidos como *0* (zero) na linha de carga. No entanto, os campos de peso não estão definidos como *0* para as medições de peso no produto. Quando os campos de peso não são definidos na linha de carga, qualquer correção da quantidade na linha de carga pode causar um cálculo de peso incorreto na carga. Esse problema pode ocorrer se os pesos no produto tiverem sido alterados desde que a linha de carga foi criada.

## <a name="resolution"></a>Resolução

Por padrão, quando uma linha de carga é criada, os campos de peso do produto são inseridos nela. Se o peso for zero, você poderá recalculá-lo usando a funcionalidade *Verificação de consistência do peso da carga do depósito*.

1. Acesse **Administração do sistema \> Tarefas periódicas \> Banco de dados \> Verificação de consistência**.
1. Na caixa de diálogo **Verificação de consistência**, defina o campo **Módulo** como *Gerenciamento de depósito*.
1. Defina o campo **Verificar/Corrigir** como *Corrigir erro*.
1. Na lista de caixas de seleção, marque a caixa de seleção **Verificação de consistência do peso da carga do depósito** e verifique se somente a linha dessa caixa de seleção está realçada.
1. Na parte superior da lista de caixas de seleção, selecione o botão de reticências (**...**) e, em seguida, selecione **Caixa de diálogo** no menu.
1. Na caixa de diálogo **Verificação de consistência do peso da carga do depósito**, defina os campos a seguir para especificar os critérios de execução da verificação de consistência:

    - **ID de carga:** especifique uma ID de carga. Deixe este campo em branco para verificar todas as IDs de carga.
    - **Número de item:** especifique um número de item. Deixe este campo em branco para verificar todos os itens.
    - **Sempre recalcular o peso nas cargas:** defina esta opção como *Sim*.
    - **Permitir substituição de peso nas linhas de carga:** defina esta opção como *Sim*.

1. Selecione **OK** para fechar a caixa de diálogo **Verificação de consistência do peso da carga do depósito**.
1. Selecione o botão de reticências e, em seguida, selecione **Executar** no menu.

O peso é recalculado com base nos critérios especificados. Selecione o link **Detalhes da mensagem** para exibir o resultado da verificação de consistência.
