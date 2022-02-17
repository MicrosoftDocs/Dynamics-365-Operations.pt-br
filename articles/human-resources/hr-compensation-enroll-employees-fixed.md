---
title: Inscrever um funcionário em um plano de remuneração fixa
description: A remuneração ou gerente pode atribuir benefícios de funcionários a planos de remuneração fixa ao gerenciar o pagamento base.
author: twheeloc
ms.date: 08/25/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HRMCompFixedEmpl, HRMCompFixedEmplActionDialog, HcmPositionLookup, HRMCompRefPointLookup, HcmCompensationWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b7c2423faa4a0c50d9d319a9e6f489e2946c36a7
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8071406"
---
# <a name="enroll-an-employee-in-a-fixed-compensation-plan"></a>Inscrever um funcionário em um plano de remuneração fixa


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A remuneração ou gerente pode atribuir benefícios de funcionários a planos de remuneração fixa ao gerenciar o pagamento base. Este procedimento pressupõe que um plano fixo esteve criado e está ativo, e as regras de qualificação forem definidas para o plano. A empresa de dados demo usada para criar este procedimento é USMF. Para iniciar o procedimento, acesse **Recursos humanos** > **Trabalhadores** > **Funcionários** > **Remuneração** > **Plano fixo**.

1. Clique em **Novo**.
2. No campo **Ação**, selecione uma Ação de compensação fixa de **Contratar/Recontratar** para descrever a alteração na compensação de funcionário.
3. Na lista, clique no link na linha selecionada.
4. No campo **Posição**, clique no botão suspenso para abrir a pesquisa.
5. Na lista, clique no link na linha selecionada.
    * O nível é exibido a partir da guia rápida **Nível** de remuneração> **>** a partir da **Tarefa** que é atribuída à **posição**. O nível deve ser definido no trabalho antes da remuneração puder ser atribuída ao funcionário.  
6. No campo **Plano**, selecione o plano de remuneração fixa do funcionário. A pesquisa do **plano** é filtrada para mostrar apenas os planos em que o funcionário está qualificado com base nas **regras de qualificação**.
7. Na lista, localize e selecione o PDV desejado.
    * As datas **Efetiva** e de **Vencimento** para o padrão de remuneração das datas de início e de término para a atribuição da posição do funcionário. É possível ajustar essas datas conforme necessário.  
    * Se o plano de remuneração fixa é um plano de etapa, selecione a etapa que contém a taxa de pagamento correta para o funcionário. Se o plano de remuneração fixado é um plano de grade ou faixa, insira a taxa de pagamento correta para o funcionário. A taxa de pagamento será validada nas configurações de tolerância para o plano, e os pontos de referência mínimo e máximo para o nível de remuneração de trabalho.  
8. Clique em **OK**.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
