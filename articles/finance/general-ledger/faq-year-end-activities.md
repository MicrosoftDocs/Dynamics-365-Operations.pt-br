---
title: Perguntas frequentes sobre atividades do exercício
description: Este artigo lista perguntas que podem surgir ao fechar um ano, e as respostas que podem ajudar nas atividades de fechamento do exercício.
author: moaamer
ms.date: 11/08/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 2a75d1e3e68837a437b2369ba369b0063e015b12
ms.sourcegitcommit: 78cbb125f20a33df38bda0546203b8f837cbcd93
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/09/2022
ms.locfileid: "9751921"
---
# <a name="year-end-activities-faq"></a>Perguntas frequentes sobre atividades do exercício 

[!include [banner](../includes/banner.md)]

Este artigo lista perguntas que podem surgir ao fechar um ano, e as respostas que podem ajudar nas atividades de fechamento do exercício. As informações neste artigo se concentram principalmente em perguntas relativas a atividades de fechamento do exercício para a contabilidade e contas a pagar.

## <a name="general-ledger-year-end-enhancements"></a>Aprimoramentos do exercício da contabilidade 
A versão 10.0.20 introduziu um aprimoramento no fechamento do exercício, que é habilitado por padrão a partir da versão 10.0.25. Se a sua organização usa uma versão anterior à 10.0.25, recomendamos habilitar esse recurso antes de começar o processo de fechamento do exercício. Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema. Os administradores podem usar o espaço de trabalho Gerenciamento de recursos para verificar o status do recurso e ativá-lo se necessário. Lá, o recurso está listado da seguinte maneira:

 - Módulo: Contabilidade
 - Nome do recurso: Aprimoramentos do exercício da contabilidade

A configuração dos modelos de fechamento de exercício foi movida para uma nova página de configuração, **Configuração do modelo de fechamento do exercício**. A página de fechamento do exercício existente será alterada de forma semelhante à Reavaliação de moeda estrangeira para contabilidade, na qual uma lista é exibida toda vez que o fechamento do exercício é executado ou revertido. Um gerente de contabilidade pode iniciar o fechamento do exercício a partir da nova página. 

Para reverter o fechamento do exercício, selecione o ano fiscal mais recente para a entidade legal apropriada e escolha o botão **Reverter fechamento do exercício**. A reversão excluirá as entradas contábeis para o fechamento do exercício anterior e não executará novamente o fechamento do exercício de forma automática. 

Você poderá executar o fechamento do exercício novamente reiniciando o processo para o ano fiscal e a entidade legal. O processo continuará usando a configuração de parâmetros da Contabilidade para determinar se a nova execução do fechamento do exercício contabilizará somente as transações novas ou alteradas ou reverterá completamente o fechamento anterior, executando novamente o processo para todas as transações.  

## <a name="general-ledger-how-do-i-know-that-were-running-year-end-close-and-not-undoing-year-end-close"></a>Contabilidade: como sei que estamos executando o fechamento do exercício e não desfazendo o fechamento do exercício?
Algumas organizações tentam executar o fechamento do exercício, mas na verdade desfazem o fechamento do exercício. Se o fechamento do exercício for muito rápido ou não produzir saldos iniciais, valide a configuração **Desfazer fechamento anterior** em **Fechamento do exercício** (**Contabilidade > Fechamento do período > Fechamento do exercício > Executar fechamento de ano fiscal**). 

[![Executar o fechamento do exercício versus desfazer fechamento do exercício.](./media/faq-2020-yr-end-01.png)](./media/faq-2020-yr-end-01.png)

Se a seleção **Desfazer fechamento anterior** estiver definida como **Sim**, o fechamento do exercício anterior será revertido. Ao desfazer a ação, todas as entradas de saldo de fechamento e saldo inicial serão excluídas, como se o fechamento do exercício nunca tivesse sido executado. Os comprovantes serão excluídos. O fechamento do exercício não será executado automaticamente novamente. Você deverá iniciar o processo novamente, desta vez alterando **Desfazer fechamento anterior** para **Não**. 

> [!NOTE]
> A entrada de saldo de fechamento é opcionalmente criada no ano que está sendo encerrado. Isso ocorrerá somente se o parâmetro da contabilidade **Criar transações de fechamento durante a transferência** estiver definido como **Sim**. A entrada do saldo inicial sempre é criada, pois esse é o saldo inicial para o próximo ano.  
 
## <a name="general-ledger-what-is-the-difference-between-undo-and-delete-gl-parameter-for-year-end-close"></a>Contabilidade: qual é a diferença entre desfazer e excluir o parâmetro GL para o fechamento do exercício?
Pode haver confusão sobre a diferença entre o parâmetro **Desfazer fechamento anterior**, que está na caixa de diálogo **Fechamento do exercício**, e o parâmetro **Excluir transações de fechamento de ano durante a transferência** na contabilidade (**Contabilidade > Fechamento do período > Fechamento do exercício > Executar fechamento de ano fiscal**).  

[![Diferença entre Desfazer e Excluir o parâmetro GL para o fechamento do exercício.](./media/faq-2020-yr-end-02.png)](./media/faq-2020-yr-end-02.png)

Selecione **Desfazer fechamento anterior** no menu suspenso da caixa de diálogo ao executar o processo de fechamento do exercício para excluir todas as entradas de saldo de fechamento e de saldo inicial, como se o fechamento do exercício nunca tivesse sido executado. Os comprovantes serão excluídos. O fechamento do exercício não será executado automaticamente novamente. Para executar o fechamento do exercício, inicie esse processo novamente, desta vez alterando **Desfazer fechamento anterior** para **Não** (**Contabilidade > Configuração do razão > Parâmetros da contabilidade**). 

[![Configuração de parâmetros da contabilidade.](./media/faq-2020-yr-end-03.png)](./media/faq-2020-yr-end-03.png)

O parâmetro **Excluir transações de fechamento de ano durante a transferência** na Contabilidade é usado somente durante a execução do fechamento do exercício (não ao desfazê-lo). A seleção **Desfazer fechamento anterior** está definida como **Não**. Se esse parâmetro estiver definido como **Sim**, todas as entradas de saldo de fechamento e saldo inicial serão excluídas e o fechamento do exercício será executado novamente. Esse processo é usado quando a organização deseja que todas as transações, incluindo os ajustes desde o último fechamento do exercício, sejam lançadas em uma única entrada contábil para as entradas de saldo de fechamento e de saldo inicial. 

Se essa opção estiver definida como **Não**, todas as entradas de saldo de fechamento e de saldo inicial permanecerão. Elas não serão excluídas. Em vez disso, uma nova entrada de saldo de fechamento e de saldo inicial será criada apenas para a variação ou para as transações novas lançadas desde o último fechamento do exercício daquele ano fiscal.  

> [!NOTE]
> A entrada de saldo de fechamento é criada no ano que está sendo encerrado. Isso ocorrerá somente se o parâmetro **Criar transações de fechamento durante a transferência** da contabilidade estiver definido como **Sim**. A entrada do saldo inicial sempre é criada, pois esse é o saldo inicial para o próximo ano. 

## <a name="general-ledger-what-can-be-changed-to-enhance-performance-of-year-end-processing"></a>Contabilidade: o que pode ser alterado para melhorar o desempenho do processo do final de ano? 
Você pode fazer diversas alterações para melhorar o desempenho do fechamento do exercício. É recomendável avaliar essas alterações sugeridas para considerar se a alteração é adequada à sua organização.  

### <a name="dimension-sets"></a>Conjuntos de dimensões
Ao executar o fechamento do exercício, o saldo de cada conjunto de dimensões é recriado, o que tem um impacto direto no desempenho. Algumas organizações criam conjuntos de dimensões desnecessariamente porque já foram usados ou podem ser usados em algum momento.  Esses conjuntos de dimensões desnecessários ainda são recriados durante o fechamento do exercício, o que acrescenta tempo ao processo. Avalie os conjuntos de dimensões e exclua quaisquer conjuntos de dimensões desnecessários.

Os conjuntos de dimensões desnecessários também afetam o trabalho em lotes **BudgetDimensionFocusInitializeBalance** (**Contabilidade > Plano de contas > Dimensões > Conjuntos de dimensões financeiras**).

[![Conjuntos de dimensões financeiras.](./media/faq-2020-yr-end-04.png)](./media/faq-2020-yr-end-04.png)

### <a name="year-end-close-template-configuration"></a>Configuração do modelo de fechamento do exercício
O modelo de fechamento do exercício permite que as organizações selecionem o nível de dimensão financeira a ser mantido ao transferir saldos de lucros e perdas para ganhos retidos. As configurações permitem que uma organização mantenha as dimensões financeiras detalhadas (**Fechar tudo**) ao mover os saldos para ganhos retidos ou optar por resumir os valores para um único valor de dimensão (**Fechar um**). Isso pode ser definido para cada dimensão financeira. Para obter mais informações sobre essas configurações, consulte o artigo [Fechamento do exercício](year-end-close.md).

Recomendamos que você avalie os requisitos da sua organização e, se possível, feche o número máximo de dimensões usando a opção **Fechar um** exercício para melhorar o desempenho. Ao fazer o fechamento para um único valor de dimensão (que também pode ser um valor em branco), o sistema calcula menos detalhes ao determinar os saldos das entradas da conta de ganhos retidos.

## <a name="degenerate-dimensions"></a>Degenerar dimensões

Uma dimensão degenerada fornece pouca ou nenhuma reutilização por si mesma e em combinação com outras dimensões. Há dois tipos diferentes de dimensões degeneradas. O primeiro tipo é uma dimensão que é degenerada individualmente. Normalmente, esse tipo de dimensão de degeneração aparecerá somente em uma única transação ou em pequenos conjuntos de transações. O segundo tipo é uma dimensão que se torna degenerada em combinação com uma ou mais dimensões adicionais que exibem o mesmo potencial com base nas possíveis permutações que podem ser geradas. Uma dimensão degenerada pode ter um impacto significativo no desempenho do processo de fechamento do exercício. Para minimizar os problemas de desempenho, defina todas as dimensões degenerada como **Fechar um** na configuração de fechamento do exercício, conforme descrito na seção anterior.

## <a name="general-ledger-what-does-the-period-close-year-end-close-do"></a>Contabilidade: o que fazem o fechamento do período e o fechamento do exercício?
 
[![Fechamento do período, fechamento do exercício.](./media/faq-2020-yr-end-05.png)](./media/faq-2020-yr-end-05.png)

### <a name="performance-improvements-for-rebuilding-financial-dimension-sets"></a>Melhorias de desempenho para a recriação de conjuntos de dimensões financeiras
Um novo recurso adicionado na versão 10.0.16 melhora o desempenho dos processos de consolidação e fechamento do exercício. O nome do recurso é Melhorias de desempenho para a recriação de conjuntos de dimensões financeiras. Este recurso altera a forma como os conjuntos de dimensões são recriados para que sejam recriados apenas para um período relevante. Nas versões anteriores, os conjuntos de dimensões eram recriados para todas as datas. Por exemplo, se você estiver fechando o ano 2020, o sistema só recriará os saldos para transações no ano fiscal 2020. Se você estiver executando a consolidação para um intervalo de datas de 1º de novembro de 2020 a 30 de novembro de 2020, o sistema apenas recriará os saldos para esse intervalo.

Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema. Os administradores podem usar o espaço de trabalho Gerenciamento de recursos para verificar o status do recurso e ativá-lo se necessário. Lá, o recurso está listado da seguinte maneira:
 
- Módulo: Contabilidade
- Nome do recurso: Melhorias de desempenho para a recriação de conjuntos de dimensões financeiras

## <a name="accounts-payable-what-changes-have-been-made-to-support-1099-year-end-reporting-for-2021"></a>Contas a pagar: que alterações foram feitas para oferecer suporte a relatórios 1099 de final do exercício para 2021?

Em 2021, os formulários DIV, NEC e MISC foram ligeiramente alterados e algumas caixas adicionais foram incluídas.

#### <a name="div-new-box2e-2f"></a>DIV: nova caixa 2e, 2f
 
- Caixa 2e. Mostra a parte do valor na caixa 1a, que é a seção 897 ganho atribuível à disposição dos juros imobiliários dos EUA (USRPI).  
- Caixa 2f. Mostra a parte do valor na caixa 2a, que é a seção 897 ganho atribuível à disposição de USRPI. Observe que as caixas 2e e 2f se aplicam somente a pessoas e entidades estrangeiras cuja renda mantém sua característica ao ser transmitida, ou distribuída, a seus proprietários ou beneficiários estrangeiros diretos ou indiretos. Geralmente, ela é tratada como conectada de modo efetivo ao comércio ou atividade nos Estados Unidos. Consulte as instruções para sua declaração de imposto. 
 
#### <a name="nec-new-box-2"></a>NEC: nova caixa 2 
 
Se a caixa 2 estiver marcada, relate os produtos de consumo que totalizam US$ 5.000 ou mais que foram vendidos para você para revenda, em uma compra e venda, em uma comissão de depósito ou de outra forma. Em geral, relate qualquer renda da sua venda desses produtos na Agenda C (formulário 1040). 
 
Enquanto isso, o tamanho do formulário de NEC é alterado. Durante a impressão, há três formulários por página. 
 
#### <a name="misc-new-box-11"></a>MISC: nova caixa 11 
 
A caixa 11 mostra o valor pago pela compra de peixe para revenda por qualquer pessoa envolvida no comércio ou no ramo de pesca. Consulte as instruções para sua declaração de imposto para relatar essa renda. 
 
#### <a name="electronic-filing"></a>Transmissão eletrônica 
Para obter informações sobre a transmissão eletrônica, consulte [Publicação para requisitos de transmissão eletrônica](https://www.irs.gov/pub/irs-pdf/p1220.pdf).

Atualizar especificações de formato e layouts de registro para o relatório eletrônico de 2021 
- Seç. 2 Registro do Emissor "A". 
- Códigos de valor - aumentada a posição do campo 28-45, o tamanho foi para 18. 
 
#### <a name="sec-2-issuer-a-record-for-reporting-payments-on-form-1099-div"></a>Seç. 2 Registro do Emissor "A", para relatar pagamentos no formulário 1099-DIV: 
- Tipo de valor – adicionada a seção 897 Dividendos Ordinários e Código de Valor H adicionado. 
- Tipo de valor – adicionada a seção 897 Ganhos de Capital e Código de Valor J adicionado. 
 
#### <a name="sec-3-payee-b-record"></a>Seç. 3 Registro do Beneficiário "B" 
- Registros de Informações Gerais – terceiro marcador atualizado de 16 para 18 campos de Valor de Pagamento. 
- Título do campo Pagamento H – posição do campo atualizada 247-258, título do campo, tamanho e descrição geral do campo. 
- Título do campo Pagamento J – posição do campo atualizada 259-270, título do campo, tamanho e descrição geral do campo. 
- Campo em branco atualizado para a posição do campo 271-286. 
- Indicador de país estrangeiro atualizado para a posição do campo 287. 
- Campo da linha do Nome do Beneficiário atualizado para a posição do campo 288-327. 
- Campo da linha do Sobrenome do Beneficiário atualizado para a posição do campo 328-367. 
- Posições de layout do registro, formulário 1099-MISC – posição do campo 548 e título do campo FATCA do indicador de requisitos de transmissão excluídos. 
- Posições de layout do registro, formulário 1099-NEC – atualizado o campo 545-546 para em branco, campo 547 atualizado para indicador de venda direta, tamanho, descrição e comentários atualizados no campo 548-722 para em branco. 
 
#### <a name="sec-4-end-of-issuer-c-record"></a>Seç. 4 Fim do Registro do Emissor "C" 
- Título do campo Pagamento H – posição do campo atualizada 304-321, título do campo, tamanho e descrição geral do campo. 
- Título do campo Pagamento J – posição do campo atualizada 322-339, título do campo, tamanho e descrição geral do campo. 
- Título do campo 340-499 – tamanho atualizado para 160. 
 
#### <a name="sec-5-state-totals-k-record"></a>Seç. 5 Registro Declarar Totais "K" 
- Título do campo Pagamento H – posição do campo atualizada 304-321, título do campo, tamanho e descrição geral do campo. 
- Título do campo Pagamento J – posição do campo atualizada 322-339, título do campo, tamanho e descrição geral do campo. 
- Título do campo 340-499 – tamanho atualizado para 160.  

## <a name="accounts-payable-1099--how-do-i-change-the-1099-box-and-values-for-a-vendor-that-wasnt-tracking-1099-information-throughout-the-year"></a>Contas a pagar: 1099 – como alterar a caixa 1099 e os valores de um fornecedor que não estava acompanhando as informações 1099 durante todo o ano?
Use a funcionalidade Atualização de 1099 (**Contas a pagar > Fornecedores > Todos os fornecedores > Selecionar um fornecedor > Guia do fornecedor na faixa de opções > Atualização de 1099**) para passar pelas transações de faturas pagas anteriormente e reatribuir corretamente os dados 1099 de acordo com as configurações na guia **Imposto 1099** na página **Fornecedor**.

## <a name="can-i-run-the-update-1099-for-all-my-vendors-at-once"></a>É possível executar a Atualização de 1099 para todos os meus fornecedores de uma só vez?
Não. A rotina Atualização de 1099 é executada para um único fornecedor de cada vez. Se essa requisição for necessária para sua organização, vote na ideia chamada [Processo em lote para atualização dos dados 1099 do fornecedor](https://experience.dynamics.com/ideas/idea/?ideaid=5493d608-350e-eb11-b5d9-0003ff68ded8).

## <a name="accounts-payable-1099--recalculate-existing-1099-amounts-versus-update-all-in-the-update-1099-utility"></a>Contas a pagar: 1099 – Recalcular valores do imposto 1099 existentes versus Atualizar tudo no utilitário Atualização de 1099
A caixa de seleção **Recalcular valores do imposto 1099 existentes** redefine o valor do 1099 para os valores totais pagos, quando usada em conjunto com a caixa de seleção **Atualizar tudo**. 

[![Transações do imposto 1099: antes de executar a rotina de atualização.](./media/faq-2020-yr-end-07.png)](./media/faq-2020-yr-end-07.png)

A caixa de seleção **Recalcular valores do imposto 1099 existentes** só aparece quando há valores parciais do 1099 na fatura ou se ele tiver sido modificado no formulário Imposto 1099. Por exemplo, suponha que você tenha uma fatura de US$ 1.000, mas o usuário digita manualmente na fatura um valor do 1099 de US$ 500.

[![Transações do imposto 1099: marcar Atualizar tudo e Recalcular valores do imposto 1099 existentes.](./media/faq-2020-yr-end-08.png)](./media/faq-2020-yr-end-08.png)

Quando isso for pago, US$ 500 será o valor pago do 1099. Se você executar a rotina de recálculo, o sistema alterará o valor do 1099 para US$ 1.000, que é o total pago.

[![Transações do imposto 1099: após executar a rotina do 1099.](./media/faq-2020-yr-end-09.png)](./media/faq-2020-yr-end-09.png)

## <a name="accounts-payable-1099--manually-create-1099-transactions"></a>Contas a pagar: 1099 – criar manualmente transações 1099
Talvez seja necessário que uma organização crie manualmente transações 1099 que não estejam associadas a uma fatura. Você pode adicionar transações 1099 manuais em **Contas a pagar > Tarefas periódicas > Imposto 1099 > Liquidação de fornecedor para impostos 1099**. Selecione o botão **Transações 1099 manuais**. 

As transações 1099 criadas manualmente não são atualizadas com os processos **Atualizar tudo** ou **Recalcular valores do imposto 1099 existentes** no utilitário **Atualização de 1099**.

## <a name="accounts-payable-1099--does-dynamics-365-finance-support-the-1096-form"></a>Contas a pagar: 1099 – o Dynamics 365 Finance oferece suporte ao formulário 1096? 

O Dynamics 365 Finance não imprime o formulário 1096 Resumo e transmissão anual de retornos de informações dos EUA.

## <a name="accounts-payable-1099--are-there-any-new-features-that-support-1099-reporting-for-public-sector"></a>Contas a pagar: 1099 – há novos recursos que oferecem suporte ao relatório 1099 para o setor público? 
Um novo recurso para o setor público, **Atualização de informações 1099 por conta principal**, foi adicionado. Ele pode ser habilitado no espaço de trabalho **Gerenciamento de recursos**. Este recurso permite associar os valores do 1099 de um fornecedor pela conta principal na distribuição contábil, em vez da conta padrão no registro do fornecedor.

Para obter mais informações, consulte [Configurar fornecedores para relatório 1099](../localizations/noam-usa-set-up-vndrs-1099-rprtg.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
