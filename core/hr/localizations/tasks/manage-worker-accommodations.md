--- 
title: "Gerenciar acomodações do trabalhador"
description: "Este procedimento apresenta as etapas para configurar os tipos de acomodação do ambiente de trabalho, como cadeiras ergonômicas ou intervalos periódicos."
author: ShielaSogge
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
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 3d2f17d7841275e18a32382c5644253f3f4fe2eb
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="manage-worker-accommodations"></a>Gerenciar acomodações do trabalhador

[!include[task guide banner](../../../includes/task-guide-banner.md)]

Este procedimento apresenta as etapas para configurar os tipos de acomodação do ambiente de trabalho, como cadeiras ergonômicas ou intervalos periódicos. Mostra também como atribuir esses tipos de acomodação a um funcionário, e tanto aprovar como negar o tipo de acomodação. A empresa de dados demo usada para criar este procedimento é USMF.


## <a name="setup-accommodations"></a>Instalar acomodações
1. Vá para Recursos humanos > Configurar > Tipos de acomodação.
2. Clique em Novo.
3. No campo Tipo de acomodação, insira um nome para a acomodação. Exemplo: Teclado.
4. No campo Descrição, insira uma descrição para a acomodação. Exemplo: Teclado ergonômico.
5. No campo Nota, insira qualquer informação que ajude a esclarecer a acomodação.
6. Clique em Salvar.
7. Feche a página.

## <a name="assign-accommodations"></a>Atribuir acomodações
1. Vá para Recursos humanos > Trabalhadores > Funcionários.
2. Da lista, selecione um funcionário.
3. Clique no nome do funcionário para exibir detalhes sobre o funcionário que está solicitando a acomodação.
4. Expanda a aba rápida Informações pessoais.
5. Clique em Acomodações.
6. Clique em Novo.
7. No campo Tipo de acomodação, selecione a acomodação apropriada. Exemplo: Teclado
8. No campo Tarefa de trabalho, insira a tarefa de trabalho que exige a acomodação.
9. No campo Status, insira o status apropriado. Exemplo: Razoável
    * Os seguintes status estão disponíveis. Solicitada indica que a acomodação foi criada mas ainda não foi revisada. Razoável indica que a acomodação é razoável e será concedida. Dificuldades inaceitáveis indica que a acomodação colocará uma carga excessiva sobre o empregado, e foi negada. Neste exemplo, a solicitação foi aprovada imediatamente porque a solicitação de acomodação foi mínima.  
10. No campo Aceito, selecione a pessoa que aceitou a solicitação de acomodação.
11. Clique em Selecionar.
12. No campo Data de aceite, insira a data e hora em que a solicitação de acomodação foi aceitada.
13. Expanda a seção Nota.
14. No campo Financeiro, insira qualquer informação ou custos de recurso que ajudem a esclarecer o impacto da acomodação.
    * Se a acomodação foi negada, o campo Responder pode ser usado para indicar o motivo pelo qual a solicitação foi negada.  
15. Clique em Salvar.


