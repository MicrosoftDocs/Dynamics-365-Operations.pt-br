---
title: Definir processo de remuneração e calcular resultados
description: Os processos de remuneração são usados para determinar os novos valores e prêmios de remuneração para os funcionários inscritos em planos de remuneração fixos e variáveis.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMCompProcess, HRMCompProcessLine, HRMCompEvent, HRMCompEventEmpl, HcmCompensationWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 254eb4f83cc734e43920b912e81c7a9230ca82dd
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4417311"
---
# <a name="define-compensation-process-and-calculate-results"></a>Definir processo de remuneração e calcular resultados

Os processos de remuneração são usados para determinar os novos valores e prêmios de remuneração para os funcionários inscritos em planos de remuneração fixos e variáveis. Os processos de remuneração pode ser executados várias vezes para executar análises de hipótese para verificar se todas as alterações e definições estão corretas. Este procedimento criará um processo de remuneração, executará o processo e exibirá os resultados. A empresa de dados demo usada para criar este procedimento é USMF.


## <a name="create-a-compensation-process"></a>Crie um processo de remuneração
1. Vá para Recursos humanos > Remuneração > Processo > Processos de remuneração.
2. Clique em Novo.
3. No campo Processo, digite um valor.
4. No campo Descrição, digite um valor.
5. No campo Tipo de processo, selecione uma opção.
    * Um ciclo especifica o período avaliado para determinar a remuneração. A avaliação considera as posições que foram mantidas pelos funcionários, as classificações de desempenho a serem incluídas, o cálculo da porcentagem de tempo no qual o funcionário foi empregado durante o ciclo e muito mais. Um exemplo de uma data de início do ciclo pode ser o primeiro dia do ano fiscal anterior.  
6. No campo Início do ciclo, insira uma data.
    * A data final do ciclo é importante porque é a data usada para determinar os funcionários que estavam empregados e inscritos ativamente em um ou mais planos de remuneração.  
7. No campo Fim do ciclo, insira uma data.
    * A data ativa da transação é a data na qual as novas taxas de remuneração devem entrar em vigor. Muitas empresas incluem alguns meses entre a fim de um ciclo e o tempo no qual as novas taxas de remuneração entram em vigor. O tempo adicional é usado para processamento e revisão da nova remuneração.  
8. No campo Data de ativação da transação, insira uma data.
    * A data pontual é usada para planos de remuneração de variável que determinam o valor do prêmio de um funcionário com base na taxa de remuneração nesse momento.  
    * A data de contratação proporcional para pagamento fixo é usada com planos de remuneração fixa com uma regra de contratação de porcentagem.  Os funcionários que são contratados entre o início do ciclo e a data de contratação proporcional para pagamento fixo receberão 100% do aumento calculado de remuneração, em vez de porcentagem proporcional.  
9. No campo Data de contratação proporcional para pagamento fixo, insira uma data.
    * O prazo da revisão é a data na qual todos os resultados do processo devem ser revisados, de modo que possam ser carregados no registro de remuneração do funcionário antes da data ativa da transação. Este campo serve somente para informar.  
10. No campo Prazo final de revisão, insira uma data.
11. Clique em Salvar.

## <a name="setup-the-compensation-plans-and-actions-for-a-compensation-process"></a>Configure os planos de remuneração e ações de um processo de remuneração.
1. Clique em Configuração.
    * A página Configuração é usada para selecionar os planos a serem processados como parte desse processo de remuneração, bem como as ações que devem ser executadas em relação a cada plano.  
2. No campo Plano, insira ou selecione um valor.
3. Clique em Salvar.
4. Clique em Adicionar.
5. No campo Ação, selecione um tipo de ação de Capital próprio.
6. Clique em Adicionar.
7. No campo Ação, selecione um tipo de ação de Mérito.
    * As ações de remuneração podem ser "encadeadas" juntas usando o campo Usar resultado anterior para indicar se a ação selecionada deve usar o pagamento base de funcionários ou o resultado da ação anterior, como ponto de partida para o cálculo dessa ação.  
8. Selecione Sim no campo Usar resultado anterior.
9. Clique em Adicionar.
10. No campo Ação, selecione um tipo de ação Geral.
    * Os diferentes tipos de ação de remuneração permitem campos diferentes. Para um tipo de ação de remuneração Geral, podem ser especificados um valor de aumento ou uma porcentagem de aumento.  
11. Selecione a opção Selecionar valor de aumento.
12. No campo Aumentar valor, insira um número.
13. Clique em Adicionar.
14. No campo Ação, selecione um tipo de ação Promoção.
    * Os tipos de ação de Promoção e Outra alteração de nível habilitam usuários para fazer ajustes manuais na remuneração do funcionário. As recomendações podem ser habilitadas para esses tipos de ação, bem como para outros tipos de ação para que seja possível inserir um novo valor recomendado de remuneração de um funcionário.  
15. Clique em Adicionar.
16. No campo Tipo, selecione uma opção.
    * Os planos de remuneração fixa e variável podem ser realizados no mesmo processo de remuneração.  
17. No campo Plano, insira ou selecione um valor.
    * Use a caixa de seleção Habilitar pagamento por desempenho para determinar se os valores de remuneração fixos e variáveis devem ser ajustados com base na classificação de desempenho do funcionário.  
    * O aproveitamento pode ser substituído em planos de remuneração variável.  
18. Clique em Salvar.
19. Clique em Adicionar.
20. Feche a página.

## <a name="run-the-compensation-process"></a>Execute o processo de remuneração
1. Clique em Executar processo.
    * O controle Mostrar resultados do processamento permite exibir mensagens de processamento para o processo de remuneração completo quando processando for concluído.  
2. Selecione Sim no campo Mostrar resultados do processamento.
3. Clique em OK.

## <a name="view-the-results"></a>Exiba os resultados
1. Clique em Resultados do processo.
2. Clique em Resultados de funcionários.
3. Na lista, localize e selecione o PDV desejado.
4. Expanda a seção Remuneração fixa.
    * Expanda as Guias Rápidas para exibir os resultados do processo. Se Habilitar recomendações foi marcado para uma ação de remuneração, os campos Recomendação serão ativados para essa ação.  
5. Na lista, localize e selecione o PDV desejado.
    * Os resultados de um único funcionário podem ser exibidos clicando no botão Exibir resultados.  
    * Você pode substituir o valor calculado de remuneração ajustando a porcentagem ou o valor do aumento nos campos Recomendação.  
6. No campo Porcentagem recomendada, insira um número.
7. Na lista, localize e selecione o PDV desejado.
8. No campo Porcentagem recomendada, insira um número.
    * Recalcular pode ser usado para ignorar todas as alterações feitas no registro existente e para gerar um novo resultado de remuneração do funcionário selecionado.  
    * Quando todas as alterações forem concluídas para um funcionário, altere o status para Aprovado.  
9. Clique em Alterar status.
10. Clique em Aprovado.
    * Depois que o registro for aprovado, ele poderá ser carregado para o registro oficial de remuneração do funcionário. A nova remuneração será efetiva a partir da data da transação definida no processo de remuneração.  

