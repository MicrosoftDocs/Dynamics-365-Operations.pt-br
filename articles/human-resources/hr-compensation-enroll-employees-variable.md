---
title: Inscrever um funcionário em um plano de remuneração variável
description: O gerente de remuneração e os benefícios podem inserir funcionários em planos de remuneração variável e calcular os prêmios em dinheiro e não provenientes de pagamento à vista para funcionários.
author: twheeloc
ms.date: 08/25/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HRMCompVarEnrollEmpl, HcmCompensationWorkspace
audience: Application User
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 11f86bfa4bfcece164755bb5d86944e0bed0fff2
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8692272"
---
# <a name="enroll-an-employee-in-a-variable-compensation-plan"></a>Inscrever um funcionário em um plano de remuneração variável


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

O gerente de remuneração e os benefícios podem inserir funcionários em planos de remuneração variável e calcular os prêmios em dinheiro e não provenientes de pagamento à vista para funcionários. Este procedimento pressupõe que um plano de remuneração variável tenha sido criado com o campo **Habilitar inscrição** definido como **Sim**, e que tenham sido criadas regras de qualificação para esse plano de remuneração variável. A empresa de dados demo usada para criar este procedimento é USMF. Para iniciar este procedimento, acesse **Recursos humanos** > **Trabalhadores** > **Funcionários** > **Remuneração** > **Inscrição de plano variável**.

1. Clique em **Novo**.
2. No campo **Plano**, clique no botão suspenso para abrir a pesquisa.
    * A pesquisa do plano será filtrada para mostrar apenas os planos de remuneração variável em que o funcionário está qualificado com base nas regras de qualificação.  
3. Na lista, clique no link na linha selecionada.
4. Alternar a expansão da seção **Geral**.
5. No campo **Data efetiva**, insira uma data.
6. Clique em **Salvar**.
7. Alterne a expansão da seção **Sobreposição**.
    * Opcionalmente, a data de uma regra de contratação pode ser definida para substituir a data de contratação para um funcionário quando a regra de contratação especificada para o plano variável selecionado é porcentagem.  
    * Se o plano variável for uma porcentagem do plano de base, a porcentagem do prêmio pode ser substituída para o funcionário. Se o plano de remuneração variável for um número de plano de unidades, a o número de unidades pode ser substituído por outro funcionário.  
    * Se o funcionário é fornecido um valor liso da concessão, o valor pode ser definido aqui.  
8. Alterne a expansão da seção **Substituições organizacionais**.
    * Se o desempenho do funcionário deve ser levado em consideração, no desempenho de departamentos diferentes ou em um departamento diferente daquele atribuído a posição de um funcionário, o departamento pode ser substituído. A coluna **Porcentagem** deve totalizar 100.  



[!INCLUDE[footer-include](../includes/footer-banner.md)]
