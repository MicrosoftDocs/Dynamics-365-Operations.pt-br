---
title: Opções de implementação da rede de distribuição de conteúdo
description: Este artigo revisa as diferentes opções para a implementação da CDN (rede de distribuição de conteúdo) que pode ser usada com ambientes do Microsoft Dynamics 365 Commerce. Essas opções incluem instâncias nativas fornecidas pelo Commerce do Azure Front Door e instâncias de propriedade do cliente do Azure Front Door.
author: BrianShook
ms.date: 07/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-11-01
ms.dyn365.ops.version: 10.0.14
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: de2ecab86809af3ace64ba06956f00137d254ab7
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275138"
---
# <a name="content-delivery-network-implementation-options"></a>Opções de implementação da rede de distribuição de conteúdo

[!include [banner](includes/banner.md)]

Este artigo revisa as diferentes opções para a implementação da CDN (rede de distribuição de conteúdo) que pode ser usada com ambientes do Microsoft Dynamics 365 Commerce. Essas opções incluem instâncias nativas fornecidas pelo Commerce do Azure Front Door e instâncias de propriedade do cliente do Azure Front Door.

Os clientes comerciais têm várias opções quando estão considerando qual serviço CDN usar com seu ambiente comercial. O Commerce é liberado com o suporte básico ao Azure Front Door que cobre requisitos básicos de hospedagem e de domínio personalizado. Para as empresas que desejam mais controle e habilidades de segurança mais específicas, como um firewall de aplicativos da Web (WAF), a melhor opção pode ser usar uma instância do Azure Front Door de propriedade do cliente ou um serviço CDN externo.

As três opções de implementação da CDN a seguir podem ser usadas com ambientes do Commerce:

- A instância do Azure Front Door fornecida pelo Commerce
- Uma instância do Azure Front Door de propriedade do cliente (para maior controle e recursos de segurança adicionais)
- Um serviço CDN externo

Todas as três opções de implementação de CDN fornecem somente conteúdo HTML dinâmico de domínios personalizados. O Commerce manipula automaticamente todas as Folhas de Estilo em Cascata (CSS), JavaScript, imagens, vídeo e outros conteúdos estáticos por meio das CDNs gerenciadas pela Microsoft. A opção escolhida determina os recursos operacionais, as capacidades de controle e os recursos de segurança adicionais disponíveis.

A ilustração a seguir mostra uma visão geral da arquitetura do Commerce.

![Visão geral da arquitetura do Commerce.](media/Commerce_CDN-Option_ComparisonModels.png)

Para obter mais informações sobre como configurar uma instância do Azure Front Door para seu site do Commerce, consulte [Adicionar suporte à CDN](add-cdn-support.md).

## <a name="use-the-commerce-provided-azure-front-door-instance"></a>Usar a instância do Azure Front Door fornecida pelo Commerce

A tabela a seguir lista os prós e contras do uso da instância do Azure Front Door fornecida pelo Commerce para gerenciar pontos de extremidade de conteúdo.

| Prós | Contras |
|------|------|
| <ul><li>A instância foi incluída no custo do Commerce.</li><li>Como a instância é gerenciada pela equipe do Commerce, menos manutenção é necessária e existem etapas de configuração compartilhadas.</li><li>A infraestrutura hospedada pelo Azure é escalonável, segura e confiável.</li><li>O certificado SSL (Secure Sockets Layer) requer uma configuração ocasional e é automaticamente renovado.</li><li>A instância é monitorada em busca de erros e anomalias pela equipe do Commerce.</li></ul> | <ul><li>Não há suporte para uma WAF.</li><li>Não há personalizações específicas nem ajustes de configuração.</li><li>A instância depende da equipe do Commerce para atualizações ou alterações.</li><li>Uma instância separada do Azure Front Door é necessária para domínios apex, e o trabalho extra é necessário para integrar os domínios apex ao DNS do Azure.</li><li>Nenhuma telemetria sobre respostas por segundo (RPS) ou taxa de erro é fornecida ao cliente.</li></ul> |

A ilustração a seguir mostra a arquitetura da instância do Azure Front Door fornecida pelo Commerce.

![Instância do Azure Front Door fornecida pelo Commerce.](media/Commerce_CDN-Option_CommerceFrontDoor.png)

## <a name="use-a-customer-owned-azure-front-door-instance"></a>Usar uma instância do Azure Front Door de propriedade do cliente

A tabela a seguir lista os prós e contras do uso da instância do Azure Front Door de propriedade do cliente para gerenciar pontos de extremidade de conteúdo.

| Prós | Contras |
|------|------|
| <ul><li>A configuração é segura e fácil de gerenciar.</li><li>A infraestrutura hospedada pelo Azure é escalonável, segura e confiável.</li><li>A instância permite a integração do WAF e os controles de regras granulares para a segurança mais ajustada especificamente para o seu site.</li><li>A instância permite um controle mais preciso de certificados SSL (de propriedade do cliente e gerenciados pelo Azure Front Door) e vinculação de domínio.</li><li>A instância oferece uma solução de domínio apex se estiver emparelhada diretamente com o DNS do Azure.</li><li>Telemetria e alertas são fornecidos.</li><li>O certificado SSL requer uma configuração ocasional e é automaticamente renovado.</li></ul> | <ul><li>A instância é autogerenciada.</li><li>É necessário o crescimento inicial do conhecimento.</li></ul> |

A ilustração a seguir mostra uma infraestrutura do Commerce que inclui uma instância do Azure Front Door pertencente ao cliente.

![Infraestrutura do Commerce que inclui uma instância do Azure Front Door pertencente ao cliente.](media/Commerce_CDN-Option_CustomerOwnedAzureFrontDoor.png)

## <a name="use-an-external-cdn-service"></a>USar um serviço CDN externo

A tabela a seguir lista os prós e contras do uso de um serviço CDN externo para gerenciar pontos de extremidade de conteúdo.

| Prós | Contras |
|------|------|
| <ul><li>Essa opção é útil quando o domínio existente já está hospedado em uma CDN externa.</li><li>WAF: depende do provedor externo.</li></ul> | <ul><li>São necessários um contrato separado e custos adicionais.</li><li>O SSL pode incorrer em custos adicionais.</li><li>Como o serviço é separado da estrutura de nuvem do Azure, a infraestrutura adicional deve ser gerenciada.</li><li>O serviço pode exigir investimentos maiores no ponto de extremidade e na configuração de segurança.</li><li>O serviço é autogerenciado.</li><li>O serviço é automonitorado.</li></ul> |

A ilustração a seguir mostra uma infraestrutura do Commerce que inclui um serviço CDN externo.

![Infraestrutura do Commerce que inclui um serviço CDN externo.](media/Commerce_CDN-Option_ExternalFrontDoor.png)

## <a name="additional-resources"></a>Recursos adicionais

[Adicionar suporte a uma rede de distribuição de conteúdo (CDN)](add-cdn-support.md)
