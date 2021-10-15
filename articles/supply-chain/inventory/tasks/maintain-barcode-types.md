---
title: Manter tipos de códigos de barra
description: Este procedimento mostra como configurar a definição de um novo código de barras que pode ser usado como parte do relatório da lista de separação.
author: yufeihuang
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BarcodeSetup, InventParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b689d1fc85d59ac87efa1903fd7122ae5ff011da
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7571104"
---
# <a name="maintain-bar-code-types"></a>Manter tipos de códigos de barra

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como configurar a definição de um novo código de barras que pode ser usado como parte do relatório da lista de separação. Você pode ver todo esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados. Se você estiver usando USMF você pode usar os valores de exemplo mostrados. Essas tarefas normalmente seriam realizadas por um gerente do depósito.

1. Acesse **Códigos de barras**.
1. Selecione **Novo**.
1. No campo **Configuração de código de barras**, digite um valor.
1. No campo **Descrição**, digite um valor.
1. No campo **Tipo de código de barras**, selecione uma opção.
    * Se você estiver usando USMF, você pode selecionar 'Código 39'.
1. No campo **ID da Máscara**, especifique a ID da máscara de código de barras. As máscaras de código de barras são usadas para criar códigos de barras e identificar rapidamente códigos de barras que são digitalizados para um sistema de ponto de venda (PDV). Para obter detalhes, consulte [Configurar máscaras de código de barras](../../../commerce/set-up-bar-code-masks.md).
1. No campo **Tamanho**, insira um número.
1. No campo **Comprimento máximo**, insira um número.
1. Selecione **Salvar**.
1. Feche a página.
1. Acesse **Parâmetros de gerenciamento de estoque e depósito**.
1. No campo **Configuração de código de barras**, insira ou selecione um valor.
    * Selecione a configuração de código de barras que você criou antes, mas esteja ciente de que o formato do código de barras deve corresponder ao formato do identificador exclusivo para o tipo de registro usado no processo. Por exemplo, para roteiros de separação, o formato do código de barras deve corresponder ao formato da referência do roteiro de separação, que normalmente é uma sequência numérica.  
1. Selecione **Salvar**.
1. Feche a página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
