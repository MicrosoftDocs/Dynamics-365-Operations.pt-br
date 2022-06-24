---
title: Configurar posições
description: Este artigo descreve como as posições são um elemento importante do nível inferior de uma hierarquia da organização.
author: twheeloc
ms.date: 10/28/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, HcmWorkforceWorkspace, HcmWorkerActivityChart, HcmAllWorkersListPart, HcmPosition, HcmPositionNewPosition, HcmJobLookup, HcmPositionReportsToDialog, HcmPositionLookup, FinancialDimensionDefaultTemplatesLookup, DimensionLookup, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e0c6664166c531bd4c445cc1bb5f0297ce7cff4d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8899604"
---
# <a name="set-up-positions"></a>Configurar posições


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Os cargos são um elemento importante do nível inferior de uma hierarquia organizacional. Um cargo é uma instância individual de um trabalho. Por exemplo, a posição, "Gerente de vendas (Leste)", é uma das posições associadas ao trabalho, "Gerente de vendas". Uma posição existe em um departamento e pode ter somente um trabalhador associado a ela. Nesta tarefa mostraremos as etapas necessárias para criar uma posição. Esse procedimento é destinado ao Especialista de recursos humanos.

1. Selecione **Gerenciamento da força de trabalho**.
2. Selecione **Abrir posições**.
3. Selecione **Novo** para abrir a caixa de diálogo suspensa.
4. No campo **Trabalho**, insira ou selecione um valor.

    Os campos **Descrição do trabalho**, **Título** e **Fator de emprego equivalente a tempo integral** são copiados automaticamente do trabalho selecionado na posição.

5. Selecione **Criar posição**.
6. No campo **Departamento**, insira ou selecione um valor.
7. No campo **Tipo de posição**, insira ou selecione um valor.
8. No campo **Região de remuneração**, insira ou selecione um valor.

    O campo **Região de remuneração** determina as regras de qualificação de remuneração e os orçamentos de aumento fixo que se aplicam a um funcionário naquela posição.

9. No campo **Disponível para atribuição**, insira uma data e hora.
10. Expanda a seção **Duração da posição**.

    A duração da posição é inserida por padrão com base na ativação e nas datas de aposentadoria inseridas anteriormente.

11. Expanda a seção **Relatórios para posição**.

    Quando você atribui um trabalhador a um cargo que está subordinado a outro cargo, você cria uma relação de subordinação direta entre os trabalhadores atribuídos aos dois cargos.

12. Selecione **Novo em** para abrir a caixa de diálogo suspensa.
13. No campo **Subordinado a**, insira ou selecione um valor.
14. Selecione **Criar**.
15. Expanda a seção **Atribuição de trabalhador**.
16. Expanda a seção **Relacionamentos**.

    Se a organização usar uma hierarquia de matriz ou outra hierarquia personalizada, você poderá configurar tipos de hierarquia de cargos e adicionar relações de subordinação a cargos de cada tipo de hierarquia que você configurou.

17. Selecione **Adicionar**.
18. Na lista, marque a linha selecionada.
19. No campo **Nome da hierarquia**, insira ou selecione um valor.
20. No campo **Relatórios para posição**, insira ou selecione um valor.
21. Expanda a seção **Folha de pagamento**.
22. No campo **Ciclo de pagamento**, insira ou selecione um valor.
23. No campo **Pago por**, insira ou selecione um valor.
24. No campo **Horas regulares anuais**, insira um número.

    O valor inserido é o número de horas pagas regularmente que o funcionário na posição deve trabalhar todos os anos.

25. Expanda a seção **Sindicato**.
26. Recolha a seção **Sindicato**.
27. Expanda a seção **Dimensões financeiras**.
28. No campo **Modelo de distribuição**, insira ou selecione um valor.
29. No campo **Departamento**, insira ou selecione um valor.
30. Selecione **Salvar**.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
