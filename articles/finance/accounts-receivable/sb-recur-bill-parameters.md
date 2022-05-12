---
title: Parâmetros de cobrança de contrato recorrentes
description: Este tópico explica como configurar os valores padrão para agendas de cobrança que são criadas na cobrança do contrato recorrente. Também explica como criar grupos de agenda de cobrança.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 4c52095aa49962cbfc577faf71ab0d71929a386b
ms.sourcegitcommit: 836695c0e95d366ba993f34eee30f57191f356d8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2022
ms.locfileid: "8629379"
---
# <a name="recurring-contract-billing-parameters"></a>Parâmetros de cobrança de contrato recorrentes

Use a página **Parâmetros de cobrança de contrato recorrentes** para configurar os valores padrão para agendas de cobrança que são criadas na cobrança do contrato recorrente. Todas as agendas de cobrança criadas inicialmente usarão esses valores padrão. No entanto, você pode alterar os valores para cada agenda de cobrança conforme necessário.

## <a name="general-tab"></a>Guia Geral

1. Na página **Parâmetros de cobrança de contrato recorrente**, na guia **Geral**, no campo **Grupo de agenda de cobrança**, selecione um grupo da agenda de cobrança. Para obter informações sobre como configurar grupos de agenda de cobrança, consulte a seção [Grupos de agenda de cobrança](#set-up-billing-schedule-groups) a seguir neste tópico.
2. No campo **Tipo de encerramento**, selecione como a fatura final será calculada quando uma agenda de cobrança for encerrada:

    - **Ajustar agenda** – interrompe a agenda de cobrança na data de demissão, altera o status da agenda para **Última cobrança** e ajusta a agenda de adiamento associada, revertendo o valor que não deve mais ser reconhecido. Se a data de início da cobrança for posterior à data de encerramento, os períodos de cobrança restantes serão removidos.
    - **Cobrança restante** – adiciona os valores que restam da agenda de cobrança ao período de encerramento, altera o status da agenda para **Última cobrança** e atualiza a agenda de adiamento. Se a data de início da cobrança for posterior à data de encerramento, o valor total de todos os períodos de cobrança restantes será adicionado ao período de cobrança e os períodos de cobrança restantes serão removidos.
    - **Nenhum ajuste** – encerra a agenda de cobrança na data de encerramento. Nenhum ajuste foi feito na agenda de cobrança.

3. No campo **Tipo de agenda exclusiva**, selecione **Nenhum** para especificar que os clientes estão limitados a uma única agenda de cobrança. Selecione **Por cliente** ou **Por usuário final** para especificar que os clientes estão limitados a uma agenda exclusiva.
4. Defina a opção **Alinhar ao mês** como **Sim** para alinhar as linhas de detalhes da agenda de cobrança com o fim de um mês quando uma agenda de cobrança for criada ou atualizada. Defina como **Não** para usar datas incrementais.
5. Defina a opção **Ratear períodos parciais** como **Sim** para alocar valores de cobrança com base no número de dias do período. Defina como **Não** para ter um valor igual em cada período de cobrança, independentemente do número de dias.
6. Se você definir a opção **Ratear períodos parciais** como **Sim**, defina o campo **Método de rateio** como **Diariamente** para distribuir os valores com base no número de dias do período. Defina como **Mensal** para ter um valor igual a cada mês.
7. Especifique se as agendas de cobrança recém-criadas estão em espera por padrão.

    > [!NOTE]
    > Para remover a espera em uma agenda de cobrança, o usuário deve fazer parte de um grupo de usuários. Selecione **Substituição de grupo de usuários de remoção de bloqueio** para configurar um grupo de usuários em que a opção **Permitir remoção de bloqueio** está habilitada.

8. No campo **Tipo de transação de fatura**, selecione o tipo de transação de fatura padrão para novas agendas de cobrança.
9. Defina a opção **Alinhar adiamento à cobrança** como **Sim** para alinhar a agenda de adiamento correspondente para que ela use as mesmas datas que a agenda de cobrança. Defina como **Não** para usar datas diferentes.
10. Se você estiver usando o recurso divisão de receita, defina a opção **Criar divisão de receita automaticamente** como **Sim** quando os itens forem adicionados a uma agenda de cobrança. A caixa de seleção **Divisão de receita** será automaticamente selecionada na linha da agenda de cobrança se o item for configurado como um item de divisão de receita. Defina a opção como **Não** se desejar selecionar manualmente a caixa de seleção **Divisão de receita**.
11. Defina os campos para a criação da ordem de venda:

    - As faturas podem ser consolidadas por período, cliente ou item. Qualquer combinação de valores **Sim** e **Nenhum** pode ser definida. As faturas também podem ser divididas por grupo de itens.
    - As seguintes opções de lançamento estão disponíveis para faturas:

        - **Criar ordem de venda** – criar apenas a ordem de venda.
        - **Mostrar fatura de lançamento** – faturar a ordem de venda e abrir uma página na qual você pode lançar manualmente a fatura.
        - **Criar fatura de texto livre** – selecione esta opção se estiver usando faturas de texto livre.
        - **Lançar fatura automaticamente** – faturar a ordem de venda e lançá-la automaticamente.

    - Defina a opção **Adicionar datas de cobrança ao item de descrição** como **Sim** para adicionar uma descrição que inclui a data de início e a data de término da cobrança.
    - Defina a opção **Excluir consumo zero** como **Sim** para excluir linhas da agenda de cobrança sem consumo. Defina como **Não** para incluir essas linhas na ordem de venda.
    - Defina a opção **Não imprimir itens filhos** como **Sim** se você não quiser imprimir os itens filhos de uma divisão de receita na ordem de venda. Somente o item pai aparecerá na fatura. Se o valor líquido dos itens filhos (ocultos) for uma soma diferente de zero, o valor líquido da linha pai mostrará um resumo das linhas filho. Defina a opção como **Não** para imprimir todos os itens filhos abaixo do item pai na fatura de venda.

12. Defina os campos para suporte e renovações:

    - Defina a opção **Habilitar automaticamente o suporte e a renovação** como **Sim** para usar automaticamente o recurso de suporte e renovação em uma ordem de venda.
    - No campo **Nível de suporte e renovação**, selecione o nível de suporte e renovação padrão.
    - No campo **Quantidade de suporte e renovação**, especifique a quantidade de suporte e renovação.
    - No campo **Data de início de suporte e renovação padrão**, especifique a data a ser usada como data de início padrão para suporte e renovações:

        - **Data da transação** – use a data da transação como a data de início.
        - **Início do mês atual** – use o primeiro mês atual como a data de início.
        - **Início do próximo mês** – use o próximo mês como a data de início. Se a data da transação for a primeira, a primeira do mês atual será usada.
        - **Regra de 15** – use a primeira do mês atual como data de início se a data da transação estiver entre o primeiro e o décimo quinto dia do mês. Se a data da transação for o décimo sexto ou posterior, use o primeiro do mês seguinte como data de início.

    - Defina a opção **Incluir desconto em cálculo** como **Sim** para incluir o valor do desconto no valor de suporte ou renovação. Defina como **Não** para excluir o valor do desconto.
    - Nos campos **Frequência de suporte** e **Frequência de renovação**, selecione a frequência a ser usada quando itens de suporte e renovação forem adicionados a uma agenda de cobrança: **Diário**, **Mensal**, **Trimestral**, **Semestral** ou **Anual**.
    - Defina a opção **Alinhar por grupo de itens** como **Sim** para alinhar as datas inicial e final dos novos itens aos itens existentes com base no grupo de itens.
    - Defina a opção **Alinhar ao próximo período não faturado** como **Sim** para determinar a data de alinhamento para um item de renovação com base na data do próximo período não faturado após o início da renovação.
    - Defina a opção **Copiar número de série** como **Sim** para copiar o número de série do item desde a linha da ordem de venda inicial até a linha da agenda de cobrança correspondente.

13. Se você estiver usando escalonamento na agenda de cobrança, selecione o método utilizado para o cálculo do índice de preço do cliente.
14. Defina a opção **Acompanhar alteração de preço** como **Sim** se desejar um registro de alterações de preço nas linhas da agenda de cobrança. Se uma linha da agenda de cobrança for alterada manualmente de padrão para simples e um novo preço for inserido, as informações de auditoria serão rastreadas na linha da agenda de cobrança. Defina a opção como **Não** se não quiser rastrear essas alterações.
15. Especifique se os registros são filtrados por data inicial ou por data final por padrão na página **Gerar fatura**.
16. Se você usar o recurso **Receita não faturada**, especifique as opções que são utilizadas:

    - Defina a opção **Lançar diário geral automaticamente** como **Sim** se desejar que o diário geral seja criado e lançado ao mesmo tempo. Defina-o como **Não** se desejar criar o diário geral e, em seguida, lançá-lo manualmente.
    - No campo **Nome do diário padrão**, selecione o nome do diário padrão a ser usado quando o diário geral for criado.
    - No campo **Método não faturado de curto prazo**, selecione o método não faturado de curto prazo, se estiver usando um. Se você selecionar **Nenhum**, a funcionalidade de curto prazo não será usada com receita não faturada. Selecione **Períodos anteriores** para usar sempre 12 meses ou **Ano fixo** para usar o ano fiscal restante.

17. Especifique as opções usadas quando uma agenda de cobrança e suas linhas são encerradas:

    - **Emitir crédito** – cria uma nota de crédito quando uma agenda de cobrança ou linha de agenda de cobrança é encerrada.
    - **Ajuste de crédito** – cria um ajuste de crédito para uma agenda de cobrança quando uma linha é encerrada. O ajuste de crédito é exibido em um período de cobrança futuro para a agenda de cobrança. O ajuste de crédito também atualizará o valor da fatura para o próximo período de cobrança até que o crédito tenha sido aplicado à agenda de cobrança.
    - **Sem crédito** – não cria um ajuste de crédito ou uma nota de crédito quando uma agenda de cobrança ou linha de agenda de cobrança é encerrada. Esta opção está disponível somente quando a opção **Sem ajuste** é usada para encerrar uma agenda de cobrança.

## <a name="sequence-number-tab"></a>Guia do número de sequência

Use a guia **Número de sequência** na página **Parâmetros de cobrança de contrato recorrentes** para definir o valor padrão dos números da agenda de cobrança. Os valores padrão são configurados na página **Sequências numéricas** (**Administração da organização \> Sequências numéricas \> Sequências numéricas**).

## <a name="set-up-billing-schedule-groups"></a>Configurar grupos de agendamento de cobrança

Use a página **Grupo de agendas de cobrança** para criar um grupo de agendas de cobrança para uma Cobrança de contrato recorrente. Quando uma nova agenda de cobrança é criada e um grupo de agendas de cobrança é aplicado a ela, os valores definidos na página **Grupo de agendas de cobrança** são inseridos como valores padrão para a agenda de cobrança. Você pode alterar qualquer um dos valores padrão para a agenda de cobrança específica criada. Você pode configurar vários grupos de agendas de cobrança e, depois, atribuir um deles como o grupo de agendas de cobrança padrão na página **Parâmetros de cobrança recorrente de contrato**.

Para criar um grupo de agendas de cobrança para Cobrança recorrente de contrato, siga estas etapas:

1. Na página **Grupo de agendas de cobrança**, selecione **Novo** para criar um grupo de agendas de cobrança.
2. No campo **Grupo de agendas de cobrança**, insira um identificador exclusivo.
3. No campo **Descrição**, insira uma descrição.
4. Na **Frequência da cobrança**, especifique com que frequência a agenda de cobrança é faturada para um cliente: **Único**, **Diário**, **Mensal**, **Trimestral**, **Semestral** ou **Anual**.
5. No campo **Intervalo de cobrança**, insira o intervalo. Por exemplo, defina o campo **Frequência da cobrança** como **Mensal** e o campo **Intervalo de cobrança** como **2** para faturar em meses alternados.
6. No campo **Método de precificação**, selecione o método de precificação padrão para os itens na agenda de cobrança:

    - **Padrão** – calcule o preço unitário com base na quantidade total inserida e use a definição de preços padrão da página **Produtos lançados** no Gerenciamento de informações do produto.
    - **Fixo** – aplique um preço simples que é inserido na linha da agenda de cobrança.
    - **Camada** – calcule o preço unitário usando uma quantidade fixa em diferentes chaves de preços. Cada camada deve ser preenchida antes de passar para a próxima chave de preços.
    - **Camada fixa** – calcule o preço unitário usando uma quantidade fixa e valores de preço bruto em diferentes chaves de preços. O preço cobrado em um período de cobrança usa o preço bruto que corresponde à camada onde existe a quantidade de cobrança.

7. No campo **Tipo de item**, selecione o tipo de item para o grupo de cobrança:

    - **Padrão** – selecione esse valor se a quantidade for estática.
    - **Uso** – selecione esse valor para itens monitorados ou de tipo de consumo. Se você selecionar esse valor, defina o campo **Opção de leitura de uso** como **Leitura** para inserir o valor (leitura) para um período de cobrança em um medidor ou dispositivo. O valor consumido será calculado com base no período de cobrança anterior e na leitura atual inserida.
    - **Marco** – selecione esse valor para usar a funcionalidade de Cobrança por etapa. Se você selecionar esse valor, no campo **Modelo de etapa**, selecione o modelo de etapa se estiver usando um.
    - **Consumo** – selecione esse valor para inserir o valor que é consumido para um período de cobrança.

8. Defina a opção **Faturar separadamente** como **Sim** para criar uma combinação de faturas consolidadas e faturas separadas para o mesmo cliente. Por exemplo, um cliente tem cinco agendas de cobrança. Três delas serão consolidadas em uma única fatura, mas cada as outras duas exigirão uma fatura separada. Defina a opção como **Não** para criar apenas uma fatura consolidada para o cliente.
9. Defina a opção **Renovar automaticamente** como **Sim** para renovar automaticamente a agenda de cobrança recorrente para o próximo período de cobrança quando a fatura for criada. Defina como **Não** para renovar manualmente a agenda de cobrança. No campo **Linhas a serem adicionadas por renovação**, especifique o número de linhas a serem adicionadas para cada renovação.
10. Defina a opção **Escalonamento** como **Sim** para aplicar *escalonamentos* (aumento de preço) às agendas de cobrança associadas a este grupo de agendas de cobrança.
