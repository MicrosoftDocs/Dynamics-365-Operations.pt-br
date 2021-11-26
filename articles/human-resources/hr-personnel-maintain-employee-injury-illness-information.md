---
title: Manter informações de ferimentos e doenças de funcionários
description: Esta tarefa descreve como criar um caso de lesão ou doença.
author: twheeloc
ms.date: 11/03/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HRMInjuryIncident, HcmWorkerLookUp, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7c351919616c8ab5cf15d14c6cc79a5097e248fc
ms.sourcegitcommit: 7e0e2a266d9a9473df72e207554d9bd150e17ce3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2021
ms.locfileid: "7771234"
---
# <a name="maintain-employee-injury-and-illness-information"></a>Manter informações de ferimentos e doenças de funcionários

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



É recomendável concluir a primeira guia de tarefas 'Configuração de lesões e doenças', pois algumas informações de configuração são usadas aqui. 



Essa gravação de tarefa descreve as etapas básicas para criar um caso de lesão ou de doença. Além dos detalhes da lesão ou doença, um status de caso é rastreado. Por padrão, os casos têm o status **Aberto**. Você pode gerenciar o status usando o item de menu **Status do caso** na parte superior da página.

1. Acesse **Recursos humanos \> Trabalhadores \> Lesão e doença \> Incidentes de lesão ou doença**.
2. Selecione **Novo**.
3. No campo **Descrição do caso**, insira um valor (por exemplo, **Lesão no pulso**).
4. No campo **Trabalhador**, insira ou selecione um valor (por exemplo, **Ana Bowman**).
5. No campo **Data e hora do incidente**, insira uma data e hora (por exemplo, 20 de janeiro de 2016, às 10h).
6. No campo **Tipo de lesão ou doença**, insira ou selecione um valor (por exemplo, **Fratura**).
7. No campo **Parte do corpo**, insira ou selecione um valor (por exemplo, **Pulso**).
8. No campo **Tipo de resultado**, insira ou selecione um valor (por exemplo, **Terapia**).
9. No campo **Data e hora relatadas**, insira uma data e hora.

    A data e a hora reportadas devem ser posteriores à data e à hora do incidente.

10. No campo **Pessoa que reportou o caso**, insira ou selecione um valor (por exemplo, **Ana Bowman**).

    A pessoa especificada pode ser o funcionário ou outra testemunha do incidente.

11. Na seção **Incidente**, no campo **Onde o incidente ocorreu**, insira um valor (por exemplo, **Depósito**).
12. No campo **No local de trabalho**, selecione **Sim** se o incidente tiver ocorrido no local de trabalho.
13. No campo **Data e hora de início do trabalho**, insira a data e a hora em que a pessoa afetada começou a trabalhar antes do incidente ocorrer.
14. No campo **Trabalho ou tarefa do funcionário**, insira o trabalho ou a tarefa que o trabalhador estava executando quando o incidente ocorreu (por exemplo, **Carregando caixas**). 
15. No campo **Causa do incidente**, insira a causa do incidente (por exemplo, **Escorregou em piso molhado**).
16. No campo **Nível de gravidade**, insira ou selecione um valor.
17. No campo **Ação a ser realizada**, insira um valor (por exemplo, **Limpar derramamentos imediatamente**).
18. No campo **Dias esperados longe de trabalho**, insira o número de dias que a pessoa deverá ficar ausente do trabalho.

    Depois que o indivíduo retornar ao trabalho, atualize o campo **Dias de afastamento do trabalho** com o número real de dias de afastamento.

19. Na seção **Custos de lesões ou doenças**, selecione **Adicionar**.
20. No campo **Data**, insira uma data.
21. No campo **Tipo de custo**, insira ou selecione um valor (por exemplo, **Terapia**).

    Você também pode inserir a um valor e anexar toda a documentação de suporte ao custo (por exemplo, faturas ou anotações do médico).

22. Selecione **Adicionar**.
23. No campo **Data**, insira uma data.
24. No campo **Tipo de custo**, insira ou selecione um valor (por exemplo, **Médico**).
25. Na seção **Tratamentos de lesões ou doenças**, selecione **Adicionar**.
26. No campo **Data de tratamento**, insira uma data e hora.
27. No campo **Tipo de tratamento**, insira ou selecione um valor (por exemplo, **Tala**).
28. Opcional: defina a seção **Visita à sala de emergência do hospital** como **Sim**.
29. No campo **Comentários sobre o tratamento**, insira um valor (por exemplo, **Tala por 2 semanas**).
30. No campo **Nome do médico**, insira um valor (por exemplo, **Dr. Anderson**).
31. No campo **Instalação e local de tratamento**, insira um valor (por exemplo, **Emergência da rua Elm**).
32. No campo **Detalhes do tratamento**, insira um valor (por exemplo, **Raio X confirma a fratura, uso de tala**).
33. Selecione **Salvar**.

O status do caso pode ser atualizado a qualquer momento. Se o processamento da lesão ou doença estiver em andamento, defina o status como **Em processo**. Depois que fechar o incidente, você só poderá adicionar ou remover custos, tratamentos ou arquivamentos relacionados ao incidente. Para alterar outras informações, você deverá reabrir o caso.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
