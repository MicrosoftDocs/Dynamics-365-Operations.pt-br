---
title: Recursos removidos ou obsoletos do Dynamics 365 Commerce
description: Este tópico descreve os recursos que já foram removidos ou foram planejados para remoção de Dynamics 365 Commerce.
author: josaw
ms.date: 03/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2020-04-30
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 7b06f8ca65e4fac13f322f8d72b8ad4f9db8ccd7
ms.sourcegitcommit: 2e554371f5005ef26f8131ac27eb171f0bb57b4e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2022
ms.locfileid: "8384598"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-commerce"></a>Recursos removidos ou obsoletos do Dynamics 365 Commerce

[!include [banner](../includes/banner.md)]

Este tópico descreve os recursos que já foram removidos ou foram planejados para remoção de Dynamics 365 Commerce.

- Um recurso *removido* não estará mais disponível no produto.
- Um recurso *preterido* não está no desenvolvimento ativo e poderá ser removido em uma atualização futura.

Esta lista é destinada a ajudá-lo a considerar essas remoções e reprovações para seu próprio planejamento. 

> [!NOTE]
> Informações detalhadas sobre objetos em aplicativos de Finanças e Operações podem ser encontradas nos [Relatórios de referência técnica](/dynamics/s-e/). Você pode comparar as diferentes versões desses relatórios para aprender sobre objetos que foram alterados ou removidos em cada versão de aplicativos de Finanças e Operações.

## <a name="features-removed-or-deprecated-in-the-commerce-10021-release"></a>Recursos removidos ou substituídos na versão 10.0.21 do Commerce

[!include [banner](../includes/preview-banner.md)]

### <a name="overlapping-discounts-handling-setting-in-commerce-parameters"></a>Configuração de tratamento de descontos sobrepostos em parâmetros do Commerce

A configuração **Tratamento de descontos sobrepostos**, na página **Parâmetros do Commerce**, é substituída na versão 10.0.21 do Commerce. No futuro, o mecanismo de preço do Commerce usará um único algoritmo para determinar a combinação ideal de descontos sobrepostos.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | <p>A configuração **Tratamento de descontos sobrepostos** nos parâmetros do Commerce controla como o mecanismo de preço do Commerce pesquisa e determina a combinação ideal de descontos sobrepostos. No momento, essa configuração oferece três opções:<p><ul><li> **Melhor desempenho**: esta opção usa um algoritmo de heurística avançado e um método de [classificação de valor marginal](../optimal-combination-overlapping-discounts.md) para priorizar, avaliar e determinar a melhor combinação de descontos de forma oportuna.</li><li>**Cálculo equilibrado**: na base de código atual, esta opção funciona exatamente como a opção **Melhor desempenho**. Portanto, é essencialmente uma opção duplicada.</li><li>**Cálculo exaustivo**: esta opção usa um algoritmo antigo que passa por todas as combinações de desconto possíveis durante o cálculo do preço. Para ordens com linhas e quantidades grandes, essa opção pode causar problemas de desempenho.</li></ul><p>Para ajudar a simplificar a configuração, melhorar o desempenho e reduzir os incidentes causados pelo algoritmo antigo, vamos remover completamente a configuração **Tratamento de descontos sobrepostos** e atualizar a lógica interna do mecanismo de preço do Commerce, de modo que ele use somente o algoritmo avançado (ou seja, o algoritmo por trás da opção **Melhor desempenho**).</p> |
| **Substituída por outro recurso?**   | Não. Recomendamos que as organizações que usam o **Cálculo equilibrado** ou a opção **Cálculo exaustivo** alternem para a opção **Melhor desempenho** antes que este recurso seja removido. |
| **Áreas afetadas do produto**         | Preços e descontos |
| **Opção de implantação**              | Tudo |
| **Status**                         | A partir da versão do 10.0.21, a configuração **Tratamento de descontos sobrepostos** será removida dos parâmetros do Commerce em outubro de 2022. |

### <a name="retail-sdk-distributed-by-using-lifecycle-services"></a>SDK do Retail distribuído usando Lifecycle Services

O SDK do Retail é fornecido no LCS (Lifecycle Services). Esse modo de distribuição foi preterido na versão 10.0.21. No futuro, os pacotes de referência, bibliotecas e exemplos do SDK do Retail serão publicados em repositórios públicos no GitHub.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | O SDK do Retail é fornecido no LCS. O processo do LCS leva algumas horas para terminar e deve ser repetido a cada atualização. No futuro, os pacotes de referência, bibliotecas e exemplos do SDK do Retail serão publicados em repositórios públicos no GitHub. Exemplos de extensão e pacotes de referência podem ser consumidos facilmente, e as atualizações são concluídas em alguns minutos. |
| **Substituída por outro recurso?**   |  [Baixar exemplos de SDK do Retail e pacotes de referência do GitHub e NuGet](../dev-itpro/retail-sdk/sdk-github.md) |
| **Áreas afetadas do produto**         | SDK do Retail |
| **Opção de implantação**              | Todas |
| **Status**                         | Preterido: a partir da versão 10.0.21, o SDK enviado por meio de VMs do LCS será removido em abril de 2023. |

### <a name="retail-deployable-package-and-combined-pos-hardware-station-and-cloud-scale-unit-installers"></a>Pacote implantável do Retail e PDV combinados, Estação de hardware e instaladores do Cloud Scale Unit

Os pacotes implantáveis do Retail gerados usando o MSBuild do SDK do Retail foram preteridos em 10.0.21. No futuro, use o pacote do CSU (Cloud Scale Unit) para extensões do Cloud Scale Unit (Commerce Runtime, banco de dados de canal, APIs do Commerce sem periféricos, pagamentos e POS (Cloud Point of Sale)). Use instaladores somente de extensão para POS, Estação de hardware e Cloud Scale Unit auto-hospedado.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Um pacote implantável do Retail é um pacote combinado que contém um conjunto completo de pacotes de extensão e instaladores. Esse pacote combinado torna a implantação complexa, pois as extensões de CSU vão para o Cloud Scale Unit e os instaladores são implantados nas lojas. Os instaladores incluem a extensão e o produto base, o que torna as atualizações difíceis. Em cada atualização, uma mesclagem de código e uma geração de pacote são necessárias. Para simplificar o processo, agora os pacotes de extensão são separados em componentes para fácil implantação e gerenciamento. Com a nova abordagem, as extensões e os instaladores do produto base são separados e podem ser atendidos e atualizados de forma independente, sem mesclagem de código ou reempacotamento.|
| **Substituída por outro recurso?**   | Extensões de CSU, instaladores de extensão de POS, instaladores de extensão de Estação de hardware |
| **Áreas afetadas do produto**         | Extensão e implantação do Dynamics 365 Commerce |
| **Opção de implantação**              | Todas |
| **Status**                         | Preterido: a partir da versão 10.0.21, o suporte para implantação de RetailDeployablePackage no LCS será removido em outubro de 2022. |

Para obter mais informações, consulte:

+ [Gerar um pacote separado para o CSU (Commerce Cloud Scale Unit)](../dev-itpro/retail-sdk/retail-sdk-packaging.md#generate-a-separate-package-for-commerce-cloud-scale-unit-csu)
+ [Criar um pacote de extensão do Modern POS](../dev-itpro/pos-extension/mpos-extension-packaging.md)
+ [Integrar o POS a um novo dispositivo de hardware](../dev-itpro/hardware-device-extension.md)
+ Exemplos de código
    + [Cloud Scale Unit](https://github.com/microsoft/Dynamics365Commerce.ScaleUnit)
    + [PDV, CSU e Estação de hardware](https://github.com/microsoft/Dynamics365Commerce.InStore)

### <a name="modernpossln-and-cloudpossln-in-the-retail-sdk"></a>ModernPos.Sln e CloudPos.sln no SDK do Retail

O desenvolvimento de extensão de PDV usando ModernPos.sln, CloudPos.sln, POS.Extension.csproj e a pasta PDV foi preterido na versão 10.0.21. No futuro, use o SDK de empacotamento independente de PDV para extensões de PDV.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Em versões anteriores do SDK do Retail, se houver extensões de PDV, uma mesclagem de código e um novo empacotamento serão necessários para atualizar para a versão mais recente do PDV. A mesclagem de código era um processo de atualização demorado, e você tinha que manter o SDK do Retail completo no repositório. Você também precisava compilar o projeto POS.App principal. Usando o modelo de empacotamento independente, você precisa manter apenas sua extensão. O processo de atualização para a última versão das extensões de PDV é tão fácil quanto atualizar a versão do pacote NuGet que seu projeto consome. As extensões podem ser implantadas de forma independente, e os serviços usam os instaladores de extensão. O PDV base pode ser implantado e mantido separadamente, e não são necessários mesclagem de código ou reempacotamento com o código ou instalador base. |
| **Substituída por outro recurso?**   | [SDK de empacotamento independente de PDV](../dev-itpro/pos-extension/pos-extension-getting-started.md) |
| **Áreas afetadas do produto**         | Implantação e extensão de PDV do Dynamics 365 Commerce |
| **Opção de implantação**              | Todas |
| **Status**                         | Preterido: a partir da versão 10.0.21, o suporte a pacotes de PDV combinados e modelo de extensão usando ModernPos.Sln, CloudPOs.sln e POS.Extensons.csproj no SDK do Retail será removido em abril de 2023. |

## <a name="features-removed-or-deprecated-in-the-commerce-10017-release"></a>Recursos removidos ou substituídos na versão 10.0.17 do Commerce

### <a name="full-dataset-generation-interval-is-deprecated"></a>O intervalo completo de geração do conjunto de dados foi substituído

|  &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | A partir dessa versão, no formulário **Parâmetros do agendador do Commerce** na matriz do Dynamics 365 Headquarters, o campo **Intervalo completo de geração do conjunto de dados em dias** será preterido. Também a partir dessa versão, o campo será removido visualmente para que o valor não possa ser editado. Isso permanecerá como o valor **0**. |
| **Substituída por outro recurso?**   | Não |
| **Áreas afetadas do produto**         | Dynamics 365 Commerce |
| **Opção de implantação**              | Todas|
| **Status**                         | Preterido. Não use este campo nem altere o valor nele.|

## <a name="features-removed-or-deprecated-in-the-commerce-10015-release"></a>Recursos removidos ou substituídos na versão 10.0.15 do Commerce

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>Suporte do Internet Explorer 11 para Dynamics 365 foi substituído

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Desde dezembro de 2020, o suporte do Internet Explorer 11 da Microsoft para todos os produtos Dynamics 365 foi preterido e o Internet Explorer 11 não tem mais suporte desde agosto de 2021.<br><br>Isso afetará os clientes que usam os produtos do Dynamics 365 projetados para serem usados por meio de uma interface do Internet Explorer 11. Depois de agosto de 2021, o Internet Explorer 11 não terá suporte para esses produtos do Dynamics 365. |
| **Substituída por outro recurso?**   | Recomendamos que os clientes façam a transição para o Microsoft Edge.|
| **Áreas afetadas do produto**         | Todos os produtos do Dynamics 365 |
| **Opção de implantação**              | Tudo|
| **Status**                         | Preterido. O Internet Explorer 11 não tem mais suporte desde agosto de 2021.|

## <a name="features-removed-or-deprecated-in-the-commerce-10011-release"></a>Recursos removidos ou substituídos na versão 10.0.11 do Commerce
### <a name="data-action-hooks"></a>Ganchos de ação de dados
| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | O recurso de ganchos de ação de dados foi substituído devido a problemas de desempenho. |
| **Substituída por outro recurso?**   | Recomendamos o uso de [substituições de ação de dados](../e-commerce-extensibility/data-action-overrides.md) para modificar a lógica comercial na camada de ação de dados.|
| **Áreas afetadas do produto**         | Ações de dados de extensibilidade do comércio eletrônico |
| **Opção de implantação**              | Todas |
| **Status**                         | botãoPreterido: a partir da versão 10.0.11 |

### <a name="retail-sdk-support-for-visual-studio-2015-msbuild-140-and-retail-sdkreference-libraries-and-tools"></a>Suporte do SDK do Retail para o Visual Studio 2015, msbuild 14.0 e bibliotecas e ferramentas do SDK\Referência do Retail
| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | O suporte do SDK do Retail para o Visual Studio 2015 foi preterido e atualizado para o suporte ao VS 2017, ao msbuild 15.0 e a todas as bibliotecas de referência e ferramentas do gerador de proxy do Commerce na pasta RetailSDK\References movidas para pacotes NuGet para simplificar o processo de extensão e de atualização do SDK.|
| **Substituída por outro recurso?**   | Recomendamos que você siga as informações em [Migrar o SDK do Retail do Visual Studio 2015 para o Visual Studio 2017](../dev-itpro/retail-sdk/migrate-sdk.md) para atualizar seu sistema. |
| **Áreas afetadas do produto**         | Extensões do SDK do Retail |
| **Opção de implantação**              | Todas |
| **Status**                         | botãoPreterido: a partir da versão 10.0.11 |

### <a name="retail-server-extension-using-iedmmodelextender-and-commercecontroller"></a>Extensão do Servidor do Retail usando IEdmModelExtender e CommerceController
| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | A extensão do Servidor do Retail usando IEdmModelExtender e CommerceController foi preterida para fornecer um modelo de extensão simplificado. A nova implementação terá somente a classe Controller sem nenhuma implementação de classe IEdmModelExtender adicional. Isso também evita a dependência com uma versão do OData específica (se a versão do OData for atualizada, as extensões poderão ser quebradas.) |
| **Substituída por outro recurso?**   |  Recomendamos que você use o modelo de extensão de classe IController, importando o pacote NuGet (Microsoft.Dynamics.Commerce.Hosting.Contracts). |
| **Áreas afetadas do produto**         | Extensões do servidor do Retail |
| **Opção de implantação**              | Todas |
| **Status**                         | botãoPreterido: a partir da versão 10.0.11 |

### <a name="hardware-station-extension-using-ihardwarestationcontroller"></a>Extensão do Hardware Station usando IHardwareStationController
| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | A extensão da estação de hardware usando o IHardwareStationController foi preterida para fornecer um modelo de extensão simplificado. A nova implementação terá somente a classe IController sem qualquer implementação de classe adicional e, para evitar a dependência com as principais bibliotecas do Hardware Station, a extensão anterior precisará se referir a várias bibliotecas. |
| **Substituída por outro recurso?**   | Recomendamos o uso do modelo de extensão de classe IController, importando o pacote NuGet (Microsoft.Dynamics.Commerce.Hosting.Contracts). |
| **Áreas afetadas do produto**         | Extensões do Hardware Station |
| **Opção de implantação**              | Todas |
| **Status**                         | botãoPreterido: a partir da versão 10.0.11 |

## <a name="features-removed-or-deprecated-in-the-commerce-10010-release"></a>Recursos removidos ou substituídos na versão 10.0.10 do Commerce
### <a name="pos-operation-803---picking-and-receiving"></a>Operação PDV 803 - Separação e Recebimento
| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | As operações de separação e recebimento estão sendo preteridas devido à nova reestruturação da operação. |
| **Substituída por outro recurso?**   | Sim. Ele é substituído por duas novas operações PDV: operação de entrada (804) e operação de saída (805).|
| **Áreas afetadas do produto**         | Aplicativo de ponto de venda (PDV) |
| **Opção de implantação**              | Todas |
| **Status**                         | Preterido: a partir da versão 10.0.10, a operação de separação e recebimento não receberá mais nenhuma atualização de recurso nova. Somente correções críticas de bugs serão realizadas para esta operação em versões futuras. Todos os clientes são incentivados a mudar para as novas [operações de entrada](../pos-inbound-inventory-operation.md) e de [saída](../pos-outbound-inventory-operation.md), o que continuará a ser parte de nosso roteiro de produtos de longo prazo. |


## <a name="features-removed-or-deprecated-in-the-commerce-1007-release"></a>Recursos removidos ou substituídos na versão 10.0.7 do Commerce
### <a name="commerce-getproductavailabilities-and-getavailableinventorynearby-apis"></a>API de GetProductAvailabilities e GetAvailableInventoryNearby comerciais
| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | APIs novas e otimizadas foram criadas para substituir APIs GetProductAvailabilities e GetAvailableInventoryNearby. |
| **Substituída por outro recurso?**   | Sim: ele é substituído por APIs de GetEstimatedAvailabilty e GetEstimatedProductWarehouseAvailability. |
| **Áreas afetadas do produto**         | Aplicativo SDK de comércio eletrônico |
| **Opção de implantação**              | Todas |
| **Status**                         | Preterido: a partir da versão 10.0.7, não terão mais investimentos em engenharia feitos para GetProductAvailabilities e GetAvailableInventoryNearby. As organizações que usam essas APIs em suas implantações de comércio eletrônico devem ser convertidas em novas APIs de GetEstimatedAvailability e GetEstimatedProductWarehouseAvailability e habilitar o [Recurso de cálculo de disponibilidade de produtos otimizados](../calculated-inventory-retail-channels.md).  |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Comunicados anteriores sobre recursos removidos ou obsoletos
Para saber mais sobre os recursos que foram removidos ou preteridos em versões anteriores, consulte [Recursos removidos ou obsoletos em versões anteriores](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=/dynamics365/commerce/toc.json).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
