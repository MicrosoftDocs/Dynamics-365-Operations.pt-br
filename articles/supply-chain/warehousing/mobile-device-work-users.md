---
title: Contas de usuário do dispositivo móvel
description: Este tópico descreve como configurar e gerenciar contas de usuário que permitem aos trabalhadores entrar e usar o aplicativo de depósito.
author: Mirzaab
ms.date: 09/15/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-09-15
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: f3a930814a1fb98e3b1611adf309c10e66b49b9d
ms.sourcegitcommit: fd6270dc7f49f93a8155d2b827153b13edb7be8a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2021
ms.locfileid: "7902088"
---
# <a name="mobile-device-user-accounts"></a>Contas de usuário do dispositivo móvel

[!include [banner](../includes/banner.md)]

Toda vez que um trabalhador começa a usar o aplicativo de depósito, ele deve entrar usando um nome de usuário e senha. Qualquer número de usuários do aplicativo de depósito pode ser associado a cada trabalhador no sistema, e os depósitos são normalmente associados a cada um desses usuários do aplicativo de depósito. Várias opções também são configuradas para cada trabalhador, para estabelecer as configurações padrão e outras configurações relevantes ao uso do aplicativo de depósito.

## <a name="set-up-the-required-worker-and-employee-records"></a>Configurar os registros de trabalhador e funcionário necessários

Antes de poder configurar os usuários do aplicativo de depósito, cada trabalhador já deve existir como um funcionário ou trabalhador do Supply Chain Management no módulo **Human Resources**.

## <a name="set-up-mobile-device-user-accounts"></a><a name="set-wma-users"></a>Configurar contas de usuário do dispositivo móvel

Depois que os trabalhadores e funcionários necessários são configurados no Human Resources, você pode atribuir os usuários do aplicativo de depósito a cada um deles e configurar outras opções que afetam a forma como eles podem usar o aplicativo.

1. Acesse **Gerenciamento de depósito \> Configuração \> Trabalhador**.
1. Para editar um trabalhador existente, selecione-o no painel da lista. Para adicionar um novo registro, selecione **Novo** no Painel de Ações.
1. Se você estiver configurando um novo trabalhador, siga estas etapas:

    1. No campo **Trabalhador**, selecione o usuário de destino na lista de funcionários.
    1. Escolha **Selecionar**.
    1. No Painel de ações, selecione **Salvar**.

1. Um perfil padrão pode ser usado para orientar o trabalhador do depósito na estação de embalagem por meio do processo necessário ali. Como alternativa, o perfil padrão pode ser usado para salvar as configurações de perfil preferenciais para o trabalhador. Na Guia Rápida **Perfil**, defina os seguintes campos:

    - **Política de embalagem de contêiner** — selecione uma política de embalagem de contêiner que define como os contêineres na estação de embalagem devem ser processados. A política de embalagem de contêiner selecionada aqui será selecionada previamente para o trabalhador quando ele abrir a estação de embalagem. Para obter mais informações, consulte a seguinte postagem no blog: [Funcionalidade de embalagem aprimorada](https://cloudblogs.microsoft.com/dynamics365/no-audience/2016/12/01/improved-packing-functionality-dynamics-365-for-operations-1611),
    - **ID do perfil de embalagem** — selecione uma ID do perfil de embalagem que define as configurações da política de embalagem e do contêiner que serão usadas. Se a ID do perfil de embalagem selecionada estiver associada a uma política de embalagem de contêiner, você não poderá alterar a configuração da **Política de embalagem de contêiner** nessa página.

1. Na Guia Rápida **Estação de embalagem padrão**, configure os campos a seguir para definir a estação de embalagem padrão aplicável quando o trabalhador entrar. O trabalhador ainda poderá selecionar outra estação de embalagem conforme necessário.

    - **Local** — selecione o local em que a estação de embalagem padrão está localizada.
    - **Depósito** — selecione o depósito em que a estação de embalagem padrão está localizada.
    - **Localização** — selecione a localização da estação de embalagem padrão.

1. A Guia Rápida **Usuários** permite que você crie qualquer números de contas de usuário do aplicativo de depósito para o trabalhador selecionado. Cada conta é associada a um depósito ou depósitos específicos. Use a barra de ferramentas para adicionar ou remover contas de usuário, redefinir a senha de uma conta selecionada ou atribuir depósitos a uma conta selecionada. Para cada conta de usuário, você pode definir os seguintes campos:

    - **ID do Usuário** — insira uma ID exclusiva.
    - **Nome de usuário** — insira um nome para a ID.
    - **Depósito padrão** — defina o depósito padrão em que o trabalhador geralmente trabalha. Você pode usar a barra de ferramentas para atribuir depósitos adicionais e o trabalhador pode alternar entre depósitos usando a atividade indireta **Alterar depósito** no item de menu do dispositivo móvel.
    - **Nome do menu** — selecione o menu raiz que será a página inicial do trabalhador. A possibilidade de configurar um menu raiz para cada trabalhador é útil porque permite que você controle a estrutura de menus que cada trabalhador pode usar. Por exemplo, o menu para trabalhadores ativos somente na área de saída pode ser ajustado para tarefas relacionadas a operações de saída dessa área.
    - **Inativo** — uma caixa de seleção marcada indica que a conta de usuário está inativa. A conta de usuário será automaticamente desativada se um trabalhador inserir a senha errada cinco vezes em seguida no aplicativo de depósito. No entanto, você também pode marcar esta caixa de seleção manualmente. Desmarque a caixa de seleção para tornar o usuário ativo novamente.

1. Na Guia Rápida **Trabalho**, defina os seguintes campos:

    - **Permitir substituição de local de separação** — defina esta opção como *Sim* para permitir que o trabalhador substitua a localização das etapas de separação. Esse recurso pode ser útil se o estoque físico não corresponder ao local sugerido pelo sistema.
    - **Permitir substituição de local de colocação** — defina esta opção como *Sim* para permitir que o trabalhador substitua a localização das etapas de colocação. Esse recurso pode ser útil se o local em que você sugeriu estiver cheio ou não estiver disponível ou se as localizações de preparo forem alteradas.
    - **Permitir separação em excesso de vendas** — defina esta opção como *Sim* para permitir que o trabalhador faça a separação em excesso quando as ordens de venda forem separadas. Para obter mais informações, consulte [Separação em excesso para ordens de venda e ordens de transferência](over-picking-for-sales-and-transfer-orders.md).
    - **Permitir separação em excesso de ordem de transferência** — defina esta opção como *Sim* para permitir que o trabalhador faça a separação em excesso quando as ordens de transferência forem separadas. Para obter mais informações, consulte [Separação em excesso para ordens de venda e ordens de transferência](over-picking-for-sales-and-transfer-orders.md).
    - **Permitir movimento de estoque com trabalho associado** — defina esta opção como *Sim* para permitir que o trabalhador mova o estoque que já estiver reservado ou já estiver associado a outro trabalho. Para obter mais informações, consulte [Movimento de estoque com trabalho associado no Gerenciamento de depósito](move-inventory-associated-work.md).
    - **Permitir realocação manual de itens** — defina esta opção como *Sim* para permitir a realocação manual para o trabalhador durante a separação insuficiente. A realocação de itens guia os trabalhadores para separar o estoque de outro local. Embora a realocação automática esteja disponível para todos os trabalhadores, a realocação manual requer uma configuração explícita para um trabalhador. A possibilidade de controlar a realocação manual para cada trabalhador pode ser útil porque permite que você controle a visibilidade que cada trabalhador tem quando, por exemplo, a separação de itens da área de quarentena ou a de atacado está limitada a funcionários confiáveis. Para obter mais informações, consulte a seguinte postagem no blog: [Realocação automática e manual de item durante a separação insuficiente](https://cloudblogs.microsoft.com/dynamics365/no-audience/2016/11/07/automatic-and-manual-item-reallocation-during-the-short-picking-dynamics-365-for-operations-1611/).
    - **É um supervisor de contagem cíclica:** — defina esta opção como *Sim* para tornar o trabalhador um supervisor de contagem cíclica. Nesse caso, todas as contagens cíclicas executadas pelo trabalhador no aplicativo de depósito serão imediatamente aprovadas. Os campos **Limite máximo da porcentagem**, **Limite máximo da quantidade** e **Limite máximo do valor** não são considerados para trabalhadores para os quais esta opção está definida como *Sim*.
    - **Limite máximo da porcentagem** — insira i limite da porcentagem mais alta que uma contagem cíclica pode diferir da quantidade prevista, sem exigir aprovação por um supervisor de contagem cíclica.
    - **Limite máximo da quantidade** — insira a quantidade total da qual a quantidade inserida pode diferir da quantidade esperada (em unidades), sem exigir aprovação por um supervisor de contagem cíclica.
    - **Limite máximo do valor** — insira o valor máximo que a contagem do estoque pode diferir do custo esperado, sem exigir aprovação por um supervisor de contagem cíclica.

1. No Painel de ações, selecione **Salvar**.
1. Se você adicionou uma nova conta de usuário, a caixa de diálogo **Definir senha** será exibida e você poderá criar uma senha simples que o usuário poderá usar para entrar no aplicativo móvel. Insira a senha simples duas vezes e selecione **Salvar senha** para continuar.

## <a name="set-the-language-number-formats-and-time-zone-for-each-warehouse-app-user"></a>Definir o idioma, os formatos de número e o fuso horário de cada usuário do aplicativo de depósito

Quando um trabalhador entra no aplicativo móvel Warehouse Management, o idioma, os formatos de número e o de fuso horário são alterados para coincidir com as preferências do trabalhador. As configurações de conta do trabalhador que foi selecionado na etapa 3 na seção [Configurar contas de usuário do dispositivo móvel](#set-wma-users) determinam as configurações usadas. Se você precisar de configurações separadas para cada usuário, use contas de trabalhador diferentes. O procedimento a seguir mostra como alterar o idioma, os formatos de número e o fuso horário de cada usuário do aplicativo de depósito.

1. Acesse **Gerenciamento de depósito \> Configuração \> Trabalhador**.
1. Encontre o nome do trabalhador que você deseja configurar. Verifique se o trabalhador tem todas as contas de usuário do aplicativo de depósito que estão listadas na Guia Rápida **Usuários**. Crie um trabalhador e/ou adicione contas de usuário do aplicativo de depósito conforme necessário, seguindo as etapas na seção [Configurar contas de usuário do dispositivo móvel](#set-wma-users).
1. Acesse **Administração do sistema \> Usuários \> Usuários**.
1. Selecione a conta de usuário na qual a coluna **Pessoa** mostra o nome do trabalhador encontrado na etapa 2.

    > [!IMPORTANT]
    > Os valores de **ID de usuário** listados na página **Usuários** *não* estão relacionados ao valor mostrado na Guia Rápida **Usuários** da página **Trabalhador** que você abriu na etapa 1.

1. No Painel de Ações, selecione **Opções do usuário**.
1. Na guia **Preferências**, defina os seguintes campos:

    - **Idioma** — selecione o idioma de preferência do trabalhador. Este campo também controla o formato de data mostrado no aplicativo de depósito.
    - **Formato de data, hora e número** — selecione o idioma que determinará os formatos de número mostrados no aplicativo de depósito. Observe que os formatos de data e hora mostrados no aplicativo de depósito são, na verdade, determinados pelo campo **Idioma**, e não por este campo.
    - **Fuso horário** — selecione o fuso horário no qual o trabalhador trabalha. Este campo afeta o carimbo de data/hora de todos os registros que o trabalhador faz usando o aplicativo.

> [!NOTE]
> Em alguns casos, o aplicativo de depósito não encontrará configurações de trabalhador específicas que estabelecem o idioma, os formatos de número e o fuso horário. As seguintes regras são aplicadas:
>
> - Se o aplicativo não estiver conectado a um ambiente do Supply Chain Management (por exemplo, a primeira vez que o aplicativo é iniciado depois de instalado), será usado o idioma do dispositivo local. Quando o idioma do dispositivo for alterado, o idioma do aplicativo também será alterado. Para obter mais informações sobre como configurar o idioma para o dispositivo local, consulte a documentação do dispositivo e/ou sistema operacional.
> - Se o aplicativo estiver conectado a um ambiente do Supply Chain Management, mas nenhuma preferência estiver definida para o trabalhador conectado, o idioma, os formatos de número e o fuso horário serão selecionados com base na conta associada à ID de cliente que o dispositivo usa para conectar-se ao Supply Chain Management. Para obter mais informações, consulte [Criar e configurar uma conta de usuário no Supply Chain Management](install-configure-warehouse-management-app.md#user-azure-ad).

> [!TIP]
> Se você notar que carimbos de data/hora incorretos são exibidos para registros feitos usando o aplicativo de depósito, talvez seja necessário ajustar o fuso horário definido para a conta de usuário que os trabalhadores usam para entrar e/ou autenticar com o Supply Chain Management. Como foi mencionado anteriormente, a configuração de fuso horário pode vir da conta de usuário que é usada para entrar no aplicativo de depósito, conforme configurado na página **Trabalhador**. Como alternativa, se a conta de usuário não estiver definida na página **Trabalhador**, o fuso horário virá da conta de usuário associada à ID de cliente usada para autenticação, conforme configurado na página **[aplicativos do Azure Active Directory](install-configure-warehouse-management-app.md)**.
