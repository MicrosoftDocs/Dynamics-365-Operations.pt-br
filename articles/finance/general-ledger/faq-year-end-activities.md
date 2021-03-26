---
title: Perguntas frequentes sobre atividades do exercício
description: Este tópico foi compilado para ajudar nas atividades de fechamento do exercício.
author: kweekley
manager: tfehr
ms.date: 01/25/2021
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: a9feafcab5969e9ec8fcbb8a6903d7b59505f6ae
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5249402"
---
# <a name="year-end-activities-faq"></a>Perguntas frequentes sobre atividades do exercício 

Este tópico foi compilado para ajudar nas atividades de fechamento do exercício. As informações neste tópico se concentram principalmente em perguntas relativas a atividades de fechamento do exercício para a contabilidade e contas a pagar.

## <a name="general-ledger-how-do-i-know-that-were-running-year-end-close-and-not-undoing-year-end-close"></a>Contabilidade: como sei que estamos executando o fechamento do exercício e não desfazendo o fechamento do exercício?
Algumas organizações tentam executar o fechamento do exercício, mas na verdade desfazem o fechamento do exercício. Se o fechamento do exercício for muito rápido ou não produzir saldos iniciais, valide a configuração **Desfazer fechamento anterior** em **Fechamento do exercício** (**Contabilidade > Fechamento do período > Fechamento do exercício > Executar fechamento de ano fiscal**). 

[![Execução do fechamento do exercício versus desfazer fechamento do exercício](./media/faq-2020-yr-end-01.png)](./media/faq-2020-yr-end-01.png)

Se a seleção **Desfazer fechamento anterior** estiver definida como **Sim**, o fechamento do exercício anterior será revertido. Ao desfazer a ação, todas as entradas de saldo de fechamento e saldo inicial serão excluídas, como se o fechamento do exercício nunca tivesse sido executado. Os comprovantes serão excluídos. O fechamento do exercício não será executado automaticamente novamente. Você deverá iniciar o processo novamente, desta vez alterando **Desfazer fechamento anterior** para **Não**. 

> [!NOTE]
> A entrada de saldo de fechamento é opcionalmente criada no ano que está sendo encerrado. Isso ocorrerá somente se o parâmetro da contabilidade **Criar transações de fechamento durante a transferência** estiver definido como **Sim**. A entrada do saldo inicial sempre é criada, pois esse é o saldo inicial para o próximo ano.  
 
## <a name="general-ledger-what-is-the-difference-between-undo-and-delete-gl-parameter-for-year-end-close"></a>Contabilidade: qual é a diferença entre desfazer e excluir o parâmetro GL para o fechamento do exercício?
Pode haver confusão sobre a diferença entre o parâmetro **Desfazer fechamento anterior**, que está na caixa de diálogo **Fechamento do exercício**, e o parâmetro **Excluir transações de fechamento de ano durante a transferência** na contabilidade (**Contabilidade > Fechamento do período > Fechamento do exercício > Executar fechamento de ano fiscal**).  

[![Diferença entre desfazer e excluir o parâmetro GL para o fechamento do exercício](./media/faq-2020-yr-end-02.png)](./media/faq-2020-yr-end-02.png)

Selecione **Desfazer fechamento anterior** no menu suspenso da caixa de diálogo ao executar o processo de fechamento do exercício para excluir todas as entradas de saldo de fechamento e de saldo inicial, como se o fechamento do exercício nunca tivesse sido executado. Os comprovantes serão excluídos. O fechamento do exercício não será executado automaticamente novamente. Para executar o fechamento do exercício, inicie esse processo novamente, desta vez alterando **Desfazer fechamento anterior próximo** para **Não** (**Contabilidade > Configuração do razão > Parâmetros da contabilidade**). 

[![Configuração de parâmetros da contabilidade](./media/faq-2020-yr-end-03.png)](./media/faq-2020-yr-end-03.png)

O parâmetro **Excluir transações de fechamento de ano durante a transferência** na contabilidade é usado somente durante a execução do fechamento do exercício (não ao desfazê-lo). A seleção **Desfazer fechamento anterior** está definida como **Não**. Se esse parâmetro estiver definido como **Sim**, todas as entradas de saldo de fechamento e saldo inicial serão excluídas e o fechamento do exercício será executado novamente. Esse processo é usado quando a organização deseja que todas as transações, incluindo os ajustes desde o último fechamento do exercício, sejam lançadas em uma única entrada contábil para as entradas de saldo de fechamento e de saldo inicial. 

Se essa opção estiver definida como **Não**, todas as entradas de saldo de fechamento e de saldo inicial permanecerão. Elas não serão excluídas. Em vez disso, uma nova entrada de saldo de fechamento e de saldo inicial será criada apenas para a variação ou para as transações novas lançadas desde o último fechamento do exercício daquele ano fiscal.  

> [!NOTE]
> A entrada de saldo de fechamento é criada no ano que está sendo encerrado. Isso ocorrerá somente se o parâmetro **Criar transações de fechamento durante a transferência** da contabilidade estiver definido como **Sim**. A entrada do saldo inicial sempre é criada, pois esse é o saldo inicial para o próximo ano. 

## <a name="general-ledger-what-can-be-changed-to-enhance-performance-of-year-end-processing"></a>Contabilidade: o que pode ser alterado para melhorar o desempenho do processo do final de ano? 
Você pode fazer diversas alterações para melhorar o desempenho do fechamento do exercício. É recomendável avaliar essas alterações sugeridas para considerar se a alteração é adequada à sua organização.  

### <a name="dimension-sets"></a>Conjuntos de dimensões
Ao executar o fechamento do exercício, o saldo de cada conjunto de dimensões é recriado, o que tem um impacto direto no desempenho. Algumas organizações criam conjuntos de dimensões desnecessariamente porque já foram usados ou podem ser usados em algum momento.  Esses conjuntos de dimensões desnecessários ainda são recriados durante o fechamento do exercício, o que acrescenta tempo ao processo. Avalie os conjuntos de dimensões e exclua quaisquer conjuntos de dimensões desnecessários.

Os conjuntos de dimensões desnecessários também afetam o trabalho em lotes **BudgetDimensionFocusInitializeBalance** (**Contabilidade > Plano de contas > Dimensões > Conjuntos de dimensões financeiras**).

[![Conjuntos de dimensões financeiras](./media/faq-2020-yr-end-04.png)](./media/faq-2020-yr-end-04.png)

### <a name="year-end-close-template-configuration"></a>Configuração do modelo de fechamento do exercício
Com o modelo de fechamento do exercício, as organizações podem selecionar o nível de dimensão financeira a ser mantido ao transferir saldos de lucros e perdas para ganhos retidos. As configurações permitem que uma organização mantenha as dimensões financeiras detalhadas (**Fechar tudo**) ao mover os saldos para ganhos retidos ou optar por resumir os valores para um único valor de dimensão (**Fechar um**). Isso pode ser definido para cada dimensão financeira. Para obter mais informações sobre essas configurações, consulte o tópico [Fechamento do exercício](year-end-close.md).

Recomendamos que você avalie os requisitos da sua organização e, se possível, feche o número máximo de dimensões usando a opção **Fechar um** exercício para melhorar o desempenho. Ao fechar para um único valor de dimensão (que também pode ser um valor em branco), o sistema calcula menos detalhes ao determinar os saldos das entradas da conta de ganhos retidos.

### <a name="10013-update-or-later"></a>Atualização para 10.0.13 ou posterior
Se você atualizou para a versão 10.0.13 ou posterior desde a última vez em que sua organização executou um fechamento do exercício, o processo poderá ser mais demorado devido à [implementação do recurso HashV2](https://community.dynamics.com/365/financeandoperations/b/dynamics-365-finance-blog/posts/verify-hash-function-changes-after-update-to-dynamics-365-finance-2020-release-wave-2). (O termo *hash* se refere a um campo que é calculado a partir de outros campos da cadeia. A API para calcular o valor de GUID hash foi atualizada para melhorar a segurança. Para agilizar o processo de fechamento do exercício, recomendamos recriar os saldos dos conjuntos de dimensões antes de executar o fechamento do exercício. Se você já tiver recriado os saldos dos conjuntos de dimensões depois de fazer a atualização para o 10.0.13, não será necessário executar novamente o processo de recriação.
 
## <a name="general-ledger--what-does-the-period-close--year-end-close-do"></a>Contabilidade – o que fazem o Fechamento do período e o Fechamento do exercício?
 
[![Fechamento do período, fechamento do exercício](./media/faq-2020-yr-end-05.png)](./media/faq-2020-yr-end-05.png)

### <a name="performance-improvements-for-rebuilding-financial-dimension-sets-new-feature"></a>Melhorias de desempenho para a recriação de conjuntos de dimensões financeiras (novo recurso)
Um novo recurso adicionado na versão 10.0.16 melhora o desempenho dos processos de consolidação e fechamento do exercício. O nome do recurso é Melhorias de desempenho para a recriação de conjuntos de dimensões financeiras. Este recurso altera a forma como os conjuntos de dimensões são recriados para que sejam recriados apenas para um período relevante. Nas versões anteriores, os conjuntos de dimensões eram recriados para todas as datas. Por exemplo, se você estiver fechando o ano 2020, o sistema só recriará os saldos para transações no ano fiscal 2020. Se você estiver executando a consolidação para um intervalo de datas de 1º de novembro de 2020 a 30 de novembro de 2020, o sistema apenas recriará os saldos para esse intervalo.

Como este recurso é considerado uma alteração da falha, você precisará habilitá-lo usando o espaço de trabalho **Gerenciamento de recursos**.
 
[![Fechamento do exercício](./media/faq-2020-yr-end-06.png)](./media/faq-2020-yr-end-06.png)

## <a name="accounts-payable-what-changes-have-been-made-to-support-1099-year-end-reporting-for-2020"></a>Contas a pagar: que alterações foram feitas para oferecer suporte a relatórios 1099 de final de ano para 2020?

Dois novos recursos regulatórios foram adicionados para alterações de final de ano do 1099 em 2020. O primeiro recurso, **Aplicar alterações aos formulários 1099-NEC e 1099-MISC para 2020**, foi lançado na metade do ano como um recurso obrigatório. A finalidade é garantir que os dados transacionais 1099 para o ano 2020 possam ser acompanhados no novo formulário 1099-NEC. Este recurso adicionou os campos 1099 que são necessários para oferecer suporte ao novo 1099-NEC e atualizou os campos 1099-MISC. Esta atualização também atualiza os dados de registro do fornecedor para as informações da caixa 1099. 

O segundo recurso normativo, **Demonstrativos 1099 atualizados para a legislação tributária de 2020**, contém as seguintes alterações.

- 1099-OID – a Administração Fiscal converteu o formulário para uso contínuo.
   - O terceiro e o quarto dígitos do ano do relatório devem ser preenchidos quando impressos. Use o terceiro e quarto dígitos do campo **Ano do relatório** das **Opções de impressão do imposto 1099**. 

- 1099-NEC – um novo formulário para 2020. Ele registra a remuneração que não é do funcionário. 

-   1099-MISC – devido à criação do formulário 1099-NEC, a Administração Fiscal revisou o formulário 1099-MISC e reorganizou os números de caixa para relatar determinadas receitas.
As alterações no relatório de receitas e os números de caixa do formulário estão listados abaixo.
   - O pagador realizou vendas diretas de US$ 5.000 ou mais (caixa de seleção) na caixa 7.
   - As rendas de seguro de colheita são relatadas na caixa 9.
   - A renda bruta para um advogado é relatada na caixa 10.
   - Os diferimentos da seção 409A são relatados na caixa 12.
   - A receita de remuneração diferida não qualificada é relatada na caixa 14.
   - As caixas 15, 16 e 17 relatam, respectivamente, os impostos estaduais retidos, o número de identificação do estado e valor da receita obtida no estado.

- Sem alterações no 1099-DIV e no 1099-INT em 2020.

- Transmissão eletrônica – o formato mudou para acomodar o novo formulário NEC e as alterações de caixa MISC descritas acima. Para obter informações específicas sobre requisitos de transmissão eletrônica, consulte a [Publicação 1220 da Administração Fiscal](https://www.irs.gov/pub/irs-pdf/p1220.pdf).

## <a name="accounts-payable-1099--how-do-i-change-the-1099-box-and-values-for-a-vendor-that-wasnt-tracking-1099-information-throughout-the-year"></a>Contas a pagar: 1099 – como alterar a caixa 1099 e os valores de um fornecedor que não estava acompanhando as informações 1099 durante todo o ano?
Use a funcionalidade Atualização de 1099 (**Contas a pagar > Fornecedores > Todos os fornecedores > Selecionar um fornecedor > Guia do fornecedor na faixa de opções > Atualização de 1099**) para passar pelas transações de faturas pagas anteriormente e reatribuir corretamente os dados 1099 de acordo com as configurações na guia **Imposto 1099** na página **Fornecedor**.

## <a name="can-i-run-the-update-1099-for-all-my-vendors-at-once"></a>É possível executar a Atualização de 1099 para todos os meus fornecedores de uma só vez?
Não. A rotina Atualização de 1099 é executada para um único fornecedor de cada vez. Se essa requisição for necessária para sua organização, vote na ideia chamada [Processo em lotes para atualização dos dados 1099 do fornecedor](https://experience.dynamics.com/ideas/idea/?ideaid=5493d608-350e-eb11-b5d9-0003ff68ded8).

## <a name="accounts-payable-1099--recalculate-existing-1099-amounts-vs-update-all-in-the-update-1099-utility"></a>Contas a pagar: 1099 – "Recalcular valores do imposto 1099 existentes" versus "Atualizar tudo" no utilitário Atualização de 1099.
A caixa de seleção **Recalcular valores do imposto 1099 existentes** redefine o valor do 1099 para os valores totais pagos, quando usada em conjunto com a caixa de seleção **Atualizar tudo**. 

[![Transações do imposto 1099: antes de executar a rotina de atualização](./media/faq-2020-yr-end-07.png)](./media/faq-2020-yr-end-07.png)

A caixa de seleção **Recalcular valores do imposto 1099 existentes** só aparece quando há valores parciais do 1099 na fatura ou se ele tiver sido modificado no formulário Imposto 1099. Por exemplo, suponha que você tenha uma fatura de US$ 1.000, mas o usuário digita manualmente na fatura um valor do 1099 de US$ 500.

[![Transações do imposto 1099: marcar Atualizar tudo e Recalcular valores do imposto 1099 existentes](./media/faq-2020-yr-end-08.png)](./media/faq-2020-yr-end-08.png)

Quando isso for pago, US$ 500 será o valor pago do 1099. Se você executar a rotina de recálculo, o sistema alterará o valor do 1099 para US$ 1.000, que é o total pago.

[![Transações do imposto 1099: após executar a rotina do 1099](./media/faq-2020-yr-end-09.png)](./media/faq-2020-yr-end-09.png)

## <a name="accounts-payable-1099--manually-create-1099-transactions"></a>Contas a pagar: 1099 – criar manualmente transações 1099
Talvez seja necessário que uma organização crie manualmente transações 1099 que não estejam associadas a uma fatura. Você pode adicionar transações 1099 manuais em **Contas a pagar > Tarefas periódicas > Imposto 1099 > Liquidação de fornecedor para impostos 1099**. Selecione o botão **Transações 1099 manuais**. 

As transações 1099 criadas manualmente não são atualizadas com os processos **Atualizar tudo** ou **Recalcular valores do imposto 1099 existentes** no utilitário **Atualização de 1099**.

## <a name="accounts-payable-1099--does-dynamics-365-finance-support-the-1096-form"></a>Contas a pagar: 1099 – o Dynamics 365 Finance oferece suporte ao formulário 1096? 

O Dynamics 365 Finance não imprime o formulário 1096 Resumo e transmissão anual de retornos de informações dos EUA.

## <a name="accounts-payable-1099--are-there-any-new-features-that-support-1099-reporting-for-public-sector"></a>Contas a pagar: 1099 – há novos recursos que oferecem suporte ao relatório 1099 para o setor público? 
Um novo recurso para o setor público, **Atualização de informações 1099 por conta principal**, foi adicionado. Ele pode ser habilitado no espaço de trabalho **Gerenciamento de recursos**. Este recurso permite associar os valores do 1099 de um fornecedor pela conta principal na distribuição contábil, em vez da conta padrão no registro do fornecedor.

Para obter mais informações, consulte [Configurar fornecedores para relatório 1099](../localizations/noam-usa-set-up-vndrs-1099-rprtg.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]