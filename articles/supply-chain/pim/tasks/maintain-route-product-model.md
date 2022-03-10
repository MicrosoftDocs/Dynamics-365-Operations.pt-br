---
title: Manter roteiro de um modelo de produto
description: Executar este procedimento exige que exista um modelo de configuração do produto.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCRouteOperationDetails, WrkCtrCapabilityLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 88df8b867ac7f354417add0462e7999747333451
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7577255"
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