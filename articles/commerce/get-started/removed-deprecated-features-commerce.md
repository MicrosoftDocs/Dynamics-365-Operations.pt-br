---
title: Recursos removidos ou obsoletos do Dynamics 365 Commerce
description: Este tópico descreve os recursos que já foram removidos ou foram planejados para remoção de Dynamics 365 Commerce.
author: josaw
manager: AnnBe
ms.date: 01/11/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2020-04-30
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 357f4673d77ee990c4e1b0ce84a704fd4d778402
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5240210"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-commerce"></a>Recursos removidos ou obsoletos do Dynamics 365 Commerce

[!include [banner](../includes/banner.md)]

Este tópico descreve os recursos que já foram removidos ou foram planejados para remoção de Dynamics 365 Commerce.

- Um recurso *removido* não estará mais disponível no produto.
- Um recurso *preterido* não está no desenvolvimento ativo e poderá ser removido em uma atualização futura.

Esta lista é destinada a ajudá-lo a considerar essas remoções e reprovações para seu próprio planejamento. 

> [!NOTE]
> Informações detalhadas sobre objetos no Finance and Operations apps podem ser encontradas nos [Relatórios de referência técnica](https://docs.microsoft.com/dynamics/s-e/). Você pode comparar as diferentes versões desses relatórios para aprender sobre objetos que foram alterados ou removidos em cada versão do Finance and Operations apps.

## <a name="features-removed-or-deprecated-in-the-commerce-10017-release"></a>Recursos removidos ou substituídos na versão 10.0.17 do Commerce

> [!Important]
> A versão 10.0.17 está disponível como parte de uma versão preliminar. O conteúdo e a funcionalidade estão sujeitos a alterações. Para obter informações sobre as versões prévias, consulte [Perguntas frequentes sobre as atualizações de serviço One Version](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/one-version).

### <a name="full-dataset-generation-interval-is-deprecated"></a>O intervalo completo de geração do conjunto de dados foi substituído

|   |  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | A partir dessa versão, no formulário **Parâmetros do agendador do Commerce** na matriz do Dynamics 365 Headquarters, o campo **Intervalo completo de geração do conjunto de dados em dias** será preterido. Também a partir dessa versão, o campo será removido visualmente para que o valor não possa ser editado. Isso permanecerá como o valor **0**. |
| **Substituída por outro recurso?**   | Não |
| **Áreas afetadas do produto**         | Dynamics 365 Commerce |
| **Opção de implantação**              | Todas|
| **Status**                         | Preterido. Não use este campo nem altere o valor nele.|

## <a name="features-removed-or-deprecated-in-the-commerce-10015-release"></a>Recursos removidos ou substituídos na versão 10.0.15 do Commerce

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>Suporte do Internet Explorer 11 para Dynamics 365 foi substituído

|   |  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | A partir de dezembro de 2020, o suporte do Internet Explorer 11 da Microsoft para todos os produtos Dynamics 365 é preterido e Internet Explorer 11 não receberá suporte depois de agosto de 2021.<br><br>Isso afetará os clientes que usam os produtos do Dynamics 365 projetados para serem usados por meio de uma interface do Internet Explorer 11. Depois de agosto de 2021, o Internet Explorer 11 não terá suporte para esses produtos do Dynamics 365. |
| **Substituída por outro recurso?**   | Recomendamos que os clientes façam a transição para o Microsoft Edge.|
| **Áreas afetadas do produto**         | Todos os produtos do Dynamics 365 |
| **Opção de implantação**              | Todas|
| **Status**                         | Preterido. Internet Explorer 11 não terá suporte depois de agosto de 2021.|

## <a name="features-removed-or-deprecated-in-the-commerce-10011-release"></a>Recursos removidos ou substituídos na versão 10.0.11 do Commerce
### <a name="data-action-hooks"></a>Ganchos de ação de dados
|   |  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | O recurso de ganchos de ação de dados foi substituído devido a problemas de desempenho. |
| **Substituída por outro recurso?**   | Recomendamos o uso de [substituições de ação de dados](../e-commerce-extensibility/data-action-overrides.md) para modificar a lógica comercial na camada de ação de dados.|
| **Áreas afetadas do produto**         | Ações de dados de extensibilidade do comércio eletrônico |
| **Opção de implantação**              | Todas |
| **Status**                         | botãoPreterido: a partir da versão 10.0.11 |

### <a name="retail-sdk-support-for-visual-studio-2015-msbuild-140-and-retail-sdkreference-libraries-and-tools"></a>Suporte do SDK do Retail para o Visual Studio 2015, msbuild 14.0 e bibliotecas e ferramentas do SDK\Referência do Retail
|   |  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | O suporte do SDK do Retail para o Visual Studio 2015 foi preterido e atualizado para o suporte ao VS 2017, ao msbuild 15.0 e a todas as bibliotecas de referência e ferramentas do gerador de proxy do Commerce na pasta RetailSDK\References movidas para pacotes NuGet para simplificar o processo de extensão e de atualização do SDK.|
| **Substituída por outro recurso?**   | Recomendamos que você siga as informações em [Migrar o SDK do Retail do Visual Studio 2015 para o Visual Studio 2017](../dev-itpro/retail-sdk/migrate-sdk.md) para atualizar seu sistema. |
| **Áreas afetadas do produto**         | Extensões do SDK do Retail |
| **Opção de implantação**              | Todas |
| **Status**                         | botãoPreterido: a partir da versão 10.0.11 |

### <a name="retail-server-extension-using-iedmmodelextender-and-commercecontroller"></a>Extensão do Servidor do Retail usando IEdmModelExtender e CommerceController
|   |  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | A extensão do Servidor do Retail usando IEdmModelExtender e CommerceController foi preterida para fornecer um modelo de extensão simplificado. A nova implementação terá somente a classe Controller sem nenhuma implementação de classe IEdmModelExtender adicional. Isso também evita a dependência com uma versão do OData específica (se a versão do OData for atualizada, as extensões poderão ser quebradas.) |
| **Substituída por outro recurso?**   |  Recomendamos que você use o modelo de extensão de classe IController, importando o pacote NuGet (Microsoft.Dynamics.Commerce.Hosting.Contracts). |
| **Áreas afetadas do produto**         | Extensões do servidor do Retail |
| **Opção de implantação**              | Todas |
| **Status**                         | botãoPreterido: a partir da versão 10.0.11 |

### <a name="hardware-station-extension-using-ihardwarestationcontroller"></a>Extensão do Hardware Station usando IHardwareStationController
|   |  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | A extensão da estação de hardware usando o IHardwareStationController foi preterida para fornecer um modelo de extensão simplificado. A nova implementação terá somente a classe IController sem qualquer implementação de classe adicional e, para evitar a dependência com as principais bibliotecas do Hardware Station, a extensão anterior precisará se referir a várias bibliotecas. |
| **Substituída por outro recurso?**   | Recomendamos o uso do modelo de extensão de classe IController, importando o pacote NuGet (Microsoft.Dynamics.Commerce.Hosting.Contracts). |
| **Áreas afetadas do produto**         | Extensões do Hardware Station |
| **Opção de implantação**              | Todas |
| **Status**                         | botãoPreterido: a partir da versão 10.0.11 |

## <a name="features-removed-or-deprecated-in-the-commerce-10010-release"></a>Recursos removidos ou substituídos na versão 10.0.10 do Commerce
### <a name="pos-operation-803---picking-and-receiving"></a>Operação PDV 803 - Separação e Recebimento
|   |  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | As operações de separação e recebimento estão sendo preteridas devido à nova reestruturação da operação. |
| **Substituída por outro recurso?**   | Sim. Ele é substituído por duas novas operações PDV: operação de entrada (804) e operação de saída (805).|
| **Áreas afetadas do produto**         | Aplicativo de ponto de venda (PDV) |
| **Opção de implantação**              | Todas |
| **Status**                         | Preterido: a partir da versão 10.0.10, a operação de separação e recebimento não receberá mais nenhuma atualização de recurso nova. Somente correções críticas de bugs serão realizadas para esta operação em versões futuras. Todos os clientes são incentivados a mudar para as novas [operações de entrada](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) e de [saída](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation), o que continuará a ser parte de nosso roteiro de produtos de longo prazo. |


## <a name="features-removed-or-deprecated-in-the-commerce-1007-release"></a>Recursos removidos ou substituídos na versão 10.0.7 do Commerce
### <a name="commerce-getproductavailabilities-and-getavailableinventorynearby-apis"></a>API de GetProductAvailabilities e GetAvailableInventoryNearby comerciais
|   |  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | APIs novas e otimizadas foram criadas para substituir APIs GetProductAvailabilities e GetAvailableInventoryNearby. |
| **Substituída por outro recurso?**   | Sim: ele é substituído por APIs de GetEstimatedAvailabilty e GetEstimatedProductWarehouseAvailability. |
| **Áreas afetadas do produto**         | Aplicativo SDK de comércio eletrônico |
| **Opção de implantação**              | Todas |
| **Status**                         | Preterido: a partir da versão 10.0.7, não terão mais investimentos em engenharia feitos para GetProductAvailabilities e GetAvailableInventoryNearby. As organizações que usam essas APIs em suas implantações de comércio eletrônico devem ser convertidas em novas APIs de GetEstimatedAvailability e GetEstimatedProductWarehouseAvailability e habilitar o [Recurso de cálculo de disponibilidade de produtos otimizados](https://docs.microsoft.com/dynamics365/commerce/calculated-inventory-retail-channels).  |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Comunicados anteriores sobre recursos removidos ou obsoletos
Para saber mais sobre os recursos que foram removidos ou preteridos em versões anteriores, consulte [Recursos removidos ou obsoletos em versões anteriores](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=/dynamics365/commerce/toc.json).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]