---
title: Manter roteiro de um modelo de produto
description: Executar este procedimento exige que exista um modelo de configuração do produto.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCRouteOperationDetails, WrkCtrCapabilityLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cc41f99085e5f30ae29edce296a5e3752cbabd33
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422040"
---
# <a name="maintain-route-for-a-product-model"></a>Manter roteiro de um modelo de produto

[!include [banner](../../includes/banner.md)]

Executar este procedimento exige que exista um modelo de configuração do produto. Este procedimento usa o modelo de alto-falante avançado da empresa de demonstração USMF para direcioná-lo pelo processo.


## <a name="add-a-route-operation"></a>Adicione uma operação de roteiro
1. Clique em Definição de modelo de variante de produto.
2. Clique em Modelos de configuração do produto.
3. Na lista, localize e selecione o PDV desejado.
    * Selecione o modelo alto-falante avançado para este exercício.  
4. Na lista, clique no link na linha selecionada.
5. Expandir a seção Operações de roteiro.
6. Clique em Adicionar.
7. No campo Nome, digite um valor.
8. No campo Descrição, digite um valor.
9. Clique em Salvar.

## <a name="enter-route-operation-details"></a>Informe os detalhes da operação do roteiro
1. Clique em Detalhes da operação do roteiro.
2. No campo Operação, insira ou selecione um valor.
3. No campo Nº Não. insira um número.
    * Os números da operação determinam a sequência no roteiro.  
    * Cada propriedade em uma operação de roteiro pode ter um valor estático ou ser mapeada a um atributo. O mapeamento a um atributo resultará no valor que está sendo definido como parte da configuração.  
4. No campo Grupo de roteiro, insira ou selecione um valor.
    * O grupo de roteiros determina o comportamento essencial para o custo, o consumo e a configuração.  
5. Clique na guia Configuração.
6. Clique na guia Horas.
7. Em Processar quantidade. insira um número.
    * Determina a quantidade que será processada em uma operação.  
8. No campo Horas/tempo, insira um número.
    * Digite a razão do tempo.  
9. Marque a caixa de seleção Definir.
10. No campo Tempo de execução, insira um número.
    * Determine o tempo de processamento para a quantidade especificada.  
11. Clique na guia Requisitos de recurso.
12. Clique em Adicionar.
13. Na lista, marque a linha selecionada.
14. No campo Tipo de requisição, selecione uma opção.
    * Decida se deseja especificar os recursos ou os recursos específicos que devem possuir.  
15. No campo Requisito, insira ou selecione um valor.
16. Clique em OK.

