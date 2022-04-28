---
title: Transações de adiamento na Cobrança de assinatura
description: Este tópico descreve as várias transações que podem ser usadas em transações de adiamento como parte de adiamentos de receita e despesas na cobrança de assinatura.
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
ms.openlocfilehash: f66c538afc732caf3faed3cfea6c695ff7f16273
ms.sourcegitcommit: d0e99545d722c924db57ae2bd06f72154a1f1f97
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2022
ms.locfileid: "8558084"
---
# <a name="deferral-default-transactions"></a>Transações padrão de adiamento

Este tópico descreve as transações que permitem adiamentos de receita e de despesa. As agendas de adiamento sempre se baseiam em e dependem de um documento de origem ou de uma agenda de cobrança. As agendas de adiamento são criadas com base nos padrões e não podem ser inseridas ou criadas separadamente.

## <a name="sales-order-transaction-deferral"></a>Adiamento da transação da ordem de venda

Use a página **Adiamentos** ou **Criar nota de crédito** para informar ou editar parâmetros de adiamento para uma linha da ordem de venda.

> [!NOTE]
> Quando uma ordem de venda é criada a partir de uma agenda de cobrança, todos os valores na página **Adiamentos** ou **Criar nota de crédito** são somente leitura e os parâmetros de adiamento não podem ser editados. Para editar os valores, use a página **Modificar agendamento**.

### <a name="edit-deferral-options"></a>Editar opções de adiamento

Para editar as opções de adiamento de uma linha, siga estas etapas.

1. Criar uma transação da ordem de venda.
2. Selecione a linha e, em seguida, selecione **Adiamentos**.
3. Na página **Adiamento da transação**, a opção **Adiada** deve ser definida como **Sim**. Edite outros campos, conforme necessário.
4. Para visualizar a agenda de adiamento, selecione **Visualizar**.
5. Se tiver feito alterações no adiamento da transação, selecione **OK** e retorne à página da transação.
6. Confirme e lance a transação.

Depois que a transação for lançada, abra a página **Todas as agendas de adiamento** para exibir a agenda de adiamento.

### <a name="create-a-credit-note"></a>Crie uma nota de crédito

Para criar uma nota de crédito, siga estas etapas.

1. Criar uma transação da ordem de venda.
2. Na seção **Linhas de ordem de venda**, selecione o item para o qual você deseja criar uma nota de crédito.
3. Selecione **Linha da ordem de venda** \> **Novo** e selecione **Nota de crédito**.
4. Selecione **Adiamentos**.
5. Na página **Adiamento da transação da ordem de venda** defina a opção **Ajustar agenda existente** como **Sim** para o item.
6. No campo **Agenda ajustada**, selecione a agenda de adiamento que você deseja aplicar à nota de crédito.
7. Atualize os campos **Recalcular data** e **Data de término**, conforme necessário.
8. Selecione **OK**.
9. Conclua o lançamento da transação da ordem de venda.

### <a name="purchase-orders-and-purchase-invoices"></a>Ordens de compra e faturas de compra

Se quiser usar a funcionalidade de adiamento para uma ordem de compra, gere a fatura primeiro. Em seguida, use a página **Faturas de fornecedor pendentes** para editar ou adicionar itens de adiamento. Não é possível editar ou adicionar adiamentos diretamente em uma ordem de compra.

1. Use a página **Faturas de fornecedor pendentes** para inserir uma fatura de fornecedor.

    Quando você insere uma linha, o adiamento é definido automaticamente para o item ou para a categoria de compras selecionada. Esse adiamento se baseia na configuração de adiamento na página **Padrões de adiamento**. Os adiamentos podem ser editados ou adicionados no nível de distribuição.

3. Na linha de compra, selecione **Finanças \> Distribuir valores**.
4. Para cada valor de distribuição, selecione **Adiamentos**. Quando a fatura é lançada, uma agenda de adiamento é criada para cada distribuição para a qual um adiamento é definido.

### <a name="tax"></a>Imposto

Em alguns casos, o valor do imposto pode ser total ou parcialmente não recuperável. Se o valor do imposto de uma linha de adiamento contiver um valor não recuperável, o valor do imposto não recuperável será incluído no valor da agenda de adiamento quando a fatura for lançada.

### <a name="variance"></a>Variação

Se o valor na linha da fatura do fornecedor for diferente do valor na linha da ordem de compra, as distribuições de variação serão criadas. Se a linha for adiada, a conta contábil para essas distribuições será definida como a conta de adiamento e os valores serão incluídos no valor da agenda de adiamento quando a fatura for lançada. Essas distribuições são denominadas **Variação de preços** e **Variação de custo**.

### <a name="general-journals-and-invoice-journals"></a>Diários gerais e diários de faturas

Use a página **Adiamentos** para inserir os parâmetros de adiamento para uma linha de comprovante de diário. Você também pode visualizar a agenda de adiamento para adiamentos lineares. Quando você insere uma linha, o adiamento é definido automaticamente com base na configuração das contas de adiamento na página **Padrões de adiamento**. Você pode alterar manualmente as opções de adiamento de cada linha. Quando o comprovante de diário é lançado, a agenda de adiamento é criada.

#### <a name="post-and-transfer"></a>Lançar e Transferir

Para lançar o comprovante de diário, use o comando **Lançar e transferir**. As opções de adiamento seguirão a linha à qual o comprovante se aplica. Para comprovantes que não têm erros, uma agenda de adiamento é criada, se ela for adiada. Para um comprovante que tem um erro e é transferido, as opções de adiamento também são transferidas com ele.

#### <a name="tax"></a>Imposto

Em alguns casos, o valor do imposto pode ser total ou parcialmente não recuperável. Se o valor do imposto de uma linha de adiamento contiver um valor não recuperável, o valor do imposto não recuperável será incluído no valor da agenda de adiamento quando a fatura for lançada.

## <a name="free-text-invoice-transaction-deferral"></a>Fatura de texto livre - adiamento da transação

Use a página **Adiamentos** para inserir os parâmetros de adiamento para uma distribuição de linha de fatura de texto livre. Quando uma distribuição é inserida, o adiamento é definido automaticamente com base nas configurações de adiamento na página **Padrões de adiamento**.

## <a name="fields"></a>Campos

A página **Adiamento da transação** contém os campos a seguir.

| Campo | Descrição |
|-------|-------------|
| Diferido | <p>Especifique se a linha é um adiamento:</p><ul><li>**Sim** – A linha é um adiamento.</li><li>**Não** – A linha não é um adiamento.</li></ul><p>Quando esta opção é definida como **Sim**, a opção **Ajustar agenda existente** não fica disponível. Para itens e encargos já configurados como adiados, esta opção é definida como **Sim**. Para itens e encargos não configurados como adiados por padrão, defina esta opção como **Sim**.</p> |
| Ajustar agenda existente | <p>Especifique se a linha é um ajuste para uma agenda de adiamento existente:</p><ul><li>**Sim** – a nova linha de venda é um ajuste para uma agenda de adiamento existente. Nesse caso, você pode selecionar uma agenda de adiamento no campo **Agenda ajustada**.</li><li>**Não** – a nova linha de venda não é um ajuste para uma agenda de adiamento existente.</li></ul><p>Quando esta opção é definida como **Sim**, a opção **Adiada** não fica disponível.</p> |
| Agenda ajustada | <p>Selecione a agenda de adiamento que a linha está ajustando. Todos os valores na página serão atualizados com os valores da agenda de adiamento original. Esses valores não podem ser editados.</p><p>Este campo fica disponível somente quando a opção **Ajustar agenda existente** for definida como **Sim**.</p> |
| Data de recálculo | <p>Especifique a data de início do período para o qual você deseja recalcular o valor restante. A data padrão é a data do próximo período não reconhecido.</p><p>Este campo fica disponível somente quando a opção **Ajustar agenda existente** for definida como **Sim**.</p> |
| Data final | <p>Dependendo do tipo de adiamento, a data de término pode ou não ser atualizada:</p><ul><li>Para um adiamento linear, especifique a nova data de término da agenda. A data de término existente da agenda de adiamento é o valor padrão.</li><li>Para um adiamento baseado em evento, especifique a data de término da linha do evento de crédito. Esta data pode ficar em branco.</li></ul><p>Este campo fica disponível somente quando a opção **Ajustar agenda existente** for definida como **Sim**.</p> |
| Número de agenda de cobrança | <p>O número da agenda de cobrança.</p><p>Este campo fica disponível somente para agendas de cobrança de contrato recorrente.</p> |
| Método de ajuste de adiamento | <p>O método de ajuste adiado. O valor corresponde ao valor na página **Processamento de encerramento em massa** para a agenda de cobrança de contrato recorrente.</p><p>Este campo fica disponível somente para agendas de cobrança de contrato recorrente.</p> |
| **Contas - receita** | |
| Conta de adiamento | <p>A conta de adiamento, que é a conta de lançamento que aparece na página **Ordem de venda**.</p><p>Se a linha não for adiada, este campo ficará em branco. Nesse caso, a conta de lançamento é a conta de receita padrão.</p> |
| Conta de reconhecimento | <p>Especifique a conta usada quando um adiamento é reconhecido. Essa conta deve ser diferente da conta de adiamento.</p><p>Quando a opção **Adiada** é inicialmente definida como **Sim**, os valores de dimensão usados na conta de adiamento são copiados para a conta de reconhecimento. Se a dimensão na conta de adiamento não existir para a conta de reconhecimento, ela será ignorada.</p> |
| Conta de reconhecimento inicial | <p>Selecione a conta para o reconhecimento de receita inicial. O valor padrão é a partir da página **Padrões de adiamento**.</p><p>Este campo só estará disponível quando o campo **Método de lançamento de adiamento** estiver definido como **Lucros e perdas** na página **Parâmetros de adiamento de receita e despesa**.</p> |
| Contrapartida de reconhecimento | <p>Selecione a conta para o reconhecimento de receita de compensação. O valor padrão é a partir da página **Padrões de adiamento**.</p><p>Este campo só estará disponível quando o campo **Método de lançamento de adiamento** estiver definido como **Lucros e perdas** na página **Parâmetros de adiamento de receita e despesa**.</p> |
| **Contas - Desconto** | Esta seção aparece somente para itens adiados. Ele está oculto para encargos adiados. |
| Conta de adiamento | <p>Especifique o número da conta de adiamento do desconto. O valor padrão é a partir da página **Padrões de adiamento**.</p><p>Este campo está disponível somente quando o campo **Opção de adiamento de desconto** for definido como **Agenda separada para desconto** na página **Parâmetros de adiamentos de receita e despesas** e um desconto é aplicado à linha.</p> |
| Conta de reconhecimento | <p>Especifique o número da conta de reconhecimento do desconto. O valor padrão é a partir da página **Padrões de adiamento**.</p><p>Este campo está disponível somente quando o campo **Opção de adiamento de desconto** for definido como **Agenda separada para desconto** na página **Parâmetros de adiamentos de receita e despesas** e um desconto é aplicado à linha.</p> |
| Conta de reconhecimento inicial | <p>Selecione a conta para o reconhecimento de desconto inicial. O valor padrão é a partir da página **Padrões de adiamento**.</p><p>Este campo está disponível somente quando o campo **Método de lançamento de adiamento** for definido como **Lucro e perda** na página **Parâmetros de adiamentos de receita e despesas** e um desconto for aplicado à linha.</p> |
| Contrapartida de reconhecimento | <p>Selecione a conta para o reconhecimento de receita de compensação. O valor padrão é a partir da página **Padrões de adiamento**.</p><p>Este campo está disponível somente quando o campo **Método de lançamento de adiamento** for definido como **Lucro e perda** na página **Parâmetros de adiamentos de receita e despesas** e um desconto for aplicado à linha.</p> |
| **Contas - Consumo** | Esta seção aparece somente para itens adiados. Ele está oculto para encargos adiados. |
| Conta de adiamento | <p>Especifique o número da conta de adiamento do consumo.</p><p>Para produtos padrão, duas agendas de adiamento são criadas:</p><ul><li>**Vendas padrão** – uma agenda de receita que tem um saldo de crédito. Nesse caso, selecione a conta de adiamento de consumo.</li><li>**Consumo** – uma agenda de despesas de consumo (custo dos produtos vendidos \[COGS\]) que tem um saldo de débito. Nesse caso, selecione a conta de reconhecimento de consumo.</li></ul><p>Quando a fatura é lançada, o valor de consumo é lançado na conta de adiamento de consumo especificada. Esses campos não estão disponíveis para itens de serviço.</p> |
| Conta de reconhecimento | Especifique o número da conta de reconhecimento do consumo. |
| Conta de reconhecimento inicial | <p>Especifique a conta do valor de reconhecimento de consumo inicial. O valor padrão é a partir da página **Padrões de adiamento**.</p><p>Este campo só estará disponível quando o campo **Método de lançamento de adiamento** estiver definido como **Lucros e perdas** na página **Parâmetros de adiamento de receita e despesa**.</p> |
| Contrapartida de reconhecimento | <p>Especifique a conta do valor de compensação de reconhecimento de consumo. O valor padrão é a partir da página **Padrões de adiamento**.</p><p>Este campo só estará disponível quando o campo **Método de lançamento de adiamento** estiver definido como **Lucros e perdas** na página **Parâmetros de adiamento de receita e despesa**.</p> |
| **Agendar** | |
| Tipo de agenda | <p>Selecione o tipo de agenda de adiamento: **Linear** (padrão) ou **Baseada em evento**.</p><p>As opções que aparecem na página se baseiam no tipo de agenda de adiamento selecionado.</p><p>Se o modelo padrão estiver definido na página **Padrões de adiamento** para a linha de transação, o tipo de agenda de adiamento se baseará no tipo de modelo selecionado.</p> |
| **Agenda - Linear** | |
| Consolidar períodos anteriores | <p>Especifique se você deseja consolidar as linhas da agenda de adiamento para períodos anteriores:</p><ul><li>**Sim** – consolide as linhas da agenda de adiamento para períodos anteriores.</li><li>**Não** – não consolide as linhas da agenda de adiamento para períodos anteriores.</li></ul><p>O valor padrão é a partir da página **Parâmetros de adiamentos de receita e despesa**.</p> |
| Igual por período | <p>Especifique se o número de dias em cada período é igual a ou varia de período:</p><ul><li>**Sim** – cada período tem o mesmo número de dias.</li><li>**Não** – os períodos não têm o mesmo número de dias.</li></ul><p>Quando esta opção é definida como **Não**, o número de dias em um período é considerado quando o valor em cada período para uma agenda de adiamento é calculado.</p><p>O valor padrão é a partir da página **Parâmetros de adiamentos de receita e despesa**.</p> |
| Agenda do modelo | <p>Especifique se a agenda de adiamento é criada com base em um modelo ou data de término:</p><ul><li>**Sim** – a agenda de adiamento é criada com base em um modelo.</li><li>**Não** – a agenda de adiamento é criada com base em uma data de término.</li></ul> |
| Modelo | Escolha o modelo de adiamento. |
| Substituir data inicial | <p>Especifique se você deseja substituir a data de início:</p><ul><li>**Sim** – substitui a data de início pela data inserida no campo **Data de início**.</li><li>**Não** – a data inicial é a regra da **Data de início de adiamento padrão** aplicada à data da fatura especificada na página **Lançar fatura**. Esta regra pode ser definida na página **Parâmetros de adiamento de receita e despesa**.</li></ul> |
| Data inicial de adiamento | Especifique a data de início do adiamento. A data da transação é o valor padrão. |
| Data final de adiamento | <p>A data de término do adiamento.</p><p>Essa data é calculada automaticamente com base no modelo de adiamento. Se nenhum modelo for selecionado, você deverá inserir manualmente a data.</p> |
| **Agenda - Baseada no evento** | |
| Modelo | <p>Selecione o modelo baseado no evento. Esse campo é opcional.</p><p>Se você selecionar um modelo, os valores do modelo substituirão todas as linhas de evento e dados baseados em evento.</p> |
| Tipo de alocação | <p>Selecione o tipo de alocação para as linhas de evento:</p><ul><li>**Valores variáveis** – um valor de alocação específico é inserido para cada linha.</li><li>**Valores iguais** – o valor é alocado igualmente para cada linha.</li><li>**Porcentagem** – um valor é alocado com base no valor percentual inserido para cada linha.</li><li>**Porcentagem de conclusão** – um valor de conclusão cumulativo é inserido para cada linha.</li><p>**Quantidade variável** – uma quantidade de alocação específica é inserida para cada linha.</li></ul><p>**Observação:** se você quiser selecionar **Porcentagem de conclusão**, as datas deverão estar em ordem crescente.</p> |
| **Criar eventos separados por unidade** | |
| Descrição | <p>Especifique se deseja separar os eventos por unidade:</p><ul><li>**Sim** – separe as linhas do evento para que haja uma linha por quantidade.<p>Por exemplo, há três linhas de evento e a fatura tem uma quantidade de quatro. Nesse caso, a agenda de adiamento resultante terá 12 linhas.</p></li><li>**Não** – não separe as linhas de evento.</li></ul> |
| Conta de vencimento | <p>Selecione a conta usada para linhas expiradas reconhecidas. Você pode selecionar a conta depois que a agenda de adiamento for criada.</p><p>Se uma data de vencimento for definida para um evento, durante o processo de reconhecimento, o valor do reconhecimento será enviado para a conta de expiração, em vez da conta de reconhecimento.</p> |
| **Agenda - Linhas baseadas no evento** | |
| Descrição | Uma descrição do evento. |
| Data final de adiamento | <p>Selecione a data de término do evento.</p><p>**Observação:** se você selecionar uma data de término, o campo **Data de vencimento** será desmarcado. Você não pode usar uma data de término e uma data de vencimento.</p> |
| Data de vencimento | <p>Selecione a data de vencimento do evento.</p><p>**Observação:** se você selecionar uma data de término, o campo **Data de vencimento** será desmarcado. Você não pode usar uma data de término e uma data de vencimento.</p> |
| Quantidade | <p>Especifique a quantidade de alocação. O valor padrão para todas as linhas é **0** (zero). Se você atualizar a quantidade, a quantidade total de todas as linhas deverá ser igual ou menor do que a quantidade especificada para o item de linha na ordem de venda.</p><p>Este campo está disponível somente quando o campo **Tipo de alocação** estiver definido como **Quantidade variável**.</p><p>Se a quantidade do item de linha na ordem de venda for alterada para que ela seja menor que a quantidade original e a fatura for criada, serão criadas menos linhas baseadas em eventos. A quantidade alocada total não excede a quantidade especificada na ordem de venda original ou na agenda de cobrança.</p> |
| Porcentagem de alocação | <p>Especifique a porcentagem de alocação. Se o campo **Tipo de alocação** for definido como **Porcentagem** ou **Porcentagem de conclusão**, você pode inserir uma porcentagem manualmente. Caso contrário, ela será calculada automaticamente.</p><p>Se o campo **Tipo de alocação** estiver definido como **Porcentagem**, o total das porcentagens deve ser igual a 100.</p> |
| Valor | <p>Especifique o valor da alocação. Se o campo **Tipo de alocação** for definido como **Valores variáveis** ou **Porcentagem de conclusão**, você pode inserir um valor manualmente.</p><p>Se o campo **Tipo de alocação** estiver definido como **Porcentagem de conclusão** e você inserir um valor aqui, o valor do campo **Porcentagem de conclusão** será calculado automaticamente.</p><p>Por causa do arredondamento, o valor calculado pode não corresponder exatamente ao que é inserido manualmente. Se você precisar de um valor exato, defina o campo **Tipo de alocação** como **Valores variáveis**.</p> |
| Porcentagem de conclusão | <p>Especifique o percentual de conclusão. O valor deve ser um inteiro entre 0 (zero) e 100.</p><p>Este campo está disponível somente quando o campo **Tipo de alocação** estiver definido como **Porcentagem de conclusão**.</p> |
| Valor de conclusão | <p>O total calculado para todas as linhas na agenda de adiamento.</p><p>Se o campo **Tipo de alocação** for definido como **Porcentagem de conclusão**, você pode inserir um valor manualmente. Nesse caso, o valor do campo **Porcentagem de conclusão** é calculado com base no valor inserido.</p><p>Por causa do arredondamento, o valor calculado pode não corresponder exatamente ao que é inserido manualmente.</p><p>Este campo está disponível somente quando o campo **Tipo de alocação** estiver definido como **Porcentagem de conclusão**.</p> |
| Reconhecer ao lançar | <p>Especifique se a linha será reconhecida automaticamente assim que a transação for lançada:</p><ul><li>**Selecionada** – a linha será reconhecida automaticamente assim que a transação for lançada.</li><li>**Desmarcada** – a linha não será reconhecida automaticamente assim que a transação for lançada.</li></ul> |
| Conta de reconhecimento | <p>Especifique a conta de reconhecimento para o evento, se a conta for diferente da conta usada para toda a agenda de adiamento.</p><p>Você pode usar este campo junto com a opção **Reconhecer no lançamento**.</p> |
