---
title: Sincronizar a configuração de imposto do Serviço de Cálculo de Imposto com o Dynamics 365 Finance
description: Este artigo explica como sincronizar dados mestre de configuração de imposto do Serviço de Cálculo de Imposto com o Microsoft Dynamics 365 Finance.
author: EricWangChen
ms.date: 01/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.21
ms.custom: intro-internal
ms.search.form: TaxIntegration, TaxServiceParameters
ms.openlocfilehash: 315f2b27a64906ca0fc404d704d0b170dbfa48c5
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283843"
---
# <a name="sync-the-tax-setup-from-the-tax-calculation-service-to-dynamics-365-finance"></a>Sincronizar a configuração de imposto do Serviço de Cálculo de Imposto com o Dynamics 365 Finance

[!include [banner](../includes/banner.md)]

Este artigo explica como sincronizar dados mestre de configuração de imposto do Serviço de Cálculo de Imposto com o Microsoft Dynamics 365 Finance.

Depois que você concluir as etapas de configuração necessárias em [Introdução ao cálculo de imposto](global-get-started-with-tax-calculation-service.md), os dados de configuração de imposto a seguir serão sincronizados automaticamente entre o Serviço de Cálculo de Imposto e o Finance.

## <a name="sales-tax-code"></a>Código do imposto

| Serviço de Cálculo de Imposto           | Finance                             |
| --------------------------------- | ----------------------------------- |
| Código do imposto                          | Código do imposto                      |
| Descrição                       | Nome                                |
| Entrada do usuário                        | Período de liquidação                   |
| Entrada do usuário                        | Grupo de lançamentos contábeis                |
| Entrada do usuário                        | Moeda do imposto                  |
| Uma taxa de imposto negativa é configurada | Permitir porcentagem negativa de imposto |

## <a name="tax-value"></a>Valor do imposto

| Serviço de Cálculo de Imposto | Finance                   |
| ----------------------- | ------------------------- |
| A partir da data da transação   | Data Inicial                 |
| Até a data da transação     | Data final                   |
| Valor mínimo          | Limite mínimo             |
| Valor máximo          | Limite máximo             |
| Alíquota do imposto                | Valor                     |
| Taxa não dedutível     | Porcentagem não dedutível |

## <a name="tax-limits"></a>Limites de imposto

| Serviço de Cálculo de Imposto | Finance           |
| ----------------------- | ----------------- |
| A partir da data da transação   | Data Inicial         |
| Até a data da transação     | Data final           |
| Valor mínimo do imposto      | Imposto mínimo |
| Valor máximo do imposto      | Imposto máximo |

## <a name="sales-tax-group"></a>Grupo de impostos sobre vendas

| Serviço de Cálculo de Imposto                         | Finance                                    |
| ----------------------------------------------- | ------------------------------------------ |
| Grupo de impostos                                       | Grupo de impostos sobre vendas                            |
| Códigos de imposto neste grupo de impostos                  | Códigos de imposto neste grupo de impostos |
| O código de imposto está marcado como **Isento**         | Isenção                                     |
| O código de imposto está marcado como **Isento**         | Código de isenção                                |
| O código de imposto está marcado como **É Encargo Revertido**. | Encargos revertidos                             |
| O código de imposto está marcado como **É Imposto Sobre o Uso**        | Imposto sobre o uso                                    |

## <a name="item-sales-tax-group"></a>Grupo de impostos do item

| Serviço de Cálculo de Imposto             | Finance                                         |
| ----------------------------------- | ----------------------------------------------- |
| Grupo de impostos do item                      | Grupo de impostos do item                            |
| Códigos de imposto neste grupo de impostos do item | Códigos de imposto neste grupo de impostos do item |

Depois que a sincronização for concluída, continue a manter os parâmetros restantes no Finance para fins de lançamento e relatório.

> [!NOTE]
> Não há suporte para a sincronização da configuração de imposto entre o Finance e o Serviço de Cálculo de Imposto. Para um ambiente existente do Finance, crie primeiro a configuração de imposto no Serviço de Cálculo de Imposto. Em seguida, sincronize os dados de configuração no ambiente do Finance.
