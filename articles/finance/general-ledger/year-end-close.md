---
title: Fechamento do exercício
description: Este artigo descreve a configuração e as etapas necessárias para executar o processo de fechamento do exercício da contabilidade.
author: kweekley
ms.date: 11/06/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerClosingSheet
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7e1c7722b560246fb597f0b7f91a70afecf69e22
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779734"
---
# <a name="year-end-close"></a>Fechamento do exercício

[!include [banner](../includes/banner.md)]

Este artigo descreve a configuração e as etapas necessárias para executar o processo de fechamento do exercício da contabilidade.

Ao final de um ano fiscal, é necessário executar o processo de fechamento anual para transferir saldos de abertura para o próximo ano. A maioria das organizações executarão o processo de fechamento anual diversas vezes. A primeira execução move os saldos para o novo ano fiscal. O processo pode então ser executado novamente, quantas vezes forem necessárias, para mover os saldos de entradas de ajuste para o novo ano fiscal.

Durante o processo de fechamento do exercício, existem dois tipos de transações possíveis criadas. Uma transação de Abertura sempre é gerada e é usada para criar os saldos iniciais do novo ano fiscal. A transação de Abertura mostra os saldos da conta contábil de balanço no novo ano fiscal e saldos dos balanços de conta contábil de lucros e perdas na conta contábil de rendimentos retidos no novo ano fiscal. A transação de Fechamento é criada opcionalmente para trazer os saldos das contas de lucros e perdas para zero quando o ano fiscal estiver sendo fechado.

## <a name="prepare-to-run-the-year-end-close"></a>Preparação para executar o fechamento anual

Antes de executar o processo de fechamento anual, confirme as configurações para:

Na página **Conta principal**:

- Verifique se o campo **Tipo de conta principal** está definido corretamente para cada conta principal. O tipo de conta principal determina se o saldo da conta principal será levado a diante como um saldo inicial ou fechado nos rendimentos retidos na transação de abertura.
- O saldo da conta principal pode ser transferido para uma nova conta principal durante o fechamento do exercício. Insira a nova conta principal no campo **Conta de abertura**. Normalmente, esse campo é usado para contas principais de balanço quando a conta principal está inativada e uma nova conta principal é usada para o novo ano fiscal.

Na página **Parâmetros da contabilidade** em **Fechamento do ano fiscal**:

- A opção **Excluir entradas de fechamento do exercício existentes ao fechar novamente o ano** é usada para especificar se a transação de abertura de um fechamento do exercício anterior gerada pelo sistema deve ser excluída quando o fechamento do exercício for executado novamente. Se essa opção estiver definida como **Sim**, as transações de abertura e as transações de fechamento opcionais anteriores serão excluídas e uma nova transação de abertura ou de fechamento será criada com base nos saldos atuais. Se essa opção estiver definida como **Não**, as transações de abertura e as transações de fechamento opcionais anteriores serão mantidas e uma nova transação de abertura ou de fechamento será criada para migrar os saldos das transações de ajuste que foram lançadas após o fechamento do exercício anterior.
- A opção **Criar transações de fechamento durante a transferência** é usada para criar transações de fechamento no ano fiscal que está sendo fechado para zerar os saldos de todas as contas principais. Se essa opção estiver definida como **Sim**, ambas as transações de abertura e fechamento serão criadas. Se essa opção estiver definida como **Não**, somente a transação de abertura será criada no próximo ano fiscal para transferir os saldos. Os saldos das contas principais continuam no final do ano fiscal.
- A opção **Mudar o status do ano fiscal para permanentemente fechado** é usada para mudar o ano fiscal para o status de permanentemente fechado. Use essa opção com cuidado, pois os períodos que tiverem um status de permanentemente fechados não poderão ser reabertos. Portanto, os ajustes não poderão ser lançados no ano fiscal. Como uma prática recomendada, essa opção deve ser definida como **Não**.
- A opção **O número do comprovante deve ser preenchido** foi removida. Um comprovante agora é necessário quando o processo de fechamento do exercício é executado. Nesse momento, o número do comprovante é inserido manualmente.

Na página **Calendário fiscal**:

- O próximo ano fiscal deve existir antes que o fechamento do exercício seja executado. Caso contrário, os saldos iniciais não poderão ser criados no período de abertura.

Na página **Calendário contábil**:

- Opcional: cada período fiscal do ano fiscal que está sendo fechado pode ser definido como **Em espera** para impedir que novas transações sejam inseridas. Quando as entradas de ajuste são identificadas, os períodos em espera podem ser reabertos para que as entradas de ajuste possam ser lançadas, mesmo que o processo de fechamento do exercício já tenha sido executado.

Na página **Configuração do modelo de fechamento do exercício**:

- Quando o recurso **Aprimoramentos do fechamento de exercício da contabilidade** está ativado, o processo de configuração do modelo de fechamento do exercício é separado do processo de execução do fechamento do exercício. O modelo pode ser definido na página **Configuração do modelo de fechamento do exercício** (**Contabilidade \> Configuração do razão \> Configuração do modelo de fechamento do exercício**), ou pode ser acessado a partir do processo de fechamento do exercício.

## <a name="define-year-end-close-templates"></a>Definir modelos de fechamento do exercício

Após a conclusão da configuração, o processo de fechamento anual pode ser executado. Na página **Configuração do modelo de fechamento do exercício**, é possível definir um modelo para o grupo de entidades legais para o qual o processo de fechamento do exercício será executado. O modelo será reutilizado a cada fechamento do exercício, mas poderá ser modificado caso ocorra alterações na organização.

Primeiramente, defina o campo **Nome do grupo** para o modelo e selecione o calendário fiscal. O nome do grupo deve identificar o grupo de entidades legais que estão incluídas. Ao determinar os grupos de entidades legais, lembre-se de que as entidades legais poderão ser incluídas no mesmo grupo somente se o mesmo calendário fiscal estiver selecionado para elas. Por exemplo, os modelos podem ser configurados com base na geografia, e grupos separados podem ser criados para entidades legais norte-americanas, entidades legais da EMEA (Europa , Oriente Médio e África) e entidades legais da APAC (Pacífico Asiático).

Em seguida, as entidades legais podem ser adicionadas ao modelo. As entidades legais podem ser adicionadas selecionando uma hierarquia da organização ou selecionando as entidades legais. Se uma hierarquia da organização é selecionada, apenas as entidades legais que utilizam o calendário fiscal selecionado dentro da hierarquia serão adicionadas ao modelo. Se você usar entidades legais para adicionar ao modelo, apenas as entidades legais com o mesmo calendário fiscal podem ser adicionadas. O mesmo calendário fiscal é necessário porque o fechamento do exercício é executado através da seleção de um ano fiscal, o que pode variar de calendário para calendário.

Depois que as entidades legais são adicionadas, defina as contas principais de rendimentos retidos para cada entidade legal.

A guia **Dimensão financeira** é usada para definir quais dimensões financeiras serão usadas na transação de abertura. Observe que as configurações nessa guia são aplicáveis somente à entidade legal selecionada na grade **Entidades legais**. Você deve repetir a configuração para cada entidade legal na grade.

A opção **Transferir dimensões de balanço** é usada para especificar se as dimensões financeiras nas transações que são lançadas nas contas de balanço devem ser mantidas na transação de abertura. Como uma prática recomendada, essa opção deve ser definida como **Sim**. A configuração das dimensões de balanço não afeta os saldos existentes nas contas contábeis de lucros retidos. Esses saldos são determinados pelas dimensões de lucros e perdas definidas na próxima seção. Por exemplo, o ano fiscal 2019 foi o primeiro ano que foi fechado e a opção **Fechar tudo** foi usada para selecionar as dimensões **Departamento** e **Centro de custo** para fechamento. Nesse caso, uma conta de lucros retidos separada foi criada para cada combinação de departamento e centro de custo. Quando o fechamento do exercício for executado no ano fiscal 2020, os lucros retidos do ano anterior permanecerão exatamente como foram lançados, mesmo que a opção **Transferir dimensões de balanço** esteja definida como **Não**. Os saldos lançados em lucros retidos de fechamentos de exercício anteriores nunca são alterados.

A seção **Transferir dimensões de lucros e perdas** é usada para especificar quais dimensões financeiras em transações lançadas nas contas de lucros e perdas serão transferidas para a conta principal de rendimentos retidos. Primeiramente, identifique as dimensões financeiras que são relevantes para a entidade legal selecionada. Essas dimensões financeiras incluem qualquer dimensão financeira que foi lançada durante o ano, mesmo que a dimensão financeira não faça parte de uma estrutura de conta ativa. Em seguida, defina cada dimensão como **Fechar individual** ou **Fechar todas**. A opção padrão é **Fechar tudo**. Essa opção mantém os valores originais da dimensão financeira de transações lançadas e as utiliza para criar os saldos iniciais para a conta de rendimentos retidos. Saldos iniciais de rendimentos retidos separados serão criados para cada combinação única de valores da dimensão financeira. Se a opção **Fechar individual** for selecionada, todas as transações lançadas que tiverem essa dimensão financeira serão resumidas em um saldo inicial de rendimentos retidos para o valor da dimensão que for inserido no campo que aparecer após **Fechar individual**. Por exemplo, todas as transações do ano fiscal foram lançadas com a estrutura de conta **Conta principal – Departamento**. Na dimensão financeira do **Departamento** no modelo, a opção **Fechar individual** é selecionada e **100** é o valor inserido. Se a receita total de todas as transações que foram lançadas nos departamentos 200, 300 e 400 for $100.000, um saldo inicial será criado para **Rendimentos retidos – 100**. Se você selecionar **Fechar individual**, mas deixar o valor da dimensão financeira em branco, todas as transações serão lançadas em rendimentos retidos, e o valor da dimensão ficará em branco.

## <a name="run-the-year-end-close-process"></a>Executar o processo de fechamento do exercício

Depois que os modelos de fechamento do exercício forem criados, você poderá iniciar o processo de fechamento do exercício na página **Fechamento do exercício** (**Contabilidade \> Fechamento do período \> Fechamento do exercício**). Antes de executar o fechamento do exercício, você pode adicionar novos modelos de fechamento de exercício ou modificar modelos existentes selecionando **Configuração do modelo de fechamento do exercício** para abrir a página de configuração dos modelos.

Selecione o modelo de fechamento do exercício e, no Painel de Ações, selecione **Executar fechamento do exercício**. Selecione todas as entidades legais ou um subconjunto de entidades legais no modelo para o qual você estiver executando o fechamento do exercício. Se estiver executando o fechamento do exercício pela primeira vez em um ano fiscal, você provavelmente selecionará todas as entidades legais para criar saldos iniciais para todas elas. Se tiver executado o fechamento do exercício anteriormente, talvez você queira executar o processo novamente somente para as entidades legais para as quais entradas de ajuste foram lançadas.

Em seguida, selecione o ano fiscal para executar o processo de fechamento do exercício. Se houver mais de um período de fechamento para o último período do ano fiscal, o campo **Nome do período** ficará disponível. Você poderá selecionar o período de fechamento a ser usado para lançar a transação de fechamento se a configuração estiver definida para criar a transação de fechamento.

Em seguida, insira um número de comprovante. O mesmo número de comprovante será usado para todas as entidades legais que você selecionou para o processo de fechamento do exercício. O número de comprovante não é gerado utilizando-se uma sequência numérica.

Por padrão, o processo de fechamento do exercício é executado no modo de lote. Portanto, depois que ele for iniciado, você poderá retornar a outras atividades.

Como as estruturas de conta podem ser alteradas durante um ano fiscal, a estrutura de conta relevante nem sempre pode ser identificada. Portanto, o processo de fechamento do exercício não segue as estruturas de conta. Quando as transações de abertura são criadas, os saldos são levados a diante com dimensões financeiras, conforme definido no modelo do fechamento do exercício. As entradas dos saldos iniciais podem incluir dimensões financeiras que já não estão na estrutura de conta atual e combinações de segmentos que não são mais válidas na estrutura de conta atual. Se a sua organização deseja excluir uma dimensão financeira para o saldo inicial de lucros retidos, defina a dimensão financeira como **Fechar individual** e deixe o valor da dimensão em branco.

Após a conclusão do processo, um registro será criado para cada combinação de entidade legal e ano fiscal. Você verá somente os registros das entidades legais às quais tem acesso. Cada registro inclui a data e a hora do sistema quando o processo foi executado e um link direto para os comprovantes criados para o fechamento do exercício.

[![Registros criados na Guia Rápida Histórico de fechamentos de exercício da página Fechamento do exercício](./media/run-yr-end-close.png)](./media/run-yr-end-close.png)

Se você executar o fechamento do exercício novamente, verá um ou vários registros para cada combinação de entidade legal e ano fiscal, dependendo da configuração da opção **Excluir entradas de fechamento do exercício existentes ao fechar novamente o ano** na página **Parâmetros da contabilidade**:

- Se a opção estiver definida como **Sim**, o comprovante do fechamento do exercício anterior será excluído. O registro será marcado como **Revertido** e carimbado com a data e a hora em que a reversão foi feita. Além disso, o link para o número do comprovante será removido. Quando o fechamento do exercício for concluído, um novo registro será criado para o novo comprovante que foi criado.
- Se a opção estiver definida como **Não**, o registro do fechamento do exercício anterior permanecerá, juntamente com o link para o comprovante. Toda vez que o fechamento do exercício for executado novamente, um novo registro será criado, juntamente com um link para os novos comprovantes.

## <a name="reverse-the-year-end-close-process"></a>Reverter o processo de fechamento do exercício

Na página **Fechamento do exercício**, é possível reverter um fechamento de exercício. Selecione o registro para a combinação de entidade legal e ano fiscal que devem ser revertidos e selecione **Reverter fechamento de exercício**. O processo de reversão exclui todos os comprovantes de abertura e fechamento criados para o ano fiscal. O registro será marcado como **Revertido** e carimbado com a data e a hora em que a reversão foi feita. Além disso, o link para o número do comprovante será removido. Como no processo de fechamento do exercício, a reversão é executada no modo de lote.

Uma caixa de seleção **Exibir revertidos** que está disponível acima da grade permite ocultar ou mostrar os registros para processos de fechamento de exercício revertidos. Depois de executar o processo **Reverter fechamento de exercício**, talvez seja necessário marcar a caixa de seleção **Exibir revertidos** para ver o registro. Você pode definir filtros adicionais para exibir outras informações.

[![Usando a caixa de seleção Exibir revertidos para ver os registros dos processos de fechamento de exercício revertidos na página Fechamento do exercício](./media/rvrs-yr-end-close.png)](./media/rvrs-yr-end-close.png)

Para saber mais, consulte [Fechar a contabilidade no fim do período](close-general-ledger-at-period-end.md) e [Fechar o ano fiscal](tasks/close-fiscal-year.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
