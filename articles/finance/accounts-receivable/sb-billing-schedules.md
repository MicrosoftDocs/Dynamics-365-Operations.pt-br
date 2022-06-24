---
title: Criar agendas de cobrança
description: Este artigo explica como criar, excluir e editar agendas de cobrança.
author: JodiChristiansen
ms.date: 02/09/2022
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
ms.openlocfilehash: 1248799f92dc6cbce8528a53cc8a3012d2a67b3c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8903382"
---
# <a name="create-billing-schedules"></a>Criar agendas de cobrança

[!include [banner](../includes/banner.md)]

Na página **Agenda de cobrança**, você pode criar, excluir ou editar agendas de cobrança. Você também pode revisar a lista de agendas de cobrança. Quando você cria um agenda de cobrança, os valores padrão para ela são determinados pelo grupo de cobrança associado. As informações adicionais são configuradas na página **Parâmetros de cobrança recorrente de contrato**.

## <a name="create-a-billing-schedule"></a>Criar uma agenda de cobrança

Para criar uma agenda de cobrança, siga estas etapas.

1. Na página **Agenda de cobrança** , selecione **Novo**.
2. Na caixa de diálogo **Criar agenda de cobrança**, no campo **Grupo de agendas de cobrança**, selecione um grupo de agendas de cobrança.
3. No campo **Conta de cliente**, selecione uma conta de cliente.
4. No campo **Data de início**, selecione a data de início e, no campo **Número de períodos**, insira o número de períodos. O campo **Data de término** é atualizado com base no número de períodos inseridos. Se você atualizar o campo **Data de término de cobrança**, o campo **Número de períodos** será atualizado para **0** (zero).
5. Selecione **OK**.
6. Na página **Agenda de cobrança**, na guia **Geral**, no campo **Descrição**, insira uma descrição da agenda de cobrança.
7. No campo **Modelo de etapa**, selecione um modelo de etapa para **Cobrança por etapa**.

Campos como **Conta de fatura** e **Código de moeda** são atualizados com informações do cliente.

Os campos **Frequência de cobrança** e **Intervalo de cobrança** são definidos automaticamente, com base no grupo de agendas de cobrança selecionado.

8. Para criar faturas separadas, defina a opção **Faturar separadamente** como **Sim**.
9. Para renovar automaticamente uma agenda de cobrança após o período de cobrança final, defina a opção **Renovar automaticamente** como **Sim** e, em seguida, defina o campo **Linhas a serem adicionadas por renovação**.

Os campos **Parâmetros** são definidos automaticamente, com base nos valores da página **Parâmetros de cobrança recorrente de contrato**.

10. Para ratear o valor de uma agenda de cobrança, defina a opção **Ratear períodos parciais** como **Sim**.
11. Para alinhar as linhas de detalhes da agenda de cobrança ao final de um mês, defina a opção **Alinhar ao mês** como **Sim**.
12. Nos campos **Data de início do contrato** e **Data de término do contrato**, insira as datas de início e término do contrato. Essas datas são meramente informativas.

O campo **Pagamento** mostra as informações de pagamento do cliente. Quando um item de linha estiver em espera ou for encerrado, as informações de pagamento não poderão ser alteradas.

> [!NOTE]
> Quando você consolida as faturas por item, os campos **Condições de pagamento**, **Método** e **Agenda de pagamento** devem ser correspondentes. Caso contrário, não será possível consolidar as faturas.

13. Na guia **Endereço**, você pode revisar e atualizar os campos **Endereço de entrega** e **Endereço de cobrança**.
14. Na guia **Informações de contato**, você pode associar uma conta de usuário final à agenda de cobrança.
15. Nos campos **Informações de contato**, você pode inserir um contato, um endereço de email e um endereço de Internet.
16. Para rastrear informações sobre comissões do parceiro, defina os campos **Conta do parceiro** e **Taxa de comissão do parceiro**. Esses campos são meramente informativos.
17. Na guia **Total**, você pode visualizar os vários totais que foram calculados para a agenda de cobrança.
18. Na guia **Espera**, você pode visualizar informações de auditoria sobre quando a agenda de cobrança foi mantida em espera e quando a espera foi removida.
19. Na guia **Encerramento**, você pode visualizar um histórico dos encerramentos que foram aplicados ou removidos da agenda de cobrança.
20. Selecione **Salvar**.
21. Na guia rápida **Linhas da agenda de cobrança**, selecione **Adicionar linha**.
22. No campo **Número de item**, selecione o número do item. Se o item adicionado for um item pai em uma divisão de receita, as linhas serão atualizadas automaticamente com os itens filho. Você pode editar somente o item pai em uma divisão de receita. Em seguida, todos os itens filho são atualizados de acordo.
23. No campo **Tipo de item**, selecione o tipo do item.
24. Atualize as datas de início e de término.
25. Antes de criar as faturas, você pode alterar a frequência de cobrança atualizando o campo **Frequência de cobrança**. Depois que a primeira fatura da agenda de cobrança for criada, a frequência de cobrança não poderá ser alterada.
26. No campo **Unidade**, selecione a unidade de medida do item.
27. No campo **Método de precificação**, selecione o método de precificação do item.

O campo **Preço unitário** é automaticamente definido no estoque. No entanto, você poderá atualizá-lo se alterar o método de precificação para **Fixo**.

## <a name="remove-a-line-item"></a>Remover item de linha

Para remover um item de uma agenda de cobrança, siga estas etapas.

1. Na página **Agenda de cobrança**, no campo **Número da agenda de cobrança**, selecione o número da agenda de cobrança a ser editada.
2. Na guia rápida **Linhas da agenda de cobrança**, selecione a linha a ser excluída e, em seguida, selecione **Remover**.
3. Selecione **Salvar**.

O restante deste artigo descreve as ações e os detalhes que estão disponíveis para as linhas na guia rápida **Linhas da agenda de cobrança**.

## <a name="billing-schedule-line-actions"></a>Ações de linhas da agenda de cobrança

Os botões da guia rápida **Linhas da agenda de cobrança** permitem aplicar ações a linhas individuais.

| Botão | Descrição |
|--------|-------------|
| Adicionar linha | Adicione uma linha à agenda de cobrança. |
| Adicionar da lista de itens | Adicione vários itens a uma agenda de cobrança selecionando-os em uma lista. |
| Remover | <p>Remova a linha selecionada da agenda de cobrança.</p><p>Para os itens que fazem parte de uma divisão de receita, você pode remover somente o item pai. Todos os itens filho associados são removidos automaticamente.</p> |
| Exibir detalhe de cobrança | Visualize os detalhes de cobrança. |
| Encerrar | <p>Encerre as linhas selecionadas. Este botão está disponível somente quando as linhas selecionadas têm o status **Ativo**.</p><p>Para os itens que fazem parte de uma divisão de receita, você pode encerrar somente o item pai.</p> |
| Remover finalização | <p>Remova o encerramento das linhas selecionadas. Este botão está disponível somente quando as linhas selecionadas têm o status **Encerrado**.</p><p>Para os itens que fazem parte de uma divisão de receita, você pode remover o encerramento somente do item pai.</p> |
| Colocar em espera | <p>Selecione os detalhes para colocar a linha selecionada em espera.</p><p>Para os itens que fazem parte de uma divisão de receita, você pode colocar somente o item pai em espera.</p> |
| Remover bloqueio | <p>Remova a espera da linha selecionada.</p><p>Para os itens que fazem parte de uma divisão de receita, você pode remover a espera somente do item pai.</p> |
| Escalonamento e desconto | Este botão não está disponível para itens que fazem parte de uma divisão de receita, exceto itens pai em que a divisão de receita usa o método de alocação de **Valor zero**. |
| Adiamentos | <p>Insira opções de diferimento para a linha selecionada.</p><p>Este botão não está disponível para itens pai em uma divisão de receita.</p> |
| Alocação de etapa | <p>Revise e atualize as informações de alocação em etapas para a linha selecionada.</p><p>Este botão está disponível somente quando o item de linha da agenda de cobrança é um item de etapa.</p> |
| Suporte e renovação | <p>Revise e atualize as informações de suporte e renovação para a linha selecionada.</p><p>Este botão está disponível somente quando o item de linha da agenda de cobrança é um item de suporte ou renovação.</p> |
| Exibir dimensões | Mostre ou oculte as colunas de dimensão exibidas na grade **Linhas da agenda de cobrança**. |
| Calcular preço unitário | <p>Calcule o preço unitário do item, para que o cliente possa pagar o valor do contrato em prestações (por exemplo, diariamente, mensalmente, trimestralmente, semestralmente ou anualmente). Você pode selecionar o preço do contrato e a frequência de preço.</p><p>Você pode exibir uma trilha de auditoria das alterações: o preço e a frequência do contrato antigo, a frequência e o preço do novo contrato, o usuário que fez a alteração e a data e a hora da alteração.</p> |
| Data do alinhamento | <p>Especifique a data de alinhamento para itens de renovação.</p><p>Se você selecionar um grupo de itens no campo **Grupo de itens**, todos os itens usarão a data de alinhamento do primeiro item no grupo de itens da agenda de cobrança. Se o campo **Grupo de itens** estiver em branco, você poderá especificar uma data de alinhamento a ser usada para todos os itens.</p><p>Este botão estará disponível somente quando o campo **Frequência da cobrança** estiver definido como **Anual**.</p> |
| Receita não faturada | <p>Defina o item para usar o recurso de receita não faturada. Em seguida, você poderá especificar a receita não faturada e as contas de desconto não faturado para o item.</p><p>Este botão está disponível somente para itens em que o campo **Tipo de item** está definido como **Padrão**. Ele não está disponível para agendas de cobrança existentes ou para linhas da agenda de cobrança em que a fatura já foi criada.</p> |
| Adicionar filho da divisão de receita | <p>Selecione um item filho a ser adicionado à ordem de venda.</p><p>Este botão está disponível somente para itens pai em uma divisão de receita.</p> |
| Opções de preço avançado | Edite as opções de precificação de um item. |

## <a name="billing-schedule-line-details"></a>Detalhes de linhas da agenda de cobrança

Ao selecionar uma linha na guia rápida **Linhas da agenda de cobrança**, você visualiza detalhes específicos dessa linha. Esses detalhes são divididos entre guias diferentes.

### <a name="general-tab"></a>Guia Geral

As informações a seguir estão disponíveis na guia **Geral**:

| Campo ou seção | Descrição |
|------------------|-------------|
| Uso | <p>Esta seção fornece informações sobre itens de uso. Ela contém os seguintes campos:</p><ul><li>**Identificador de uso** – O identificador do item de uso ou uso.</li><li>**Opção de leitura** – A opção de leitura de uso: **Leitura** ou **Consumo**.</li><li>**Consumo previsto** – Especifique o consumo previsto para um item de uso que tenha períodos em que a fatura não foi criada. Na página **Detalhe de cobrança**, você pode revisar as linhas de detalhes de cobrança para o consumo previsto.</li></ul> |
| Referências externas\* | Esta seção contém os campos **Externo** e **Número da linha**, nos quais você pode especificar informações de referência externa. |
| Etapa | <p>Esta seção fornece informações sobre itens de etapa. Ela contém o campo **Data de conclusão prevista**, que mostra a data de conclusão do item.</li></ul> |
| Texto | Um comentário para a linha. O texto é traduzido para o idioma padrão do cliente ou da entidade legal. |
| Grupo de itens | O grupo de itens do item da linha. |
| Data do alinhamento | A data de alinhamento da agenda de cobrança. |

\* Ao consolidar faturas por item na página **Gerar fatura**, os campos **Referência externa** devem ser correspondentes. Se mesmo um caractere for diferente, os itens não serão consolidados na fatura. Nenhuma verificação de validação é feita em um dos campos da seção **Referência externa**, e o valor no campo **Número da linha** deve ser um inteiro positivo.

### <a name="address-tab"></a>Guia Endereço

As informações a seguir estão disponíveis na guia **Endereço**:

| Campo | Descrição |
|-------|-------------|
| Endereço de entrega | <p>Selecione o endereço de entrega do item da linha. O endereço de entrega padrão é o endereço de entrega principal na guia rápida **Endereço**.</p><p>Ao alterar o endereço, você pode selecionar as seguintes opções de endereço:</p><ul><li>**Endereços** – Selecione um endereço para o cliente atual.</li><li>**Em uso** – Selecione um endereço que esteja sendo usado no momento para o cliente atual.</li><li>**Outro endereço** – Selecione um endereço para qualquer registro de cliente.</li></ul><p>Para itens que usam divisão de receita, somente o endereço do item pai pode ser editado. O endereço dos itens filho corresponde ao endereço do pai e não pode ser editado separadamente.</p> |
| Endereço de cobrança | <p>Selecione o endereço de cobrança para o item da linha. O endereço de entrega padrão é o endereço de entrega principal na guia rápida **Endereço**. Você pode alterar o endereço conforme necessário, com base na finalidade dos endereços disponíveis:</p><ul><li>Se nenhum dos endereços tiver uma finalidade de **Fatura**, o endereço de cobrança padrão será o endereço principal do cliente, independentemente da finalidade.</li><li>Se um ou mais endereços tiverem uma finalidade de **Fatura**, o endereço de cobrança padrão será o endereço inserido mais recentemente.</li><li>Se um ou mais endereços tiverem uma finalidade de **Fatura** e um dos endereços da fatura for definido como o endereço principal, o endereço de cobrança padrão será o endereço que tem uma finalidade de **Fatura** e será definido como o endereço principal.</li><li>Para itens que usam divisão de receita, somente o endereço do item pai pode ser editado. O endereço dos itens filho corresponde ao endereço do pai e não pode ser editado separadamente.</li></ul> |

### <a name="product-tab"></a>Guia Produto

As informações a seguir estão disponíveis na guia **Produto**.

| Campo ou seção | Descrição |
|------------------|-------------|
| Dimensões de armazenamento | <p>Esta seção mostra as informações de armazenamento do item. Ela contém o campo **Número de série**, que mostra o número de série do item.</p><p>O número de série é copiado da ordem de venda inicial durante o processo de suporte e renovação. Para itens que usam divisão de receita, o número de série do item pai é copiado para todos os itens filho. O número de série é copiado quando a opção **Copiar número de série** é definida como **Sim** na página cobrança **Parâmetros de cobrança recorrente de contrato**.</li></ul> |
| Dimensões do produto | Os detalhes do produto para o item e os valores são atualizados automaticamente, com base no valor **Número da grade** selecionado para a linha da agenda de cobrança. |

### <a name="account-tab"></a>Guia Conta

As informações a seguir estão disponíveis na guia **Conta**.

| Campo | Descrição |
|-------|-------------|
| Conta principal | A conta principal criada na linha de venda. O valor padrão é da ordem de venda. Este campo pode ficar em branco. |
| Dimensões financeiras do item | <p>Os valores padrão de dimensão financeira, com base no registro de item e cliente.</p><p>Para itens que usam divisão de receita, os itens filho usam os valores de dimensão financeira dos registros de cliente e item, conforme descrito anteriormente. Se for necessário atualizar os valores de dimensão financeira dos itens filho, você poderá importar a entidade de dados.</p> |

### <a name="renewals-tab"></a>Guia Renovações

As informações a seguir estão disponíveis na guia **Renovações**.

| Campo | Descrição |
|-------|-------------|
| Renovar automaticamente | <p>Um valor que indica se a linha da agenda de cobrança é automaticamente renovada para o próximo período de cobrança:</p><ul><li>**Sim** – A linha da agenda de cobrança é automaticamente renovada para o próximo período de cobrança quando você cria uma fatura.</li><li>**Não** – A linha da agenda de cobrança não é automaticamente renovada. Você deve renovar manualmente a agenda de cobrança.</li></ul> |
| Linhas a serem adicionadas por renovação | O número de linhas a serem adicionadas a uma renovação da agenda de cobrança. |

Além disso, os seguintes botões estão disponíveis na guia **Renovações**.

| Botão | Descrição |
|--------|-------------|
| Auditoria de entrada de diário de receita não faturada | Visualize todas as alterações de itens que usam o recurso de receita não faturada. |
| Adicionar condição de renovação | Adicione um termo de renovação do item. A data de início do novo termo de renovação é a próxima data após a data de término do período anterior. Os campos **Data de término da renovação**, **Data de início do diferimento**, **Data de término do diferimento** e **Quantidade do item** e **Preço unitário** podem ser atualizados. |
| Modificar termo de renovação | <p>Modifique um termo de renovação. Para o termo inicial, você pode alterar as datas de início e término do diferimento antes que a entrada de diário inicial seja criada. Para os termos subsequentes, a data de início não pode ser alterada. É sempre a próxima data após o final do termo anterior.</p><p>Se existir um termo de renovação após o termo que você está modificando, as datas do termo não poderão ser alteradas. Nesse caso, somente os campos **Quantidade** e **Preço unitário** do item de renovação podem ser atualizados.</p><p>Por exemplo, existem três termos. <ul><li>O primeiro termo não pode ser alterado porque já foi iniciado.</li><li>No segundo termo, somente a quantidade e o preço unitário podem ser alterados.</li><li>No terceiro termo, todos os valores, exceto a data de início, podem ser alterados. Além disso, a opção **Agendar de modelo** permite criar uma agenda de diferimento baseada no modelo do item de receita não faturada. Quando esta opção é definida como **Sim**, selecione o modelo de diferimento no campo **Modelo** e altere as datas de início e término do diferimento conforme necessário. Os termos de renovação subsequentes usam o mesmo modelo de diferimento. No entanto, o modelo de diferimento pode ser alterado.</p></li></ul> |

### <a name="termination-tab"></a>Guia Encerramento

As informações a seguir estão disponíveis na guia **Encerramento**.

| Campo | Descrição |
|-------|-------------|
| Data da rescisão | A data em que a linha da agenda de cobrança é encerrada. O valor padrão é do campo **Data de encerramento** no cabeçalho. Você pode alterar o valor conforme desejado. |
| Tipo de finalização | O tipo de encerramento. O valor padrão é do campo **Tipo de encerramento** no cabeçalho. |

### <a name="hold-tab"></a>Guia Espera

Se os diferimentos de receita e despesa forem usados, a guia **Espera** mostrará a data do diferimento.

### <a name="escalation-and-discount-tab"></a>Guia Escalonamento e desconto

As informações a seguir estão disponíveis na guia **Escalonamento e desconto**.

| Campo | Descrição |
|-------|-------------|
| Escalonamento | <p>Selecione se os escalonamentos são permitidos para a linha da agenda de cobrança. Qualquer linha de escalonamento do cabeçalho é aplicada quando a linha da agenda de cobrança é criada.</p><ul><li>**Sim** – Os escalonamentos podem ser aplicados à linha. Quando esta opção é selecionada, você pode configurar os escalonamentos para as linhas da agenda de cobrança na página **Escalonamento e desconto**.</li><li>**Não** – Os escalonamentos não podem ser aplicados à linha.</li></ul><p>A configuração padrão é baseada no **Grupo de agendas de cobrança** selecionado.</p> |

### <a name="price-changes-tab"></a>Guia Alterações de preço

Para as linhas que são alteradas do preço **Padrão** para o preço **Fixo**, a grade na guia **Alterações de preço** inclui as seguintes colunas:

- Alterar data
- Alterado pelo usuário
- Preço padrão
- Preço fixo
- Atualização de preço
