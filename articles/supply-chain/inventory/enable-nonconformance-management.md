---
title: "Gerenciamento de não conformidade"
description: "Este artigo de instalação básico descreve o que é necessário para usar não conformidades. A configuração adicional é necessária se desejar usar ordens de qualidade."
author: perlynne
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventParameters, InventProblemType, InventProblemTypeSetup, InventQuarantineZone, InventTestDiagnosticType, InventTestReportSetup, SysUserManagement
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 28951
ms.assetid: a62d4ba8-eebc-4b14-b587-630be7298522
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 7a6f7c12ab5fe5e67ffb844c1dbc6cd688ecd4d5
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---

# <a name="nonconformance-management"></a>Gerenciamento de não conformidade

[!include[banner](../includes/banner.md)]


Este artigo de instalação básico descreve o que é necessário para usar não conformidades. A configuração adicional é necessária se desejar usar ordens de qualidade.

Para habilitar o gerenciamento de não conformidade, siga estas etapas:

1.  Defina os parâmetros de gerenciamento de estoque e de depósito relacionados a não conformidades:
    -   Defina a opção **Usar gerenciamento de qualidade** como **Sim**.
    -   No campo **Preço por hora**, insira um preço de mão de obra por hora na moeda local. O preço por hora é usado para calcular o custo de operações relacionadas à não conformidade. O preço por hora e os custos calculados fornecem informações de referência para uma não conformidade. Eles não interagem com outra funcionalidade.
    -   Use a guia **Gerenciamento de qualidade** na página **Configuração de relatório** para definir o tipo de documento a ser impresso. Você pode imprimir um relatório de não conformidade, uma etiqueta de não conformidade ou um relatório de correção. É possível definir mais de um registro para imprimir tipos de documento diferentes em um relatório ou para imprimir anotações internas e externas. Talvez você ache útil usar a página **Tipo de documento** para definir um tipo de documento exclusivo para uma não conformidade e um tipo de documento exclusivo para correções. Por exemplo, desejar inserir anotações sobre uma não conformidade usando o tipo de documento exclusivo de não conformidades. Nesse caso, identifique o tipo de documento exclusivo nas opções do relatório.
    -   Habilite as sequências numéricas para a não conformidade e as referências de correção.

2.  Habilite a aprovação do usuário de não conformidades. Use o campo **Nome** na página **Usuários** para atribuir um funcionário a cada usuário que deva aprovar uma não conformidade. O sistema usa os funcionários que alteram o status de uma não conformidade para controlar o histórico de não conformidade. Os usuários não poderão aprovar uma não conformidade a menos que tenham um identificador de funcionário atribuído.
3.  Defina os tipos de problema que serão atribuídos a uma não conformidade. Use a página **Tipos de problema** para definir uma classificação dos problemas de qualidade que são encontrados nos vários tipos de não conformidade. Você pode configurar os seguintes tipos de não conformidade: **Interno**, **Cliente**, **Fornecedor**, **Solicitação de serviço**, **Produção** e **Produção do coproduto**. Use a página **Tipos de não conformidade** para autorizar um tipo de problema a ser usado em um ou vários tipos de não conformidade. Por exemplo, um tipo de problema relativo a um código de defeito pode se aplicar a todos os tipos de não conformidade, enquanto um tipo relacionado a reclamações do cliente pode se aplicar somente aos tipos de não conformidade **Cliente** e **Solicitação de serviço**.
4.  Defina as zonas de quarentena para fornecer orientação sobre como lidar com material defeituoso. Use a página **Zonas de quarentena** para definir zonas que podem ser atribuídas a uma não conformidade. A etiqueta de não conformidade impressa mostrará a zona de quarentena atribuída e informações sobre o uso para orientar sobre como manusear o material defeituoso. As zonas podem corresponder a localizações de estoque ou recursos de operações.
5.  Defina os tipos de diagnóstico que serão atribuídos a correções. Use a página **Tipos de diagnóstico** para definir uma classificação de ações de diagnóstico. Uma correção especifica o tipo de ação de diagnóstico que deve ser tomada para uma não conformidade aprovada e quem deve realizar essa ação. Ela também especifica a data de conclusão solicitada e a data de conclusão planejada.
6.  Defina as operações relacionadas que serão atribuídas a uma não conformidade. Use a página **Operações** para definir uma classificação do trabalho que pode ser realizado para uma não conformidade aprovada. Quando você atribui uma operação relacionada a uma não conformidade, também pode fornecer informações detalhadas sobre o material associado, as horas de mão-de-obra e os encargos diversos necessários para executar a operação. Essa informação é usada para calcular um custo estimado para a operação. As informações detalhadas e os custos estimados são para referência apenas. As operações relacionadas para qualidade diferem das operações que podem ser definidas para um roteiro de produção.


<a name="see-also"></a>Consulte também
--------

[Criar e processar uma não conformidade (Guia de tarefas)](/dynamics365/unified-operations/supply-chain/inventory/tasks/create-process-non-conformance)

[Processos de gerenciamento de qualidade](quality-management-processes.md)

[Configurar pré-requisitos do gerenciamento de não conformidade (Guia de tarefas)](/dynamics365/unified-operations/supply-chain/inventory/tasks/set-up-prerequisites-nonconformance-management)
