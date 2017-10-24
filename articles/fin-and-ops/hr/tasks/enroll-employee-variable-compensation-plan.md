--- 
title: "Inscrever um funcionário em um plano de remuneração variável"
description: "O gerente de remuneração e benefícios pode inscrever os funcionários em planos de remuneração variável para calcular prêmios em dinheiro e que não sejam em dinheiro para os funcionários."
author: kherr75
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: eb162e22276fc19cf11999380d551b29ba6a6d45
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="enroll-an-employee-in-a-variable-compensation-plan"></a>Inscrever um funcionário em um plano de remuneração variável

[!include[task guide banner](../../includes/task-guide-banner.md)]

O gerente de remuneração e benefícios pode inscrever os funcionários em planos de remuneração variável para calcular prêmios em dinheiro e que não sejam em dinheiro para os funcionários. Este procedimento pressupõe que um plano de remuneração variável tenha sido criado com o campo Habilitar inscrição definido como Sim, e que tenham sido criadas regras de qualificação para esse plano de remuneração variável. A empresa de dados demo usada para criar este procedimento é USMF. Para iniciar este procedimento, vá para Recursos humanos > Trabalhadores > Funcionários > Remuneração > Inscrição de plano variável

1. Clique em Novo.
2. No campo Plano, clique no botão suspenso para abrir a pesquisa.
    * A pesquisa do plano será filtrada para mostrar apenas os planos de remuneração variável em que o funcionário está qualificado com base nas regras de qualificação.  
3. Na lista, clique no link na linha selecionada.
4. Alternar a expansão da seção Geral.
5. No campo Data efetiva, insira uma data.
6. Clique em Salvar.
7. Alternar a expansão da seção Sobreposição.
    * Opcionalmente, a data de uma regra de contratação pode ser definida para substituir a data de contratação para um funcionário quando a regra de contratação especificada para o plano variável selecionado é porcentagem.  
    * Se o plano variável for uma porcentagem do plano de base, a porcentagem do prêmio pode ser substituída para o funcionário. Se o plano de remuneração variável for um número de plano de unidades, a o número de unidades pode ser substituído por outro funcionário.  
    * Se o funcionário é fornecido um valor liso da concessão, o valor pode ser definido aqui.  
8. Ative a expansão da seção Substituições organizacional.
    * Se o desempenho do funcionário deve ser levado em consideração, no desempenho de departamentos diferentes ou em um departamento diferente daquele atribuído a posição de um funcionário, o departamento pode ser substituído. A porcentagem da coluna deve totalizar 100.  


