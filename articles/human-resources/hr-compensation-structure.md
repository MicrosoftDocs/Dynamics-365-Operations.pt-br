---
title: Desenvolver uma estrutura de remuneração
description: Este tópico explica como criar um plano de remuneração fixa e inscrever funcionários no plano com regras de qualificação.
author: twheeloc
ms.date: 08/25/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, HcmCompensationWorkspace, HcmCompFixedPlansPart, HRMCompFixedPlanTable, HRMCompCreateGridDialog, HRCCompGridView, HRMCompEligibility,  HRCCompGrid
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ec30d6259b755bf7c304e8796b32d373027ce7ff
ms.sourcegitcommit: 24e20b3b96834b23311f1bf5dbab28baf3323728
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483943"
---
# <a name="develop-a-compensation-structure"></a>Desenvolver uma estrutura de remuneração

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve como criar um plano de remuneração fixa e inscrever funcionários no plano com regras de qualificação. Este tópico usa os dados de demonstração de USMF e se aplica a gerentes de remuneração e benefícios.

## <a name="create-a-fixed-compensation-plan"></a>Crie um plano de remuneração fixa

1. Selecione **Gerenciamento de remuneração**.

2. Selecione **Planos de remuneração fixa**.

3. Selecione **Novo**.

4. No campo **Plano**, insira um valor.

5. No campo **Descrição**, insira um valor.

6. No campo **Data efetiva**, insira uma data.

7. No campo **Tipo**, selecione se o plano de remuneração fixa é um plano **Faixa**, **Classificação** ou **Etapa**.

8. A caixa de seleção **Recomendação permitida** será o valor padrão para todas as ações adicionadas a esse plano em um evento de processo. Recomendações para permitir que seja possível substituir o valor de diretriz calculado ao processar a compensação.

9. O campo **Fora da tolerância de faixa salarial** permite que você especifique como deseja manipular os valores de remuneração que estejam fora do intervalo especificado da estrutura de remuneração para o nível específico. Definir o campo **Fora da tolerância de faixa salarial** como **Nenhum** permite usar qualquer valor de remuneração. A **tolerância de meios** adverte os usuários se o valor da remuneração for menor que o valor mínimo ou maior que o valor máximo de ponto de referência para esse nível. Os usuários podem ignorar o aviso e continuar. Uma **tolerância em vigor** gera uma mensagem de erro se a remuneração de um funcionário estiver fora dos pontos de referência mínimo e máximo para o nível e ajustará automaticamente a remuneração do funcionário para estar no intervalo.

10. O campo **Regra de contratação** calcula a remuneração de um funcionário durante um evento do processo. Uma **Regra de contratação** de **Porcentagem** calcula um aumento que é distribuído para o período de tempo no qual o funcionário foi contratado no ciclo.

11. No campo **Moeda**, digite um valor.

12. No campo **Conversão da taxa de pagamento**, insira ou selecione um valor.

13. Expandir a seção **Matriz de variação de utilização**. Opcionalmente, adicione registros de utilização do intervalo para obter funcionários no valor médio mais rápido e lento para alcançar o máximo do intervalo.

14. Selecione **Salvar**. Isso habilita o botão **Configurar remuneração** e continua definindo sua estrutura de remuneração para o plano.

15. Selecione **Configurar remuneração**. É possível criar uma estrutura de remuneração usando um destes três métodos:

    - Criar uma estrutura totalmente nova selecionando um conjunto de pontos de referência e adicionando os níveis para criar sua própria estrutura.
    - Copiar uma estrutura de remuneração de um plano existente como ponto de partida e altera-la para o novo plano.
    - Selecionar uma grade de remuneração existente. Se um plano já estiver usando a grade de remuneração, o outro plano também refletirá todas as alterações feitas na grade.

16. Selecione **Criar nova matriz de remuneração a partir de uma existente**.

17. No campo **Copiar da grade**, insira ou selecione um valor. Opcionalmente, você pode alterar o nome da grade de remuneração criada, copiando a grade selecionada.

18. Selecione **OK**.

19. Selecione **Alteração em massa**. A **alteração em massa** permite que você mantenha os valores da matriz de remuneração aplicando uma porcentagem ou um valor de aumento liso a um ou vários níveis ou pontos de referência.

20. No campo **Valor do ajuste**, insira um número.

21. Na lista, marque ou desmarque todas as linhas.

22. Clique em **Aplicar à grade**.

23. Feche a página. Depois de criar a estrutura de remuneração, é possível selecionar qual dos pontos de referência usar como ponto de controle para o plano de remuneração fixa. O ponto de controle é usado para calcular a taxa de Compa de um funcionário.

24. No campo **Ponto de controle**, insira ou selecione um valor.

25. Feche a página.

## <a name="create-an-eligibility-rule-for-the-fixed-compensation-plan"></a>Criar uma regra de qualificação para o plano de remuneração fixa

Não é possível atribuir um plano de remuneração fixa a um funcionário até definir regras de qualificação para o plano.  

1. Selecione **Regras de qualificação**.

2. Selecione **Novo**.

3. No campo **Qualificação**, insira um valor.

4. No campo **Descrição**, insira um valor.

5. No campo **Data efetiva**, insira uma data. Os planos de remuneração fixa e variável usam regras de qualificação. No campo **Tipo**, selecione o tipo de plano.

6. No campo **Plano**, insira ou selecione um valor. Selecione os critérios que funcionário deve atender aos requisitos a seguir para serem qualificados para a inscrição em um plano de remuneração. Os critérios podem incluir:

    - **Departamento**
    - **Sindicato**
    - **Localização** (**Região de remuneração**)
    - **Trabalho**
    - **Função**
    - **Tipo de trabalho**
    - **Nível salarial**
    
    O funcionário deve atender todos os requisitos especificados para ser qualificado para a inscrição em um plano de remuneração. Se nenhum critério for especificado, todos os funcionários estão qualificadas para o plano de remuneração. Se um funcionário não atender aos critérios especificados na regra de qualificação, ou uma regra de qualificação não tiver sido especificada para um plano de remuneração, o plano de remuneração não aparecerá na pesquisa ao criar um registro de compensação fixa para um funcionário.

7. Feche a página.

8. Feche a página.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
