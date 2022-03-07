---
title: Manter roteiro de um modelo de produto
description: Executar este procedimento exige que exista um modelo de configuração do produto.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCRouteOperationDetails, WrkCtrCapabilityLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 704a6b72c9eb8dc49ba9410ccd3689ba5ccfdd1f03e538b95ad174f6c1ee9796
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6746127"
---
# <a name="maintain-route-for-a-product-model"></a>Manter roteiro de um modelo de produto

[!include [banner](../../includes/banner.md)]

Executar este procedimento exige que exista um modelo de configuração do produto. Este procedimento usa o modelo de alto-falante avançado da empresa de demonstração USMF para direcioná-lo pelo processo.

## <a name="add-a-route-operation"></a>Adicione uma operação de roteiro

1. Acesse **Gerenciamento de informações do produto \> Produtos \> Modelos de configuração do produto**.
1. Na lista, localize e selecione o registro desejado.
    * Selecione o modelo alto-falante avançado para este exercício.  
1. Na lista, selecione o link na linha selecionada.
1. Expandir a seção **Operações de roteiro**.
1. Selecione **Adicionar**.
1. No campo **Nome**, digite um valor.
1. No campo **Descrição**, digite um valor.
1. Selecione **Salvar**.

## <a name="enter-route-operation-details"></a>Informe os detalhes da operação do roteiro

1. Selecione **Detalhes da operação do roteiro**.
1. No campo **Operação**, insira ou selecione um valor.
1. No campo **Oper. N°**, insira um número.
    * Os números da operação determinam a sequência no roteiro.  
    * Cada propriedade em uma operação de roteiro pode ter um valor estático ou ser mapeada a um atributo. O mapeamento a um atributo resultará no valor que está sendo definido como parte da configuração.  
1. No campo **Grupo de roteiros**, insira ou selecione um valor.
    * O grupo de roteiros determina o comportamento essencial para o custo, o consumo e a configuração.  
1. Selecione a guia **Configuração**.
1. Selecione a guia **Horas**.
1. No campo **Processar qtd.**, insira um número.
    * Determina a quantidade que será processada em uma operação.  
1. No campo **Horas/tempo**, insira um número.
    * Digite a razão do tempo.  
1. Marque a caixa de seleção **Definir**.
1. No campo **Tempo de execução**, insira um número.
    * Determine o tempo de processamento para a quantidade especificada.  
1. Selecione a guia **Requisitos de recursos**.
1. Selecione **Adicionar**.
1. Na lista, marque a linha selecionada.
1. No campo **Tipo de requisito**, selecione uma opção.
    * Decida se deseja especificar os recursos ou os recursos específicos que devem possuir.  
1. No campo **Requisito**, insira ou selecione um valor.
1. Selecione **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]