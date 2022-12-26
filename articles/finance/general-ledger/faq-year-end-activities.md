---
title: Perguntas frequentes sobre atividades do exercício
description: Este artigo lista perguntas que podem surgir ao fechar um ano, e as respostas que podem ajudar nas atividades de fechamento do exercício.
author: moaamer
ms.date: 12/01/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 2e33c1dcbfa4da74f2e8acc6e29f04fda3abd185
ms.sourcegitcommit: 9f3a60a583da21382a14f32ce146fc9ce03f2a09
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2022
ms.locfileid: "9853030"
---
# <a name="year-end-activities-faq"></a>Perguntas frequentes sobre atividades do exercício 

[!include [banner](../includes/banner.md)]

Este artigo lista perguntas que podem surgir ao fechar um ano, e as respostas que podem ajudar nas atividades de fechamento do exercício. As informações neste artigo se concentram principalmente em perguntas relativas a atividades de fechamento do exercício para a contabilidade e contas a pagar.

## <a name="general-ledger-year-end-enhancements"></a>Aprimoramentos do exercício da contabilidade

A versão 10.0.20 do Microsoft Dynamics 365 Finance introduziu um aprimoramento no fechamento do exercício. Esse aprimoramento foi habilitado por padrão a partir da versão 10.0.25 e é obrigatório a partir da versão 10.0.29. Se a sua organização usa uma versão anterior à 10.0.25, recomendamos habilitar esse recurso antes de começar o processo de fechamento do exercício. Para poder usar este recurso, ele deve ser ativado no sistema. Os administradores podem usar o espaço de trabalho **Gerenciamento de recursos** para verificar o status do recurso e ativá-lo, se necessário. Lá, o recurso está listado da seguinte maneira:

- **Módulo:** Contabilidade
- **Nome do recurso:** Aprimoramentos do exercício da contabilidade

A configuração dos modelos de fechamento de exercício foi movida para uma nova página de configuração, **Configuração do modelo de fechamento do exercício**. A página de fechamento do exercício existente será semelhante à página **Reavaliação de moeda estrangeira para contabilidade**, na qual uma lista é exibida toda vez que o fechamento do exercício é executado ou revertido. A página não exibirá informações históricas sobre fechamentos de exercício que foram executados antes da ativação do recurso. Um gerente de contabilidade pode iniciar o fechamento do exercício a partir da nova página.

Para reverter o fechamento do exercício, selecione o ano fiscal mais recente para a entidade legal apropriada e selecione **Reverter fechamento do exercício**. A reversão excluirá as entradas contábeis para o fechamento do exercício anterior e não executará novamente o fechamento do exercício de forma automática. Se você habilitar o recurso **Aprimoramentos do exercício da contabilidade** depois de concluir o fechamento do exercício e quiser reverter os resultados históricos do exercício, execute o fechamento do exercício novamente após habilitar o parâmetro de contabilidade **Excluir entradas de fechamento do exercício existentes ao fechar novamente o ano**.

Você poderá executar o fechamento do exercício novamente reiniciando o processo para o ano fiscal e a entidade legal. O processo continuará usando a configuração de parâmetros da Contabilidade para determinar se a nova execução do fechamento do exercício contabilizará somente as transações novas ou alteradas ou se o processo será executado novamente para todas as transações e reverterá completamente o fechamento anterior.

## <a name="general-ledger-the-general-ledger-year-end-enhancements-feature-is-enabled-why-cant-i-view-my-previous-year-closings-in-the-history-section-of-the-year-end-close-page"></a>Contabilidade: o recurso Aprimoramentos do exercício da contabilidade está habilitado. Por que não consigo visualizar meus fechamentos do ano anterior na seção Histórico da página Fechamento do exercício?

Antes de habilitar o recurso **Aprimoramentos do exercício da contabilidade**, a data e a hora em que o último processo do fechamento do exercício foi executado são rastreadas. Não é registrado o histórico de todas as vezes que o fechamento do exercício foi executado. Dessa forma, os detalhes de cada fechamento de exercício executado não estão disponíveis para exibição. Após habilitar o recurso, as informações do processo de fechamento do exercício subsequente são mantidas. Os comprovantes de todos os processos de fechamento do exercício, mesmo aqueles executados antes da ativação do recurso, podem ser visualizados na página **Comprovantes de transações**. 

## <a name="general-ledger-the-year-end-close-process-is-failing-because-of-the-following-error-the-year-end-close-cant-be-run-because-one-or-more-ledger-transactions-posted-into-the-fiscal-year-that-you-are-closing-were-settled-to-a-ledger-transaction-in-a-different-fiscal-year-what-does-this-error-mean"></a>Contabilidade: o processo de fechamento do exercício não é possível devido ao seguinte erro: "O fechamento do exercício não pode ser executado porque uma ou mais transações do razão lançadas no ano fiscal sendo fechado foram liquidadas em uma transação contábil em outro ano fiscal". O que esse erro significa?

Como o recurso **Reconhecimento entre a liquidação do razão e o fechamento do exercício** está habilitado, somente as transações do razão liquidadas do ano fiscal sendo fechado são excluídas do saldo inicial. Esse comportamento faz com que débitos e créditos fiquem em desequilíbrio. Para obter mais informações, consulte [Reconhecimento entre a liquidação do razão e o fechamento do exercício](awareness-between-ledger-settlement-year-end-close.md).

## <a name="general-ledger-reversal-of-the-year-end-close-process-is-failing-because-of-the-following-error-the-year-end-close-for-112022-cant-be-reversed-because-beginning-balance-transaction-have-been-ledger-settled-in-fiscal-year-112023-what-does-this-error-mean"></a>Contabilidade: o processo de reversão do fechamento do exercício não é possível devido ao seguinte erro: "O fechamento do exercício para 01/01/2022 não pode ser revertido porque a transação de saldo inicial foi liquidada do razão no ano fiscal 01/01/2023". O que esse erro significa?

Como o recurso **Reconhecimento entre a liquidação do razão e o fechamento do exercício** está habilitado, as reversões do processamento do final de ano não são permitidas se as transações de abertura tiverem sido liquidadas no novo ano fiscal. Reverta a liquidação do razão no novo ano fiscal de 2023 antes de reverter o fechamento do exercício para 1º de janeiro de 2022. Outra opção é fechar novamente o exercício para 1º de janeiro de 2022, mas apenas para novas entradas de ajuste. Para fechar novamente o exercício somente para ajustes, desabilite o parâmetro de contabilidade **Excluir entradas de fechamento do exercício existentes ao fechar novamente o ano**.

## <a name="general-ledger-why-isnt-the-ledger-settlement-automation-processing-decembers-ledger-settlement-transactions"></a>Contabilidade: por que a automação de liquidação do razão não está processando as transações de liquidação do razão de dezembro?

O recurso **Automatizar liquidações contábeis** executará a automação para transações datadas do primeiro dia do ano fiscal até a data atual em que a ocorrência for executada. Para anos fiscais que terminam em 31 de dezembro, talvez seja necessário ajustar a data de execução da ocorrência para garantir que ela seja executada em dezembro. Por exemplo, a automação está configurada para ser executada no primeiro dia de cada mês. Essa automação será executada em 1º de dezembro de 2022 e está programada para 1º de janeiro de 2023. Recomendamos alterar a ocorrência para 1° de janeiro de 2023, para que seja executada em 31 de dezembro de 2022. Essa alteração garantirá que as transações com data de 2 a 31 de dezembro sejam consideradas para liquidação automática.

## <a name="general-ledger-whats-the-difference-between-the-reverse-year-end-close-action-and-the-delete-existing-year-end-entries-when-reclosing-parameter-for-year-end-close"></a>Contabilidade: qual é a diferença entre a ação Reverter fechamento do exercício e o parâmetro Excluir entradas de fechamento do exercício existentes ao fechar novamente o ano?

Pode haver confusão em relação à diferença entre a ação **Reverter fechamento do exercício** e o parâmetro **Excluir entradas do fechamento do exercício existentes ao fechar novamente o ano** da contabilidade (**Contabilidade \> Configuração do razão \> Parâmetros de contabilidade**).

Selecione a ação **Reverter fechamento do exercício** ao executar o processo de fechamento do exercício para excluir todas as entradas de saldo de fechamento e de saldo inicial, como se o fechamento do exercício nunca tivesse sido executado. Nesse caso, os comprovantes serão excluídos. O fechamento do exercício não será executado automaticamente novamente. Para executar o fechamento do exercício, selecione a ação **Executar fechamento do exercício**.

O parâmetro da contabilidade **Excluir entradas de fechamento do exercício existentes ao fechar novamente o ano** é usado somente quando o fechamento do exercício (não a reversão) está sendo executado. Se o parâmetro estiver definido como **Sim**, todas as entradas de saldo de fechamento e saldo inicial serão excluídas e o fechamento do exercício será executado novamente. Essa opção é usada quando uma organização deseja que todas as transações, incluindo os ajustes desde o último fechamento do exercício, sejam lançadas em uma única entrada contábil para as entradas de saldo de fechamento e de saldo inicial. Se o parâmetro estiver definido como **Não**, todas as entradas de saldo de fechamento e de saldo inicial permanecerão. Elas não serão excluídas. Em vez disso, uma nova entrada de saldo de fechamento e de saldo inicial será criada apenas para a variação ou para as transações novas que foram lançadas desde o último fechamento do exercício daquele ano fiscal.

> [!NOTE]
> A entrada de saldo de fechamento é criada no ano que está sendo encerrado. Isso ocorrerá somente se o parâmetro **Criar transações de fechamento durante a transferência** da contabilidade estiver definido como **Sim**. A entrada do saldo inicial é sempre criada, pois é o saldo inicial do ano seguinte.

## <a name="general-ledger-what-is-the-difference-between-close-all-and-close-single-options-on-the-transfer-profit-and-loss-dimension-section-of-the-year-end-close-process"></a>Contabilidade: qual é a diferença entre as opções "Fechar tudo" e "Fechar um" na seção Transferir dimensões de lucros e perdas do processo de fechamento do exercício?

**Fechar tudo** mantém os valores de dimensão financeira originais das transações lançadas e os utiliza para criar os saldos iniciais da conta de lucros retidos. Saldos iniciais de lucros retidos separados são criados para cada combinação exclusiva de valores de dimensão financeira. Se **Fechar um** for selecionada, todas as transações lançadas com essa dimensão financeira serão resumidas em um saldo inicial de lucros retidos para o valor de dimensão inserido no campo que aparece após **Fechar um**. 

Por exemplo, todas as transações do ano fiscal foram lançadas com a estrutura de conta Conta principal - Departamento. Na dimensão financeira Departamento no modelo, **Fechar um** está selecionada e 100 é o valor inserido como o valor da dimensão. Se a receita total de todas as transações lançadas nos departamentos 200, 300 e 400 for US$ 100 mil, um saldo inicial será criado para Lucros retidos -100. Se você selecionar **Fechar um** e deixar o valor da dimensão financeira em branco, todas as transações serão lançadas em lucros retidos e o valor de dimensão ficará em branco.

## <a name="general-ledger-when-i-select-close-single-option-on-the-transfer-profit-and-loss-dimension-section-of-the-year-end-close-process-will-my-detailed-transactional-information-be-lost"></a>Contabilidade: quando eu seleciono a opção "Fechar um" na seção Transferir dimensões de lucros e perdas do processo de fechamento do exercício, as informações detalhadas da transação serão perdidas?

As opções **Fechar tudo** e **Fechar um** são usadas para especificar quais dimensões financeiras das transações lançadas na conta de lucros e perdas são transferidas para a conta principal de lucros retidos. O lançamento histórico e detalhado nas contas de lucros e perdas não é afetado e permanecerá detalhado. A opção afeta o nível de detalhe que é transferido para as contas de lucros retidos como um saldo inicial no novo ano. 

## <a name="general-ledger-the-year-end-close-process-is-failing-because-the-reporting-currency-for-the-year-does-not-balance-what-does-this-mean"></a>Contabilidade: o processo de fechamento do exercício não é possível porque a moeda de relatório do ano não coincide. O que isso significa?

Esse erro pode ocorrer após habilitar o recurso **Reconhecimento entre a liquidação do razão e o fechamento do exercício** (o recurso de reconhecimento). Quando o recurso estiver habilitado, as transações do razão que tiverem sido liquidadas não serão mais incluídas no saldo inicial do ano fiscal seguinte ao executar o fechamento do exercício da contabilidade. Excluir as transações do razão que são liquidadas pode ser um desafio para os clientes no fechamento do exercício se o Razão for definido com uma moeda de relatório.   
A liquidação do razão é executada somente para a moeda contábil.  Quando as transações do razão são liquidadas, a validação apenas garante que os débitos da moeda contábil sejam iguais aos créditos da moeda contábil. Os valores da moeda de relatório para essas transações contábeis não são validados e podem não ter débitos = créditos.  Além disso, a liquidação do razão não calcula e lança automaticamente um lucro/perda na moeda do relatório.  Devido a essas limitações, uma transação de ganho/perda deve existir na moeda de relatório ao executar a liquidação do razão.  Se o ganho/perda não for incluído na liquidação do razão, o fechamento do exercício resultará em uma mensagem referente ao saldo.  Para obter mais informações, consulte o recurso [Reconhecimento entre a liquidação do razão e moeda do relatório sem saldo](reporting-currency-yec.md).

## <a name="general-ledger-what-can-be-changed-to-help-enhance-the-performance-of-year-end-processing"></a>Contabilidade: o que pode ser alterado para ajudar a melhorar o desempenho do processo do final de ano?

Você pode fazer diversas alterações para ajudar a melhorar o desempenho do fechamento do exercício. É recomendável avaliar essas alterações sugeridas para determinar se elas são adequadas para sua organização.

### <a name="optimize-year-end-close-service"></a>Serviço Otimizar o fechamento do exercício

O serviço **Otimizar o fechamento do exercício** permite que os clientes do Microsoft Dynamics 365 Finance acelerem o fechamento do exercício ao mover o processamento pesado para um microsserviço. O tempo economizado, resultante de um fechamento de exercício eficiente, permite que cada equipe financeira reaja em tempo hábil aos ajustes necessários, terminando na geração dos relatórios financeiros. Ao processar o fechamento do exercício em um microsserviço, diversos recursos são liberados. A elevação do processamento minimiza a carga no SQL Server e oferece aos clientes a oportunidade de acelerar o processamento de fechamento do exercício.

O serviço **Otimizar fechamento de final de ano** está disponível na versão 10.0.31, para que mais clientes possam usar o novo serviço para a temporada de final de ano de 2022. Além disso, o serviço foi ajustado para as versões 10.0.30 e 10.0.29. Para obter mais informações, consulte [Otimizar o fechamento do exercício](optimize-year-end-close.md).

### <a name="dimension-sets"></a>Conjuntos de dimensões

Ao executar o fechamento do exercício, o saldo de cada conjunto de dimensões é recriado. Esse comportamento afeta diretamente o desempenho. Algumas organizações criam conjuntos de dimensões desnecessariamente porque já foram usados ou podem ser usados em algum momento. Como esses conjuntos de dimensões desnecessários ainda são recriados durante o fechamento do exercício, o processo torna-se mais lento. Avalie os conjuntos de dimensões e exclua todos os que forem desnecessários.

Os conjuntos de dimensões desnecessários também afetam o trabalho em lotes **BudgetDimensionFocusInitializeBalance** (**Contabilidade \> Plano de contas \> Dimensões \> Conjuntos de dimensões financeiras**).

[![Conjuntos de dimensões financeiras.](./media/faq-2020-yr-end-04.png)](./media/faq-2020-yr-end-04.png)

### <a name="year-end-close-template-configuration"></a>Configuração do modelo de fechamento do exercício

O modelo de fechamento do exercício permite que as organizações selecionem o nível de dimensão financeira a ser mantido ao transferir saldos de lucros e perdas para ganhos retidos. As configurações permitem que uma organização mantenha as dimensões financeiras detalhadas (**Fechar tudo**) ao mover os saldos para ganhos retidos ou optar por resumir os valores para um único valor de dimensão (**Fechar um**). Isso pode ser definido para cada dimensão financeira. Para obter mais informações sobre essas configurações, consulte o artigo [Fechamento do exercício](year-end-close.md).

Recomendamos que você avalie os requisitos da sua organização e, se possível, feche o número máximo de dimensões usando a opção **Fechar um** exercício para melhorar o desempenho. Ao fazer o fechamento para um único valor de dimensão (que também pode ser um valor em branco), o sistema calcula menos detalhes ao determinar os saldos das entradas da conta de ganhos retidos.

### <a name="degenerate-dimensions"></a>Degenerar dimensões

Uma dimensão degenerada fornece pouca ou nenhuma reutilização por si mesma e em combinação com outras dimensões. Há dois tipos diferentes de dimensões degeneradas. O primeiro tipo é uma dimensão que é degenerada individualmente. Normalmente, esse tipo de dimensão de degeneração aparecerá somente em uma única transação ou em pequenos conjuntos de transações. O segundo tipo é uma dimensão que se torna degenerada em combinação com uma ou mais dimensões adicionais que exibem o mesmo potencial com base nas possíveis permutações que podem ser geradas. Uma dimensão degenerada pode ter um impacto significativo no desempenho do processo de fechamento do exercício. Para minimizar os problemas de desempenho, defina todas as dimensões degeneradas como **Fechar um** na configuração de fechamento do exercício, conforme descrito na seção anterior.

## <a name="accounts-payable-what-changes-have-been-made-to-support-1099-year-end-reporting-for-2022"></a>Contas a pagar: que alterações foram feitas para oferecer suporte a relatórios 1099 de final do exercício para 2022?

#### <a name="update-to-all-1099-forms"></a>Atualizar para todos os formulários 1099

As seguintes alterações foram feitas em todos os formulários 1099 para o ano fiscal de 2022:

- Em 2021, o ano foi corrigido nos formulários 1099. A partir de 2022, o ano é preenchido pelo relatório.

#### <a name="1099-misc"></a>1099-MISC

As seguintes atualizações foram feitas no Formulário 1099-MISC para o ano fiscal de 2022:

- Caixa 13: agora indica o requisito de arquivamento de FATCA (Foreign Account Tax Compliance Act).
- Caixa 14: agora usada para relatar os pagamentos Golden Parachute em excesso.
- Caixa 15: agora usada para relatar o pagamento em planos de compensação diferida não qualificada (NQDC).
- Caixa 16: agora usada para relatar impostos retidos pelo estado.
- Caixa 17: agora usada para relatar o número do estado do pagador.
- Caixa 18: agora usada para relatar imposto de renda estadual.

## <a name="accounts-payable-1099--how-do-i-change-the-1099-box-and-values-for-a-vendor-that-wasnt-tracking-1099-information-throughout-the-year"></a>Contas a pagar: 1099 – como alterar a caixa 1099 e os valores de um fornecedor que não estava acompanhando as informações 1099 durante todo o ano?

Use a funcionalidade **Atualização de 1099** para passar pelas transações de faturas pagas anteriormente e reatribuir adequadamente os dados 1099 de acordo com as configurações na guia **Imposto 1099** na página **Fornecedor**. Para usar a funcionalidade **Atualização de 1099**, vá para **Contas a pagar \> Fornecedores \> Todos os fornecedores**, selecione um fornecedor e, no Painel de Ações, na guia **Fornecedor**, selecione **Atualização de 1099**.

## <a name="can-i-run-the-update-1099-functionality-for-all-my-vendors-at-once"></a>É possível executar a funcionalidade Atualização de 1099 para todos os meus fornecedores de uma só vez?

Você pode usar a página **Informações da atualização de 1099 para vários fornecedores** para atualizar a caixa 1099 em um registro de fornecedor e atualizar transações com as informações da caixa 1099. Para abrir essa página, vá para **Contas a pagar \> Tarefa periódica \> Imposto 1099**. Para acessar a página, você deve receber o privilégio de segurança **Atualização e transações de 1099 para vários fornecedores**.

## <a name="accounts-payable-1099--recalculate-existing-1099-amounts-versus-update-all-in-the-update-1099-utility"></a>Contas a pagar: 1099 – Recalcular valores do imposto 1099 existentes versus Atualizar tudo no utilitário Atualização de 1099

A caixa de seleção **Recalcular valores do imposto 1099 existentes** redefine o valor do 1099 para os valores totais pagos, quando usada em conjunto com a caixa de seleção **Atualizar tudo**.

[![Transações do imposto 1099: antes de executar a rotina de atualização.](./media/faq-2020-yr-end-08.png)](./media/faq-2020-yr-end-08.png)

A caixa de seleção **Recalcular valores do imposto 1099 existentes** aparece apenas quando há valores parciais do 1099 na fatura ou se ela tiver sido modificada no formulário Imposto 1099. Por exemplo, suponha que você tenha uma fatura de US$ 1.000, mas o usuário registra manualmente na fatura um valor do 1099 de US$ 500.

[![Transações do imposto 1099: marcar Atualizar tudo e Recalcular valores do imposto 1099 existentes.](./media/faq-2020-yr-end-07.png)](./media/faq-2020-yr-end-07.png)

Quando a fatura for paga, US$ 500 será o valor pago do 1099. Se você executar a rotina de recálculo, o valor do 1099 será alterado para US$ 1.000, que é o total pago.

[![Transações do imposto 1099: após executar a rotina do 1099.](./media/faq-2020-yr-end-09.png)](./media/faq-2020-yr-end-09.png)

## <a name="accounts-payable-1099--manually-create-1099-transactions"></a>Contas a pagar: 1099 – criar manualmente transações 1099

Talvez seja necessário que uma organização crie manualmente transações 1099 que não estejam associadas a uma fatura. Você pode adicionar transações 1099 manuais em **Contas a pagar \> Tarefas periódicas \> Imposto 1099 \> Liquidação de fornecedor para impostos 1099**. Selecione o botão **Transações 1099 manuais**.

As transações 1099 criadas manualmente não são atualizadas com os processos **Atualizar tudo** ou **Recalcular valores do imposto 1099 existentes** no utilitário **Atualização de 1099**.

## <a name="accounts-payable-1099--does-dynamics-365-finance-support-the-1096-form"></a>Contas a pagar: 1099 – o Dynamics 365 Finance oferece suporte ao formulário 1096?

O Dynamics 365 Finance não imprime o formulário 1096 Resumo e transmissão anual de retornos de informações dos EUA.

## <a name="accounts-payable-1099--are-there-any-new-features-that-support-1099-reporting-for-public-sector"></a>Contas a pagar: 1099 – há novos recursos que oferecem suporte ao relatório 1099 para o setor público?

Um novo recurso para o setor público, **Atualização de informações 1099 por conta principal**, foi adicionado. Ele pode ser habilitado no espaço de trabalho **Gerenciamento de recursos**. Este recurso permite associar os valores do 1099 de um fornecedor pela conta principal na distribuição contábil, em vez da conta padrão no registro do fornecedor.

Para obter mais informações, consulte [Configurar fornecedores para relatório 1099](../localizations/noam-usa-set-up-vndrs-1099-rprtg.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
