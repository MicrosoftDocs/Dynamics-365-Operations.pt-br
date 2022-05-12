---
title: Mostrar saldos de férias na interface de execução de piso de produção
description: Este tópico fornece um cenário de exemplo que mostra como configurar o Microsoft Dynamics 365 Supply Chain Management de forma que ele use estatísticas de folha de pagamento para fornecer aos trabalhadores uma visão geral do seu saldo de férias para o ano atual.
author: johanhoffmann
ms.date: 04/22/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-04-22
ms.dyn365.ops.version: 10.0.XX
ms.openlocfilehash: a97858c72b0be50609cee552bd0635e2d68ea478
ms.sourcegitcommit: d715e44b92b84b1703f5915d15d403ccf17c6606
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645332"
---
# <a name="show-vacation-balances-in-the-production-floor-execution-interface"></a>Mostrar saldos de férias na interface de execução de piso de produção

[!include [banner](../includes/banner.md)]

Este tópico fornece um cenário de exemplo que mostra como configurar o Microsoft Dynamics 365 Supply Chain Management de forma que ele use estatísticas de folha de pagamento para fornecer a cada trabalhador uma visão geral do seu saldo de férias para o ano atual. Os trabalhadores poderão ver seu saldo de férias na caixa de diálogo **Meu dia** na interface de execução de piso de produção.

Esse cenário usa a Lei de férias dinamarquesa, em que o ano de férias vai de 1º de setembro a 31 de agosto. Neste cenário, sua empresa contratou um novo trabalhador e concede a esse trabalhador um saldo de 10 dias de férias para o restante do ano de férias atual.

## <a name="turn-on-the-required-features"></a>Ativar os recursos necessários

Para executar esse cenário, você deve habilitar a exibição *"Meu dia" para o recurso de interface de execução de piso de produção* no [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Para obter informações sobre como habilitar esse e outros recursos para a interface de execução de piso de produção, consulte [Configurar a interface de execução de piso de produção](production-floor-execution-configure.md).

## <a name="make-sample-data-available"></a>Disponibilizar dados de exemplo

Para trabalhar nesse cenário usando os registros e valores de exemplo especificados aqui, você deve usar um sistema em que os [dados de demonstração](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) padrão estejam instalados. Além disso, você deve selecionar a entidade legal **USMF** antes de começar.

## <a name="create-a-new-pay-type"></a>Criar um novo tipo de pagamento

Comece criando um novo *tipo de pagamento* que controlará os dias de férias obtidos dos trabalhadores (também referido como seu *saldo de férias*). Normalmente, os tipos de pagamento são usados para calcular o pagamento de trabalhadores. No entanto, o tipo de pagamento criado aqui será usado para calcular um saldo.

1. Acesse **Hora e atendimento \> Configuração \> Folha de pagamento \> Tipos de pagamento**.
1. No Painel de Ação, selecione **Novo** para adicionar uma linha à grade.
1. Na nova linha, defina os seguintes valores:

    - **Tipo de pagamento**: *5151-1*
    - **Descrição:** *Contador para dias de férias do trabalhador*
    - **Incluir na exportação:** *Não*

## <a name="update-the-pay-agreement"></a>Atualizar contrato de pagamento

Nesta seção, você editará um *contrato de pagamento existente* adicionando o novo tipo de pagamento e configurando as regras que definem como o saldo de férias de cada trabalhador é ajustado quando os dias de férias são registrados.

1. Acesse **Hora e atendimento \> Configuração \> Folha de pagamento \> Contratos de pagamento**.
1. Selecione o contrato de pagamento no qual você deseja configurar a política de férias. (Se você estiver trabalhando com dados de exemplo USMF padrão, só haverá um contrato de pagamento, *Man*.)
1. Verifique se o contrato de pagamento selecionado é válido para a data atual. Se você estiver trabalhando com dados de exemplo USMF padrão, o campo **Data final** do contrato de pagamento *Man* poderá ser definido como uma data no passado. Altere o valor para que seja um ano ou dois no futuro, conforme necessário.
1. No Painel de Ações, selecione **Linhas do contrato**.
1. Na página **Linhas do contrato de pagamento**, na guia rápida **Visão geral**, defina os seguintes valores na barra de ferramentas:

    - Na primeira lista suspensa, selecione **Segunda-feira**.
    - Na segunda lista suspensa, selecione **Ausência**.

1. No Painel de Ação, selecione **Novo** para adicionar uma linha à grade.
1. Na nova linha, defina o campo **Tipo de pagamento** como o tipo de pagamento criado para esse cenário (*5151-1*). Deixe todos os outros campos definidos com seus valores padrão.
1. Enquanto a nova linha ainda estiver selecionada, na guia rápida **Geral**, defina os seguintes valores:

    - **Código de ausências**: *Férias*
    - **Usar quantidade fixa**: *Sim*
    - **Constante**: *-1*

1. No Painel de Ações, selecione **Copiar dia**.
1. Na caixa de diálogo **Copiar dia**, defina os seguintes valores:

    - **Terça-feira**, **Quarta-feira**, **Quinta-feira** e **Sexta-feira:** *sim*
    - **Substituir:** *Sim*
    - **Ausência:** *Sim*

1. Selecione **OK**.

## <a name="create-a-payroll-statistic-group"></a>Criar um grupo de estatística de folha de pagamento

Os *grupos de estatísticas de folha de pagamento* são usados para configurar estatísticas para registros de trabalhador durante um período. Neste cenário, você usará um grupo de estatísticas de folha de pagamento para calcular o número de dias de férias que os trabalhadores ganham durante um período de férias. Na Dinamarca, o período de férias acontece de 1º de setembro a 31 de agosto.

1. Acesse **Hora e atendimento \> Configuração \> Folha de pagamento \> Grupos de estatísticas de folha de pagamento**.
1. No Painel de Ação, selecione **Novo** para adicionar uma linha à grade.
1. Na nova linha, defina os seguintes valores:

    - **Grupo de estatísticas da folha de pagamento:** *VAC*
    - **Descrição:** *Saldo de férias*
    - **Transferência**: *Não*

1. Enquanto a nova linha ainda estiver selecionada, selecione **Configuração** no Painel de Ações.
1. Na página **Configuração**, no Painel de Ações, selecione **Novo** para adicionar uma linha à grade.
1. Na nova linha, defina o campo **Tipo de pagamento** como *5151-1*.
1. Selecione e segure ou clique com o botão direito do mouse no campo **Código do período** e, em seguida, selecione **Exibir detalhes**. Agora, você pode configurar o código de período que será atribuído a este campo posteriormente.
1. Na página **Tipos de período**, no Painel de Ações, selecione **Novo** para adicionar uma linha à grade.
1. Na nova linha, defina os seguintes valores:

    - **Tipos de período:** *Ano de férias*
    - **Descrição:** *Ano de férias*
    - **Frequência:** *Anos*

1. Enquanto a nova linha ainda estiver selecionada, selecione **Gerar períodos** no Painel de Ações.
1. Na caixa de diálogo **Gerar períodos**, defina os seguintes valores:

    - **Especificar data de início do período:** *1º de setembro de 2021*
    - **Duração do período:** *5*

1. Selecione **OK**.
1. Feche a página **Tipos de período** para retornar à página **Grupos de estatísticas de folha de pagamento**.
1. Defina o campo **Código do período** como o tipo de período recém-criado (*Ano de férias*).

## <a name="create-a-statistical-balance-setup"></a>Criar configuração do saldo estatístico

Nesta seção, você criará uma *configuração do saldo estatístico* que está vinculada ao grupo de estatísticas da folha de pagamento que você criou na seção anterior. Posteriormente, você irá vincular essa configuração de saldo estatístico à exibição **Meu dia** na interface de execução de piso de produção. A exibição **Meu dia** poderá mostrar os saldos de férias para o tipo de pagamento atribuído ao grupo de estatísticas de folha de pagamento associado.

1. Acesse **Hora e atendimento \> Configuração \> Folha de pagamento \> Configuração de saldo estatístico**.
1. No Painel de Ação, selecione **Novo** para adicionar uma linha à grade.
1. Na nova linha, defina os seguintes valores:

    - **Grupo de estatísticas da folha de pagamento:** *VAC*
    - **Nome externo:** *Saldo de férias*
    - **Flex:** *Não*

## <a name="create-a-manual-premium"></a>Criar um premium manual

Os *Premiums manuais* são normalmente usados para conceder um pagamento extra aos trabalhadores por trabalho extra. Neste cenário, você criará um premium manual que pode ser usado para definir o saldo de férias inicial para cada trabalhador.

1. Acesse **Hora e atendimento \> Configuração \> Folha de pagamento \> Premiums manuais**.
1. No Painel de Ações, selecione **Novo** para adicionar um registro.
1. No novo registro, defina os seguintes valores:

    - **Premiums:** *VAC*
    - **Descrição:** *Ajustes no saldo de férias dos trabalhadores*
    - **Tipo de pagamento**: *5151-1*

## <a name="set-a-workers-initial-vacation-balance-and-adjust-it-by-one-day"></a>Defina o saldo de férias inicial de um trabalhador e ajuste-o em um dia

Os administradores da folha de pagamento usam a página **Aprovar** para revisar e aprovar os registros diários dos trabalhadores. Neste cenário, você obterá a função de um administrador para que possa definir o saldo de férias inicial para um trabalhador e registrar os dias de férias que ele tem.

1. Acesse **Horário e presença \> Revisar e aprovar \> Aprovar**.
1. Na caixa de diálogo **Aprovar**, defina os campos a seguir:

    - **Grupo de aprovação** – selecione o grupo de aprovação ao qual você pertence. (Se você estiver trabalhando com dados de exemplo USMF padrão, só haverá um grupo de aprovação, *AdmMan*.)
    - **Exibir todo o grupo, 1 dia** – selecione a opção e, em seguida, defina o campo como a data atual.

1. Selecione **OK**.
1. A página **Aprovar** exibe uma lista de registros que atendem aos seus critérios. Selecione o trabalhador que deseja aprovar. Se você estiver trabalhando com dados de exemplo USMF padrão, selecione o trabalhador *000496* (*Christina Portra*).
1. Conceder ao trabalhador selecionado 10 dias de férias:

    1. Enquanto o trabalhador ainda estiver selecionado, selecione **Linhas premium** no Painel de Ações.
    1. Na página **Linhas premium**, no Painel de Ações, selecione **Novo** para adicionar uma linha à grade.
    1. Na nova linha, defina os seguintes valores:

        - **Premiums:** *VAC*
        - **Quantidade:** *10*

    1. Feche a página **Linhas premium**.

1. Na página **Aprovar**, registre o fato de que o trabalhador usou um dos seus dias de férias na data atual:

    1. Com o trabalhador ainda selecionado, na guia **Visão geral**, selecione **Novo** na barra de ferramentas para adicionar uma linha à grade.
    1. Na nova linha, defina os seguintes valores:

        - **Tipo de registro de diário:** *Ausência*
        - **Referência:** *Férias*

    1. Na parte superior da página, selecione **Transferir** na barra de ferramentas para aplicar o saldo de férias e calcular a dedução.

## <a name="configure-the-production-floor-execution-interface-so-that-it-includes-the-my-day-dialog-box"></a>Configure a interface de execução de piso de produção para incluir a caixa de diálogo Meu dia

Nesta seção, você adicionará um botão **Meu dia** à interface de execução de piso de produção. Os trabalhadores poderão usar este botão para abrir a caixa de diálogo **Meu dia**.

1. Acesse **Controle de produção \> Configuração \> Execução de fabricação \> Configurar execução de piso de produção**.
1. Selecione uma configuração, como *Padrão*.
1. No Painel de Ação, selecione **Criar guias**.
1. Na página **Criar guias**, no painel de lista, selecione *Todos os trabalhos* para exibir as configurações dessa guia. O campo **Exibição principal** deve agora mostrar um valor de *Todos os trabalhos*.
1. No Painel de Ações, selecione **Editar**.
1. Na guia rápida **Barra de ferramentas secundária**, na coluna **Ações disponíveis**, selecione **Meu dia**. Depois, selecione o botão de seta para a direita para mover a coluna **Ações selecionadas**.

## <a name="check-your-balance-in-the-production-floor-execution-interface"></a>Verifique seu saldo na interface de execução de piso de produção

Nesta seção, você fará logon na interface de execução de piso de produção como o trabalhador cujo período de férias você configurou anteriormente. Em seguida, você abrirá a caixa de diálogo **Meu dia** para exibir o saldo das férias.

1. Acesse **Controle de produção \> Configuração \> Execução de fabricação \> Execução de piso de produção**.
1. Se for solicitado que você selecione uma configuração, escolha a configuração que você configurou anteriormente neste cenário (*Padrão*).
1. Efetue login como o usuário configurado anteriormente neste cenário. Se você estiver trabalhando com dados de exemplo USMF padrão, será possível fazer logon inserindo *123* no campo **ID do crachá**. Este ID do crachá corresponde a Christina Portra.
1. Selecione **Meu dia** na barra de ferramentas à esquerda.
1. Veja a seção **Saldos** da caixa de diálogo. Agora, esta seção deve mostrar que você tem um saldo de nove dias de férias.
