---
title: Segmentação de dispositivo, mercado e geolocalização
description: Este artigo descreve como criar, editar e gerenciar públicos-alvo e destinos no construtor de sites do Microsoft Dynamics 365 Commerce usando informações de dispositivo, mercado e geolocalização.
author: sushma-rao
ms.date: 02/03/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2021-07-31
ms.dyn365.ops.version: AX 10.0.21
ms.openlocfilehash: 90772fd942db30bbf4f65a87b1dca4b2aaacee1e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8881648"
---
# <a name="device-market-and-geolocation-targeting"></a>Segmentação de dispositivo, mercado e geolocalização

[!include [banner](includes/banner.md)]

Este artigo descreve como criar, editar e gerenciar públicos-alvo e destinos no construtor de sites do Microsoft Dynamics 365 Commerce usando informações de dispositivo, mercado e geolocalização.

O Dynamics 365 Commerce permite personalizar variações do conteúdo da sua página (conhecidas como *destinos*) para grupos específicos de clientes (conhecidos como *públicos-alvo*) para ajudar a aumentar a participação e a satisfação do usuário. Você pode criar um público-alvo ou um destino primeiro. No entanto, para uma experiência de direcionamento bem-sucedida, é preciso ter esses dois componentes.

Você cria e gerencia os públicos-alvo no construtor de sites do Commerce com base em dados do cliente, como localização, informações do dispositivo, status de entrada e outras informações derivadas dinamicamente das solicitações do cliente pela Web. Você também pode criar e gerenciar destinos em módulos de comércio eletrônico e fragmentos no construtor de sites do Commerce.

**Aviso de isenção de responsabilidade:** você é responsável por usar esse recurso em conformidade com todas as leis e os regulamentos aplicáveis, inclusive aqueles relacionados a direcionamento e criação de perfil. 

## <a name="audiences"></a>Públicos-alvo

Um público-alvo é um grupo de usuários, e a associação no grupo é determinada por um conjunto de regras dinâmicas. Essas regras são testes lógicos simples executados com base nas informações que estão disponíveis em solicitações do cliente ou em outros segmentos disponíveis. É possível combinar várias regras usando os operadores AND/OR.

O Commerce tem suporte nativo para segmentos básicos, como informações do dispositivo, status de entrada, referenciador e parâmetros de cadeia de consulta. Ele também oferece suporte para segmentos extensíveis por meio de conexões com provedores terceirizados.

### <a name="basic-segments"></a>Segmentos básicos

Por padrão, os seguintes segmentos estão disponíveis e podem ser incluídos nas definições de público-alvo:

- **Status de entrada** – Verifique se um usuário está autenticado.
- **Plataforma do dispositivo** – Teste para os seguintes tipos de dispositivo:

    - Dispositivo móvel
    - Desktop
    - Tablet
    - Outros(as)

- **SO do dispositivo** – Teste para os seguintes sistemas operacionais:

    - Windows
    - Linux
    - iOS
    - Android, Outro

- **Parâmetros de cadeia de consulta** – Teste para saber se existe um par chave-valor em um parâmetro de cadeia de consulta de uma URL de solicitação. Por exemplo, para a URL `www.fabrikam.com/en-us/request?promo=true`, é possível gravar uma regra para testar se o parâmetro **promo** tem o valor **true**.
- **Cookie** – Teste um valor de cookie definido para o domínio na URL de solicitação. Por exemplo, uma solicitação de Fabrikam.com pode incluir um cookie com o nome **CustomLayout** e o valor **1**. O teste de cookie verifica se existe um cookie, mas não cria um explicitamente. No exemplo anterior, o JavaScript deve ter definido anteriormente o cookie **CustomLayout** de outro módulo ou de outro processo empresarial.

    > [!NOTE]
    > Verifique se o uso de cookies está em conformidade com as leis aplicáveis.

- **Referenciador** – Se um usuário segue um link para solicitar a página, o referenciador é a URL da página que hospeda o link.

### <a name="extensible-segments"></a>Segmentos extensíveis

O Commerce permite expandir a lista de segmentos disponíveis conectando-se a provedores de segmentação de terceiros. Um provedor de segmentação descreverá os tipos de segmentos disponíveis. Para obter mais informações sobre como conectar a uma geolocalização ou a um provedor de segmentação, consulte [Configurar e habilitar conectores](e-commerce-extensibility/connectors.md).

> [!NOTE]
> - Se um provedor externo for habilitado, ele poderá se conectar a um serviço de desempenho imprevisível. Para ajudar a garantir uma experiência melhor para o usuário, se um usuário solicitar uma página que inclui direcionamento e essa página fizer referência a um público-alvo que verifica um provedor de segmentos de terceiros, será mostrada a versão padrão da página.
> - O usuário deve concordar com permitir cookies. O navegador do usuário solicita todos os segmentos dos provedores relevantes, e os resultados são colocados em um cookie que é retornado para o usuário. As solicitações subsequentes feitas à página usarão essas informações para fornecer conteúdo direcionado para o usuário. Para obter mais informações sobre conformidade com cookies, consulte [Conformidade com cookies](cookie-compliance.md).

**Aviso de isenção de responsabilidade:** se você habilitar esse recurso, os dados serão compartilhados com os sistemas de terceiros que selecionar. Você controla quais dados fornecerá ao terceiro, se for o caso. Você entende que os padrões de conformidade e manuseio de dados do terceiro podem ser diferentes dos padrões do Microsoft Dynamics 365 Commerce. Sua privacidade é importante para a Microsoft. Para saber mais, leia nosso [aviso de Privacidade e cookies](https://privacy.microsoft.com/privacystatement).

### <a name="create-an-audience-in-site-builder"></a>Criar um público-alvo no construtor de sites

Para criar um público-alvo no construtor de sites do Commerce, siga estas etapas.

1. No painel de navegação à esquerda, selecione **Públicos-alvo**.
1. Selecione **Novo**.
1. Insira um nome para o público-alvo. Opcionalmente, você pode adicionar marcas e uma descrição.
1. Selecione **Criar** e, em seguida, **Adicionar novo bloco de regras**. Um bloco de regras é um conjunto de regras associadas por condições AND. Também é possível criar vários blocos de regras que tenham condições OR entre eles.
1. Selecione uma fonte de dados para os segmentos e especifique o nome, o operador e os valores deles. Você pode criar e excluir mais regras de um bloco de regras ou pode criar e excluir blocos de regras inteiros. Você também pode mover blocos de regras para cima ou para baixo, conforme necessário.

    > [!NOTE]
    > É possível ter até 100 valores em uma lista, e cada item da lista pode conter até 50 caracteres.

1. Quando estiver satisfeito com a configuração do público-alvo, selecione **Concluir edição**. Em seguida, selecione **Publicar** para tornar o público-alvo disponível para uso em um destino dinâmico. Como alternativa, você pode publicar o público-alvo junto com o destino. 

Para editar um público-alvo, selecione hiperlink dele na guia **Públicos-alvo** e, depois, selecione **Editar** no editor de público-alvo que aparece. Para ver a lista de destinos e páginas que fazem referência a um público-alvo, selecione o público-alvo na exibição de lista de públicos-alvo e selecione **Exibir Atribuições**. Para excluir um público-alvo na exibição de lista de públicos-alvo ou no editor de públicos-alvo, cancele a publicação dele caso já tenha sido publicado e selecione **Excluir** na barra de comandos.

> [!NOTE]
> Os públicos-alvo são um conceito no nível de site do construtor de sites do Commerce. Você pode compartilhar o mesmo público-alvo entre vários destinos.

### <a name="rename-an-audience-in-site-builder"></a>Renomear um público-alvo no construtor de sites

Para renomear um público-alvo existente no construtor de sites do Commerce, siga estas etapas.

1. No painel de navegação à esquerda, selecione **Públicos-alvo**.
1. Selecione o nome do segmento do público-alvo que você deseja renomear.
1. Selecione **Editar** para iniciar a edição do público-alvo.
1. No painel de propriedades do público-alvo, selecione o símbolo da caneta ao lado do nome do público-alvo.
1. Edite o nome do público-alvo, conforme necessário.
1. Marque a caixa de seleção para confirmar a alteração do nome.
1. Selecione **Concluir edição**.

## <a name="targets"></a>Público-alvo

Um destino é a experiência do usuário mostrada para membros de um ou mais públicos-alvo selecionados. Ele pode incluir variações de um ou mais módulos em uma página ou em um fragmento. 

Você pode definir uma agenda para os seus destinos para especificar por quanto tempo eles devem permanecer ativos. Observe que essa ação é separada da ação de agendar um grupo de publicação, que determina quando uma coleção de conteúdo será publicada. Também é possível visualizar seus destinos para ver a aparência que eles terão para os membros dos públicos-alvo selecionados. Além disso, você pode priorizar seus destinos para especificar qual destino deve ser mostrado em caso de conflito.

### <a name="create-a-target"></a>Criar um destino

Para criar um shell de destino para módulos de página no construtor de sites do Commerce, siga estas etapas.

1. No painel de navegação à esquerda, selecione **Páginas**. Em seguida, selecione o hiperlink da página que tem os módulos que você quer direcionar.
1. Selecione **Editar** para fazer check-out da página para editá-la.
1. No menu **Destino**, selecione **Novo destino** para criar um novo shell de destino. Você pode criar vários destinos em uma página, conforme necessário.
1. Insira um nome e uma descrição para o destino e selecione **Avançar**.
1. Selecione **Adicionar** para incluir os públicos-alvo que verão o conteúdo direcionado ou para excluir públicos-alvo. Selecione **Avançar**.

    > [!NOTE]
    > A atribuição do público-alvo é uma etapa opcional durante a criação do destino. No entanto, antes de publicar o destino, você deve incluir pelo menos um público-alvo para garantir que os grupos de usuários pretendidos verão o conteúdo direcionado.

1. Defina a janela de tempo para a exibição do destino selecionando o fuso horário e as datas e horas iniciais e finais. Você pode definir o destino para que ele seja exibido sempre durante a janela de tempo ou pode selecionar dias e horas específicas. Quando terminar, selecione **Avançar**.

    > [!NOTE]
    > As horas e o fuso horário que você especificar serão globais. Se quiser direcionar outros locais em outros horários ou em fusos horários diferentes, você deverá criar destinos diferentes e definir a agenda desejada para cada local.

1. Verifique os detalhes e, quando tudo parecer correto, selecione **Criar experiência de destino** e **Ir para destino**. O shell de destino é criado. Agora, você pode adicionar módulos a ele.
1. Selecione o módulo para direcionar, selecione as reticências (**...**) e, depois, selecione **Adicionar ao destino atual**. Quando você direciona um módulo pai, todos os filhos se tornam parte desse destino. Os módulos direcionados ficam destacados em verde.
1. Faça as atualizações de conteúdo necessárias no módulo direcionado e, se precisar, adicione mais módulos ao destino. Depois, selecione **Salvar** para salvar todas as alterações.
1. Antes de publicar o destino, selecione **Visualizar** na barra de comandos para revisá-lo. Em seguida, você pode selecionar uma das seguintes opções:

    - **Visualização básica** – Selecione esta opção para visualizar apenas a variação selecionada (página ou destino padrão), sem públicos-alvo associados.
    - **Visualização avançada** – Selecione esta opção se você tiver vários destinos em uma página e quiser visualizá-los como um usuário que pertence a um conjunto selecionado de públicos-alvo ou em uma data e hora específicas. Selecione **Avançar** para selecionar em uma lista de públicos-alvo relevantes. Você também pode remover o filtro para selecionar entre todos os públicos-alvo.

1. Quando estiver satisfeito com a configuração do destino, você deverá publicar a página para que o destino seja ativado. Selecione **Publicar** para ativar o destino imediatamente. Se preferir, você pode usar um grupo de publicação para agendar quando a página será ativada. Para obter informações sobre grupos de publicação, consulte [Trabalhar com grupos de publicação](publish-groups.md).

Você também pode direcionar fragmentos. O procedimento é semelhante. No entanto, na etapa 1, você deve selecionar **Fragmentos** em vez de **Páginas** no painel de navegação à esquerda.

> [!NOTE]
> Para evitar um impacto negativo sobre as métricas, você pode ter um experimento ou destinos em uma página ou em um fragmento. Não é possível ter experimentos e destinos.

### <a name="manage-targets"></a>Gerenciar destinos

Para editar, duplicar ou excluir destinos, Acesse a página ou o fragmento padrão e siga estas etapas.

1. No menu suspenso, selecione **Destino** e, em seguida, selecione **Gerenciar destinos**.
1. Selecione um destino para editar, duplicar ou excluir.
1. Se você tiver vários destinos no mesmo módulo ou se vários destinos tiverem agendas conflitantes, selecione **Priorizar destinos** para especificar a ordem de exibição deles. Se você adicionar mais de um destino em uma página ou em um fragmento, o botão **Priorizar destinos** também será exibido na barra de notificação como um lembrete para priorizar os destinos. Se nenhuma prioridade for especificada, o destino mais recente será selecionado por padrão.

### <a name="localize-targets"></a>Localizar destinos

Os destinos em páginas e em fragmentos são incluídos automaticamente quando arquivos XLIFF são exportados e importados para fins de localização. No entanto, se localidades não forem necessárias, você poderá excluir os destinos para elas após a importação dos arquivos XLIFF localizados.

> [!NOTE]
> Os destinos são gerenciados por canal e localidade. As alterações feitas nos destinos de um canal ou de uma localidade não são transferidas automaticamente para outros canais ou localidades.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
