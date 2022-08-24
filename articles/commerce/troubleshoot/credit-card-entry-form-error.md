---
title: A página de entrada de cartão de crédito mostra um erro na finalização da compra
description: Este artigo fornece orientações de solução de problemas que podem ajudar quando a seção do método de pagamento não está carregada e mostra uma mensagem de erro.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: 25f0dde83efff7c1d9a2a456270f5d48047f44ba
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269746"
---
# <a name="credit-card-entry-page-shows-an-error-at-checkout"></a>A página de entrada de cartão de crédito mostra um erro na finalização da compra

[!include [banner](../../includes/banner.md)]

Este artigo fornece orientações de solução de problemas que podem ajudar quando a seção **Método de pagamento** não está carregada e mostra uma mensagem de erro.

## <a name="description"></a>descrição

Quando você abre a página de finalização da compra de uma loja online, a seção **Método de pagamento** não é carregada e a seguinte mensagem de erro é exibida: "Algo deu errado. Tente novamente mais tarde."

![Erro do módulo de pagamento.](media/payment-module-error.jpg)

## <a name="resolution"></a>Resolução

### <a name="wait-for-the-commerce-scale-unit-cache-to-expire"></a>Aguarde o cache do Commerce Scale Unit expirar

As configurações de serviço de pagamento na página de finalização da compra da loja online são armazenadas em cache na Commerce Scale Unit e podem levar até 15 minutos para serem exibidas no site de comércio eletrônico. Essas configurações de serviço de pagamento incluem alterações na ID da conta de comerciante, chave de API de nuvem e várias definições de configuração relacionadas ao método de pagamento.

## <a name="additional-resources"></a>Recursos adicionais

[Configurar um canal online](../channel-setup-online.md)
