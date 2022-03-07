---
title: Inscrever um funcionário em um plano de remuneração fixa
description: A remuneração ou gerente pode atribuir benefícios de funcionários a planos de remuneração fixa ao gerenciar o pagamento base.
author: andreabichsel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMCompFixedEmpl, HRMCompFixedEmplActionDialog, HcmPositionLookup, HRMCompRefPointLookup, HcmCompensationWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bc8373a4a39a1a212ab445b2b300fbddfe0e4a39
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "5111495"
---
# <a name="enroll-an-employee-in-a-fixed-compensation-plan"></a>Inscrever um funcionário em um plano de remuneração fixa

A remuneração ou gerente pode atribuir benefícios de funcionários a planos de remuneração fixa ao gerenciar o pagamento base. Este procedimento pressupõe que um plano fixo esteve criado e está ativo, e as regras de qualificação forem definidas para o plano. A empresa de dados demo usada para criar este procedimento é USMF. Para iniciar o procedimento, vá para Recursos humanos > Trabalhadores > Funcionários > Remuneração > Plano fixo

1. Clique em Novo.
2. No campo Ação, selecione uma Ação de compensação fixa do tipo Contratar/Recontratar para descrever a alteração na compensação de funcionário.
3. Na lista, clique no link na linha selecionada.
4. No campo Posição, clique no botão suspenso para abrir a pesquisa.
5. Na lista, clique no link na linha selecionada.
    * O nível que é é exibido em nível de remuneração dos trabalhos na posição. O nível deve ser definido no trabalho antes da remuneração puder ser atribuída ao funcionário.  
6. No campo Plano, selecione o plano de remuneração fixa do funcionário. A pesquisa do plano é filtrada para mostrar apenas os planos em que o funcionário está qualificado com base nas regras de qualificação.
7. Na lista, localize e selecione o PDV desejado.
    * O efetivo e as datas de vencimento para o padrão de remuneração desde o início e fim para a atribuição da posição do funcionário. É possível ajustar essas datas conforme necessário.  
    * Se o plano de remuneração fixa é um plano de etapa, selecione a etapa que contém a taxa de pagamento correta para o funcionário. Se o plano de remuneração fixado é um plano de grade ou faixa, insira a taxa de pagamento correta para o funcionário. A taxa de pagamento será validada nas configurações de tolerância para o plano, e os pontos de referência mínimo e máximo para o nível de remuneração de trabalho.  
8. Clique em OK.

