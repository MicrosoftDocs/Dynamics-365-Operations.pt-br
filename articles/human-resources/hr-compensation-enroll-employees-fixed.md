---
title: Inscrever um funcionário em um plano de remuneração fixa
description: A remuneração ou gerente pode atribuir benefícios de funcionários a planos de remuneração fixa ao gerenciar o pagamento base.
author: andreabichsel
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HRMCompFixedEmpl, HRMCompFixedEmplActionDialog, HcmPositionLookup, HRMCompRefPointLookup, HcmCompensationWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e5f0862c86234495c89b2a6ad947cc78e687de37
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054227"
---
# <a name="enroll-an-employee-in-a-fixed-compensation-plan"></a>Inscrever um funcionário em um plano de remuneração fixa

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

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



[!INCLUDE[footer-include](../includes/footer-banner.md)]