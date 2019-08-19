---
title: Desenvolver estrutura e plano de remuneração/salário
description: Essa guia da tarefa mostra o processo de criar um plano de remuneração fixa e de habilitar os funcionários a serem inseridos no plano com a qualificação.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, HcmCompensationWorkspace, HcmCompFixedPlansPart, HRMCompFixedPlanTable, HRMCompCreateGridDialog, HRCCompGridView, HRMCompEligibility,  HRCCompGrid
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3f0732736736fdc87f3367f24b1d20b9fa6efc59
ms.sourcegitcommit: ef08bf1258aefb525d56bf85ef19311be26ab94c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/30/2019
ms.locfileid: "1794895"
---
# <a name="develop-salarycompensation-structure-and-plan"></a>Desenvolver estrutura e plano de remuneração/salário

[!include [task guide banner](../../includes/task-guide-banner.md)]

Essa guia da tarefa mostra o processo de criar um plano de remuneração fixa e de habilitar os funcionários a serem inseridos no plano com a qualificação. A empresa de dados de demonstração usada para criar essa tarefa é a USMF e esta tarefa é destinada aos gerentes de Compensação e Benefícios.


## <a name="create-fixed-compensation-plan"></a>Criar planos de remuneração fixa.
1. Clique em Gerenciamento de remuneração.
2. Clique em Planos de remuneração fixa.
3. Clique em Novo.
4. No campo Plano, digite um valor.
5. No campo Descrição, digite um valor.
6. No campo Data efetiva, insira uma data.
7. No campo Tipo, selecione se o plano de remuneração fixa é uma faixa, classificação ou plano de etapa.
8. A caixa de seleção permitida recomendada atua como um valor padrão para todas as ações adicionadas a esse plano em um evento de processo.  Recomendações para permitir que seja possível substituir o valor de diretriz calculado ao processar a compensação.
9. A Tolerância fora do intervalo permite que você especifique como deseja manipular os valores de remuneração que estejam fora do intervalo especificado da estrutura de remuneração para o nível específico.  A Tolerância fora de intervalo de Nenhum permitirá que qualquer valor de remuneração seja usado.  Uma tolerância de meios de pagamento advertirá o usuário se o valor de remuneração for menor do que o valor mínimo de ponto de referência para esse nível, ou maior do que o valor máximo para o nível. O usuário pode ignorar o aviso e continuar.  Uma tolerância em vigor gera uma mensagem de erro se a remuneração de um funcionário for ajustada fora dos pontos de referência mínimo e máximo para o nível e ajustará automaticamente a remuneração do funcionário para estar no intervalo.
10. O campo da regra de contratação é usado quando um evento de processo de remuneração for executado para calcular a remuneração de um funcionário.  Uma regra de contratação de porcentagem calculará um aumento que é distribuído para o período de tempo no qual o funcionário foi contratado no ciclo.
11. No campo Moeda, digite um valor.
12. No campo Conversão da taxa de pagamento, insira ou selecione um valor.
13. Expandir a seção Matriz de variação de utilização.
    * Opcionalmente, adicione registros de utilização do intervalo para obter funcionários no valor médio mais rápido e lento para alcançar o máximo do intervalo.  
14. Nesse ponto, você deve salvar o plano de remuneração fixa para habilitar o botão de instalação de remuneração e continuar a definir a estrutura de remuneração para o plano.  Clique em Salvar.
15. Clique em Configurar remuneração.
    * Há três maneiras de criar uma estrutura de remuneração. 1: Criar uma estrutura totalmente nova selecionando um conjunto de pontos de referência e adicionando os níveis para criar sua própria estrutura. 2: Copiar uma estrutura de remuneração de um plano existente como ponto de partida e altera-la para o novo plano. 3: Selecionar uma grade de remuneração existente. Se a grade de compensação já está sendo usada por outro plano, todas as alterações feitas na grade também serão refletidas em outro plano.  
16. Marque a opção Criar novo da matriz de remuneração existente.
17. No campo Copiar da grade, insira ou selecione um valor.
    * Opcionalmente você pode alterar o nome da nova grade de compensação que será criada como uma cópia da grade selecionada.  
18. Clique em OK.
19. Clique em Alteração em massa.
    * A alteração em massa permite que você mantenha os valores da matriz de remuneração aplicando uma porcentagem ou um valor de aumento liso a um ou vários níveis e/ou pontos de referência.  
20. No campo Valor do ajuste, insira um número.
21. Na lista, marque ou desmarque todas as linhas.
22. Clique em Aplicar à grade.
23. Feche a página.
    * Depois que uma estrutura de remuneração tiver sido criada ou marcada, você pode selecionar quais dos pontos de referência deve ser usado como o ponto de controle para o plano de remuneração fixa.  O ponto de controle é usado para calcular a taxa de Compa de um funcionário.  
24. No campo Ponto de controle, insira ou selecione um valor.
25. Feche a página.

## <a name="create-an-eligibility-rule-for-the-new-fixed-compensation-plan"></a>Criar uma regra de qualificação para o novo Plano de remuneração fixa
    * O novo plano de remuneração fixa não pode ser atribuído a um funcionário até que as regras de qualificação estejam definidas para o plano.  
1. Clique em Regras de qualificação.
2. Clique em Novo.
3. No campo Qualificação, digite um valor.
4. No campo Descrição, digite um valor.
5. No campo Data efetiva, insira uma data.
    * Regras de qualificação são usadas para planos de compensação Fixos e Variáveis.  No campo Tipo, selecione o tipo de plano para o qual esse grupo de regras de qualificação é feito.  
6. No campo Plano, insira ou selecione um valor.
    * Selecione os critérios que funcionário deve atender aos requisitos a seguir para serem qualificados para a inscrição em um plano de remuneração. Os critérios podem incluir um nível de departamento, associação de trabalhadores, de localização (região de remuneração), trabalhos, função, tipo de trabalho ou de remuneração. O funcionário deve atender todos os requisitos especificados para ser qualificado para a inscrição em um plano de remuneração. Se nenhum critério for especificado, todos os funcionários estão qualificadas para o plano de remuneração. Se um funcionário não atender aos critérios especificados na regra de qualificação, ou uma regra de qualificação não tiver sido especificada para um plano de remuneração, o plano de remuneração não aparece na pesquisa ao criar um registro de compensação fixa para um funcionário.  
7. Feche a página.
8. Feche a página.

