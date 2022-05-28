---
title: Adiamentos de receita e despesa em Cobrança de assinatura
description: Este tópico explica como configurar adiamentos de receita e despesa na Cobrança de assinatura.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 9a12cf52d904db0396aa9914b8e324060289710f
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8690938"
---
# <a name="revenue-and-expense-deferrals-in-subscription-billing"></a>Adiamentos de receita e despesa em Cobrança de assinatura

Este tópico explica como configurar e usar adiamentos de receita e despesa na Cobrança de assinatura. As agendas de adiamento sempre se baseiam em e dependem de um documento de origem subjacente ou de uma agenda de cobrança. Como são criadas com base em valores padrão, não podem ser inseridas ou criadas separadamente.

O processo de configuração e uso de adiamentos de receitas e de despesas ocorre em várias páginas:

- Na página **Parâmetros de adiamento de receita e despesa** é possível definir as preferências da empresa.
- Na página **Padrões de adiamento** você pode configurar as contas e os modelos padrão usados para as agendas de adiamento.
- Nas páginas **Modelos de adiamento** e **Modelos de adiamento baseados em evento** você pode definir os modelos usados para as agendas de adiamento.
- Na página **Todas as agendas de adiamento** você pode exibir e editar qualquer agenda de adiamento.

Os adiamentos de receita e de despesas podem ser usados em conjunto com a cobrança de contrato recorrente.

## <a name="revenue-and-expense-deferral-parameters"></a>Parâmetros de adiamento de receita e despesa

A página **Parâmetros de adiamento de receita e despesa** contém os campos a seguir.

| Campo | Descrição |
|---|---| 
| Guia **Agenda** | |
| Igual por período | <p>Especifique se o número de dias em um período é usado quando o valor por período é calculado para uma agenda de adiamento:</p><ul><li>**Sim** – o valor de cada período é o mesmo, independentemente do número de dias do período. Os períodos parciais (como períodos no início ou no final de uma agenda de adiamento) serão rateados.</li><li>**Não** – O valor é calculado com base no número de dias em cada período.</li></ul><p>Você pode substituir esta configuração no nível da transação.</p> |
| Opção de adiamento de desconto de venda | <p>Especifique se as agendas de adiamento separadas são criadas para o desconto e os valores da ordem de venda:</p><ul><li>**Agenda separada para desconto** – o valor do desconto é mantido separado do valor da receita.<p>Nesse caso, duas agendas de adiamento são criadas quando uma ordem de venda é criada e lançada. Os valores de desconto e receita serão lançados em contas de adiamento diferentes.</p></li><li>**Mesclar desconto com receita** – o valor do desconto é combinado com o valor da receita. Uma agenda de adiamento é criada e o valor do desconto e o valor da receita são lançados na mesma conta de adiamento.<p>Nesse caso, uma agenda de adiamento é criada quando uma ordem de venda é criada e lançada. O valor do desconto e o valor da receita são lançados na mesma conta de adiamento.</p></li></ul><p>**Observação:** para aplicar descontos a itens que usam o recurso de receita não cobrada, selecione a opção **Agenda separada para desconto**. Os descontos podem ser aplicados a todos os itens, independentemente do fato de o recurso de receita não cobrada ser usado. Se a opção **Mesclar desconto com receita** estiver selecionada, não será possível aplicar descontos a itens que usam o recurso receita não cobrada.</p> |
| Opção de adiamento de desconto de compra | <p>Selecione se as agendas de adiamento separadas são criadas para o desconto e os valores da ordem de compra:</p><ul><li>**Agenda separada para desconto** – o valor do desconto é mantido separado do valor da despesa.<p>Nesse caso, duas agendas de adiamento são criadas quando uma ordem de compra é criada e lançada. Os valores de desconto e despesa serão lançados em contas de adiamento diferentes.</p></li><li>**Mesclar desconto com receita** – o valor do desconto é combinado com o valor da despesa. Uma agenda de adiamento é criada e o valor do desconto e o valor da despesa são lançados na mesma conta de adiamento.<p>Nesse caso, uma agenda de adiamento é criada quando uma ordem de compra é criada e lançada. O valor do desconto e o valor da despesa são lançados na mesma conta de adiamento.</p></li></ul> |
| Consolidar períodos anteriores | <p>Especifique se as linhas da agenda de adiamento para períodos anteriores serão consolidadas:</p><ul><li>**Sim** – se a data de início do adiamento estiver em um período anterior à data da transação, todos os valores até o período da data da transação serão combinados em uma única linha da agenda de adiamento.</li><li>**Não** – os valores de todos os períodos são mantidos em linhas de agenda de adiamento separadas.<p>Se a data de início do adiamento estiver no mesmo período ou em um período posterior à data da transação, esta opção não terá efeito.</p></li></ul><p>Essa configuração pode ser atualizada em nível de transação.</p> |
| Data inicial de adiamento padrão | <p>Selecione a regra usada para determinar a data de início da agenda de adiamento:</p><ul><li>**Data da transação** – use a data da transação como a data de início.</li><li>**Início do mês atual** – use o primeiro mês atual como a data de início. Se a data da transação for a primeira de qualquer mês, o primeiro mês atual será a data de início.</li><li>**Início do próximo mês** – use o próximo mês como a data de início. Se a data da transação estiver na primeira, a data da transação será usada. Caso contrário, será usado o primeiro mês seguinte.</li><li>**Regra de 15** – se a data da transação estiver entre o primeiro e o décimo quinto dia, use o primeiro mês atual como a data de início. Se a data da transação for o décimo sexto ou posterior, use o primeiro do mês seguinte como data de início.</li></ul><p>Você pode atualizar essa configuração no nível da transação.</p> |
| Método de adiamento de curto prazo | <p>Selecione o método de adiamento de curto prazo: **Nenhum**, **Períodos anteriores** ou **Ano fixo**.</p><p>|
| Método de lançamento de adiamento | <p>Selecione o método usado para criar transações de adiamento:</p><ul><li>**Balanço** – use o método de lançamento de balanço para criar transações de adiamento.</li><li>**Lucros e perdas**: Use o método de lançamento de lucros e perdas para criar transações de adiamento. Quando as transações são lançadas, você pode revisar o comprovante de fatura para ver as entradas extras que equilibram os valores iniciais de compensação e de reconhecimento.</li></ul> |
| Reverter lucros e perdas em crédito | <p>**Observação:** este campo fica disponível somente quando o campo **Método de lançamento de adiamento** for definido como **Lucros e perdas**.</p><p>Especifique se os valores de lucros e perdas são revertidos quando um estorno, um encerramento ou um reembolso são aplicados a uma agenda de cobrança ou a uma ordem de venda:</p><ul><li>**Sim** – reverte os valores de lucros e perdas e aplica um valor de ajuste de crédito à agenda de adiamento.<p>Se a reversão ocorrer em metade do período de cobrança, os valores serão rateados.</p></li><li>**Não** – nenhuma transação de reversão é criada quando um estorno, um encerramento ou um reembolso são aplicados a uma agenda de cobrança ou a uma ordem de venda:</li></ul> |
| Guia **Reconhecimento** | |
| Lançar diários gerais automaticamente | <p>Especifique se as entradas de diário criadas por adiamentos de receita e despesas são lançadas automaticamente:</p><ul><li>**Sim** – lançar automaticamente lançamentos contábeis criados por adiamentos de receitas e despesas.<p>**Dica:** ao selecionar **Sim**, você pode ajudar a evitar inconsistências contábeis causadas por alterações manuais nos comprovantes.</p></li><li>**Não** – lançamentos contábeis criados por adiamentos de receitas e despesas não são lançados automaticamente. Você deve lançar quaisquer diários manualmente.</li></ul> |
| Resumir diário de reconhecimento | <p>Especifique se os comprovantes de reconhecimento são consolidados por padrão:</p><ul><li>**Sim** – cria um único comprovante para todas as linhas de reconhecimento que têm a mesma data. Todas as linhas de um comprovante que têm a mesma conta são consolidadas em uma única linha.</li><li>**Não** – crie um comprovante para cada linha de reconhecimento.</li></ul><p>Você pode atualizar essa configuração na página **Processamento de reconhecimento**.</p> |
| Nome padrão do diário | Selecione o nome do diário para diários que são criados a partir de processos de adiamento de despesas e receitas, como o processamento de reconhecimento. |
| Descrição de linha do diário de reconhecimento | <p>Selecione a descrição que aparece na descrição da linha de comprovante de diário:</p><ul><li>**Agendar datas de linha** – mostra as datas da linha da agenda na descrição da linha do diário.</li><li>**Detalhes da transação de origem** – mostra as informações da transação de origem na descrição da linha do diário.<p>**Exemplo:** USMF-0001, CIV-00839, receita de software</p></li></ul> |
| Guia **Sequências de número** | Use esta guia para definir os valores padrão para sequências numéricas de leasing. O assistente de geração de sequência numérica é usado para gerar e atribuir sequências numéricas automaticamente. Não é necessário alterar a sequência numérica a menos que você queira fazer alterações manuais nas sequências numéricas geradas. |
| Número da agenda | O número que é a sequência usada para agendas de adiamento. |

## <a name="deferral-templates"></a>Modelos de adiamento

Use a página **Modelos de adiamento** para definir modelos lineares usados para agendas de adiamento.

Estas são algumas das vantagens de usar um modelo:

* O tamanho do adiamento é calculado automaticamente.
* Você permite agendas de adiamento que têm períodos em que o reconhecimento é ignorado.
* Você pode automatizar as adiamentos atribuindo o modelo a um produto, a um grupo de produtos, a uma categoria de produto, a clientes ou a um grupo de clientes. A atribuição do modelo é feita na página **Padrões de adiamento**.

Várias frequências de período estão disponíveis para modelos: diário, mensal ou fiscal.

As linhas de modelo consistem em um tipo (**Reconhecido** ou **Ignorado**) e no período. As linhas ignoradas têm um valor de 0 (zero) nas linhas da agenda de adiamento. Esse comportamento pode ser útil se você não deseja reconhecer a receita em todos os períodos.

### <a name="create-a-deferral-template"></a>Criar um modelo de adiamento

Para criar um modelo de adiamento, siga estas etapas.

1. Na página **Modelos de adiamento**, selecione **Novo**.
2. No campo **Modelo**, digite um nome.
3. No campo **Descrição**, insira uma descrição.
4. No campo **Frequência do Período**, selecione a frequência do período.
5. Selecione **Adicionar** para adicionar uma linha à parte superior da lista de linhas ou selecione **Acrescentar** para adicionar uma linha à parte inferior da lista.
6. No campo **Tipo**, selecione o tipo de período.
7. No campo **Duração do período**, especifique a duração do período.
8. Repita as etapas 5 a 7 para cada linha adicionar que você precisar.
9. Selecione **Salvar**.

## <a name="deferral-defaults"></a>Padrões de adiamento

Use a página **Padrões de adiamento** para configurar contas de adiamento padrão para itens e para atribuir modelos padrão a itens que não puderem ser referenciados. Você também pode configurar contas de adiamento para encargos e atribuir modelos aos encargos que podem ser adiados.

**Adiar por item**

Para transações que têm um item (por exemplo, ordens de venda), você pode atribuir contas e modelos a itens e clientes específicos. Essas configurações serão usadas como valores padrão quando uma transação for adiada. Para tornar a transação que pode ser adiada por padrão, você deve configurar os itens na página **Itens de adiamento**.

**Adiar por conta**

Para transações que não têm itens (por exemplo, diários gerais), você pode especificar as contas de adiamento. Quando essas contas são usadas em uma linha de transação, a transação é marcada automaticamente como adiada. O modelo e a conta de reconhecimento correspondentes serão atribuídos à linha de transação.

**Todos os tipos de transação (por exemplo, nas guias Ordem de Venda, Compras e Diário Geral)**

As contas na página são as contas principais que não têm dimensões financeiras. As dimensões financeiras da conta de reconhecimento são do cliente ou do item, com base na sua organização.

Cada linha de modelo deve ter um modelo linear ou um modelo baseado em evento. Ele não pode ter ambos.

### <a name="for-sales-orders"></a>Para ordens de venda

Para especificar os valores padrão de adiamento para ordens de venda, siga estas etapas.

1. Na guia **Ordem de venda**, selecione o tipo de adiamento.
2. Selecione **Adicionar** para adicionar uma linha.
3. No campo **Código do item**, selecione o código do item. O código do item determina como os valores padrão de adiamento são aplicados.
4. Especifique como o código do item é aplicado:

    * Se o campo **Código do item** for definido como **Tabela** ou **Grupo**, selecione a relação do item no campo **Relação do item**.
    * Se o campo **Código do item** for definido como **Categoria**, selecione a relação da categoria na **Relação da categoria**.
    * Se o campo **Código do item** for definido como **Todos**, os valores padrão serão aplicados a todos os registros aplicáveis.

5. Especifique como o código da conta é aplicado:

    * Se o campo **Código da conta** for definido como **Tabela** ou **Grupo**, selecione a relação da conta no campo **Relação da conta**.
    * Se o campo **Código da conta** for definido como **Todos**, a conta será aplicada a todos os registros.

6. No campo **Conta principal**, selecione a conta principal do adiamento.
7. Se o campo **Método de lançamento de adiamento** for definido como **Lucros e perdas**, selecione a conta de receita inicial no campo **Conta de receita inicial** e a contrapartida da receita no campo **Contrapartida de receita**.
8. Se o campo **Método de adiamento de curto prazo** for definido como **Períodos anteriores** ou **Ano fixo**, selecione a conta de adiamento de curto prazo no campo **Conta de adiamento de curto prazo**.
9. Para um modelo, você pode selecionar **Adicionar** para adicionar uma linha.
10. No campo **Código do item**, selecione o código do item.
11. Especifique como o código do item é aplicado:

    * Se o campo **Código do item** for definido como **Tabela** ou **Grupo**, selecione a relação do item no campo **Relação do item**.
    * Se o campo **Código do item** for definido como **Categoria**, selecione a relação da categoria no campo **Relação da categoria**.
    * Se o campo **Código do item** for definido como **Todos**, os valores padrão serão aplicados a todos os registros aplicáveis.

12. Especifique como o código da conta é aplicado:

    * Se o campo **Código da conta** for definido como **Tabela** ou **Grupo**, selecione a relação da conta no campo **Relação da conta**.
    * Se o campo **Código da conta** for definido como **Todos**, a conta será aplicada a todos os registros aplicáveis.
    * Selecione o modelo linear no campo **Modelo linear** ou no modelo baseado em evento, no campo **Modelo baseado em evento**.

13. Selecione **Salvar**.

### <a name="for-purchase-orders"></a>Para ordens de compra

Para especificar os valores padrão de adiamento para ordens de compra, siga estas etapas.

1. Na guia **Compras**, selecione o tipo de adiamento.
2. Selecione **Adicionar** para adicionar uma linha.
3. No campo **Código do item**, selecione o código do item.
4. Especifique como o código do item é aplicado:

    * Se o campo **Código do item** for definido como **Tabela** ou **Grupo**, selecione a relação do item no campo **Relação do item**.
    * Se o campo **Código do item** for definido como **Categoria**, selecione a relação da categoria no campo **Relação da categoria**.
    * Se o campo **Código do item** for definido como **Todos**, os valores padrão serão aplicados a todos os registros aplicáveis.

5. Especifique como o código da conta é aplicado:

    * Se o campo **Código da conta** for definido como **Tabela** ou **Grupo**, selecione a relação da conta no campo **Relação da conta**.
    * Se o campo **Código da conta** for definido como **Todos**, a conta será aplicada a todos os registros aplicáveis.

6. No campo **Conta principal**, selecione a conta principal do adiamento.
7. Se o campo **Método de lançamento de adiamento** for definido como **Lucros e perdas**, selecione a conta de receita inicial no campo **Conta de receita inicial** e a contrapartida da receita no campo **Contrapartida de receita**.
8. Se o campo **Método de adiamento de curto prazo** for definido como **Períodos anteriores** ou **Ano fixo**, selecione a conta de adiamento de curto prazo no campo **Conta de adiamento de curto prazo**.
9. Para um modelo, selecione **Adicionar** para adicionar uma linha. 
10. No campo **Código do item**, selecione o código do item.
11. Especifique como o código do item é aplicado:

    * Se o campo **Código do item** for definido como **Tabela** ou **Grupo**, selecione a relação do item no campo **Relação do item**.
    * Se o campo **Código do item** for definido como **Categoria**, selecione a relação da categoria no campo **Relação da categoria**.
    * Se o campo **Código do item** for definido como **Todos**, os valores padrão serão aplicados a todos os registros aplicáveis.

12. Especifique como o código da conta é aplicado:

    * Se o campo **Código da conta** for definido como **Tabela** ou **Grupo**, selecione a relação da conta no campo **Relação da conta**.
    * Se o campo **Código da conta** for definido como **Todos**, a conta será aplicada a todos os registros aplicáveis.
    * Selecione o modelo linear no campo **Modelo linear** ou no modelo baseado em evento, no campo **Modelo baseado em evento**.

13. Selecione **Salvar**.

### <a name="for-general-journals"></a>Para Diários gerais

Para especificar os valores padrão de adiamento para entradas de diário gerais, siga estas etapas.

1. Selecione a guia **Diário geral**.
2. Para um adiamento, selecione **Adicionar** para adicionar uma linha.
3. Se o campo **Método de adiamento de curto prazo** for definido como **Períodos anteriores** ou **Ano fixo**, selecione a conta de adiamento de curto prazo no campo **Conta de adiamento de curto prazo**.
4. No campo **Conta de adiamento**, selecione a conta de adiamento.
5. No campo **Conta de reconhecimento**, selecione a conta de reconhecimento.
6. Se o campo **Método de lançamento de adiamento** for definido como **Lucros e perdas**, selecione a conta de receita inicial no campo **Conta de receita inicial** e a contrapartida da receita no campo **Contrapartida de receita**.
7. Selecione o modelo linear no campo **Modelo linear** ou no modelo baseado em evento, no campo **Modelo baseado em evento**.
8. Selecione **Salvar**.

### <a name="for-free-text-invoices"></a>Para faturas de texto livre

Para especificar os valores padrão de adiamento para faturas de texto livre, siga estas etapas.

1. Selecione a guia **Fatura de texto livre**.
2. Para um adiamento, selecione **Adicionar** para adicionar uma linha.
3. Especifique como o código da conta é aplicado:

    * Se o campo **Código da conta** for definido como **Tabela** ou **Grupo**, selecione a relação da conta no campo **Relação da conta**.
    * Se o campo **Código da conta** for definido como **Todos**, o código da conta será aplicado a todos os registros aplicáveis.

4. No campo **Conta de adiamento**, selecione a conta de adiamento.
5. Se o campo **Método de adiamento de curto prazo** for definido como **Períodos anteriores** ou **Ano fixo**, selecione a conta de adiamento de curto prazo no campo **Conta de adiamento de curto prazo**.
6. No campo **Conta de reconhecimento**, selecione a conta de reconhecimento.
7. Se o campo **Método de lançamento de adiamento** for definido como **Lucros e perdas**, selecione a conta de receita inicial no campo **Conta de receita inicial** e a contrapartida da receita no campo **Contrapartida de receita**.
8. Selecione o modelo linear no campo **Modelo linear** ou no modelo baseado em evento, no campo **Modelo baseado em evento**.
9. Selecione **Salvar**.

### <a name="for-invoice-journals"></a>Para diários de faturas

Para especificar os valores padrão de adiamento para entradas de diário gerais de faturas, siga estas etapas.

1. Selecione a guia **Diário de faturas**.
2. Para um adiamento, selecione **Adicionar** para adicionar uma linha.
3. Especifique como o código da conta é aplicado:

    * Se o campo **Código da conta** for definido como **Tabela** ou **Grupo**, selecione a relação da conta no campo **Relação da conta**.
    * Se o campo **Código da conta** for definido como **Todos**, o código da conta será aplicado a todos os registros aplicáveis.

4. No campo **Conta de adiamento**, selecione a conta de adiamento.
5. Se o campo **Método de adiamento de curto prazo** for definido como **Períodos anteriores** ou **Ano fixo**, selecione a conta de adiamento de curto prazo no campo **Conta de adiamento de curto prazo**.
6. No campo **Conta de reconhecimento**, selecione a conta de reconhecimento.
7. Se o campo **Método de lançamento de adiamento** for definido como **Lucros e perdas**, selecione a conta de receita inicial no campo **Conta de receita inicial** e a contrapartida da receita no campo **Contrapartida de receita**.
8. Selecione o modelo linear no campo **Modelo linear** ou no modelo baseado em evento, no campo **Modelo baseado em evento**.
9. Selecione **Salvar**.

### <a name="items-that-are-deferred-by-default"></a>Itens que são adiados por padrão

Use a página **itens adiados por padrão** para definir quais itens são adiados por padrão. Você pode configurar os tipos de transações para as quais os itens serão adiados. Você pode especificar se um único item será adiado ou um grupo de itens ou uma categoria inteira.

Ao configurar itens como adiados, selecione as contas e os modelos padrão na página **Padrões de adiamento**. Se as contas e os modelos não estiverem selecionados, as linhas de transação nas quais esses itens são inseridos não serão adiadas.

Para os itens adiados com base na categoria de venda ou compra a que estão associados, as configurações de adiamento se baseiam na categoria. No entanto, se a categoria não estiver selecionada no campo **Relação de categoria**, serão usadas as configurações de adiamento da categoria mais alta em classificação. Por exemplo, você adiciona uma categoria de vendas de **Vídeo residencial**, mas não uma categoria de vendas de **Televisão**. Quando você adiciona um item de adiamento associado à categoria **Televisão**, as configurações de adiamento do **Vídeo residencial** são usadas para o item.

### <a name="set-up-deferred-items"></a>Configurar itens adiados

Para configurar itens adiados por padrão, siga estas etapas.

1. Na página **Itens adiados por padrão**, selecione a guia que deseja: **Ordem de venda** ou **Compras**.
2. Selecione **Adicionar** para adicionar uma linha.
3. No campo **Código do item**, selecione o código do item.
4. Especifique como o código do item é aplicado:

    * Se o campo **Código do item** for definido como **Grupo** ou **Tabela**, selecione a relação do item no campo **Relação do item**.
    * Se o campo **Código do item** for definido como **Categoria**, selecione a relação da categoria no campo **Relação da categoria**.

5. Repita as etapas 2 a 4 para cada linha adicionar que você precisar.
6. Selecione **Salvar**.

## <a name="deferred-charges"></a>Encargos adiados

Use a página **Encargos de adiamento** para definir quais encargos são adiados por padrão.

> [!NOTE]
> * No momento, os encargos de adiamento estão disponíveis somente para ordens de venda.
> * Os encargos podem ser adiados somente em nível de linha. Para adiar um encargo no nível do cabeçalho da ordem de venda, você pode configurar o encargo como um item adiado em uma linha separada na ordem de venda.
> * Para adiar um encargo para uma fatura de texto livre, você deve inserir o encargo como uma linha de fatura adiada separada.
> * Essa funcionalidade não está disponível para encargos de suporte e a funcionalidade de divisão de receita.

### <a name="set-up-deferred-charges"></a>Configurar encargos adiados

Para configurar encargos adiados, siga estas etapas.

1. Na página **Encargos de adiamento**, selecione **Adicionar** para adicionar uma linha.
2. No campo **Código de encargo**, selecione o código de encargo.
3. No campo **Relação de encargo**, selecione a relação de encargo.
4. Repita as etapas 1 a 3 para cada linha adicionar que você precisar.
5. Selecione **Salvar**.

## <a name="event-based-deferral-templates"></a>Modelos de adiamento baseado em evento

Use a página **Modelos de adiamento com base em eventos** para definir modelos de adiamento com base em eventos que você pode usar em transações de adiamento e atribuir na página **Padrões de adiamento**.

### <a name="create-an-event-based-template"></a>Criar um modelo com base em eventos

Para criar um modelo de adiamento com base em eventos, siga estas etapas.

1. Na página **Modelos de adiamento com base em evento**, selecione **Novo**.
2. No campo **Modelo** digite um nome exclusivo para o grupo de modelos.
3. No campo **Descrição**, insira uma descrição.
4. No campo **Tipo de alocação**, selecione o tipo de alocação:

    * **Valor variável** – aloque um valor específico a cada linha inserida.
    * **Valor igual** – aloque o mesmo valor para cada linha inserida. 
    * **Porcentagem** – aloque um valor com base no valor percentual inserido para cada linha.
    * **Porcentagem de conclusão** – aloque um valor de conclusão cumulativo para cada linha inserida.
    * **Quantidade variável** – aloque uma quantidade específica para cada linha inserida.

5. Defina a opção **Criar eventos separados por unidade** como **Sim**, se quiser que cada linha de evento seja dividida igualmente pelo número de unidades na transação da fatura. Defina como **Não**, se não quiser dividir as linhas do evento.
6. No campo **Conta de expiração**, selecione a conta de expiração.
7. Selecione **Adicionar** para adicionar uma linha à parte superior da lista de linhas ou selecione **Acrescentar** para adicionar uma linha à parte inferior da lista.
8. No campo **Descrição**, insira uma descrição do evento.
9. Se o campo **Tipo de alocação** for definido como **Porcentagem**, especifique a porcentagem de alocação no campo **Porcentagem de alocação**. A porcentagem ser um inteiro entre 0 (zero) e 100. Se você deixar o campo **Porcentagem de alocação** em branco, a porcentagem será considerada 0. A soma de todas as porcentagens é mostrada no campo **Porcentagem total** na parte inferior da página e deverá ser igual a 100.
10. No campo **Meses para expiração** especifique o número de meses no qual o evento é válido. A data de vencimento no adiamento da transação é inserida automaticamente com base nesse valor.
11. Marque a caixa de seleção **Reconhecer quando lançado** para reconhecer automaticamente a receita quando a transação for lançada. Se você deixar a caixa de seleção desmarcada, a receita deverá ser reconhecida manualmente.
12. No campo **Conta de reconhecimento**, selecione a conta de reconhecimento para o evento, se o evento usar uma conta diferente do que todo a agenda de adiamento. Este campo é usado juntamente com a caixa de seleção **Reconhecer quando lançado**.
13. Repita as etapas 7 a 12 para cada linha adicionar que você precisar.
14. Selecione **Salvar**.
