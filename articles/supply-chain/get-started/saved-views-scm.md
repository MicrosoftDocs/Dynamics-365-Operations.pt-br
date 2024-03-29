---
title: Exibições salvas padrão para o Supply Chain Management
description: Este artigo descreve as exibições salvas padrão que estão disponíveis e explica como habilitá-las.
author: kamaybac
ms.date: 08/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: f94fffb9aa2c208b8c2c0005a2892853eda66a01
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9334825"
---
# <a name="standard-saved-views-for-supply-chain-management"></a>Exibições salvas padrão para o Supply Chain Management

[!include [banner](../../includes/banner.md)]

O Microsoft Dynamics 365 Supply Chain Management inclui várias exibições salvas que você pode habilitar e usar conforme necessário. Algumas dessas exibições salvas padrão são otimizadas e nomeadas para uma função ou tarefa específica (por exemplo, "Controle de qualidade" ou "Recebimento"). Outras são otimizadas para incluir somente os campos e as configurações que as estatísticas de uso da Microsoft indicam que são usados com mais frequência pelos clientes. Essas exibições salvas normalmente são chamadas de exibições *simplificadas*. Este artigo descreve as exibições salvas padrão que estão disponíveis e explica como habilitá-las e personalizá-las.

Para obter detalhes completos sobre como trabalhar com exibições salvas, incluindo as exibições salvas padrão, depois de habilitá-las, consulte [Exibições salvas](../../fin-ops-core/fin-ops/get-started/saved-views.md?toc=/dynamics365/supply-chain/toc.json).

## <a name="customizing-the-standard-saved-views"></a>Personalizar as exibições salvas padrão

É possível personalizar as exibições salvas padrão, da mesma forma que é possível personalizar suas próprias exibições salvas. No entanto, ao personalizar uma exibição salva padrão, é altamente recomendável que você salve a versão personalizada com um novo nome. Caso contrário, as personalizações poderão ser substituídas quando você atualizar o Supply Chain Management.

Para obter mais informações sobre como personalizar e renomear exibições salvas, consulte [Exibições salvas](../../fin-ops-core/fin-ops/get-started/saved-views.md?toc=/dynamics365/supply-chain/toc.json).

## <a name="available-saved-views-and-how-to-enable-them"></a>Exibições salvas disponíveis e como habilitá-las

Para qualquer exibição salva, independentemente de usar as exibições salvas padrão ou não, você deverá ativar o recurso *Exibições salvas* no [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (a partir da versão 10.0.21, este recurso será habilitado por padrão).

As seções restantes deste artigo fornecem tabelas que descrevem as exibições salvas padrão disponíveis no momento para cada módulo relevante. Cada tabela mostra o nome de cada exibição salva, a página na qual você pode encontrá-la e uma descrição dela. Cada tabela também mostra o nome do recurso que inclui a exibição salva. Para ver uma exibição salva padrão no sistema, você deve ativar o recurso especificado no [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). A partir da versão 10.0.25, todas as exibições listadas serão ativadas por padrão.

## <a name="saved-views-for-the-inventory-management-module"></a>Exibições salvas para o módulo Gerenciamento de estoque

A tabela a seguir descreve as exibições salvas disponíveis para o módulo Gerenciamento de estoque.

| Página | Nome da exibição | Descrição da exibição | Nome do recurso |
|---|---|---|---|
| Lista disponível | Finanças | Esta exibição simplificada permite que você se concentre nas informações financeiras enquanto gerencia o estoque disponível. | Exibições salvas do Gerenciamento de estoque<br><br>(Ativado por padrão a partir da versão 10.0.21. Obrigatório a partir da versão 10.0.29). |
| Lista disponível | Controle de qualidade | Esta exibição simplificada permite que você se concentre no controle de qualidade enquanto gerencia o estoque disponível. | Exibições salvas do Gerenciamento de estoque<br><br>(Ativado por padrão a partir da versão 10.0.21. Obrigatório a partir da versão 10.0.29). |
| Lista disponível | Recebimento | Esta exibição simplificada permite que você se concentre nas operações de recebimento enquanto gerencia o estoque disponível. | Exibições salvas do Gerenciamento de estoque<br><br>(Ativado por padrão a partir da versão 10.0.21. Obrigatório a partir da versão 10.0.29). |
| Lista disponível | Envio | Esta exibição simplificada permite que você se concentre nas operações de remessa enquanto gerencia o estoque disponível. | Exibições salvas do Gerenciamento de estoque<br><br>(Ativado por padrão a partir da versão 10.0.21. Obrigatório a partir da versão 10.0.29). |
| Transações | Simplificado | Esta exibição simplificada permite que você analise o status do estoque sem se distrair com informações financeiras e outros campos usados com menos frequência. | Exibições salvas do Gerenciamento de estoque<br><br>(Ativado por padrão a partir da versão 10.0.21. Obrigatório a partir da versão 10.0.29). |
| Ordens de transferência | Envio | Esta exibição simplificada permite que você se concentre nas operações de remessa enquanto gerencia ordens de transferência. | Exibições salvas do Gerenciamento de estoque<br><br>(Ativado por padrão a partir da versão 10.0.21. Obrigatório a partir da versão 10.0.29). |
| Ordens de transferência | Recebimento | Esta exibição simplificada permite que você se concentre nas operações de recebimento enquanto gerencia ordens de transferência. | Exibições salvas do Gerenciamento de estoque<br><br>(Ativado por padrão a partir da versão 10.0.21. Obrigatório a partir da versão 10.0.29). |
| Ordens de transferência | Controle de qualidade | Esta exibição simplificada permite que você se concentre no controle de qualidade enquanto gerencia ordens de transferência. | Exibições salvas do Gerenciamento de estoque<br><br>(Ativado por padrão a partir da versão 10.0.21. Obrigatório a partir da versão 10.0.29). |
| Ordens de transferência | Finanças | Esta exibição simplificada permite que você se concentre nas informações financeiras enquanto gerencia ordens de transferência. | Exibições salvas do Gerenciamento de estoque<br><br>(Ativado por padrão a partir da versão 10.0.21. Obrigatório a partir da versão 10.0.29). |

## <a name="saved-views-for-the-master-planning-module"></a>Exibições salvas para o módulo Planejamento mestre

A tabela a seguir descreve as exibições salvas disponíveis para o módulo Planejamento mestre.

| Página | Nome da exibição | Descrição da exibição | Nome do recurso |
|---|---|---|---|
| Ordens planejadas: página Detalhes de ordens planejadas | Simplificado | Esta exibição simplificada inclui somente os campos usados com mais frequência para trabalhar com os detalhes de uma única ordem planejada. Dessa forma, ela fornece uma visão geral mais rápida e um processo de trabalho simplificado. | Exibições salvas para ordens planejadas<br><br>(Ativado por padrão a partir da versão 10.0.25. Obrigatório a partir da versão 10.0.29). |
| Ordens planejadas: página Lista de ordens planejadas | Simplificado | Esta exibição simplificada inclui somente os campos usados com mais frequência para trabalhar com a lista de ordens planejadas. Dessa forma, ela fornece uma visão geral mais rápida e um processo de trabalho simplificado. | Exibições salvas para ordens planejadas<br><br>(Ativado por padrão a partir da versão 10.0.25. Obrigatório a partir da versão 10.0.29). |

## <a name="saved-views-for-the-procurement-and-sourcing-module"></a>Exibições salvas para o módulo Compras e fornecimento

A tabela a seguir descreve as exibições salvas disponíveis para o módulo Compras e fornecimento.

| Página | Nome da exibição | Descrição da exibição | Nome do recurso |
|---|---|---|---|
| Detalhes da ordem de compra | Criação de ordens | Esta exibição simplificada é otimizada para a criação de novas ordens de compra. | Exibições salvas para ordens de compra<br><br>Ativado por padrão a partir da versão 10.0.25. Obrigatório a partir da versão 10.0.29). |
| Detalhes da ordem de compra | Gerenciamento de estoque | Esta exibição simplificada é otimizada para executar atividades relacionadas ao estoque, como acompanhamento de estoque recebido, recebimento de estoque, verificação de requisições líquidas e ajuste de quantidades de ordens. | Exibições salvas para ordens de compra<br><br>Ativado por padrão a partir da versão 10.0.25. Obrigatório a partir da versão 10.0.29). |
| Detalhes da ordem de compra | Gerenciamento financeiro | Esta exibição simplificada é otimizada para executar atividades relacionadas às finanças, como faturamento e verificação de preços, totais e encargos. | Exibições salvas para ordens de compra<br><br>Ativado por padrão a partir da versão 10.0.25. Obrigatório a partir da versão 10.0.29). |
| Detalhes da ordem de compra | Aprovação de ordem | Esta exibição simplificada é otimizada para a aprovação de ordens de compra. | Exibições salvas para ordens de compra<br><br>Ativado por padrão a partir da versão 10.0.25. Obrigatório a partir da versão 10.0.29). |

## <a name="saved-views-for-the-product-information-management-module"></a>Exibições salvas para o módulo Gerenciamento de informações do produto

A tabela a seguir descreve as exibições salvas disponíveis para o módulo Gerenciamento de informações do produto.

| Página | Nome da exibição | Descrição da exibição | Nome do recurso |
|---|---|---|---|
| Lista de produtos liberados | Criação do produto | Uma exibição de página simplificada que só inclui os campos mais usados ao criar produtos. | Exibições salvas para produtos liberados<br><br>(Ativado por padrão a partir da versão 10.0.21. Obrigatório a partir da versão 10.0.29). |
| Detalhes do produto liberado | Criação do produto | Uma exibição de página simplificada que só inclui os campos mais usados ao criar produtos. | Exibições salvas para produtos liberados<br><br>(Ativado por padrão a partir da versão 10.0.21. Obrigatório a partir da versão 10.0.29). |
| Detalhes do produto liberado | Gerenciamento de informações logísticas | Uma exibição de página simplificada que só inclui os campos mais usados ao gerenciar informações logísticas para produtos. | Exibições salvas para produtos liberados<br><br>(Ativado por padrão a partir da versão 10.0.21. Obrigatório a partir da versão 10.0.29). |
| Detalhes do produto liberado | Gerenciamento de informações de compra | Uma exibição de página simplificada que só inclui os campos mais usados ao gerenciar informações de compra de produtos. | Exibições salvas para produtos liberados<br><br>(Ativado por padrão a partir da versão 10.0.21. Obrigatório a partir da versão 10.0.29). |
| Detalhes do produto liberado | Gerenciamento de informações de venda | Uma exibição de página simplificada que só inclui os campos mais usados ao gerenciar informações relativas a vendas de produtos. | Exibições salvas para produtos liberados<br><br>(Ativado por padrão a partir da versão 10.0.21. Obrigatório a partir da versão 10.0.29). |

## <a name="saved-views-for-the-production-control-module"></a>Exibições salvas para o módulo Controle de produção

A tabela a seguir descreve as exibições salvas disponíveis para o módulo Controle de produção.

| Página | Nome da exibição | Descrição da exibição | Nome do recurso |
|---|---|---|---|
| Página BOM de ordens de produção | Simplificado | Esta exibição simplificada inclui somente os campos usados com mais frequência. Dessa forma, ela fornece uma visão geral mais rápida e um processo de trabalho simplificado. | Exibições salvas para controle de produção<br><br>(Ativado por padrão a partir da versão 10.0.21. Obrigatório a partir da versão 10.0.29). |
| Página Detalhes de ordens de produção | Simplificado | Esta exibição simplificada inclui somente os campos usados com mais frequência. Dessa forma, ela fornece uma visão geral mais rápida e um processo de trabalho simplificado. | Exibições salvas para controle de produção<br><br>(Ativado por padrão a partir da versão 10.0.21. Obrigatório a partir da versão 10.0.29). |
| Página Lista de separação de ordens de produção | Simplificado | Esta exibição simplificada inclui somente os campos usados com mais frequência. Dessa forma, ela fornece uma visão geral mais rápida e um processo de trabalho simplificado. | Exibições salvas para controle de produção<br><br>(Ativado por padrão a partir da versão 10.0.21. Obrigatório a partir da versão 10.0.29). |
| Página Lista de ordens de produção | Simplificado | Esta exibição simplificada inclui somente os campos usados com mais frequência. Dessa forma, ela fornece uma visão geral mais rápida e um processo de trabalho simplificado. | Exibições salvas para controle de produção<br><br>(Ativado por padrão a partir da versão 10.0.21. Obrigatório a partir da versão 10.0.29). |

## <a name="saved-views-for-the-sales-and-marketing-module"></a>Exibições salvas para o módulo Vendas e marketing

A tabela a seguir descreve as exibições salvas disponíveis para o módulo Vendas e marketing.

| Página | Nome da exibição | Descrição da exibição | Nome do recurso |
|---|---|---|---|
| Diário de Guias de Remessa | Análise de diários | Esta exibição simplificada inclui somente os campos usados com mais frequência para analisar diários de guia de remessa. | Exibições salvas para vendas e marketing<br><br>(Ativado por padrão a partir da versão 10.0.25. Obrigatório a partir da versão 10.0.29). |
| Ordem de venda | Criação de ordens | Esta exibição simplificada inclui somente os campos usados com mais frequência para criar ordens de venda. | Exibições salvas para vendas e marketing<br><br>(Ativado por padrão a partir da versão 10.0.25. Obrigatório a partir da versão 10.0.29). |
| Ordem de venda | Revisão de ordens | Esta exibição simplificada inclui somente os campos usados com mais frequência para analisar ordens de venda. | Exibições salvas para vendas e marketing<br><br>(Ativado por padrão a partir da versão 10.0.25. Obrigatório a partir da versão 10.0.29). |
| Cotação de Venda | Criação de cotação | Esta exibição simplificada inclui somente os campos usados com mais frequência para criar cotações de venda. | Exibições salvas para vendas e marketing<br><br>(Ativado por padrão a partir da versão 10.0.25. Obrigatório a partir da versão 10.0.29). |

## <a name="saved-views-for-the-warehouse-management-module"></a>Exibições salvas para o módulo Gerenciamento de depósito

A tabela a seguir descreve as exibições salvas disponíveis para o módulo Gerenciamento de depósito.

| Página | Nome da exibição | Descrição da exibição | Nome do recurso |
|---|---|---|---|
| Todas as cargas | Processamento de entrada | Esta exibição simplificada inclui somente os campos usados com mais frequência para processar cargas de entrada. | Exibições salvas para o processamento de carga<br><br>(Ativado por padrão a partir da versão 10.0.25. Obrigatório a partir da versão 10.0.29). |
| Todas as cargas | Processamento de saída | Esta exibição simplificada inclui somente os campos usados com mais frequência para processar cargas de saída. | Exibições salvas para o processamento de carga<br><br>(Ativado por padrão a partir da versão 10.0.25. Obrigatório a partir da versão 10.0.29). |
| Todas as remessas | Processamento de entrada | Esta exibição simplificada inclui somente os campos usados com mais frequência para processar remessas de entrada. | Exibições salvas para o processamento de remessa<br><br>(Ativado por padrão a partir da versão 10.0.25. Obrigatório a partir da versão 10.0.29). |
| Todas as remessas | Processamento de saída | Esta exibição simplificada inclui somente os campos usados com mais frequência para processar remessas de saída. | Exibições salvas para o processamento de remessa<br><br>(Ativado por padrão a partir da versão 10.0.25. Obrigatório a partir da versão 10.0.29). |
| Todas as ondas | Simplificado | Esta exibição simplificada inclui somente os campos usados com mais frequência. Dessa forma, ela fornece uma visão geral mais rápida e um processo de trabalho simplificado. | Exibição salva para o processamento de ciclo<br><br>(Ativado por padrão a partir da versão 10.0.25. Obrigatório a partir da versão 10.0.29). |
| Bancada do planejamento de carga | Simplificado | Esta exibição simplificada inclui somente os campos usados com mais frequência. Dessa forma, ela fornece uma visão geral mais rápida e um processo de trabalho simplificado. | Exibição salva da bancada de planejamento da carga<br><br>(Ativado por padrão a partir da versão 10.0.25. Obrigatório a partir da versão 10.0.29). |
| Detalhes do trabalho | Simplificado | Esta exibição simplificada inclui somente os campos usados com mais frequência. Dessa forma, ela fornece uma visão geral mais rápida e um processo de trabalho simplificado. | Exibição salva da página de detalhes do trabalho<br><br>(Ativado por padrão a partir da versão 10.0.25. Obrigatório a partir da versão 10.0.29). |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]